# Workflow Rollout Checklist

Use this checklist when copying a workflow from this library into a target repository.

## Before Adding a Workflow

- Confirm the target repo visibility and default branch.
- Confirm whether generated output should be committed, uploaded as an artifact, or published to Pages/internal hosting.
- Review existing `.github/workflows/` to avoid duplicate jobs or conflicting permissions.
- Identify generated, vendored, cache, data, model, and build-output folders that must be excluded.
- Start with `workflow_dispatch` unless scheduled runs are explicitly needed.

## Repo Visualizer

- Copy `workflows/repo-visualizer.yml` into `.github/workflows/repo-visualizer.yml`.
- Ensure `mkdir -p images` runs before `githubocto/repo-visualizer`.
- Tune `excluded_paths` and `excluded_globs` for the target repo.
- Run manually and verify `images/diagram.svg` is committed.

## Emerge

- Copy `configs/emerge.yml` into `.github/emerge.yml`.
- Copy `workflows/emerge-repo-visualizer.yml` into `.github/workflows/emerge-repo-visualizer.yml`.
- Replace `PROJECT_NAME` and tune permitted languages/extensions.
- Run manually and verify:
  - `images/emerge/html/emerge.html`
  - `images/emerge/emerge-statistics-metrics.txt`
  - `images/emerge/emerge-statistics-and-metrics.json`
  - GraphML/JSON exports

## After the First Run

- Inspect workflow logs before interpreting artifacts.
- Treat GitHub Node runtime deprecation notices as warnings unless the job fails.
- For Emerge, tolerate the known clipboard/pyperclip exit only when expected output files exist.
- Link generated artifacts from the repo README or internal dashboard only after confirming public/private exposure is acceptable.
