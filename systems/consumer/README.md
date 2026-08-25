# Start9 Consumer

The dark, enthusiast system. For readers who already care about sovereign
computing: product marketing, campaigns, decks, mockups, and start9.com.

**Live.** start9.com is the reference implementation, not the only consumer of
this system — product marketing, campaign pages, decks, and mockups aimed at
individuals all use it. It is not the professional system's predecessor; the two
serve different audiences and both take new work.

Open `example.html` in a browser — it exercises every pattern once.

## The register

Dark, high-contrast, display-typographic. The reader already cares about
sovereign computing; the job is identity and enthusiasm rather than evaluation.

Where the professional system removes, this one adds: gradients, 3D shadows,
glass, a display face carrying the headline, and viewport-relative type that
scales continuously with the window instead of stepping at breakpoints.

## Voice in this register

Shared rules are in [`../../VOICE.md`](../../VOICE.md). These are the ones
specific to this register — and the casing rules are the direct inverse of the
professional system's, so don't reconcile them.

**Uppercase and tracked, for chrome.** Nav items, buttons, product labels, and
section eyebrows are `text-transform: uppercase` with `letter-spacing` around
`0.1em` (up to `0.5rem` on the widest product labels). This is the system's
texture, not an accident.

**Title Case headings.** "Origin Story", "Our Team", "Community Support Techs".

**Free to go over the reader's head.** This reader already cares about sovereign
computing, so the copy can run deep and stay technical. Feeling out of one's
depth is a signal the thing is real — an acceptable outcome here, and a failure
in the professional register.

**Proof is social.** Reviews, the services brand-wall, and the mission — not
contract terms.

## Palette

| Role                | Token              | Value     |
| ------------------- | ------------------ | --------- |
| Ground              | `--s9c-ground`     | `#333333` |
| Ink                 | `--s9c-ink`        | `#ffffff` |
| Ink, on inverse     | `--s9c-ink-offset` | `#333333` |
| Ink, muted          | `--s9c-ink-muted`  | `#e0e0e0` |
| **Identity accent** | `--s9c-accent`     | `#ff4961` |
| Accent, light       | `--s9c-red-light`  | `#ee6570` |
| Accent, deep        | `--s9c-red-deep`   | `#e84258` |
| 3D shadow           | `--s9c-red-shadow` | `#993e4a` |
| **Action**          | `--s9c-action`     | `#6866cc` |
| Success             | `--s9c-success`    | `#27b45f` |
| Negative            | `--s9c-negative`   | `#e43434` |
| Bitcoin             | `--s9c-bitcoin`    | `#f7931a` |
| Lightning           | `--s9c-lightning`  | `#7b1af8` |

**Red is the identity accent; violet is the action color.** Red carries links,
hover states, emphasis sub-headings, pills, and SVG fills. Every button, form
focus ring, and date badge is violet. This is counterintuitive and deliberate —
the call to action does not compete with the brand color. Don't "correct" a
violet button to red.

**Depth is blur and scrim, never a lighter gray.** A surface comes forward with
`--s9c-light-20` + `backdrop-filter`, or recedes with `--s9c-dark-20` + the
same. The grays are for text and borders.

## Vocabulary

| Class                       | What it is                                                     |
| --------------------------- | -------------------------------------------------------------- |
| `c-ground`                  | Page ground — flat gray blended over a fixed photographic image |
| `c-hero`                    | The hero line — Basis Grotesque Pro, sentence case, tight       |
| `c-headline`                | Section headline — same face, uppercase                         |
| `c-display`                 | The Tusker slab — condensed, uppercase, low weight, sparing     |
| `c-subhead`                 | Red emphasis sub-heading                                        |
| `c-eyebrow`                 | Uppercase tracked label — eyebrows, nav, grid headings          |
| `c-body`                    | Montserrat 300, capped at `50ch`                                |
| `c-btn`                     | Violet pill CTA; `--boxy` for in-form and in-card               |
| `c-pill`                    | Red tag; inverts on hover                                       |
| `c-panel-inverse`           | Light scrim + blur; text flips dark                             |
| `c-panel-subtle`            | Dark scrim + blur; recedes                                      |
| `c-panel-shadow`            | The large soft drop shadow                                      |
| `c-glass` / `c-glass--dark` | Product-tile gradients                                          |
| `c-ruled` / `c-framed`      | Hairline white rules and frames                                 |
| `c-grid`                    | Three-across dashed grid, interior dividers only                |
| `c-connector`               | Hairline SVG path threading section to section                  |
| `c-lift`                    | Scale-up + flip-to-red hover                                    |
| `c-section` / `c-stack` / `c-cols` | Layout                                                  |
| `c-accent` / `c-muted` / `c-bitcoin` / `c-lightning` | Text colors                   |

**`<em>` is never italic here** — it is weight emphasis (600 in body, 900 in
grid headings). Set it that way rather than reaching for a `<strong>`.

**There is no page-width cap.** The consumer system fills the viewport and
scales with it; `--s9-page-max` is the professional system's idea. Root font
size is `max(2vmin, 10px)`, so every `rem` below is a fraction of the window.

## Typography — licensing

Five families, and **two of them are commercial**. No binaries are committed
here or anywhere they could be redistributed.

| Family                  | Role                    | License                    |
| ----------------------- | ----------------------- | -------------------------- |
| Basis Grotesque Pro     | Hero and buttons        | Commercial — Colophon Foundry |
| Tusker Grotesk          | Display headlines       | Commercial — Pangram Pangram  |
| Montserrat              | Body                    | SIL OFL                    |
| Arkibal Mono            | Accent mono             | Commercial                 |
| Liberation Mono         | Copy mono               | SIL OFL                    |

The start9.com repo does carry these binaries in `src/assets/fonts/`. **That
repo must stay private for that reason** — publishing it would redistribute
licensed webfonts under an MIT license Start9 has no right to grant over them.
