# Contributing to kryptic-sh

Default contribution guide for all repositories under
[`kryptic-sh`](https://github.com/kryptic-sh). Repositories may override with
their own `CONTRIBUTING.md` for project-specific dev setup, release flow, or
testing tools.

Thanks for considering a contribution. Most kryptic-sh projects are pre-1.0 —
please open an issue before starting any non-trivial PR so the design can be
sanity-checked early.

## Pull requests

- Branch from `main`. One logical change per PR.
- Commits follow [Conventional Commits](https://www.conventionalcommits.org/):
  `type(scope): message`. Types: `feat`, `fix`, `docs`, `style`, `refactor`,
  `test`, `chore`, `perf`, `ci`, `build`. Scope optional.
- Keep the PR description focused on the **why**. The diff shows the what.
- Run the project's formatter and linter before pushing.

## Rust projects

Before pushing:

```bash
cargo fmt
cargo clippy --all-targets --all-features -- -D warnings
cargo test --all-features
```

- New public API needs rustdoc and (where applicable) a `///` example.
- MSRV: `rust-version` in `Cargo.toml` tracks current stable. Floor, not ceiling
  — bumps land freely when useful. Any bump goes in `CHANGELOG.md` under the
  version that introduces it.
- Performance-sensitive changes: include a criterion bench under
  `crates/<crate>/benches/` where applicable.

## Node / TypeScript projects

Before pushing:

```bash
npm run format    # prettier
npm run lint
npm test
```

Match the package manager already in use (`npm`, `pnpm`, or `yarn`) — do not mix
lockfiles.

## Releases — BCTP

Cutting a release follows the **BCTP** flow:

1. **B**ump patch in the project's manifest (`Cargo.toml`, `package.json`,
   `pyproject.toml`, etc). Regenerate lockfiles.
2. **C**ommit version bump with message `chore: bump version`. Stage only
   manifest, lockfile, and changelog.
3. **T**ag commit as `vX.Y.Z`.
4. **P**ush commit and tag.

Tags trigger the release workflow (`release.yml`) which publishes to the
appropriate registry (crates.io, npm, etc).

Patch for bug fixes / docs; minor for additive public API; major for breaking
changes.

To yank a broken Rust release:

```bash
cargo yank --version X.Y.Z -p <crate>
```

Document the reason in `CHANGELOG.md` under a `### Yanked` heading.

## Snapshot tests

Projects using [`insta`](https://insta.rs/) keep golden files under
`tests/snapshots/`. After intentional output changes:

```bash
INSTA_UPDATE=always cargo test
# or, interactively:
cargo insta review
```

Commit the updated `*.snap` files alongside the change.

## Property + fuzz tests

- `proptest` regressions live in `proptest-regressions/`. Commit failing seeds
  so CI replays them.
- `cargo fuzz` harnesses live under each crate's `fuzz/` directory and run on
  cron with the nightly toolchain.

## Reporting bugs / requesting features

Use the issue templates in `.github/ISSUE_TEMPLATE/` where present. For security
issues, see [`SECURITY.md`](SECURITY.md) — do not file public issues.

## Code of Conduct

All projects follow the [Contributor Covenant](CODE_OF_CONDUCT.md).
