# Start9 Design System

Two design systems, one company.

Start9 sells to two audiences in two registers, and the visual language differs
accordingly. This repo is the canonical, stack-neutral source for both: colors,
shape, layout scale, component vocabulary, and — most importantly — the
editorial voice that governs all of it.

| System                                   | Register                                                                                                        | Ground          | Accent            | Used by                          |
| ---------------------------------------- | --------------------------------------------------------------------------------------------------------------- | --------------- | ----------------- | -------------------------------- |
| [**Professional**](systems/professional) | Institutional. Sober, legible, concessive. Argues cost, then control, then privacy — to organizations. | Light `#ffffff` | Blue `#3880ff`    | start9-store, Business Services |
| [**Consumer**](systems/consumer)         | Enthusiast. Dark, high-contrast, display-typographic. Sells sovereignty to individuals.                          | Dark `#333333`  | Red `#ff4961`     | start9.com, decks, campaigns     |

**Both systems are live.** start9-store and everything Start9 Business Services
touches use Professional; product marketing, campaign pages, decks, and mockups
aimed at individuals use Consumer. Pick by audience, not by recency — and when
a piece genuinely straddles the two, pick one and commit. They never blend.

## Structure

```
VOICE.md                      editorial rules shared by both systems — read first
systems/professional/         the light, institutional system
  tokens.css                  palette, shape, layout scale as --s9-* customs
  utilities.css               the g-* component vocabulary
  taiga-bridge.css            optional: maps --tui-* onto --s9-* for Taiga UI apps
  example.html                a full reference page, self-contained
  README.md                   register, voice, palette, vocabulary
systems/consumer/             the dark, enthusiast system
  tokens.css                  palette, type, surface treatments as --s9c-* customs
  utilities.css               the c-* component vocabulary
  example.html                a full reference page, self-contained
  README.md                   register, voice, palette, vocabulary
```

Each system directory is self-contained — no cross-imports — so either can be
lifted out whole.

## Using a system

Plain CSS custom properties. Link the two sheets and you have the system:

```html
<link rel="stylesheet" href="systems/professional/tokens.css" />
<link rel="stylesheet" href="systems/professional/utilities.css" />
```

For an Angular + Taiga UI 5 app, add the bridge after Taiga's own theme sheet so
the `--tui-*` tokens resolve to Start9 values:

```json
"styles": [
  "node_modules/@taiga-ui/styles/taiga-ui-theme.less",
  "node_modules/@taiga-ui/styles/taiga-ui-fonts.less",
  "systems/professional/tokens.css",
  "systems/professional/taiga-bridge.css",
  "src/styles.scss"
]
```

## Fonts

**No font binaries are committed here, deliberately** — several Start9 faces are
commercially licensed and cannot be redistributed under this repo's MIT license.
Each system's README names its families and their licensing; obtain them from the
foundry.

## Docs

- `README.md` — what this is.
- `ARCHITECTURE.md` — how it's structured and why the tokens are shaped this way.
- `VOICE.md` — the editorial spec shared by both systems. Voice that differs by
  register — casing, technical depth, what counts as proof — lives in each
  system's own README.
- `AGENTS.md` — how to contribute, and the AI-developer operating rules.

Licensed MIT (see `LICENSE`).
