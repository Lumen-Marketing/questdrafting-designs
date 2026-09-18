# Quest Drafting & Design, homepage directions

Four homepage designs in one chooser page. `index.html` is the link to send: it
runs all four as live previews at a real desktop width, with a mobile toggle,
and each card opens full screen.

```
index.html                      the chooser
direction-1-cut-line.html       "Cut Line"
direction-2-datum.html          "Datum"
direction-3-blueprint.html      "Blueprint"
direction-4-courtyard.html      "Courtyard"
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
| Drawings are printed in register, ink over ink | Datum's plates sit on solid planes, slightly off | Things arrive off register and pull into line |
| Plan line-work is the studio's own visual language | Blueprint's ground is drafting line-work on deep ink | Line-work is static; it is the ground, not an effect |
| A desert house is lived in at dusk, in a courtyard | Courtyard is a warm clay wall with an arched plate | Settle. Things rise a little and come to rest |
| A permit set is a stack of numbered sheets | Sheets are shown as sheets, named CS, A100, A103, A201 | Light table, mosaic viewer, sheet flipper, mounted plate |
| The work exists three times: massed, rendered, drawn | The same house shown as model, render and sheet | Each direction pairs them differently |

## Furniture matrix

Same sections, same order, same words in all four. No cell repeats across two
columns.

| Section | Cut Line | Datum | Blueprint | Courtyard |
|---|---|---|---|---|
| Opener | Full bleed render with a draggable cut revealing the elevation | Type first, render off register behind an orange plane | Full bleed render, statement crossing it, copy card over it | Symmetric courtyard, arched plate at the centre |
| Services | Four mirrored bleed bands, number crossing the edge | One large on orange beside three ruled rows | Accordion strip, the panel you point at opens | A spread of four entries in a recessed tray |
| Process | Strata, full width rows stepping deeper | Courses on an orange field filling white in order | Ruled timeline with drawn dimension connectors | Mirrored spine, steps hanging either side |
| The work | A roll of plates at full size, captions in the margin | Mosaic that opens full screen | Drag filmstrip with mixed slide widths | Three diptychs of unequal pairs |
| The set | Light table, pick a number and that sheet comes up | One wide plus three, numbers crossing the corner | Sheet viewer, tab list by number, on the rest of the set | Four sheets mounted on a cream board |
| The argument | Pine field, the heading crossing the top edge | Kinetic statement on ink, word by word | Statement full bleed over the night render | Cream field with the second arch beside it |
| Questions | Sticky index on the left, answers on the right | Heavy ruled pairs, question left, answer right | Ruled rows that expand in place | Two by two, questions in serif italic |
| Closing | Huge two line statement over an orange strip | Full width headline, then a split against the render | Orange band with the render behind it | Statement beside a recessed panel |

Type, material and depth, one set each:

| | Cut Line | Datum | Blueprint | Courtyard |
|---|---|---|---|---|
| Type | Bricolage Grotesque with Hanken Grotesk | Archivo Black with Familjen Grotesk | Big Shoulders Display with Sora | Newsreader with Schibsted Grotesk |
| Material | Vellum fibre | Screen print halftone | Plan line-work on deep ink | Lime plaster |
| Depth | Registration, offset planes behind plates | Misregistration resolving into register | Sheets overlapping, one crossing a section edge | Warm daylight, lit top edges, recessed trays |
| Shape | Square, 0px everywhere | Square, 0px everywhere | Square with drawn rules | Square, with the arch as the one signature form, used twice |
| Second colour | Pine #1C3A32 | Near black #0D0D0D | Steel blue #7FA6BF | Cream #F6EFE6 on clay #33251F |

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

Cut Line, Datum and Courtyard use only the `-top` copies. Blueprint still uses
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
- Every interactive piece driven with a real click and a real key press: the
  cut handle by drag and by arrow key, the light table by click, the mosaic
  viewer by click, arrow and Escape, the chooser toggle and veil by click.

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
