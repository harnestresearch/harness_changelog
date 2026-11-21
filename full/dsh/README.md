# DSH (DeepSeek Harness) Changelog History

English | [简体中文](../../zh-CN/full/dsh/README.md) · [Highlight](../../dsh/README.md) | **Full Detail**

Multi-platform technical version history for **DSH (DeepSeek Harness)** (`@deepseek-ai/dsh` CLI/Web & `@deepseek-ai/dsh-desktop`, `https://github.com/deepseek-ai/deepseek-harness`) across `mac`, `win`, `ubuntu`, `ios`, and `android`, currently covering **3** source-diffed prereleases (`0.2.2-rc.3` – `0.2.2-rc.5`, 2026-11-13 to 2026-11-18).

## Five-Platform Coverage Overview

| Platform | Distribution / Package | Tracked Releases | Version Range | Latest Version |
|---|---|---|---|---|
| `mac` | macOS (`@deepseek-ai/dsh` npm CLI/Web & `@deepseek-ai/dsh-desktop` Electron `mac-arm64` / `mac-x64`) | 3 | `0.2.2-rc.3` – `0.2.2-rc.5` | [0.2.2-rc.5](2026-11-18_0.2.2-rc.5.md) (prerelease) |
| `win` | Windows (`@deepseek-ai/dsh` npm CLI/Web & `@deepseek-ai/dsh-desktop` Electron `win-x64` NSIS) | 3 | `0.2.2-rc.3` – `0.2.2-rc.5` | [0.2.2-rc.5](2026-11-18_0.2.2-rc.5.md) (prerelease) |
| `ubuntu` | Ubuntu / Linux (`@deepseek-ai/dsh` npm CLI/Web) | 3 | `0.2.2-rc.3` – `0.2.2-rc.5` | [0.2.2-rc.5](2026-11-18_0.2.2-rc.5.md) (prerelease) |
| `ios` | Standalone DSH iOS Client | 0 | _No standalone mobile release tracked_ | — |
| `android` | Standalone DSH Android Client | 0 | _No standalone mobile release tracked_ | — |

## Desktop & CLI/Web Version Index (`mac` / `win` / `ubuntu`, Newest → Oldest)

| Version | Platforms | Release Date | Key Changes |
|---|---|---|---|
| [0.2.2-rc.5](2026-11-18_0.2.2-rc.5.md) _(prerelease)_ | `mac`, `win`, `ubuntu` | 2026-11-18 | `dsh-v0.2.2-rc.4 → dsh-v0.2.2-rc.5` (`5` commits, `433` files; `53` non-manifest files from PR #8707 + `0`-diff PR #8595 merge): unsets `web.searchProvider` in `dsh-base`, adds `WebSearchRequest.llmProvider` and `DEEPSEEK_MODEL_ROUTES` (`deepseek-official` / `deepseek-account` → `deepseek-official` Messages search; all other routes and non-model calls → `deepseek-search-api`, zero runtime fallback), defaults Web search UI to **Automatic** and renames **DeepSeek (legacy)** → **DeepSeek server-side search** across 8 locales, extracts inline `WebSearchResultItem.snippet`, and adds `1` `docs/upgrade-guide` entry for custom-gateway `web-search-deepseek.baseURL` setup |
| [0.2.2-rc.4](2026-11-18_0.2.2-rc.4.md) _(prerelease)_ | `mac`, `win`, `ubuntu` | 2026-11-18 (UTC+8) | `dsh-v0.2.2-rc.3 → dsh-v0.2.2-rc.4` (`8` commits, `395` files; `15` non-manifest files): adds non-retryable `LLM_FAILURE_CODES.CONTENT_REFUSED` in `@deepseek-ai/dsh-llm` and yields billed `usage` before throwing `CONTENT_REFUSED` (with `stop_details.explanation`, `0` outgoing `safety_check` fields) on DeepSeek `stop_reason: "refusal"` in `@deepseek-ai/dsh-llm-deepseek` (`1` `docs/upgrade-guide` entry replacing `MALFORMED_RESPONSE`), forwards `ELECTRON_RUN_AS_NODE` via `workerNodeModeEnv()` in `@deepseek-ai/dsh-experimental-liveshare` `TunnelWorker.start()`, and fixes `owner-credential-horizon.host.spec.ts` wall-clock dates |
| [0.2.2-rc.3](2026-11-13_0.2.2-rc.3.md) _(prerelease)_ | `mac`, `win`, `ubuntu` | 2026-11-13 | `dsh-v0.2.2-rc.2 → dsh-v0.2.2-rc.3` (`6` commits, `515` files): adds optional experimental `@deepseek-ai/dsh-deepseek-chat-import` (`POST /api/deepseek-chat-import/archive`, `fflate` two-pass streaming import, `512 MiB` / `256 MiB` / `1,000`-session bounds, protected empty `system/message` surface node `0`), `sidebar.session.action` HOC slot & `workspace.picker` Factory (`3` `DirectoryFlowSlotName` holes), `attachments-missing.txt` + `headOf()`/`Promise.allSettled` stream cleanup in `@deepseek-ai/dsh-session-log-export`, `GetSystemDirectoryW` CWD fix in `apps/desktop/installer/restart-status.h`, and verified CI `bubblewrap` archive caching (`0` `docs/upgrade-guide` breaking changes) |
