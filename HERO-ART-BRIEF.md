# Hero illustration brief

Standing brief for the commissioned hero art on `index.html`. The page is
designed so the image is a *design system*, not a banner: the HTML text sits
on the calm side of the image, and the image's bottom edge dissolves into
the page's first dark section.

## Hard constraints (reject any delivery that violates one)

1. **Landscape, roughly 16:10** (target 1312 x 816). Matches a laptop
   viewport under `background-size: cover` with minimal cropping.
2. **No text anywhere in the image.** No letters, signage, numbers, or
   watermarks. All type is overlaid in HTML.
3. **No decorative frame or border.**
4. **Subjects grouped in the lower third**, centered or slightly right,
   sitting just above the dark convergence zone. (The page centers its
   hero text near the top, so the composition is calm-top, not calm-left.)
5. **Top ~55% calm and empty** (open sky), quiet enough for dark display
   text at large sizes, centered.
6. **Bottom quarter darkens to converge on one flat hex color across the
   entire bottom edge.** The next page section is set to that exact color
   (currently `#10182e`), so the image hands off invisibly.

## Scene direction (adapt freely within the constraints)

Dusk over Sydney Harbour seen from the water, painterly and warm, no
photorealism. Top half: open twilight sky, calm and empty. Lower third: a
friendly oversized robot kneeling at the shoreline, adjusting or guiding a
small group of smaller robots (agents managing agents), city skyline with
Sydney Tower behind them, centered or drifting slightly right. Warm amber
highlights against deep indigo dusk; the palette should sit comfortably
with indigo `#2e3a86`, ember `#b7521e`, gold `#e3a75c`, and night
`#10182e`.

## Prompt to give the image model

> A wide painterly digital illustration at 1312 x 816 (landscape, 16:10),
> dusk over Sydney Harbour viewed from the water. The top 55% of the frame
> is calm and empty: soft gradient twilight sky in muted periwinkle and
> apricot, no objects, no clouds with hard edges. Along the lower third,
> centered and drifting slightly right: a friendly rounded giant robot
> kneels at the shoreline gently guiding three small robots, silhouetted
> city skyline with Sydney Tower behind them, warm amber rim lighting,
> deep indigo shadows. The bottom quarter of the image darkens smoothly
> until the entire bottom edge is one flat uniform color, exactly #10182e,
> with no visible detail at the bottom edge. Absolutely no text, letters,
> numbers, signage, logos, watermarks, or decorative frame anywhere in the
> image. Muted warm palette: indigo, ember orange, soft gold. Storybook
> concept-art style, clean shapes, calm mood.

Expect 3 to 5 generations. Reject results that fix one requirement but
drift on another; re-state every constraint on each iteration.

## Verification checklist after each delivery

- [ ] Sample the bottom-row pixels; they must all be within a few RGB
      points of one flat color. Set `--night` (and the gradient stop in
      `.hero`) to that sampled hex.
- [ ] Measure brightness in every region where HTML text sits (badge,
      title, tagline, pitch, meta row, CTAs, deadline line) at desktop
      widths; dark text needs a light backdrop there.
- [ ] Swap the image in (`.hero` background) and screenshot the built page
      headless (Playwright) at 1440 x 900 and 390 x 844, at several scroll
      positions, before shipping.
- [ ] On phones the busy side may cross the text; the CSS already applies a
      tinted scrim and flips the hero text light below 880px. Verify it.

## How to swap the art in

1. Save as `assets/hero.png` (plus a 1200 x 630 crop as
   `assets/social-card.png` for the OG card).
2. In `index.html`, replace the two gradient layers on `.hero` with
   `background: url(assets/hero.png) center bottom / cover no-repeat;`.
3. Delete the `.hero-placeholder-art` SVG block.
4. Update `--night` to the sampled bottom-edge color if it moved.
