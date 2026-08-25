# design-system

The canonical source for Start9's two design systems. This file is the single
contributor and AI-developer guide: workflow, conventions, and the things worth
getting right about _this_ repo.

- `README.md` — what this is.
- `ARCHITECTURE.md` — how it's structured and why the tokens are shaped this way.
- `VOICE.md` — the editorial spec. Governs copy in both systems.
- `AGENTS.md` — this file (`CLAUDE.md` is a one-line `@AGENTS.md` import so
  Claude Code picks it up).

Licensed MIT (see `LICENSE`).

**Keep these docs current.** When you change a token, a utility, or the voice
rules, update the affected file(s) in the same change — don't defer.

## Prerequisites

None. There is no build step, no package manager, no dependency. Open
`systems/professional/example.html` in a browser and you are running the system.

## Branch, commit, PR

- Branch from `master`. Lowercase imperative one-line commit subjects.
- PRs against `master`.

## Conventions

**Plain CSS only.** No SCSS, no PostCSS, no bundler. If a value needs computing,
it needs `calc()` or it doesn't belong here. Anything that requires a build step
belongs in the consuming app, not in the system.

**A token is a value, not a decision.** `--s9-accent` is a token;
`--s9-button-primary-background` is a decision, and decisions live in
`utilities.css` or in the consuming app. Adding a token per component is how a
design system becomes unmaintainable.

**Never commit a font binary.** Two consumer families are commercially licensed
(Colophon, Pangram Pangram) and this repo is MIT — shipping them would
redistribute them under a license Start9 has no right to grant. Name the family
and its foundry; let each consumer license it. This applies to any new system
added later, and it is the reason the repo is publishable at all.

**Both systems are live and neither is subordinate.** Professional is not the
successor to Consumer — they serve different audiences and both take new work.
A change to one is not a reason to change the other.

**Extend the consumer system from its implementation, not from taste.**
start9.com is the reference build. When adding to `systems/consumer/`, lift the
pattern from that codebase and say so in the commit; the vocabulary there was
extracted, and it stays coherent only if additions are too.

**A rule in `VOICE.md` must hold for both systems.** Test it against the other
register before adding it there — the two disagree about casing, technical
depth, and what counts as proof, and a rule that holds for only one belongs in
that system's README under "Voice in this register". A shared file asserting a
professional rule silently makes the consumer system look non-compliant.

**Both systems are never loaded together.** They are separate systems, not
modes. If you find yourself reaching for a `--s9c-*` value on a professional
page, the answer is a new professional token or no token at all.

## Copy in examples

`example.html` and any future example page ships **real copy following
`VOICE.md`**, not lorem ipsum. The voice is the harder half of this system to
transmit, and an example page is the only place it can be demonstrated rather
than described.

That carries an obligation: **no invented figures, customers, or case studies,
even in an example.** Where an example needs proof that doesn't exist, it uses
the `g-empty` treatment — which is itself the pattern being demonstrated.

## Verification

Manual. Open the example page and read it in a browser at a narrow and a wide
viewport. There is no test runner and adding one would be more machinery than
this repo justifies.

Before publishing a change to a token, grep the consuming repos for the old
value — `ops/start9-store/web/src/styles/` is the live consumer of the
professional system, and start9.com of the consumer one.

## What this repo is not

It is **not** the authority on how Angular components are written — that's the
`start9-frontend` skill in the `start-technologies` monorepo. This repo carries
brand values; the skill carries component structure. They meet at the skill's
design-token step and neither restates the other.

It is also **not** a component library. There is no npm package and no plan for
one. It's tokens, a vocabulary, and a voice.
