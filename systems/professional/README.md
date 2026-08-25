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

**Concede first. It is the entire persuasion engine.** Every argument gives
ground before it asks for anything: name the thing that can't be replaced, the
tradeoff that's real, the part of your own house that isn't in order. The
concession is volunteered, never extracted, and it is given prominence rather
than buried — a line in the savings table reading "no open-source corollary —
stays" does more for the argument than any claim beside it. Design accordingly:
a concession never gets small type, a muted color, or a footnote.

**Two numbers, headline and defensible.** Lead with the strong figure, then
volunteer the conservative one before anyone asks for it. Being the one who
raises it is what makes the first believable. Both belong on screen together.

**Every figure is sourced and dated.** A table carries the basis of each line
and a "verified" date. Stale numbers cost the whole argument, so the design must
leave room for the provenance rather than treating it as clutter.

**The reader sets the pace.** Nothing here is a cutover or a migration project.
The offer is a ranked queue the customer approves one item at a time, and
sequence UI — steps, phases, queues — should read as repeatable and
interruptible, never as a progress bar to a finish line.

**Depth is calibrated to a non-technical evaluator.** The reader may be an
office manager or a managing partner. Keep the real machinery on the page; make
the sentence around it plain. Leaving them over their head is a failure here.

**Sentence case, everywhere.** Headings, buttons, labels, nav items, table
headers. No `letter-spacing`, no `text-transform`. (The consumer system does the
opposite, deliberately; don't carry its casing across.)

**Close on a kicker.** The recurring rhetorical move is a single line that
concedes or reframes, set apart after the substance — "You probably won't need
us much. That's the point." Use `g-kicker`; one per section, never two.

## What Start9 Business Services sells

Copy in this register should be able to fall back to these facts. The canonical
source is `_core.md` in the business-services deck program — **check its version
line before trusting anything below.**

**The offering.** Off rented software, onto systems the customer owns. Start9
assesses, recommends, deploys, trains, and supports — then repeats with the next
application when the customer says so.

**The price.** $20,000/year, rolling one-year commitment. No per-seat pricing,
no setup fee, no support tiers. The assessment is free with no obligation to
proceed. Roughly 1/8 the cost of one competent sysadmin, for a team.

**The hardware.** Bought by the customer directly, at cost, zero Start9 markup.
Theirs on day one and if they leave.

**The four phases.** Assess (free, five questions per application: cost,
privacy, security, alternatives, transition) → Recommend (hardware and where it
lives: office, colocation, VPS, or a mix) → Deploy and train (on-site or remote)
→ Support. Then again with the next application, at the customer's pace.

**The stack.** StartOS · StartWRT · StartTunnel · security cameras (soon).

**The support model.** A dedicated account manager who knows the business by
name, human technicians off-hours, an AI agent running on Start9 GPUs so
inference never leaves, and one private space. 24/7/365.

**No lock-in.** Non-proprietary hardware, 100% open source. Walk away and it
keeps running.

**The audience, in build order.** Bitcoin and digital-asset businesses ·
professional services, agencies, consultancies · law firms · accounting, CPA,
wealth management · lawful high-risk merchant categories. Journalism and
nonprofits are **blocked on pricing**, and vertically-locked SMB — trades,
restaurants, retail, dental, medical — is deliberately not pursued. Don't put
either group in audience copy.

**The three arguments, in order of weight.**

1. **Cost** — the largest and most legible. Show the arithmetic and the source;
   never assert a percentage on its own.
2. **Control** — no vendor able to reprice, reclassify, or switch them off.
3. **Privacy** — fewer third parties holding the data, and a smaller blast
   radius when one of them is breached. Argue attacker economics, not obscurity.

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
| `g-kicker`       | The closing line that concedes or reframes; one per section        |
| `g-concession`   | A volunteered weakness, given weight rather than demoted          |
| `g-figures` / `g-figure` | Headline figure paired with the defensible one            |
| `g-provenance`   | Basis-and-date line under any table of figures                    |
| `g-primary` … `g-negative` | Text color utilities                                    |

Their `!important` is by design. Nowhere else in the system uses it.

## The patterns that carry the argument

**`g-concession` — the volunteered weakness.** The single highest-trust move
available in this register, so it gets weight rather than losing it: same ink,
same size as the claim it qualifies, marked by a rule instead of demoted by a
muted color or smaller type. If a concession reads as fine print, the design has
inverted its purpose. Use it for the uptime tradeoff, the thing with no
open-source replacement, the part of Start9's own house that isn't in order yet.

**`g-compare` — cost and capability.** Start9's column goes last and takes the
pale accent tint. The row carrying a concession takes `.is-concession` and is
marked, never omitted. **Every table is followed by `g-provenance`** naming the
basis and the verification date of its figures — the honest comparison is the
whole argument, so it has to be checkable, and a stale number discredits the
rest.

**`g-figures` — headline and defensible together.** Lead with the strong number,
then volunteer the conservative one beside it, not beneath it. Raising it
yourself is what makes the first one believable.

**`g-kicker` — the closing line.** One per section, after the substance,
conceding or reframing. It is the line the reader leaves with, so it is
full-ink and larger than body copy — never an aside.

**`g-empty` — missing proof.** Dashed and intentionally unfilled, so it reads as
a gap rather than a design. Use it wherever case studies, reviews, or reference
customers don't exist yet. Never fill the hole with a composite.

## Using it with Taiga UI

The Angular apps run Taiga UI 5. Load `taiga-bridge.css` after Taiga's own theme
sheet and its `--tui-*` tokens resolve to these values; then use Taiga
primitives and appearances as normal and skip `utilities.css` except for the
`g-*` layout classes.

House style for those apps is the `start9-frontend` skill in the
`start-technologies` monorepo — it is the authority on component structure,
and this repo is the authority on brand values. They don't overlap.
