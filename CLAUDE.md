# La Charrúa Alfajores — Website

## Project Overview

Single-page static website for **La Charrúa Alfajores**, a small Uruguayan alfajor business based in the Bay Area, California. The site is pure HTML + CSS with no JavaScript, no build tools, and no external dependencies beyond Google Fonts.

## Architecture

- **Single file**: `index.html` contains all HTML, CSS, and images
- **No JavaScript** — all animations and interactions are CSS-only
- **Images are base64-encoded** directly in the HTML (no external image files)
- **No build step** — edit and deploy directly

## Sections (in order)

| ID | Section | Background |
|----|---------|------------|
| — | `<nav>` | Fixed, glassmorphism blur |
| `#hero` | Landing with logo, tagline, CTAs | `--white` |
| `#what` | "What is an Alfajor?" + layers diagram | `--choco` |
| `#menu` | Product grid (6 items, 3 columns) | `--white` |
| `#story` | Brand story + Uruguay heritage | `--green` |
| `#instagram` | Photo gallery (3 columns) | `--choco` |
| `#order` | CTA for ordering | `--cream` |
| — | `<footer>` | `--choco` |

## Color Palette (CSS Variables)

```
--cream:   #F5EDD8    --sand:    #E8D5A8
--caramel: #C4863A    --dulce:   #8B4A16
--choco:   #3D1A0A    --white:   #FBF7EF
--green:   #2E4A2A
```

## Typography

- **Playfair Display** (serif) — headings, display text
- **Cormorant Garamond** (serif) — body text
- **Space Mono** (monospace) — labels, navigation, tags

## Key Patterns

- Responsive breakpoint: `@media (max-width: 900px)` — grids collapse to 1 column, nav links hidden
- Reusable classes: `.section-tag`, `.btn-primary`, `.btn-secondary`, `.fade-in`
- Hover effects use `transform`, `box-shadow`, and `opacity` transitions
- Animations: `float` (logo bob), `spin-slow` (badge rotation), `float-up` (fade-in entrance)

## Adding New Sections

1. Add CSS before the `/* ─── RESPONSIVE ─── */` media query block
2. Add HTML between existing sections (before `<footer>`)
3. Add responsive overrides inside the `@media (max-width: 900px)` block
4. Optionally add a nav link in `<nav> <ul>`

## Adding Images

Compress to ~600px width, 60% JPEG quality, then embed as base64:
```bash
sips -s format jpeg -s formatOptions 60 --resampleWidth 600 input.jpg --out compressed.jpg
base64 -i compressed.jpg | tr -d '\n'
```
Use as: `src="data:image/jpeg;base64,..."`.

## External Links

- Instagram: https://www.instagram.com/la.charrua.alfajores
- Email: CloudFlare-protected (`/cdn-cgi/l/email-protection`)

## Git Workflow

- Work directly on `main` branch — no feature branches, no worktrees
- Repository: https://github.com/valesanabria/LaCharruaWeb
