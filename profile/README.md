# kryptic.sh

Native software tools for people who never left the terminal. Vim-shaped,
Rust-built, no Electron, no JVM.

Hub: <https://www.kryptic.sh/>.

## Projects

- **[sqeel](https://github.com/kryptic-sh/sqeel)** — vim-native SQL client.
  Terminal or GUI, MySQL / Postgres / SQLite, tree-sitter highlighting,
  LSP-aware completion + diagnostics, full vim engine including soft-wrap and
  folding. _1.0.0-rc1, live._ <https://sqeel.kryptic.sh/>
- **[buffr](https://github.com/kryptic-sh/buffr)** — vim-inspired browser.
  Native, GPU-accelerated. Rust + CEF. _Early (0.0.1) — scaffold + config +
  hot-reload CLI + permission prompts._ <https://buffr.kryptic.sh/>
- **[hjkl](https://github.com/kryptic-sh/hjkl)** — vim engine, rope buffer,
  modal editor primitives. `no_std + alloc`. Powers sqeel, buffr, and inbx from
  one shared FSM. _0.0.23, pre-1.0 churn toward 0.1.0 trait surface._
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

Pre-1.0 across the board. sqeel is the most mature (release candidate). hjkl is
on the way to 0.1.0; sqeel, buffr, and inbx all run on it. inbx is in beta —
CLI + TUI + GUI all working. buffr and hodl are early scaffolds. Expect
breakage. Issues + PRs welcome on each repo.

## License

MIT across the board.
