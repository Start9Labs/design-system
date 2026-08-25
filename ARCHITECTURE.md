# Architecture

## Goals

1. **Stack-neutral.** Plain CSS custom properties, no build step, no framework
   dependency. The consumers today are Eleventy and Angular; they won't be
   forever, and the brand values should outlive both.
2. **Splittable.** Each system is self-contained under `systems/<slug>/` with no
   cross-imports, so lifting one out is a `git mv`.
3. **Safe to publish.** Nothing in this repo may require a license Start9 can't
   grant — which is why it names fonts instead of shipping them.

## Layout

```
VOICE.md                editorial rules — govern both systems
systems/
  professional/         light, institutional
    tokens.css          the values
    utilities.css       the g-* vocabulary, built on the values
    taiga-bridge.css    optional adapter for Taiga UI 5 apps
    example.html        reference page exercising every pattern
    README.md
  consumer/             dark, enthusiast
    tokens.css
    utilities.css
    example.html
    README.md
```

## Why tokens and utilities are separate files

`tokens.css` is the brand. `utilities.css` is one opinion about how to spend it.

An Angular + Taiga app wants the first and almost none of the second — Taiga
supplies its own components, so it takes `tokens.css`, `taiga-bridge.css`, and
only the `g-band` / `g-wrap` layout classes. A static page or a one-off
microsite wants both. Splitting them means neither consumer carries the other's
weight.

## Why `--s9-*` and not `--tui-*`

Taiga UI is the current component library, not a permanent commitment. Defining
the palette in Taiga's namespace would make the brand a function of a
third-party dependency's token vocabulary, and a Taiga major that renames tokens
would look like a rebrand.

So `--s9-*` is canonical and `taiga-bridge.css` maps `--tui-*` onto it. The
bridge is the adapter; if Taiga goes, only the bridge does.

The bridge relies on **source order, not specificity** — its selectors match
Taiga's own `.light()` defaults exactly, so it must load after
`taiga-ui-theme.less`. Raising its specificity instead would break Taiga's
component-scoped theme overrides.

## Why the two systems don't share a token namespace

`--s9-*` and `--s9c-*` are separate on purpose. They are not light and dark
modes of one system — they are two systems with different type scales, different
shape languages, and different rules about depth. Sharing a namespace would
invite a page to load both and inherit an incoherent mix.

A page picks one. There is no supported way to run both.

## Relationship to the frontend house-style skill

The `start9-frontend` skill in the `start-technologies` monorepo is the
authority on **how Angular components are written** — structure, signals, Taiga
primitives, the escalation ladder for reaching CSS at all.

This repo is the authority on **what the brand values are**.

They meet at the skill's step ③ ("a `--tui-*` design-token override in the theme
sheet"): the values that go there come from here. Neither restates the other.

## Adding a system

A new register (a sub-brand, an acquisition, a conference identity) gets its own
`systems/<slug>/` with at minimum `tokens.css` and a `README.md` stating the
register, the palette, and the type licensing. Add a row to the root `README.md`
table. Do not add it to an existing system as a variant.
