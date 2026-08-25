# Start9 Professional

The light, institutional system. Used by start9-store and by everything
Professional Services touches.

Open `example.html` in a browser — it is the full Professional Services page
built from this vocabulary, and it exercises every pattern once.

## The register

Sober, legible, dense with substance, zero persuasion theater. The reader is an
organization deciding where its data will live; the emotional key is
institutional confidence, not enthusiasm.

**This is not the consumer brand muted.** It is built from the ground up for
someone evaluating a vendor: shorter paragraphs, concrete nouns, real numbers,
no metaphor, no display typography, no motion.

## Voice in this register

Shared rules are in [`../../VOICE.md`](../../VOICE.md) and outrank anything
here. These are the ones specific to this register.

**Sentence case, everywhere.** Headings, buttons, labels, nav items, table
headers. Never Title Case. No `letter-spacing`, no `text-transform` — if a
heading needs shouting to work, the heading is wrong. (The consumer system does
the opposite, deliberately; don't carry its casing across.)

**Depth is calibrated to a non-technical evaluator.** The shared rule against
diluting substance still holds — but the reader here may be an office manager or
a practice administrator, not an enthusiast. Leaving them over their head is a
failure, not a filter. Keep the real machinery on the page and make the sentence
around it plain.

**Proof is contractual, not social.** Cost comparisons, warranty terms, support
availability, and who owns what at the end of the agreement. Reviews carry the
consumer register; terms carry this one.

**The primary action is always a conversation, never a checkout.** Professional
Services is a consultative funnel and the design must not blur that.

## What Professional Services sells

Copy in this register should be able to fall back to these facts.

**The offering.** Managed sovereign infrastructure under an annual support
agreement. Start9 builds the hardware to order, runs and maintains it, trains
staff, and provides 24/7/365 support. The organization owns the hardware and the
data; Start9 is the outsourced technical team.

**Who it's for.** Organizations needing privacy and sovereignty without running
IT in-house — newsrooms, clinics, law firms, family offices, nonprofits,
privacy-sensitive businesses.

**What's included.** Build-to-order hardware · onboarding and staff training ·
24/7/365 on-demand support · ongoing maintenance, updates, and monitoring.

**How it works.** Talk → we scope and build → onboard and train → we support,
indefinitely.

**The model.** Quote-based, because every deployment is built to order. There is
no price list, and the page says so rather than implying one exists.

**The three arguments, in order of weight.**

1. **Privacy** — no third party can read the data, because no third party holds
   it.
2. **Security** — one tenant, one perimeter, no shared-SaaS blast radius, and
   updates that stay explicit and reviewed.
3. **Cost** — capital hardware you own against a per-seat annual subscription
   that never stops. Show the arithmetic; don't assert the conclusion.

## Palette

Light only. There is no dark variant, by design.

| Role                | Token                  | Value                    |
| ------------------- | ---------------------- | ------------------------ |
| Ground              | `--s9-ground`          | `#ffffff`                |
| Ground, alternating | `--s9-ground-alt`      | `#f5f6f8`                |
| Ground, sunken      | `--s9-ground-sunken`   | `#eef0f3`                |
| Text                | `--s9-ink`             | `#0b0c10`                |
| Text, secondary     | `--s9-ink-secondary`   | `#0b0c10` at 65%         |
| Text, tertiary      | `--s9-ink-tertiary`    | `#0b0c10` at 40%         |
| Action / accent     | `--s9-accent`          | `#3880ff`                |
| Accent, secondary   | `--s9-accent-2`        | `#c4247a`                |
| Positive            | `--s9-positive`        | `#2dd55b`                |
| Negative            | `--s9-negative`        | `#ff4961`                |
| Warning             | `--s9-warning`         | `#ffc409`                |
| Line                | `--s9-border`          | `#0b0c10` at 12%         |

**Blue is the action color** — links, primary buttons, the highlighted column of
a comparison table. **Magenta is a highlight, not a surface**: use it sparingly
and never as a page-level wash.

## Shape

Deliberately sharper and thinner than most systems: `1.5px` strokes, `0.5rem`
medium radius. Nothing is a pill except a chip.

**Separation comes from hairline borders and background tints, never from
elevation.** There is no elevation color in this system — surfaces do not
lighten to come forward. One shadow token exists (`--s9-shadow`) and it belongs
on cards and the sticky header, nowhere else.

## Layout

One content width for everything: `84rem` max, `2rem` gutter. Backgrounds are
full-bleed; content columns cap and center, so the header, footer, and every
section align edge to edge at any viewport.

A page is alternating full-bleed bands, each wrapping one capped column:

```html
<section class="g-band">
  <div class="g-wrap">…</div>
</section>
<section class="g-band g-band--alt">
  <div class="g-wrap">…</div>
</section>
```

Prose caps at `52rem` for line length — `.g-wrap p` does this for you.

## Typography

**Manrope**, one family, all weights. SIL Open Font License, so it can ship with
anything; not committed here — pull it from Google Fonts or npm.

This system has **no display face**. A heading earns its weight from size and
hierarchy alone.

## Vocabulary

| Class            | What it is                                                        |
| ---------------- | ----------------------------------------------------------------- |
| `g-band`         | Full-bleed page section; `--alt` for the tinted alternate         |
| `g-wrap`         | Width-capped, centered content column; carries the prose baseline |
| `g-lead`         | The intro paragraph under a heading — full-ink, larger            |
| `g-actions`      | Button row                                                        |
| `g-button`       | Primary action; `--outline` for the secondary                     |
| `g-points`       | Bold-term lead-in list                                            |
| `g-steps`        | Numbered process list                                             |
| `g-chips`        | Pill row — audience tags, brand wall, config tiles                |
| `g-card`         | Bordered surface                                                  |
| `g-note`         | Inline callout; sits in the flow, never floats                    |
| `g-empty`        | Dashed honest-placeholder for proof that doesn't exist yet        |
| `g-specs`        | Definition grid — specs, terms, what's included                   |
| `g-compare`      | Comparison table; the Start9 column is last and tinted            |
| `g-primary` … `g-negative` | Text color utilities                                    |

Their `!important` is by design. Nowhere else in the system uses it.

## The two patterns that carry the argument

**`g-compare` — cost and capability.** The Start9 column goes last and takes the
pale accent tint. **Every table must be followed by a `<small class="g-tertiary">`
footnote naming the source and date of the figures.** The honest comparison is
the whole argument, so it has to be checkable. Never assert a savings percentage;
show the arithmetic and let the reader conclude.

**`g-empty` — missing proof.** Dashed and intentionally unfilled, so it reads as
a gap rather than a design. Use it wherever case studies, reviews, or metrics
don't exist yet. Never fill the hole with something invented.

## Using it with Taiga UI

The Angular apps run Taiga UI 5. Load `taiga-bridge.css` after Taiga's own theme
sheet and its `--tui-*` tokens resolve to these values; then use Taiga
primitives and appearances as normal and skip `utilities.css` except for the
`g-*` layout classes.

House style for those apps is the `start9-frontend` skill in the
`start-technologies` monorepo — it is the authority on component structure,
and this repo is the authority on brand values. They don't overlap.
