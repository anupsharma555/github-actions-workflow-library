# GitHub Actions Workflow Library

Reusable GitHub Actions workflow templates for repository visualization, dependency analysis, diagnostics, and repo health.

This repository is a public catalog of workflow patterns that can be copied into target repositories and tuned per repo. It starts with the workflows currently used for static repo footprint visualization and Emerge dependency analysis.

## Included Templates

- `workflows/repo-visualizer.yml`: static SVG repository footprint map using `githubocto/repo-visualizer`.
- `workflows/emerge-repo-visualizer.yml`: interactive Emerge dependency-analysis artifact generation under `images/emerge/`.
- `configs/emerge.yml`: starter Emerge config for Python and JavaScript repositories.

## Intended Use

Use this repo as a source of reviewed workflow patterns, not as a dependency that target repos call directly. For most repos, copy the relevant workflow and config into the target repo, then tune exclusions and language filters.

Default posture:

- Start workflows as manual `workflow_dispatch` jobs.
- Commit small, stable generated outputs only when useful.
- Prefer workflow artifacts for larger reports, sensitive structure, or experimental diagnostics.
- Avoid publishing private repo structure to public Pages unless intentionally approved.

## Current Workflow Families

### Repo Visualizer

Produces a static `images/diagram.svg` showing folder/file footprint. It is useful for quick structural orientation, but it is not an import/dependency graph.

### Emerge

Produces interactive HTML, JSON, GraphML, and metrics exports. It is useful for dependency graph interpretation, Louvain communities, SLOC, method count, fan-in, and fan-out review.

## Planned Workflow Families

- Language-specific dependency graphs with dependency-cruiser, Madge, and pydeps.
- Code size and complexity diagnostics with lizard, radon, cloc, scc, or tokei.
- GitHub workflow hygiene checks with actionlint and zizmor.
- Supply-chain and repo-health workflows with Scorecard, CodeQL, Dependency Review, OSV, Trivy, SBOM generation, Gitleaks, and Harden Runner.
- Documentation and link-health checks with lychee and markdownlint.

## Safety Notes

Do not add secrets, private URLs, customer names, internal repo lists, or private generated artifacts to this public repository. Keep repo-specific rollout state in the target repo, Linear, or a private internal dashboard.
