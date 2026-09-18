# Shared brief: three homepage directions for Quest Drafting & Design

A residential architectural drafting studio in Gilbert, Arizona. It takes a
house from first sketch through 3D, through a coordinated construction set,
and through plan review until the city stamps the permit.

All three directions are the SAME page: same sections, same order, same words,
same links. Only the design changes. No component, typeface, material or
depth device may be reused between directions.

## Hard rules (a single breach fails the direction)

1. Zero em dashes and zero en dashes anywhere visible, including alt text and
   the page title. Use a period, a comma or a plain hyphen.
2. No chains of middle dots. One middle dot per line at most, and prefer none:
   use line breaks, columns or hairlines.
3. No cyan or purple outer glow on anything. No neon. Depth comes from
   occlusion, inner borders and tinted shadows, never from light bleeding out.
4. No row of identical cards each with an icon in a rounded square.
5. No fake UI chrome (fake dashboards, terminals, browser bars, three dots),
   and no hand drawn SVG standing in for a photograph.
6. No decorative status dots, no LIVE badges, no version labels, no scroll
   cues ("Scroll to explore"), no weather or time strips.
7. No eyebrow label above every section. At most ceil(sections / 3) in total.
8. Banned faces: Inter, Manrope, Plus Jakarta Sans, Roboto, Arial, Space
   Grotesk, system stacks. Each direction uses the pair named in its spec,
   loaded from Google Fonts, with a real fallback stack.
9. No centred call to action panel with a radial glow.
10. Photographs are the product: never shrink one into a small rounded card.
11. Never size display type in `ch`. Headings should fill 89 to 93 percent of
    their row; measure by eye against the container, not by capping in `ch`.
12. Zero horizontal overflow at 505, 780, 880, 1024, 1280, 1440 and 1907
    pixels wide. The page must never scroll sideways.
13. Body text contrast at least 4.5:1, display type at least 3:1, measured
    against what is actually behind it. Over a photograph, that means a real
    veil or a dark ground, not hope.
14. Every number on the page must come from the content below. Invent nothing:
    no "500+ homes", no years in business, no review counts, no client names.
15. Real photographs only, from the list below. No stock, no placeholders, no
    illustration standing in for a photo.

## Technical requirements

- One self contained `.html` file: inline `<style>`, inline `<script>`, no
  build step, no frameworks, no external CSS.
- Google Fonts via `<link>` is the only external resource besides the images.
- Images load from `https://questdraftingsite.vercel.app/assets/...` exactly as
  listed below. Give every one a real `alt`, except decorative grounds, which
  take `alt=""` and `aria-hidden="true"`.
- Mobile first. Every multi column layout collapses to one column below 768px.
- Motion: `transform` and `opacity` only, IntersectionObserver for reveals,
  never a scroll event listener. Everything honours
  `@media (prefers-reduced-motion: reduce)`. Content is visible at rest: never
  leave a block parked at `opacity: 0` waiting on an observer that may not run.
- Interactive pieces must work from the keyboard and on touch, not hover only.
- Use `min-height: 100dvh`, never `100vh`. The first screen ends at the fold:
  the next section must not peek in on load at 1440x900.

## The images (the studio's own work, nothing else exists)

| File | Size | What it is |
|---|---|---|
| render-motorcourt.webp | 1600x900 | Contemporary stone estate designed around a motor court, dusk |
| render-pool-twilight.webp | 1080x608 | Twilight render of a modern estate above a pool terrace |
| render-greatroom.webp | 1080x720 | Great room interior render, glass wall onto mountains at dusk |
| render-night-stars.webp | 1080x720 | Desert home glowing beneath a starry night sky |
| model-massing-white.webp | 1080x364 | White 3D massing model of a residence, wide strip |
| model-massing-terrain.webp | 1080x634 | 3D massing model set into its sloped lot, green terrain |
| sheet-cover-elevation.webp | 1500x1000 | Cover sheet CS: rendered elevation, sheet index, codes |
| sheet-site-plan.webp | 1500x1000 | Site plan A100: property lines, dimensions, the house on its lot |
| sheet-dimensional-plan.webp | 1500x1000 | Dimensional floor plan A103: every room and wall dimensioned |
| sheet-elevations.webp | 1500x1000 | Elevations A201: rear and right elevations, materials called out |

Every sheet carries a client street address in its bottom title block. When a
sheet is used as a large image, position it so the bottom strip is cropped out
(`object-position: 50% 15%` or similar). Never enlarge that strip.

Logo: `https://questdraftingsite.vercel.app/assets/logo.png` (wordmark, dark
type plus an orange mark, needs a light plate behind it on a dark ground).

## Brand

The brand colour is the logo orange `#E8552B`. It stays. Each direction adds
its own supporting palette and ONE complementary accent, and puts the accent on
large surfaces (a full band, filled buttons, big numerals), never only on small
icons or thin outlines.

## The content, verbatim (do not rewrite the facts)

**Studio:** Quest Drafting & Design LLC
**Line:** Residential architectural drafting in Gilbert, Arizona
**Phone:** (602) 339-6455 (`tel:+16023396455`)
**Email:** info@questdraftinganddesign.com
**Service area:** Gilbert, Queen Creek, Mesa, Chandler, Phoenix, Scottsdale

**Hero statement:** From vision, to model, to permit.
**Hero support:** We turn a property and an idea into a home that is resolved
on paper, modeled, documented and permitted, before the first shovel hits the
ground.
**Primary action:** Get a Quote. **Second action:** the phone number.

**The four services**

1. Architectural Design. From first massing study to a resolved floor plan,
   shaped by your lot, your zoning, and how you actually live. Custom homes,
   hillside and desert estates, additions, casitas, guest houses and site
   structures.
2. 3D Visualization. You approve the home itself, not a flat line drawing you
   have to imagine in three dimensions. A full 3D model and photoreal
   renderings, day and twilight, before a single construction sheet is final.
3. Construction Documents. The complete coordinated set your builder and your
   city both need, typically around 22 sheets across roughly six disciplines,
   drawn to the 2024 IBC / IRC / IECC code cycle.
4. Permit Stewardship. We do not hand you drawings and disappear. Submittals
   formatted to each jurisdiction's checklist, plan review comments answered,
   resubmittals managed until the permit is in hand.

**The process, in order:** Survey and setbacks. Design. 3D model.
Construction documents. Permit submitted. Permit in hand.

**The set (real sheet numbers, from the title blocks):** CS Cover sheet.
A100 Site plan. A103 Dimensional plan. A201 Elevations.

**The argument (use as a statement block):** Every hand-off is a chance for
something to be lost. Most residential projects pass through several hands
before a permit is issued. Quest takes a project the whole way, on one flat fee
agreed before we start.

**Four questions and answers**

- How much does a project cost? A flat fee agreed up front, based on the scope
  of your project. One fixed price and a defined timeline, with no hourly
  surprises.
- What is in a construction document set? Around 22 sheets across roughly six
  disciplines: cover, site, floor plans, roof plans, elevations, sections and
  coordinated details, drawn to the 2024 code cycle.
- Can you design an ADU, casita or guest house? Yes. Casitas, accessory
  dwelling units, guest houses, additions, remodels, RV garages and site
  structures. What you can build depends on your lot and your zoning.
- Why build a 3D model before the drawings? Because it lets you approve the
  actual home while changes are still free.

**Closing line:** Put your project on the board.

## Section order (identical in all three directions)

1. Navigation: Work, Services, About, Blog, FAQ, Contact, plus Get a Quote.
2. Opener: the hero statement, the support line, the two actions, and the
   studio's own photography.
3. What the studio does: the four services.
4. How it goes: the process in order.
5. The work: the four renders and the two 3D models.
6. The set: the four sheets, named by number.
7. The argument: the statement block.
8. Questions: the four questions and answers.
9. Closing: "Put your project on the board", Get a Quote, phone, service area.
10. Footer: studio, contact, service area, page links.

Sections 3 to 8 must each use a DIFFERENT layout family inside one direction:
no two sections in the same direction may share a layout. Across directions, no
layout family may repeat either. Your direction spec names the ones you own.
