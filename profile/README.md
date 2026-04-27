# kryptic.sh

Native software tools for people who never left the terminal. Vim-shaped,
Rust-built, no Electron, no JVM.

Hub: <https://www.kryptic.sh/>.

## Projects

- **[sqeel](https://github.com/kryptic-sh/sqeel)** — vim-native SQL client.
  Terminal or GUI, MySQL / Postgres / SQLite, tree-sitter highlighting,
  LSP-aware completion + diagnostics, full vim engine including soft-wrap and
  folding. _0.1.0, live on crates.io — `cargo install sqeel`._
  <https://sqeel.kryptic.sh/>
- **[buffr](https://github.com/kryptic-sh/buffr)** — vim-inspired browser.
  Native, GPU-accelerated. Rust + CEF. _Early (0.0.1) — scaffold + config +
  hot-reload CLI + permission prompts._ <https://buffr.kryptic.sh/>
- **[hjkl](https://github.com/kryptic-sh/hjkl)** — vim-modal terminal editor +
  the vim engine, rope buffer, and editor primitives behind it. `no_std + alloc`
  core. Powers sqeel, buffr, and inbx from one shared FSM. _0.3.0 — multi-buffer
  editing, fuzzy file/buffer/grep pickers, tree-sitter highlighting + comment
  markers, smart indent, `.editorconfig`. `cargo install hjkl`._
  <https://hjkl.kryptic.sh/>
- **[inbx](https://github.com/kryptic-sh/inbx)** — modal-vim email client.
  IMAP/SMTP, Gmail XOAUTH2, Microsoft Graph, JMAP (incl. SSE push). Maildir +
  SQLite + tantivy. CardDAV. _Beta — working CLI + TUI + GUI._
  <https://inbx.kryptic.sh/>
- **[hodl](https://github.com/kryptic-sh/hodl)** — light crypto wallet, TUI.
  ratatui UI, BIP-39 seed, BIP-32/44 derivation. Multi-chain (Bitcoin, Ethereum,
  BSC, Monero, Navio, plus major BTC forks). Local keys, encrypted at rest.
  Never phones home. _Early scaffold._ <https://hodl.kryptic.sh/>

## Principles

- **Native Rust.** No JVM, no Electron, no webview wrappers.
- **Vim-shaped.** Modal editing, operators, text objects, marks — first class,
  not a plugin.
- **Mouse + keyboard.** Both work, always. Mode shouldn't dictate input.
- **One engine, many surfaces.** `hjkl` drives the modal layer across every
  project — same FSM, TUI or GUI or browser.
- **No telemetry. No analytics. No "experiences."** Just tools.

## Status

hjkl is at 0.3.0 — standalone editor binary plus 9 crates on crates.io. SPEC
frozen since 0.1.0; sqeel + buffr + inbx all run on it from the registry. sqeel
shipped 0.1.0. inbx is in beta — CLI + TUI + GUI all working. buffr and hodl are
early scaffolds. Expect breakage on 0.0.x projects. Issues + PRs welcome on each
repo.

## License

MIT across the board.
