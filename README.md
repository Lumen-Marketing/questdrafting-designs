# Quest Drafting & Design, homepage directions

Four homepage designs in one chooser page. `index.html` is the link to send: it
runs all four as live previews at a real desktop width, with a mobile toggle,
and each card opens full screen.

```
index.html                      the chooser
direction-1-cut-line.html       "Cut Line"
direction-2-sun-study.html      "Sun Study"
direction-3-blueprint.html      "Blueprint"
direction-4-trace.html          "Trace"
assets/                         the studio's own renders, models, sheets, logo
```

All assets are self hosted in `assets/`. Nothing hotlinks. These are four
alternative designs of the same homepage, not a price ladder.

## The trade, worked out before any design

Residential architectural drafting. The studio sells drawings that a builder can
build from and a city will stamp, so the design and the motion come from the
document and the model, not from a generic template.

| Trade fact | Design | Motion |
|---|---|---|
| A section is a cut through the building | Cut Line's opener cuts the photograph and finds the drawing | A cut line you drag across the render |
| A sun study renders the house at different hours | Sun Study runs the page from dusk to night | Move the light by hand, and a pinned sideways track |
| Plan line-work is the studio's own visual language | Blueprint's ground is drafting line-work on deep ink | Line-work is static; it is the ground, not an effect |
| A drafter works in overlays, in register | Trace is milky film laid on a graphite board | The four sheets of one set landing in register, pinned |
| A permit set is a stack of numbered sheets | Sheets are shown as sheets, named CS, A100, A103, A201 | Light table, fanned set, sheet flipper, pinned register |
| The work exists three times: massed, rendered, drawn | The same house as model, render and sheet | Each direction pairs them differently |

## Furniture matrix

Same sections, same order, same words in all four. No cell repeats across two
columns.

| Section | Cut Line | Sun Study | Blueprint | Trace |
|---|---|---|---|---|
| Opener | Full bleed render with a draggable cut revealing the elevation | Full bleed render with three hours you can move the light through | Full bleed render, statement crossing it, copy card over it | Headline printed on a sheet of film laid over the render |
| Services | Four mirrored bleed bands, number crossing the edge | Four tall columns on one mirrored offset | Accordion strip, the panel you point at opens | Four strips of film laid across one plate |
| Process | Strata, full width rows stepping deeper | Pinned track, six stations travelling sideways | Ruled timeline with drawn dimension connectors | Six overlays, each laid over the last |
| The work | A roll of plates at full size, captions in the margin | A skyline. Different heights, one baseline | Drag filmstrip with mixed slide widths | A film mat with windows cut in it |
| The set | Light table, pick a number and that sheet comes up | Four sheets fanned out, straightening into a stack | Sheet viewer, tab list by number, on the rest of the set | Pinned register, four sheets landing one at a time |
| The argument | Pine field, the heading crossing the top edge | Night ground with the stars render behind it | Statement full bleed over the night render | One sheet of film, printed, with registration crosses |
| Questions | Sticky index on the left, answers on the right | Two by two on night | Ruled rows that expand in place | Two by two on graphite, heavy rules |
| Closing | Huge two line statement over an orange strip | Deep night, then an orange strip | Orange band with the render behind it | Statement, then an orange strip |

Type, material and depth, one set each:

| | Cut Line | Sun Study | Blueprint | Trace |
|---|---|---|---|---|
| Type | Bricolage Grotesque with Hanken Grotesk | Syne with Outfit | Big Shoulders Display with Sora | Anybody with Chivo |
| Material | Vellum fibre | Raking light, one low sun | Plan line-work on deep ink | Mylar tooth |
| Depth | Registration, offset planes behind plates | Plates overlapping and casting onto each other | Sheets overlapping, one crossing a section edge | Registration in Z, film lying on film |
| Shape | Square, 0px everywhere | Square, 0px everywhere | Square with drawn rules | Square, 0px everywhere |
| Second colour | Pine #1C3A32 | Night indigo #111524 | Steel blue #7FA6BF | Graphite #1E2628 |

The brand orange `#E8552B` is fixed and appears in all four, always on a large
surface: a full strip, a whole field, a filled button, or display type.

## SWAP values

Everything below is unconfirmed and must be checked with the client before this
goes live anywhere public.

- `SWAP:` **Around 22 sheets** in a construction document set. Carried over from
  the studio's current site, not confirmed.
- `SWAP:` **Roughly six disciplines** in that set. Same.
- `SWAP:` **2024 IBC / IRC / IECC code cycle.** Same.
- `SWAP:` **Service area list** (Gilbert, Queen Creek, Mesa, Chandler, Phoenix,
  Scottsdale). Taken from the current site.
- `SWAP:` **Street address, licence number, years in business, pricing.** Not
  supplied, so they appear nowhere on any page.

Real and verified: the studio name, the phone number (602) 339-6455, the email
address, the city, and the sheet numbers CS, A100, A103, A201, which are printed
on the drawings themselves.

## The sheet images carry a client address

The four original sheets have a client street address in the bottom title block.
Rather than rely on a CSS crop holding at every screen size, the four sheets are
saved a second time with that band cut off:

```
assets/sheet-cover-elevation-top.webp     top 85 percent of the original
assets/sheet-site-plan-top.webp
assets/sheet-dimensional-plan-top.webp
assets/sheet-elevations-top.webp
```

Cut Line, Sun Study and Trace use only the `-top` copies. Blueprint still uses
the originals with a CSS crop. If these go public, either get the client's
permission or switch Blueprint to the `-top` copies too.

## Checks run

On each direction separately, at 505, 780, 880, 1024, 1280, 1440 and 1907 pixels:

- No horizontal overflow at any width.
- Zero em dashes and en dashes, including alt text and the page title.
- The opener ends at the fold at 1440 by 900, with the next section below it.
- Every display heading measured in its own typeface and sized to fill 89 to 93
  percent of its own column, at every width, using container units.
- Body text contrast at least 4.5:1 and display type at least 3:1, measured off
  the rendered pixels rather than the tokens.
- Every interactive piece driven with a real click, drag or key press: the cut
  handle by drag and by arrow key, the light table by click, the three hours in
  Sun Study by click, and the four sheet buttons in Trace by click.
- Both pinned set pieces driven by real scrolling at several positions, with
  motion enabled: Sun Study's track travels from 0 to the end of its rail, and
  Trace's four sheets land in register one at a time.
- Scroll driven motion uses native CSS scroll timelines, so there is no scroll
  event listener anywhere. Where a browser does not support them, or the reader
  asks for reduced motion, both set pieces fall back to ordinary layouts with
  everything visible.

## Deploy

GitHub Pages, from a repo under the Lumen Marketing org. From this folder:

```
git init
git add .
git commit -m "Quest Drafting and Design, four homepage directions"
git branch -M main
git remote add origin https://github.com/Lumen-Marketing/questdrafting-designs.git
git push -u origin main
```

Then in the repo: Settings, Pages, Deploy from branch, `main` and `/ (root)`.
The link to send is `https://lumen-marketing.github.io/questdrafting-designs/`.
