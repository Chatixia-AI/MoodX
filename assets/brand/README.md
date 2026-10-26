# MoodX speaker-bounce icon

The golden speaker orb and two blue acoustic ripples represent a sound landing
in a meeting. The three diagonal grille slots identify the orb as a speaker.
Concepts were explored with AI assistance; the production SVG was reconstructed
as simple editable vector shapes and visually reviewed at small sizes.

## Source and exports

- `moodx-icon.svg`: canonical editable source, 512-unit viewBox, solid fills.
- `moodx-icon-{32,64,128,256,512}.png`: raster exports for app and browser use.
- `../../macos/MoodXMixer/Resources/MoodX.icns`: native macOS icon, containing
  PNG representations rendered directly from the SVG at 16–1024 px.

The larger ICNS representations support Retina display density; they do not
require a large raster source. The SVG has no font or embedded-image dependency.

| Role | Color |
| --- | --- |
| Midnight navy | `#071D46` |
| Golden amber | `#FFBE32` |
| Sky blue | `#39C8F2` |
| Ripple side face | `#1363D8` |

## Integration

- Landing page: `site/public/img/moodx-icon.svg` and its 32 px PNG fallback.
- Browser mixer: `mixer/moodx-icon.svg` and its 32 px PNG fallback.
- Pitch deck and repository README: reference the canonical SVG.
- Native app: `CFBundleIconFile` points to `MoodX.icns`; the bundle build
  script copies that resource before signing.

The landing page and mixer each serve their own directory root, so their
deployed SVG and PNG copies must remain byte-identical to the canonical assets
when updating the logo. Preserve the navy tile, padding, and palette. Use empty
alt text for decorative icons beside a visible MoodX label and descriptive alt
text when the logo appears alone.

Render PNGs and all ICNS representations from the SVG when the source changes;
do not enlarge a small PNG. No audio-routing or meeting behavior changes.
