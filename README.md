# My personal website

Source for <https://lincoronato.github.io>.

It is a plain static site: two files do all the work, and there is nothing to
install, build, or compile.

| File | What it holds |
| --- | --- |
| `index.html` | All the **text** of the page |
| `style.css` | All the **colours, fonts, and layout** |
| `assets/` | Your photo, your CV, and any PDFs you link to |

## How to edit it

1. Open `index.html` in any text editor.
2. Find the text you want to change and type over it. Everything marked
   `PLACEHOLDER` is meant to be replaced.
3. Save, then **double-click `index.html`** to open it in your browser and see
   the result. No internet, no server needed.
4. When you are happy, commit and push — the live site updates in about a minute.

## Common changes

**Change the colour scheme.** Line 9 of `index.html` reads
`<html lang="en" data-palette="midnight">`. Replace `midnight` with one of:
`harbor`, `forest`, `plum`, `graphite`, `sand`.

**Change the font.** Open `style.css`; the `--font:` line near the top has three
alternatives written out as comments right below it.

**Add a paper.** In `index.html`, copy one whole `<div class="paper"> ... </div>`
block, paste it below, and edit the text inside.

**Add a PDF.** Drop the file into `assets/docs/`, then link to it with
`href="assets/docs/yourfile.pdf"`.

**Add your photo.** Save it into `assets/`. If it is called `headshot.jpg`,
change `assets/headshot.svg` to `assets/headshot.jpg` in `index.html`.

**Add your CV.** Save it as `assets/cv.pdf` and the CV link already works.

**Remove a whole section.** Delete its `<section> ... </section>` block, and also
delete its line in the `<nav>` menu near the top.

## Credits

Layout adapted from an MIT-licensed template — see [CREDITS.md](CREDITS.md).
