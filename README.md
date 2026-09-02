# MECH 501/600 — Computational Turbulence: Tutorials

Quarto website with the tutorial series for MECH 501/600 (McGill University).

## Local preview

```bash
quarto preview                      # student version (default)
quarto preview --profile solutions  # instructor version with solutions
```

Requires [Quarto](https://quarto.org/docs/get-started/) and Python with
`jupyter numpy matplotlib scipy`.

## Structure

- `_quarto.yml` — site config; default profile is `student`
- `_quarto-solutions.yml` — overrides for the solutions build (separate output dir)
- `tutorials/` — one `.qmd` per tutorial
- `styles.css` — task/solution box styling
- `.github/workflows/publish.yml` — auto-deploys the **student** site to GitHub Pages on push to `main`

## Student vs. solutions content

Wrap solutions in:

```markdown
::: {.content-visible when-profile="solutions"}
::: {.solution-box}
... solution text/code ...
:::
:::
```

They are stripped from the student build entirely (not just hidden).
The solutions build goes to `_site-solutions/` and is never deployed.

## Publishing (first time)

1. Create a GitHub repo and push this folder to `main`.
2. Run once locally: `quarto publish gh-pages` (creates the `gh-pages` branch),
   or just push — the Action will create it.
3. In repo Settings → Pages, set the source to the `gh-pages` branch.
4. Update the GitHub link in `_quarto.yml` (marked `TODO`).

## Execution caching

`freeze: auto` caches Python cell output in `_freeze/`. Commit that folder;
CI then renders without re-running your post-processing.

## Adding a tutorial

1. Copy `tutorials/tutorial-01.qmd` to `tutorials/tutorial-02.qmd`.
2. Add it to the `sidebar` section in `_quarto.yml` and to the table in `index.qmd`.
