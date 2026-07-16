# Rumours Lounge Website

Static site for Rumours Lounge, built to run on GitHub Pages — same setup as sobelow.co.za and As Above Studios.

## File structure

```
index.html      → the whole site (one page, anchor-linked sections)
style.css       → all styling
assets/         → posters + room photos
```

## Publishing on GitHub Pages

1. Create a new repo (e.g. `rumours-lounge` or `rumourslounge.co.za`)
2. Push these files to the repo root (`index.html`, `style.css`, `assets/`)
3. In the repo: **Settings → Pages → Branch → main → / (root) → Save**
4. Site goes live at `https://<username>.github.io/<repo-name>/`
   — or point a custom domain at it via a `CNAME` file if you've got `rumourslounge.co.za` or similar

## Updating "This Week" (do this every Monday)

Open `index.html` and find the section marked:

```html
<!-- THIS WEEK — UPDATE THIS EVERY MONDAY. -->
```

There are four `.week-row` blocks — Wed, Thu, Fri, Sat. For each one, update:

- **Date** — `<div class="week-day">Wed · Jul 22</div>`
- **Title** — band name or event name
- **Description** — support act, doors time, etc.
- **Poster** — if you have one, drop the image file into `/assets` and update the `<img src="assets/yourfile.jpg">` path. If you don't have one yet, leave the `week-thumb empty` version as-is — it'll show "Poster soon" automatically.

Commit and push — GitHub Pages updates automatically, usually within a minute or two.

## Adding new photos to "This Is The Room"

Drop new images into `/assets`, then swap the `src` on any of the three `<img>` tags inside the `.room-grid` in `index.html`. Keep images under ~300KB each for fast loading — resize/compress before uploading if a photo comes straight off a camera (the room photos in this repo were resized from ~20MB originals down to ~100–140KB).

## Fonts

Anton (headlines) and Inter (body text) load from Google Fonts — no local font files needed, but this means the site needs an internet connection to render fonts correctly (it'll fall back to a system sans-serif otherwise, which still looks fine).
