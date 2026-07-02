# Public and Private Repo Posture

Workflow artifacts can reveal repository structure, dependency shape, file names, and operational conventions. Choose the output mode intentionally.

## Public Repositories

Reasonable defaults:

- Commit small static artifacts such as `images/diagram.svg`.
- Commit Emerge output only when the repo structure is intended to be public.
- Use GitHub Pages when an interactive visualization should be easy to browse.
- Avoid committing large generated bundles if artifacts are enough.

## Private Repositories

Reasonable defaults:

- Keep exploratory outputs as GitHub Actions artifacts first.
- Commit generated artifacts only when all repo collaborators may view them.
- Do not publish private repo structure to public Pages.
- Prefer a private internal dashboard if artifacts need to be browsed across repos.

## Sensitive Outputs

Do not publish or commit outputs that include:

- Secrets or secret-like values.
- Customer names, private URLs, account identifiers, or internal support details.
- Local filesystem paths that reveal private machine structure.
- Data/model/runtime artifacts that are not part of source control.

## Promotion Rule

Start advisory and private. Promote to committed output, scheduled workflow, or dashboard only after the first run proves the output is stable, useful, and safe to expose.
