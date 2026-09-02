# Project context

Quarto website for **MECH 501/600 — Computational Turbulence** (McGill University),
taught by Hendrik Nicolai. Contains tutorials with tasks students answer and
upload to Crowdmark. Content mixes Python post-processing (executable cells),
OpenFOAM configuration, and cluster/bash instructions.

Key facts:

- Default profile is `student`; solutions are wrapped in
  `::: {.content-visible when-profile="solutions"}` + `::: {.solution-box}`
  and rendered with `quarto render --profile solutions` (never deployed).
- Branding: McGill red `#ed1b2f`, light/dark themes in `theme-light.scss` /
  `theme-dark.scss`; theme-neutral rules in `styles.css`.
- Logos in `assets/` (tile: `logo.svg`, wordmark: `logo-full.svg`).
- GitHub Actions deploys the student site to `gh-pages` on push to `main`.
- `freeze: auto` — commit `_freeze/` so CI doesn't re-run Python.
- Citations: `references.bib` + numeric style `assets/numeric.csl`; pages
  end with `## References` + `::: {#refs} :::`. Crossref prefixes are
  Eq./Fig./Tab. (set in `_quarto.yml`).

# Working style

- Always answer briefly and concisely. No long explanations unless asked.
- If a request is unclear or ambiguous, ask before doing the work.
