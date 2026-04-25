# kryptic.sh

Native software tools for people who never left the terminal. Vim-shaped,
Rust-built, no Electron, no JVM.

## Projects

- **[sqeel](https://github.com/kryptic-sh/sqeel)** — vim-native SQL client.
  Terminal or GUI, MySQL / Postgres / SQLite, tree-sitter highlighting,
  LSP-aware completion + diagnostics, full vim engine including soft-wrap and
  folding.
- **[buffr](https://github.com/kryptic-sh/buffr)** — vim-inspired browser.
  Native, GPU-accelerated. Rust + CEF.

## Principles

- **Native Rust.** No JVM, no Electron, no webview wrappers.
- **Vim-shaped.** Modal editing, operators, text objects, marks — first
  class, not a plugin.
- **Mouse + keyboard.** Both work, always. Mode shouldn't dictate input.
- **One codebase, multiple shells.** Terminal and GUI from the same core
  where it makes sense.
- **No telemetry. No analytics. No "experiences."** Just tools.

## Status

Early on every project. Expect breakage. Issues + PRs welcome on each repo.

## License

MIT across the board.
