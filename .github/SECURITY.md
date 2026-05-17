# Security Policy

This policy applies to all repositories under the
[`kryptic-sh`](https://github.com/kryptic-sh) organization unless a repository
defines its own `SECURITY.md`.

## Supported versions

Unless a repository states otherwise, only the **latest released version**
receives security fixes. Pre-1.0 projects support the latest patch of the
current minor only.

## Reporting a vulnerability

**Do not open a public GitHub issue for security reports.**

Email `mxaddict@kryptic.sh` with:

- Affected repository and version(s)
- Description of the issue and impact
- Reproduction steps or proof-of-concept
- Disclosure timeline preference

Acknowledgment within 72 hours. Coordinated disclosure window is typically 30
days from acknowledgment, extendable for complex issues.

## Dependencies

CI runs supply-chain audits (`cargo deny`, `npm audit`, equivalent) on a cron
schedule. Vulnerable transitive dependencies trigger an issue automatically.

## Scope

Security policy covers code in the repository itself. Issues in upstream
dependencies should be reported to the upstream maintainer; cross-post here only
if a kryptic-sh project is the primary attack vector.
