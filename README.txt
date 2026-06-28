SCI-FI SUNDAY: SHORT-SHORT CHARCUTERIE
======================================

FILES
  index.html      the page
  shorts.xlsx     the data (edit this to change entries)
  images/         board_bg.jpg  -> the wood charcuterie board background
                  food_*.svg    -> one transparent food vector per row

HOW TO RUN
  Because the page fetches shorts.xlsx, opening index.html directly with
  file:// will be blocked by the browser. Run a tiny local server instead:

      cd into this folder
      python3 -m http.server
      then open  http://localhost:8000

  Or just push the whole folder to GitHub Pages and it works as-is.

EDITING THE DATA  (shorts.xlsx, first sheet)
  Columns, in order:
    name         title of the short-short
    length       e.g. "12 min"
    tastes_like  the flavor note shown on hover
    image        filename inside images/  (e.g. last_question.png)
    url          link opened in a new tab when the entry is "eaten"
  Add or remove rows freely; the board re-plates on reload.

SWAPPING IMAGES
  Each row points at a file in images/ via its "image" cell. The food art
  is plain SVG with a transparent background, so you can open any of the
  food_*.svg files in a text editor or Illustrator/Inkscape and recolor or
  redraw them. Drop in your own SVG or PNG (transparent works best) and
  point the row's "image" cell at the new filename.

  To change the board itself, replace images/board_bg.jpg.

BEHAVIOR
  hover  -> shows name, length, and "what it tastes like"
  click  -> plays an "om-nom-nom", marks the bite eaten (unclickable),
            and opens the url in a new tab
  stars  -> rate 1-5; saved in this browser (localStorage) so it persists
            when you return to the page
