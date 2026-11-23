# DSH (DeepSeek Harness) Latest Changes

English | [简体中文](zh-CN/dsh.md) · **Highlight** | [Full Detail](full/dsh.md)

> See [dsh/README.md](dsh/README.md) for the five-platform index (`mac`, `win`, `ubuntu`, `ios`, `android`) covering DeepSeek Harness (`@deepseek-ai/dsh` CLI/Web & `@deepseek-ai/dsh-desktop`, currently tracking prerelease `0.2.3-alpha.2`).

## 0.2.3-alpha.2 — Prerelease (2026-11-22)

Prerelease (`dsh-v0.2.3-alpha.2`, official GitHub Release `published_at`: `2026-11-22 19:00:39 UTC+8` / `2026-11-22T11:00:39Z` UTC; git merge commit `4b399c39a6d` at `2026-11-22 16:50:28 UTC+8`) succeeding `dsh-v0.2.3-alpha.1` (`2026-11-22`). See [dsh/2026-11-22_0.2.3-alpha.2.md](dsh/2026-11-22_0.2.3-alpha.2.md) for exact Node.js range semantics, enforcement boundaries, and migration guidance, or [full/dsh/2026-11-22_0.2.3-alpha.2.md](full/dsh/2026-11-22_0.2.3-alpha.2.md) for full technical details. _(Read-only git tag diff and official Release metadata only; no runtime execution or build/test verification.)_

### Highlights

- **Raised Node.js Requirement to `^24.22.3 || >=26.13.1` (`1` Upgrade Guide)**: Raises `engines.node` from `>=24.9.0` to `^24.22.3 || >=26.13.1` in root `package.json` and `@deepseek-ai/dsh` (`apps/cli/package.json`) to require the November 2026 `undici` security fixes—allowing `24.x >= 24.22.3` (not strict `==24.22.3`) and `>=26.13.1` (including `27+` under semver, though CI only tests `24.22.3`, latest `24`, and floating `26`), while excluding `<24.22.3`, all `25.x`, and `26.0.0`–`26.13.0`. Declared as manifest metadata without `engine-strict` or CLI startup blocking; strict `=== '24.22.3'` applies only to the CI `DSH_NODE_COMPAT_BUILD=1` gate and bundled primary-runtime / Python single-file exe builds.
- **Aligned `undici` Overrides, Electron `^44.11.5`, Bundled Node `24.22.3` & Vendor Alpha Bumps**: Pins `undici` overrides (`6.29.1` / `7.30.2` / `8.12.4`) and direct deps (`8.12.4`), bumps Desktop Electron `^44.7.0` → `^44.11.5` (embedding Node `24.22.3`) with `node-addon-require-builtin ^0.1.10`, locks primary-runtime and Python SDK single-file executables to Node `24.22.3`, and bumps 9 internal vendor packages to `*-alpha.1`. No user-facing UI, CLI, protocol, or feature changes over `0.2.3-alpha.1`.

---

## Prior Prerelease: 0.2.3-alpha.1 (2026-11-22)

Prerelease (`dsh-v0.2.3-alpha.1`, official GitHub Release `published_at`: `2026-11-22 11:19:36 UTC+8` / `2026-11-22T03:19:36Z` UTC; git merge commit `d98f5d68519` at `2026-11-22 00:45:52 UTC+8`; covers `alpha.1` only, not npm `alpha.2`) succeeding `dsh-v0.2.2-rc.5` (`2026-11-18`). See [dsh/2026-11-22_0.2.3-alpha.1.md](dsh/2026-11-22_0.2.3-alpha.1.md) for highlights, gating/platform boundaries, and security migrations, or [full/dsh/2026-11-22_0.2.3-alpha.1.md](full/dsh/2026-11-22_0.2.3-alpha.1.md) for full technical details. _(Read-only git tag diff and official Release metadata only; no runtime execution or live OAuth/billing verification.)_

### Highlights

- **Connector Accounts, MCP OAuth & Seven Standalone Optional Connectors**: Adds unified Plugins-page connector account management, explicit MCP OAuth with background refresh, opt-in on-demand MCP tool loading, shared CLI account/upstream skill services, and 7 standalone optional connector plugins (**Linear**, **Notion**, **Tencent Docs**, **Feishu**, **WeCom**, **Tencent Meeting**, **DingTalk**; **Feishu** and **WeCom** support macOS & Windows `x64` only; none are pre-enabled).
- **Web Remote Login, Pairing & Session Surfaces**: Web mode adds **Settings → Remote connection** (one-use QR login, tokenized links, owner-approved browser pairing; omitted in Desktop window), pluggable `connection.authentication` providers, default-authenticated `webServer` routes (`auth: 'required'`), and a 17-authority per-hostname cookie cap; Web & Desktop gain a dockable drag-to-reorder **Session status panel** and Host-shared **read/unread** session status.
- **Experimental Git Plugin Sources, Timeline & Code Review / GitLab**: Under optional experimental bundles (all **OFF by default**), adds Git repository plugin sources (incl. private repos via Host Git/SSH credentials), an experimental **Timeline** plugin (task trees, blockers, clickable progress bar, timed model-billed reports, Follow chat language), a **Code review** page (GitHub PRs via Host `gh` CLI), forge extension seams (lenses, line annotations, custom slots), and Session-bound **GitLab** MR review/merge via Host `glab` CLI.
- **Security & Runtime Migrations (`55` New + `2` Updated Upgrade Guides)**: Tightens `workspace-write` to live Session `cwd` (removing `working_directory` and subagent `cwd`, switching worktrees to `enter_worktree`/`exit_worktree`, requiring extra authorization for `.git` writes in linked worktrees, and running archive cleanup outside read-only sandboxes); unifies DeepSeek auth under `ctx.deepseekAuth` (relabeling API-key provider to **DeepSeek API** while preserving `rc.5`'s server-side search billing boundary—no per-search call fee, still consumes auxiliary model tokens); upgrades Cordis Core to `4.0.0-rc.12` + `cordis_inspect` default in Standard mode; switches Node PTC to persistent scoped REPL by default and **removes Python PTC**; adds experimental Windows Computer Use, `cua-mcp`, and `cua_run_code` (when CUA is enabled); enables Personalized recommendations by default; consolidates `/office` + `pypdf`; and adds opt-in experimental SQLite session storage (JSONL remains default).

---

## Prior Prerelease: 0.2.2-rc.5 (2026-11-18)

Prerelease (`dsh-v0.2.2-rc.5`, official GitHub Release `published_at`: `2026-11-18 20:51:39 UTC+8` / `2026-11-18T12:51:39Z` UTC; git merge commit `9c2670d3bce` at `2026-11-18 17:45:47 UTC+8`) succeeding `dsh-v0.2.2-rc.4` (`2026-11-18 UTC+8`). See [dsh/2026-11-18_0.2.2-rc.5.md](dsh/2026-11-18_0.2.2-rc.5.md) for highlights, routing/fallback/billing boundaries, and migration notes, or [full/dsh/2026-11-18_0.2.2-rc.5.md](full/dsh/2026-11-18_0.2.2-rc.5.md) for full technical details. _(Read-only git tag diff and official Release metadata only; no runtime execution or live billing verification.)_

### Highlights

- **Route-Based Automatic Web Search Default & Settings Rename** _(Official: "DeepSeek models use DeepSeek server-side search with no per-search charge; other models default to DeepSeek Search API")_: Unsets `web.searchProvider` in `dsh-base` so **Automatic** (`自动选择`) prefers **DeepSeek server-side search** (`deepseek-official`, renamed across 8 locales from **DeepSeek (legacy)**) strictly on the `'deepseek-official'` and `'deepseek-account'` LLM provider routes, and **DeepSeek Search API** (`deepseek-search-api`) on all other routes (including custom-routed DeepSeek models) and non-model calls, with local `available()` single-provider fallthrough only and zero runtime fallback (`1` custom-gateway upgrade-guide entry; server-side search waives per-call fees per official copy but still consumes auxiliary model tokens).
- **Inline `snippet` Extraction in DeepSeek Server-Side Search**: `@deepseek-ai/dsh-web-search-deepseek` now extracts inline `web_search_result.snippet` excerpts before falling back to `text`-block `citations[].cited_text`, preserving result snippets when `/anthropic/v1/messages` returns text blocks without `citations`.

---

## Prior Prerelease: 0.2.2-rc.4 (2026-11-18, UTC+8)

Prerelease (`dsh-v0.2.2-rc.4`, official GitHub Release `published_at`: `2026-11-18 01:53:41 UTC+8` / `2026-11-17T17:53:41Z` UTC; git merge commit `3f321d32bfe` at `2026-11-17 21:30:09 UTC+8`) succeeding `dsh-v0.2.2-rc.3` (`2026-11-13`). See [dsh/2026-11-18_0.2.2-rc.4.md](dsh/2026-11-18_0.2.2-rc.4.md) for highlights, official-vs-source comparison, fixes, and breaking changes, or [full/dsh/2026-11-18_0.2.2-rc.4.md](full/dsh/2026-11-18_0.2.2-rc.4.md) for full technical details. _(Read-only git tag diff only; not runtime-executed.)_

### Highlights

- **DeepSeek Stream Content-Safety Refusal `CONTENT_REFUSED` & Billed Usage Reporting** _(Official: "Improve handling of unexpected model responses")_: Streamed DeepSeek Messages responses ending with `stop_reason: "refusal"` now yield billed pre-refusal token usage and fail with the non-retryable `CONTENT_REFUSED` code (preserving `stop_details.explanation`, withdrawing the Web draft, and retaining the attempt outside model history) instead of throwing `MALFORMED_RESPONSE` mid-delta (`1` SDK/event upgrade-guide entry; no outgoing `safety_check` request field added).
- **Desktop LiveShare Tunnel Worker `ELECTRON_RUN_AS_NODE` Forwarding** _(Official: "Fix LiveShare failing to create shares in the desktop app")_: Forwards `ELECTRON_RUN_AS_NODE` when `@deepseek-ai/dsh-experimental-liveshare` spawns its owner-gateway worker (`process.execPath`) so the `mac` / `win` Electron Desktop shell runs the worker in Node mode rather than terminating it as a duplicate GUI instance under the single-instance lock, plus a wall-clock fix for `owner-credential-horizon.host.spec.ts`.

---

## Prior Prerelease: 0.2.2-rc.3 (2026-11-13)

Prerelease (`dsh-v0.2.2-rc.3`, `2026-11-13 13:26:07 UTC+8`) succeeding `dsh-v0.2.2-rc.2` (`2026-11-11`). See [dsh/2026-11-13_0.2.2-rc.3.md](dsh/2026-11-13_0.2.2-rc.3.md) for highlights, new features, fixes, and breaking changes, or [full/dsh/2026-11-13_0.2.2-rc.3.md](full/dsh/2026-11-13_0.2.2-rc.3.md) for full technical details.

### Highlights

- **DeepSeek Website Chat Export Importer (Experimental Plugin)**: Added an optional experimental plugin ("DeepSeek chat import", enabled under **Plugins → More → Experimental plugins**) that places an upload button right of **New session** to import `deepseek_data-*.zip` exports from `chat.deepseek.com` as native, resumable DSH Sessions in a chosen Workspace—preserving titles, timestamps, reasoning traces, web search/fetch cards, read links, and image attachments across 8 UI languages, alongside a new `sidebar.session.action` slot and reusable `workspace.picker` menu factory.
- **Resilient Session Log ZIP Exports**: Exporting a session log as a ZIP archive now records deleted, synthetic, or invalid attachment references in `attachments-missing.txt` instead of aborting the entire download, and cleanly closes open file streams on early cancellation.
- **Windows Update Directory Lock & CI Sandbox Fixes**: Fixed the Windows NSIS update-restart status window locking the installation directory during upgrades, cached SHA-256-verified `bubblewrap` archives with bounded downloads in Linux CI, and introduced **no breaking changes** over `0.2.2-rc.2`.
