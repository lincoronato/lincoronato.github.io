# My personal website

Source for <https://lincoronato.github.io>.

A plain static site: two files do all the work. Nothing to install, build, or
compile.

| File | What it holds |
| --- | --- |
| `index.html` | All the **text** of the page |
| `style.css` | All the **colours, fonts, and layout** |
| `assets/` | Photo, CV, and any PDFs |
| `CREDITS.md` | Licence notice for the borrowed layout |

---

## 1. How to edit it yourself

**Use a plain-text editor.** [VS Code](https://code.visualstudio.com) is free and
the easiest choice — install it, then right-click the folder → *Open with → VS
Code*. Do **not** use Word or Pages. (TextEdit works only if you first do
*Format → Make Plain Text*; it silently mangles HTML otherwise.)

**The edit loop is:**

1. Change something in `index.html` or `style.css`.
2. Save.
3. Double-click `index.html` in Finder — it opens in your browser.
4. Already open? Just press **⌘R** to reload.

No internet, no server, no commands. Nothing you do here touches the live site
until you publish (section 4).

**If you break something**, you can always undo it: `git checkout index.html`
throws away your unsaved-to-git changes to that file and restores the last
committed version.

---

## 2. The things you will most likely want to change

### Colour scheme

Line 7 of `index.html`:

```html
<html lang="en" data-palette="teal">
```

Replace `teal` with any of: `midnight`, `harbor`, `forest`, `plum`, `graphite`,
`sand`. Save, reload. That is the whole procedure.

### The exact colours

Near the top of `style.css`, find the block starting `html[data-palette="teal"]`.
Each line is a colour you can replace with your own hex code:

| Variable | What it colours |
| --- | --- |
| `--side-bg` | the banner background (currently `#0d4b4d`, dark teal) |
| `--side-ink` | banner text |
| `--side-dim` | banner secondary text (your role) |
| `--side-active` | the highlight on the current menu item (warm amber) |
| `--link` | paper titles, links, course names, the small labels — all the coloured text (`#0d4b4d`) |
| `--accent` | decoration only: the bar under each heading, the affiliation bullets (`#c2700a`, amber) |

Change a value once and it updates everywhere that colour is used.

### Font

In `style.css`, the `--font:` line near the top. Three alternatives are written
out as comments directly underneath — delete the `/*` and `*/` around the one you
want, and comment out the current line.

### How wide the text is

Also near the top of `style.css`:

```css
--content-w: 1020px;
```

Raise it to fill more of a wide screen, lower it for shorter lines. Anywhere
between 800px and 1200px is reasonable.

---

## 3. Adding and removing content

**Fill in a placeholder.** Search `index.html` for the word `PLACEHOLDER` (⌘F in
VS Code) and type over it.

**Add a paper.** Copy one whole block from `<div class="paper">` down to its
closing `</div>`, paste it below, edit the text. Inside a paper block:

- `class="title"` — the paper name
- `class="authors"` — coauthors
- `class="venue"` — journal and year
- `<details class="brief">` — the click-to-open abstract
- `class="plinks"` — the row of pdf / doi / arXiv links
- `class="extra"` — the *Presented at* / *Awards* / *Media* lines

Any line you do not need can simply be deleted.

**Add a PDF.** Put it in `assets/docs/`, then link with
`href="assets/docs/yourfile.pdf"`.

**Change your photo.** The current one is `assets/headshot3-cropped.jpg`; drop a
new file in `assets/` and update the filename in `index.html`. It is displayed as
a portrait, taller than wide, so a landscape photo loses a lot from the sides.
Keep it near 800px on the long side and under ~200KB.

**Change your CV.** The CV button points at your separate `files` repository, so
update it there — or put a PDF at `assets/cv.pdf` and change the CV link in
`index.html` to point at it.

**Remove a whole section.** Delete its `<section>…</section>` block *and* its
line in the `<nav>` menu near the top of the file.

---

## 4. Publishing

When you are happy with what you see locally:

```bash
cd ~/Documents/GitHub/github.io && git add -A && git commit -m "Update site" && git push
```

The live site updates about a minute later.

**Alternative, no commands:** you can also edit straight on github.com. Open the
file there, click the pencil icon, make your change, and click *Commit changes*.
That publishes immediately. It is the easiest route for a quick typo fix, but you
do not get to preview first — so prefer the local loop for anything substantial.

---

## Credits

Layout adapted from an MIT-licensed template — see [CREDITS.md](CREDITS.md).
