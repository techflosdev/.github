# Contributing to techflows

Thanks for contributing to **techflows** (`techflosdev`). This guide covers org-wide expectations. Individual repositories may add project-specific steps in their own `CONTRIBUTING.md` or README.

## Code of Conduct

Participation is governed by our [Code of Conduct](./CODE_OF_CONDUCT.md). Be respectful and constructive.

## Ways to contribute

- Report bugs and propose features (use issue templates)
- Improve documentation
- Submit pull requests (fixes, features, tests, CI)
- Review PRs and help triage issues
- Improve security posture (see [SECURITY.md](./SECURITY.md))

## Development workflow

1. **Find or open an issue** — discuss larger changes before coding.
2. **Fork** (external) or branch from `main` (members).
3. **Create a focused branch**: `fix/short-description`, `feat/...`, `docs/...`, `chore/...`.
4. **Keep PRs small** — one concern per PR when practical.
5. **Open a pull request** early (draft is fine) using the PR template.
6. **Respond to review** from `@techflosdev/maintainers` and CI.

### Commit messages

Prefer [Conventional Commits](https://www.conventionalcommits.org/)-style subjects:

- `feat: add widget export`
- `fix: handle empty token response`
- `docs: clarify install steps`
- `chore: bump actions versions`

### Signing commits

Org maintainers committing as **vyrnsynx** should sign commits (SSH signing key). Verified commits are preferred on protected branches.

## Pull request checklist

- [ ] Linked to an issue when applicable
- [ ] Tests or manual verification notes included
- [ ] Docs / changelog updated if user-facing
- [ ] No secrets committed; `.env` and keys stay local
- [ ] CI green (or failures explained)

## Using the org reusable CI workflow

Product repositories can call the reusable workflow published from this hub:

**Workflow file:** [`ci.yml`](./.github/workflows/ci.yml)  
**Caller reference:** `techflosdev/.github/.github/workflows/ci.yml@main`

### Example caller (Node / npm placeholder)

Create `.github/workflows/ci.yml` in your product repo:

```yaml
name: CI

on:
  push:
    branches: [main]
  pull_request:
  workflow_dispatch:

permissions:
  contents: read

jobs:
  ci:
    uses: techflosdev/.github/.github/workflows/ci.yml@main
    with:
      # Pick a language matrix entry; see reusable workflow inputs
      run-lint: true
      run-test: true
      node-version: "20"
      # TODO: set package-manager and scripts to match your repo
      # package-manager: npm
      # lint-command: npm run lint
      # test-command: npm test
```

### Example caller (Python / pytest placeholder)

```yaml
name: CI

on:
  push:
    branches: [main]
  pull_request:

permissions:
  contents: read

jobs:
  ci:
    uses: techflosdev/.github/.github/workflows/ci.yml@main
    with:
      run-lint: true
      run-test: true
      python-version: "3.12"
      # TODO: wire real commands for your project
      # lint-command: ruff check .
      # test-command: pytest -q
```

The reusable workflow ships **safe placeholders** that pass by default (`workflow_dispatch` / demo steps) so template repos stay green. Replace TODO commands with your real `npm` / `pytest` / etc. scripts — do not invent project-specific test commands in this hub.

Pinning a tag or commit SHA instead of `@main` is recommended once your pipeline stabilizes:

```yaml
uses: techflosdev/.github/.github/workflows/ci.yml@v1   # after you tag releases
```

## Path labels & auto-assign

This hub includes:

- **PR auto-assign / review request** → `@techflosdev/maintainers` (see `.github/workflows/pr-auto-assign.yml`)
- **Path-based labeling** → `.github/labeler.yml` + `labeler.yml` workflow
- **Dependabot sample** → `.github/dependabot.yml` (copy into product repos and adjust ecosystems)
- **CODEOWNERS** → `@techflosdev/maintainers` owns `*`

Product repos should copy or adapt `labeler.yml`, `dependabot.yml`, and `CODEOWNERS` as needed. Org default community files (CoC, Contributing, Security, Support, issue/PR templates) apply automatically when a repo does not define its own.

## Labels we use

Common labels (create in each repo or rely on org defaults where configured):

| Label | Purpose |
| --- | --- |
| `bug` | Something broken |
| `enhancement` | New capability or improvement |
| `documentation` | Docs-only |
| `good first issue` | Good for newcomers |
| `dependencies` | Dependency updates |
| `security` | Security-related |
| `needs-triage` | Awaiting maintainer triage |
| `ci` | CI / workflows |
| `breaking-change` | Requires major version bump |

## Review & merge

- Prefer squash merge unless history is intentionally linear and reviewed.
- At least one maintainer review is expected for `main` on protected repos.
- Do not force-push to `main`.

## License

Unless a repository states otherwise, contributions are accepted under that repository's license.

## Questions

See [SUPPORT.md](./SUPPORT.md) or ask in the relevant repository's issues/discussions.