# DSH (DeepSeek Harness) Changelog History

English | [简体中文](../zh-CN/dsh/README.md) · **Highlight** | [Full Detail](../full/dsh/README.md)

Multi-platform version history for **DSH (DeepSeek Harness)** (`@deepseek-ai/dsh` CLI/Web & `@deepseek-ai/dsh-desktop`, `https://github.com/deepseek-ai/deepseek-harness`) across `mac`, `win`, `ubuntu`, `ios`, and `android`, currently covering **3** analyzed prereleases (`0.2.2-rc.3` – `0.2.2-rc.5`, 2026-11-13 to 2026-11-18).

## Five-Platform Coverage Overview

| Platform | Distribution / Package | Tracked Releases | Version Range | Latest Version |
|---|---|---|---|---|
| `mac` | macOS (`@deepseek-ai/dsh` npm CLI/Web & `@deepseek-ai/dsh-desktop` `mac-arm64` / `mac-x64`) | 3 | `0.2.2-rc.3` – `0.2.2-rc.5` | [0.2.2-rc.5](2026-11-18_0.2.2-rc.5.md) (prerelease) |
| `win` | Windows (`@deepseek-ai/dsh` npm CLI/Web & `@deepseek-ai/dsh-desktop` `win-x64` NSIS) | 3 | `0.2.2-rc.3` – `0.2.2-rc.5` | [0.2.2-rc.5](2026-11-18_0.2.2-rc.5.md) (prerelease) |
| `ubuntu` | Ubuntu / Linux (`@deepseek-ai/dsh` npm CLI/Web) | 3 | `0.2.2-rc.3` – `0.2.2-rc.5` | [0.2.2-rc.5](2026-11-18_0.2.2-rc.5.md) (prerelease) |
| `ios` | Standalone DSH iOS Client | 0 | _No standalone mobile release tracked_ | — |
| `android` | Standalone DSH Android Client | 0 | _No standalone mobile release tracked_ | — |

## Desktop & CLI/Web Version Index (`mac` / `win` / `ubuntu`, Newest → Oldest)

| Version | Platforms | Release Date | Highlights |
|---|---|---|---|
| [0.2.2-rc.5](2026-11-18_0.2.2-rc.5.md) _(prerelease)_ | `mac`, `win`, `ubuntu` | 2026-11-18 | **Automatic** web search default routes `deepseek-official` / `deepseek-account` conversations to **DeepSeek server-side search** (renamed across 8 locales from **DeepSeek (legacy)**; no per-search call fee per official copy, billed as auxiliary model tokens) and other routes/non-model calls to **DeepSeek Search API**, extracts inline `web_search_result.snippet` excerpts, and adds `1` custom-gateway upgrade-guide entry |
| [0.2.2-rc.4](2026-11-18_0.2.2-rc.4.md) _(prerelease)_ | `mac`, `win`, `ubuntu` | 2026-11-18 (UTC+8) | Streamed DeepSeek `stop_reason: "refusal"` reports billed usage then non-retryable `CONTENT_REFUSED` (with `stop_details.explanation`, Web draft withdrawal, and `1` SDK/event upgrade-guide change from `MALFORMED_RESPONSE`), and Desktop LiveShare owner-gateway worker forwards `ELECTRON_RUN_AS_NODE` so Electron's single-instance lock no longer aborts share registration |
| [0.2.2-rc.3](2026-11-13_0.2.2-rc.3.md) _(prerelease)_ | `mac`, `win`, `ubuntu` | 2026-11-13 | Experimental DeepSeek website chat export importer (`deepseek_data-*.zip` → resumable Workspace Sessions across 8 locales), `sidebar.session.action` slot & reusable `workspace.picker` factory, resilient Session ZIP export (`attachments-missing.txt` + stream cleanup), Windows NSIS update-restart directory lock fix, and verified CI `bubblewrap` caching (no breaking changes) |
