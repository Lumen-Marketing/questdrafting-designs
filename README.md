# Quest Drafting & Design, homepage directions

Six homepage designs in one chooser page. `index.html` is the link to send: it
runs all six as live previews at a real desktop width, with a mobile toggle,
and each card opens full screen.

```
index.html                      the chooser
direction-1-cut-line.html       "Cut Line"
direction-2-sun-study.html      "Sun Study"
direction-3-blueprint.html      "Blueprint"
direction-4-trace.html          "Trace"
direction-5-monograph.html      "Monograph"
direction-6-redline.html        "Redline"
assets/                         the studio's own renders, models, sheets, logo
```

All assets are self hosted in `assets/`. Nothing hotlinks. These are six
alternative designs of the same homepage, not a price ladder.

## The trade, worked out before any design

Residential architectural drafting. The studio sells drawings that a builder can
build from and a city will stamp, so the design and the motion come from the
document and the model, not from a generic template.

| Trade fact | Design | Motion |
|---|---|---|
| A section is a cut through the building | Cut Line's opener cuts the photograph and finds the drawing | A cut line you drag, and plates cut open from the left |
| A sun study renders the house at different hours | Sun Study runs the page from dusk to night | Move the light by hand, and a pinned sideways track |
| Plan line-work is the studio's own visual language | Blueprint's ground is drafting line-work on deep ink | An index that brings a plate up |
| A drafter works in overlays, in register | Trace is milky film laid on a graphite board | Four sheets landing in register, and film panning behind a mat |
| Finished architecture gets published | Monograph treats the house as a book plate | Turning to the next plate |
| What the studio sells is a permit, not a drawing | Redline is the marked up print that comes back from review | Every mark on the page draws itself |
| The work exists three times: massed, rendered, drawn | The same house as model, render and sheet | Each direction pairs them differently |

## How the photographs are handled

The studio has six images. They were being shown at 400 to 600 pixels wide
inside text led sections, which was the single biggest weakness in the first
pass. Three things changed at the asset level before any layout was touched:

- **Purpose cut crops.** `w-*.webp` are ultrawide letterbox crops cut into the
  architecture and upscaled so they hold at full bleed. `t-*.webp` are tall
  portrait crops for column and stack layouts. The originals carry a lot of sky
  and grass; the crops spend the pixels on the building.
- **The massing model is knocked out.** `model-cut.png` keys the SketchUp green
  ground away so the mass sits on the page's own surface as an object, instead
  of reading as a screenshot inside a green box.
- **The terrain model is neutralised.** `model-terrain-neutral.webp` pulls the
  grass hue to a cool slate so the site model can sit on the dark directions
  without fighting them. The contour lines survive.

No direction reuses another's photo component, and no photograph anywhere is
reduced to a thumbnail in a captioned card.

## Furniture matrix

Same sections, same order, same words in all six. No cell repeats across two
columns.

| Section | Cut Line | Sun Study | Blueprint | Trace | Monograph | Redline |
|---|---|---|---|---|---|---|
| Opener | Full bleed render with a draggable cut revealing the elevation | Full bleed render with three hours you can move the light through | Full bleed render, statement crossing it, copy card over it | Headline printed on a sheet of film laid over the render | Title page. One wide figure, the title set beneath it | The render under review, boxed, circled and stamped |
| Services | Four mirrored bleed bands, number crossing the edge | Four tall columns on one mirrored offset | Accordion strip, the panel you point at opens | Four strips of film laid across one plate | Contents page, ruled rows with roman folios | Four clauses on a checklist |
| Process | Strata, full width rows stepping deeper | Pinned track, six stations travelling sideways | Ruled timeline with drawn dimension connectors | Six overlays, each laid over the last | Six notes across a two column gutter | A route of six ruled stops |
| The work | Plates run to the page edges, each cut open from the left | A pile of prints under one lamp, pick one up | A drawing index beside one plate running off the right edge | A graphite mat with the film panning behind its windows | Full page plates, each pinned then covered by the next | Renders carrying the studio's own marks at full size |
| The set | Light table, pick a number and that sheet comes up | Four sheets fanned out, straightening into a stack | Sheet viewer, tab list by number, on the rest of the set | Pinned register, four sheets landing one at a time | The signature, four sheets laid open flat | A transmittal logging four sheets out |
| The argument | Pine field, the heading crossing the top edge | Night ground with the stars render behind it | Statement full bleed over the night render | One sheet of film, printed, with registration crosses | The one black page in the book | Ink field with the mark drawn through it |
| Questions | Sticky index on the left, answers on the right | Two by two on night | Ruled rows that expand in place | Two by two on graphite, heavy rules | Marginalia. Question ruled, answer in the outer column | Plan review comments, numbered |
| Closing | Huge two line statement over an orange strip | Deep night, then an orange strip | Orange band with the render behind it | Statement, then an orange strip | Colophon. The last page, a full orange field | The stamp. One heavy orange block set off square |

Type, material and depth, one set each:

| | Cut Line | Sun Study | Blueprint | Trace | Monograph | Redline |
|---|---|---|---|---|---|---|
| Type | Bricolage Grotesque with Hanken Grotesk | Syne with Outfit | Big Shoulders Display with Sora | Anybody with Chivo | Bodoni Moda with Instrument Sans | Gabarito with Schibsted Grotesk |
| Material | Vellum fibre | Raking light, one low sun | Plan line-work on deep ink | Mylar tooth | Paper tooth | Print tooth, dry toner |
| Depth | Registration, offset planes behind plates | Plates overlapping and casting onto each other | Sheets overlapping, one crossing a section edge | Registration in Z, film lying on film | The page edge, leaves lying on leaves | The mark floating above the print |
| Shape | Square, 0px everywhere | Square, 0px everywhere | Square with drawn rules | Square, 0px everywhere | Square, 0px everywhere | Square, 0px everywhere |
| Second colour | Pine #1C3A32 | Night indigo #111524 | Steel blue #7FA6BF | Graphite #1E2628 | True black #0A0A0A | Warm stock #F6F3EC |

The brand orange `#E8552B` is fixed and appears in all six, always on a large
surface: a full strip, a whole field, a stamp block, a filled button, or
display type. It is never used for small text on a light ground, where it
measures about 3.5 to 1.

## Scroll driven motion

Four of the six carry a set piece driven by scroll position itself. None of
them uses a scroll event listener.

| Direction | Set piece | How |
|---|---|---|
| Cut Line | Plates cut open from the left as they ride up | `animation-timeline: view()` on a `clip-path` |
| Sun Study | Six process steps pinned and travelling sideways | `view-timeline` on the track |
| Trace | Four sheets landing in register, pinned. Film panning behind the mat | `view-timeline` on the stack and the mat |
| Monograph | Each plate holds the screen, the next page rises over it | `position: sticky` |
| Redline | Every rule and circle draws itself | `stroke-dashoffset` on `animation-timeline: view()` |

Each one is behind `@supports (animation-timeline: view())` and
`@media (prefers-reduced-motion: no-preference)`. A browser without support,
or a reader who asks for reduced motion, gets an ordinary layout with
everything visible and nothing hidden.

## SWAP values

Everything below is unconfirmed and must be checked with the client before this
goes live anywhere public.

- **Around 22 sheets, roughly six disciplines.** No longer a SWAP. The cover
  sheet's own sheet index lists exactly 22 sheets (CS, A100, GAN, A101, A102,
  A103, A200, A300, A400, A500, AD, E100, E200, E300, M100, P100, GSN, S100,
  S200, S300, SD1, SD2) across six disciplines: general, architectural,
  electrical, mechanical, plumbing and structural. Read off the drawing.
- `SWAP:` **2024 IBC / IRC / IECC code cycle.** The cover sheet lists IBC, IRC,
  IEBC, IECC and UPC by name but the crop does not show the year. Confirm the
  cycle year with the client.
- `SWAP:` **Service area list** (Gilbert, Queen Creek, Mesa, Chandler, Phoenix,
  Scottsdale). Taken from the current site.
- `SWAP:` **The review notes in Redline's work section.** The three annotations
  are plausible drafting comments written for the layout, not real review
  comments off these projects. Either replace them with real ones or cut them.
- `SWAP:` **Street address, licence number, years in business, pricing.** Not
  supplied, so they appear nowhere on any page.

Real and verified: the studio name, the phone number (602) 339-6455, the email
address, the city, and the sheet numbers CS, A100, A103, A201, which are printed
on the drawings themselves.

## The sheet images carried a client's details

Two separate leaks, both fixed in the image files rather than with CSS:

**1. The bottom title block.** All four sheets carry a client street address
there. Rather than rely on a CSS crop holding at every screen size, the four
sheets are saved a second time with that band cut off:

```
assets/sheet-cover-elevation-top.webp     top 85 percent of the original
assets/sheet-site-plan-top.webp
assets/sheet-dimensional-plan-top.webp
assets/sheet-elevations-top.webp
```

Every direction except Blueprint uses only the `-top` copies. Blueprint still
uses the originals with a CSS crop. If these go public, either get the client's
permission or switch Blueprint to the `-top` copies too.

**2. The site plan's PROPERTY DESCRIPTION block.** Cutting the bottom band did
not catch this one. The A100 site plan carries the owner's company name, the
full street address and the parcel number in a table at the top right, which
was visible in every direction that shows that sheet. Those three rows are now
overwritten in both `sheet-site-plan.webp` and `sheet-site-plan-top.webp` with
"CLIENT ON FILE", "GILBERT, AZ 85234" and "ON FILE". The rest of the sheet is
untouched. The cover, dimensional plan and elevations sheets were checked and
carry no identifying details.

## Checks run

On each direction separately, at 505, 780, 880, 1024, 1280, 1440 and 1907 pixels:

- No horizontal overflow at any width, and no element wider than the viewport.
- Zero em dashes and en dashes, including alt text and the page title.
- The opener ends at the fold at 1440 by 900, with the next section below it.
- Every display heading measured in its own typeface and sized to fill 89 to 93
  percent of its own column, at every width, using container units.
- Body text contrast at least 4.5:1 and display type at least 3:1, measured off
  the rendered pixels rather than the tokens.
- Every interactive piece driven with a real click, drag or key press: the cut
  handle by drag and by arrow key, the light table by click, the three hours in
  Sun Study by click, the pile by click, Blueprint's drawing index by click, and
  the four sheet buttons in Trace by click.
- Both pinned set pieces driven by real scrolling at several positions, with
  motion enabled.

## Deploy

GitHub Pages, from a repo under the Lumen Marketing org. From this folder:

```
git add -A
git commit -m "Six directions, rebuilt photo components"
git push origin main
```

Then in the repo: Settings, Pages, Deploy from branch, `main` and `/ (root)`.
The link to send is `https://lumen-marketing.github.io/questdrafting-designs/`.
