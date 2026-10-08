# techflosdev/.github

Organization template hub for **[techflows](https://www.techflows.app/)** (`techflosdev`).

## What lives here

| Path | Purpose |
| --- | --- |
| `profile/README.md` | Public org profile (GitHub org README) |
| `CODE_OF_CONDUCT.md`, `CONTRIBUTING.md`, `SECURITY.md`, `SUPPORT.md` | Default community health files for org repos |
| `.github/ISSUE_TEMPLATE/`, `.github/PULL_REQUEST_TEMPLATE.md` | Default issue / PR templates |
| `.github/workflows/ci.yml` | **Reusable** CI workflow (`workflow_call`) |
| `.github/workflows/pr-auto-assign.yml` | Request review from `@techflosdev/maintainers` |
| `.github/workflows/labeler.yml` + `labeler.yml` | Path-based PR labels |
| `.github/workflows/stale.yml` | Stale issues/PRs |
| `.github/dependabot.yml` | Dependabot sample (Actions + commented ecosystems) |
| `CODEOWNERS` / `.github/CODEOWNERS` | `@techflosdev/maintainers` |

Community health files and issue/PR templates are **auto-applied** by GitHub to organization repositories that do not define their own. Workflows are **not** auto-copied — product repos should call the reusable CI or copy the sample workflows.

## Consume reusable CI

```yaml
jobs:
  ci:
    uses: techflosdev/.github/.github/workflows/ci.yml@main
    with:
      run-lint: true
      run-test: true
      node-version: "20"
      # lint-command: npm run lint   # TODO: real command
      # test-command: npm test      # TODO: real command
```

See [CONTRIBUTING.md](./CONTRIBUTING.md) for full guidance.

## Teams

- [@techflosdev/maintainers](https://github.com/orgs/techflosdev/teams/maintainers)
- [@techflosdev/contributors](https://github.com/orgs/techflosdev/teams/contributors)