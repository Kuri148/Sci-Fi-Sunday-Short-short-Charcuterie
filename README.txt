SCI-FI SUNDAY: SHORT-SHORT CHARCUTERIE
======================================

FILES
  index.html      the page
  shorts.xlsx     the data (edit this to change entries)
  images/         one cover image per row (filenames referenced in the xlsx)

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
  Drop a new file into images/ and point the row's "image" cell at it.
  Square images look best; any aspect ratio is cropped to a square.

BEHAVIOR
  hover  -> shows name, length, and "what it tastes like"
  click  -> plays an "om-nom-nom", marks the bite eaten (unclickable),
            and opens the url in a new tab
  stars  -> rate 1-5; saved in this browser (localStorage) so it persists
            when you return to the page
