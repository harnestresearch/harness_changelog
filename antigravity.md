# Antigravity Latest Changes

English | [简体中文](zh-CN/antigravity.md) · **Highlight** | [Full Detail](full/antigravity.md)

> See [antigravity/README.md](antigravity/README.md) for the five-platform index (`mac`, `win`, `ubuntu`, `ios`, `android`) covering both Antigravity desktop tracks: **Antigravity Desktop (`antigravity-hub`, `2.32.2`)** and **Antigravity IDE (`2.7.0`)**.

## Antigravity Desktop (Hub) 2.32.2 (2026-11-17, Package `Last-Modified`)

See [antigravity/2026-11-17_2.32.2.md](antigravity/2026-11-17_2.32.2.md) for highlights, or [full/antigravity/2026-11-17_2.32.2.md](full/antigravity/2026-11-17_2.32.2.md) for full technical details.

### Highlights

- **Maintenance Point Build with Unchanged Desktop Shell & MCP Toolset**: Across all `1,068` extracted files (`18,668,119` B) in the Electron `44.9.1` desktop shell (`app.asar`), only the `package.json` version string changes (`2.32.1` → `2.32.2`), and bundled `chrome-devtools-mcp` `1.9.0` (`app.asar.unpacked`) has zero file changes—carrying forward all [2.32.1](antigravity/2026-11-14_2.32.1.md) and [2.32.0](antigravity/2026-11-13_2.32.0.md) features below.
- **Backend Recompile with Internal Telemetry Symbol Tweaks Only**: Recompiles the Go `language_server` (`cl/1021296516` → `cl/1022991777`) on official `darwin-arm` dual DMGs (with `linux-x64` same-build/LS spot-checks and `windows-x64` spot-checks—not a full three-platform static diff), showing zero changes across extracted UI strings, `9` `gemini-4-*` model tier strings, `376` RPC prefix matches, `189` flag pairs, or `65` `*ToolConfig` entries, and only internal telemetry CEL timeout helper and `Shutdown` closure symbol changes (static recompilation observations only; no functional bugfix or full-user rollout is claimed).

---

## Prior Hub Patch: 2.32.1 (2026-11-14)

See [antigravity/2026-11-14_2.32.1.md](antigravity/2026-11-14_2.32.1.md) for highlights, or [full/antigravity/2026-11-14_2.32.1.md](full/antigravity/2026-11-14_2.32.1.md) for full technical details.

### Highlights

- **Built-in `Gemini 4 Hydrogen` Default Model Tiers**: Added **Gemini 4 Hydrogen** (`low`, `medium`, and `high` reasoning effort tiers, e.g. `Gemini 4 Hydrogen (High)`) to the built-in default model catalog alongside the existing `Gemini 4 Argon` and `Gemini 4 Carbon` model presets.
- **Next-Day Patch Build Preserving All `2.32.0` Features**: Ships a refreshed backend build with a byte-identical Electron `44.9.1` desktop shell and bundled MCP toolset vs. `2.32.0`, carrying forward all [2.32.0](antigravity/2026-11-13_2.32.0.md) additions below.

---

## Recent Major Hub Release: 2.32.0 (2026-11-13)

See [antigravity/2026-11-13_2.32.0.md](antigravity/2026-11-13_2.32.0.md) for highlights, or [full/antigravity/2026-11-13_2.32.0.md](full/antigravity/2026-11-13_2.32.0.md) for full technical details.

### Highlights

- **Dynamic Workflows with Bundled Python Runtime**: Officially launched **Dynamic Workflows**, enabling agents to orchestrate parallel subagents and multi-step execution pipelines in Python using the standalone Python runtime bundled with the app.
- **Everforest Themes & Prompt Navigation Shortcuts**: Added **Everforest Light** and **Everforest Dark** low-contrast themes under `Settings > Appearance`, keyboard shortcuts to jump between previous and next prompts from the composer or reading view, an optional customizable **Submit Prompt** shortcut under `Settings > Shortcuts`, and fixed a `Pin Conversation` shortcut conflict with Chrome tab groups on Linux.
- **Stronger Built-in Browser Tab Protections & Compatibility**: Cross-site subframes inside agent-controlled browser tabs now load signed out (stripping cross-site credentials) and remain hidden from agent screenshots and snapshots unless explicitly allowed and targeted; extended navigation blocking to protected sign-in pages alongside payment pages; added agent notifications and download-drawer status indicators for file-type-blocked downloads; and stripped the `Electron` User-Agent token (preserving Google Sign-In compatibility) so websites no longer block the built-in browser.
- **Sign-In Fallback, Cloud GitHub Cloning & UX Refinements**: Added copyable sign-in links and one-time authorization code paste fallback when automatic browser redirects do not complete, local workspace cloning for Cloud GitHub repositories and direct PR link sign-in for remote agents, height-adaptive model selector menus with a **Refresh** button on load failure, MCP server startup error surfacing on plugin cards, and host sandbox-unavailability explanations in permission menus.
- **Desktop Process Cleanup, CJK Font Weight & Stability Fixes (13 Fixes)**: Replaced the login-shell environment reader so quitting the app cleanly terminates background `language_server` processes on `SIGTERM`, hardened settings saves against temporary file locks, and fixed CJK bold text rendering at regular weight, long-conversation scroll stalls, conversation-revert toolbar flicker, draft/queue list flattening, full-page plugin tab resets after restart, and Google Drive `@` mention sign-in—alongside flag-gated SSH remote (`--ssh-host`), desktop Computer Use, and three-layer guest webview foundations.

---

## Antigravity IDE 2.7.0 (Release Date Unconfirmed; Built 2026-11-11)

See [antigravity/2026-11-11_ide-2.7.0.md](antigravity/2026-11-11_ide-2.7.0.md) for highlights, or [full/antigravity/2026-11-11_ide-2.7.0.md](full/antigravity/2026-11-11_ide-2.7.0.md) for full technical details. _(Release time is unconfirmed; `2026-11-11 12:46` UTC+8 in `product.json` is the build time, not the release time.)_

### Highlights

- **Sign-In Status Bar & Cross-Window Auth Sync**: Upgraded the status bar button to an authentication-aware indicator (one-click sign-in when signed out, quick status menu when signed in), added Sign In / Sign Out commands, synchronized authentication state across open IDE windows, and added Google Cloud / enterprise Terms-of-Service tracking.
- **Current-File vs. All-Files Diff Actions & Terminal Shortcuts**: Clarified inline/side-by-side diff actions as applying to the **Current File**, added standalone **Accept All Changes** and **Reject All Changes** commands across **All Files**, added new conversation, chat focus, and insert-terminal-output commands, and split `Ctrl+L` / `Ctrl+Alt+L` terminal shortcuts.
- **Expanded Agent Bridge & Cloud Workstation CLI Detection**: Expanded the webview bridge for background task management (`ManageTask`), media processing, and browser recording; automatically reuses pre-installed `/usr/bin/agy` binaries in Google Cloud Workstations and Cloud Shell, retries on local hub port collisions, and identifies Antigravity IDE in one-click feedback.

---

## Antigravity Desktop (Hub) 2.31.2 (2026-11-12)

See [antigravity/2026-11-12_2.31.2.md](antigravity/2026-11-12_2.31.2.md) for highlights, or [full/antigravity/2026-11-12_2.31.2.md](full/antigravity/2026-11-12_2.31.2.md) for full technical details.

### Highlights

- **In-Page WebMCP Tool Discovery in the Built-in Browser**: Added a Guest WebMCP bridge enabling Antigravity Hub to discover, invoke, and cancel structured tools declared directly by live web pages over HTTPS or localhost—protected by a 30s default timeout (1s–120s range), a 64 KiB output cap, zero script injection into guest pages, and automatic blocking on payment and identity-provider sites (such as Stripe, PayPal, Adyen, and Google Pay).
- **Native Multi-Agent Swarm Collaboration**: Replaced the legacy single-tool swarm template with a dedicated native Swarm toolset for managing parallel workers, posting updates to a shared message board, reading recent or mentioned messages, and waiting on or joining collaborative work.
- **Direct Remote MCP OAuth Sign-In**: Added one-step OAuth sign-in support for remote MCP servers alongside existing plugin authentication and custom local/remote MCP server configurations (`~/.gemini/config/mcp_config.json`).
- **Plan-Execute Transitions, Persistent Terminals & Notebook Execution**: Added explicit plan-mode enter/exit transitions and focus tracking, persistent terminal execution that preserves working environment and shell variables across turns (with configurable notification timeouts), and dedicated Jupyter notebook cell editing and execution tools.
- **Local DevTools Port Hardening & Safety Pre-Screening**: Tightened local filesystem permissions on the user data directory (`0700`) and active browser debugging port file (`0600`), upgraded the Electron desktop runtime, broadened Playwright Node detection in the fallback browser-tool launcher, and added a lightweight model-assisted threat pre-screener in log mode alongside the read-only tool and command allowlist.
