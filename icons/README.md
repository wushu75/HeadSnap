# HeadSnap AI Icons

## SVG Icons (Source of Truth)
- `icon16.svg` — Toolbar icon (16×16px)
- `icon48.svg` — Extension management page (48×48px)
- `icon128.svg` — Chrome Web Store (128×128px)

## PNG Generation
Convert SVGs to PNGs before packaging:

```bash
# Using Inkscape
inkscape icon16.svg --export-filename=icon16.png -w 16 -h 16
inkscape icon48.svg --export-filename=icon48.png -w 48 -h 48
inkscape icon128.svg --export-filename=icon128.png -w 128 -h 128

# Or using ImageMagick
convert -background none icon16.svg icon16.png
convert -background none icon48.svg icon48.png
convert -background none icon128.svg icon128.png
```

## Design Notes
- Primary color: #007BFF (Professional Blue)
- Accent: #00C6FF (Cyan gradient)
- Gold sparkles: #FFD700 (Premium feel)
- Person silhouette: White on gradient
- Rounded corners for modern, friendly appearance
