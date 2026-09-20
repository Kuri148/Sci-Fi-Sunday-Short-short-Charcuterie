# SCI-FI SUNDAY: SHORT-SHORT CHARCUTERIE

## Live site

https://kuri148.github.io/Sci-Fi-Sunday-Short-short-Charcuterie/

Scan to open on your phone:

![QR code linking to the live site](images/site_qr.png)

## Files

- `index.html` — the page
- `shorts.xlsx` — the data (edit this to change entries)
- `images/`
  - `Wood_Pattern.svg` — the tiling wood background
  - `*.svg` — one transparent food vector per row
  - `board_bg.jpg` — old background (kept, no longer used)

## How to run

Because the page fetches `shorts.xlsx`, opening `index.html` directly with
`file://` will be blocked by the browser. Run a tiny local server instead:

```
cd into this folder
python3 -m http.server
then open  http://localhost:8000
```

Or just push the whole folder to GitHub Pages and it works as-is.

## Editing the data (`shorts.xlsx`, first sheet)

Columns, in order:

- `name` — title of the short-short
- `length` — e.g. "12 min"
- `tastes_like` — the flavor note shown on hover
- `image` — filename inside `images/` (e.g. `last_question.png`)
- `url` — link opened in a new tab when the entry is clicked

Optional columns, for shorts we've already watched together:

- `viewed` — month label, e.g. "September". Rows with a value drop below a
  "we viewed these in <month>" divider (one divider per month, sheet order)
- `stars` — 1-5; locked in and shown read-only on those cards

Rows with no `viewed` value stay at the top and remain rateable. `length`,
`tastes_like` and `url` may be left blank.

Add or remove rows freely; the board re-plates on reload.

## Swapping images

Each row points at a file in `images/` via its `image` cell. The food art
is plain SVG with a transparent background, so you can open any of the
`food_*.svg` files in a text editor or Illustrator/Inkscape and recolor or
redraw them. Drop in your own SVG or PNG (transparent works best) and
point the row's `image` cell at the new filename.

To change the board itself, replace `images/Wood_Pattern.svg` (it tiles).

## Behavior

- **hover** — shows name, length, and "what it tastes like"
- **click** — plays an "om-nom-nom" and opens the url in a new tab (every
  click, on any card, including the viewed ones)
- **stars** — rate 1-5; saved in this browser (localStorage) so it persists
  when you return to the page
