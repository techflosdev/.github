# Security Policy

## Supported versions

Security updates are applied to the **latest release** of each actively maintained techflows project unless a repository states otherwise in its own `SECURITY.md`.

| Support | Status |
| --- | --- |
| Latest tagged release | Supported |
| `main` / default branch | Supported for reporting; fixes land here first |
| Older releases | Best-effort; please upgrade when possible |

## Reporting a vulnerability

**Please do not open a public issue for security vulnerabilities.**

Report privately using one of these channels (preferred order):

1. **GitHub Private Vulnerability Reporting** — on the affected repository, use **Security → Report a vulnerability** (enabled where available).
2. **Email**: [security@techflows.app](mailto:security@techflows.app) with:
   - Repository / component name
   - Description of the issue and impact
   - Steps to reproduce or a proof-of-concept (if safe to share)
   - Affected versions / commit SHAs if known
   - Your preferred contact and disclosure timeline

We aim to **acknowledge** reports within **3 business days** and to provide an initial assessment within **7 business days**.

## Disclosure process

1. We confirm receipt and assign a maintainer.
2. We investigate and, if needed, request more detail privately.
3. We prepare a fix on a private branch when possible.
4. We coordinate disclosure timing with the reporter (we prefer coordinated disclosure after a fix or mitigation is available).
5. We publish an advisory / release notes and credit the reporter unless they request anonymity.

## Scope

In scope: vulnerabilities in techflows-owned repositories under [@techflosdev](https://github.com/techflosdev), official packages, and infrastructure we operate for those projects.

Out of scope (examples): social engineering against third parties, DoS against shared public infrastructure without a clear product bug, reports against dependencies with no actionable path in our code (please report upstream when appropriate), and issues that require physical access or already-compromised credentials with no product defect.

## Safe harbor

We will not pursue legal action against researchers who:

- Make a good-faith effort to avoid privacy violations, destruction of data, and interruption of service
- Do not exploit the vulnerability beyond what is necessary to demonstrate it
- Report findings promptly and keep details confidential until we have addressed them
- Do not access data that is not their own beyond what is required to demonstrate the issue

## Security contacts

- Maintainers team: [@techflosdev/maintainers](https://github.com/orgs/techflosdev/teams/maintainers)
- Email: security@techflows.app
- Website: [https://www.techflows.app/](https://www.techflows.app/)