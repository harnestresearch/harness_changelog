# DSH (DeepSeek Harness) Latest Changes

English | [简体中文](../zh-CN/full/dsh.md) · [Highlight](../dsh.md) | **Full Detail**

> See [dsh/README.md](dsh/README.md) for the five-platform technical index (`mac`, `win`, `ubuntu`, `ios`, `android`) covering DeepSeek Harness (`@deepseek-ai/dsh` CLI/Web & `@deepseek-ai/dsh-desktop`, currently tracking prerelease `0.2.2-rc.5`).

## 0.2.2-rc.5 — Prerelease (2026-11-18)

See [dsh/2026-11-18_0.2.2-rc.5.md](dsh/2026-11-18_0.2.2-rc.5.md) for full details.

### Overview

`dsh-v0.2.2-rc.5` (official GitHub Release `published_at` `2026-11-18 20:51:39 UTC+8` / `2026-11-18T12:51:39Z` UTC; git merge commit `9c2670d3bce` at `2026-11-18 17:45:47 +0800`) is a **prerelease** candidate succeeding `dsh-v0.2.2-rc.4` (`3f321d32bfe`, published `2026-11-18 01:53:41 UTC+8`) across `5` commits and `433` changed files (`+917 / -594` lines: `53` non-manifest source/doc/upgrade-guide/test/snapshot files `+537 / -214` from PR #8707, `380` version-only `package.json` bumps, and a `0`-diff duplicate clock-test branch merge in PR #8595; verified strictly from read-only git tag objects and official Release metadata without runtime execution or live billing verification).

### Per-Route Automatic Search Selection, Inline Snippets & Migration Boundaries

- **Route-ID Search Preference & Tool Context Wiring (`dsh-base`, `dsh-web`, `dsh-tool-web`, PR #8707; Official: *"DeepSeek models use DeepSeek server-side search with no per-search charge; other models default to DeepSeek Search API"*)**:
  - Removes `searchProvider: deepseek-search-api` from `packages/bundle/base/cordis.patch.yml` (`fetchProvider: http` unchanged) and adds optional `llmProvider?: string` to `WebSearchRequest` (`packages/web/web/src/types.ts`). When unconfigured, `WebRuntime.selectSearchProvider(llmProvider)` (`packages/web/web/src/index.ts`) prefers `'deepseek-official'` only when `llmProvider` is in `DEEPSEEK_MODEL_ROUTES` (`'deepseek-official'`, `'deepseek-account'`), and `'deepseek-search-api'` on all other routes (including DeepSeek models configured under `llm-pi-ai` / custom profiles) and non-model calls, keeping `searchReady(modelSelection.provider)` and `applyWebSearchTool` (`session.requestContext()?.provider`) aligned.
  - **Fallback & Billing Boundaries**: Configured `web.searchProvider` / `$DSH_WEB_SEARCH_PROVIDER` overrides every route with zero fallback; unconfigured `Automatic` falls through to another provider only if the preferred ID is unregistered or locally `available() === false` **and** exactly one usable provider remains (`WEB_PROVIDER_AMBIGUOUS` if >1, `WEB_PROVIDER_UNAVAILABLE` if 0), and **never** falls back on runtime HTTP/auth errors. Official copy waives per-search call fees on `deepseek-official`, **not** token costs (each query runs an auxiliary `deepseek-v4-flash` Messages turn consuming extra model tokens, while `deepseek-search-api` incurs per-request charges; actual server billing is unverified at runtime).
- **Settings `Automatic` Default, 8-Locale Rename & Inline `snippet` Extraction (`ui-settings-web-search`, `web-search-deepseek`, PR #8707)**:
  - `WebSearchCard.tsx` and `locales.ts` default the Search menu to **Automatic** (`自动选择`, showing `searchAutoHint` + guide link and no provider form) and rename `providerLegacy` across all 8 locales from `DeepSeek (legacy)` / `DeepSeek（旧版）` to `DeepSeek server-side search` / `DeepSeek 服务端搜索`; `mapAnthropicResponse()` (`packages/web/web-search-deepseek/src/provider.ts`) extracts non-empty `WebSearchResultItem.snippet` before falling back to `text`-block `citations[].cited_text`.
- **Breaking Changes (`1` `docs/upgrade-guide` Entry)**: `docs/upgrade-guide/v0.2.2-rc.4/web-search-deepseek-model-default/guide.{md,zh.md}` documents that unconfigured DeepSeek-route sessions switch to `/anthropic/v1/messages` (recording `web/deepseek-search-llm-request`), and because `web-search-deepseek` resolves its endpoint (`web-search-deepseek.baseURL` → `$DEEPSEEK_SEARCH_BASE_URL` → `https://api.deepseek.com/anthropic/v1`) independently of the chat route's `baseURL`, custom-gateway deployments fail until they configure `web-search-deepseek.baseURL` / `$DEEPSEEK_SEARCH_BASE_URL` or pin `searchProvider: deepseek-search-api`.

---

## Prior Prerelease: 0.2.2-rc.4 (2026-11-18, UTC+8)

See [dsh/2026-11-18_0.2.2-rc.4.md](dsh/2026-11-18_0.2.2-rc.4.md) for full details.

### Overview

`dsh-v0.2.2-rc.4` (official GitHub Release `published_at` `2026-11-18 01:53:41 UTC+8` / `2026-11-17T17:53:41Z` UTC; git merge commit `3f321d32bfe` at `2026-11-17 21:30:09 +0800`) is a **prerelease** fix candidate succeeding `dsh-v0.2.2-rc.3` (`38a6a5c965a`, published `2026-11-13 15:56:55 UTC+8`) across `8` commits and `395` changed files (`+579 / -429` lines: `15` non-manifest source/doc/test/snapshot files `+199 / -49` and `380` version-only `package.json` bumps; verified strictly from read-only git tag objects and official Release metadata without runtime execution).

### Streamed Refusal Classification, Desktop LiveShare Worker Fix & Contract Change

- **DeepSeek SSE `stop_reason: "refusal"` → `CONTENT_REFUSED` (`@deepseek-ai/dsh-llm` & `@deepseek-ai/dsh-llm-deepseek`, PR #8584; Official: *"Improve handling of unexpected model responses"*)**:
  - Adds non-retryable `CONTENT_REFUSED: {}` (omitting `retryChoice: true`) to `LLM_FAILURE_CODES` (`packages/llm/llm/src/error.ts`) and updates `translate()` (`packages/llm/llm-deepseek/src/translate.ts`) to capture `delta.stop_reason === 'refusal'` with `stop_details.explanation`, yield billed `{ type: 'usage', usage }` on `message_stop`, and throw `LlmError(..., 'CONTENT_REFUSED')` instead of throwing `MALFORMED_RESPONSE` mid-delta. Outgoing request serialization is unchanged (`0` net diff in `serialize.ts` / `config.ts`; no `safety_check` field sent), and Web withdraws the streamed draft while Session retains `assistant/attempt` outside model history (`snapshots/session/deepseek-content-refusal/`).
- **Desktop LiveShare `ELECTRON_RUN_AS_NODE` Worker Spawn & Clock Test Fix (`@deepseek-ai/dsh-experimental-liveshare`, PR #8634 & PR #8638; Official: *"Fix LiveShare failing to create shares in the desktop app"*)**:
  - `TunnelWorker.start()` (`packages/experimental/liveshare/src/host/tunnel-worker.ts`) adds `workerNodeModeEnv(process.env)` to forward `ELECTRON_RUN_AS_NODE` when spawning `process.execPath` (`owner-gateway/cli.js`), preventing Desktop Electron (`mac` / `win`) from starting a second GUI app terminated (`exit code 0`) by `acquireDesktopSingleInstance()`, while keeping plain Node Hosts unchanged; `owner-credential-horizon.host.spec.ts` replaces its expired hardcoded `2026-11-14` horizon with `Date.now()`-relative offsets.
- **Breaking Changes (`1` `docs/upgrade-guide` Entry)**: `docs/upgrade-guide/v0.2.2-rc.3/deepseek-refusal-code/guide.{md,zh.md}` documents that LLM error finishes and failed `turn/end` errors for streamed DeepSeek `stop_reason: "refusal"` report `CONTENT_REFUSED` instead of `MALFORMED_RESPONSE` (no Session v4 JSONL, `cordis.yml`, or CLI breaking changes).

---

## Prior Prerelease: 0.2.2-rc.3 (2026-11-13)

See [dsh/2026-11-13_0.2.2-rc.3.md](dsh/2026-11-13_0.2.2-rc.3.md) for full details.

### Overview

`dsh-v0.2.2-rc.3` (`2026-11-13 13:26:07 +0800`, commit `38a6a5c965a`) is a **prerelease** candidate succeeding `dsh-v0.2.2-rc.2` (`2026-11-11 10:32:18 +0800`, commit `ddac96760b6`) across `6` commits and `515` changed files (`+10,988 / -669` lines; `135` source/test/doc/CI files and `380` workspace manifests).

### Experimental Chat Export Importer & Client UI Extension Seams

- **`@deepseek-ai/dsh-deepseek-chat-import` (`packages/experimental/deepseek-chat-import`, PR #8342)**:
  - Ships as an off-by-default experimental optional bundle (`OPTIONAL_BUNDLES`, `MORE_BUNDLES`, `EXPERIMENTAL_BUNDLES`, `cordis.patch.yml`, `ctx.deepseekChatImport` / `@Remote limits()`, 8 locales) serving owner-only route `POST /api/deepseek-chat-import/archive?workspaceId=…` with `XMLHttpRequest` upload progress or `__DSH_TRANSPORT__.fetch` carrier fallback and streamed `application/x-ndjson` progress/outcome lines.
  - Validates `deepseek_data-*.zip` (`export_format_version: 3`, `2026-11-12` schema) in memory via `fflate` (`maxSessions = 1000`, `maxUploadBytes = 512 MiB`, `maxEntryBytes = 256 MiB`, `maxTitleBytes = 80`), rejecting duplicate central-directory names and misdeclared `ZIP_STORED` sizes. Runs a two-pass streaming import (image attachment storage followed by per-conversation `current_message_id` branch selection, protected empty `system/message` head at surface node `0` for corruption-free Agent resumption, `stage_id` step splitting, `web_search` / `web_fetch` / Markdown `READ_LINK` / synthetic file-card mapping, and `CONTENT_FILTER` round exclusion).
- **Client UI Slots & Icons (`ui-sidebar`, `ui-workspace`, `ui-directory-picker-*`, `ui-primitives`)**:
  - Added root-scoped HOC slot `sidebar.session.action` wrapping `.newSessionRow`, published root-scoped Component Factory `workspace.picker` declaring `workspace.picker.directoryFlow` (injected transactionally by both `-browse` and `-native` directory pickers), and added `IconUploadOutlineRegular` / `IconUploadOutlineMedium`.

### Desktop Installer, Session Export & CI Fixes (No Breaking Changes)

- **Windows Restart Status CWD Fix (`apps/desktop/installer/restart-status.h`, PR #8385)**: Spawns the NSIS update-restart `rundll32.exe` status banner with `GetSystemDirectoryW` as `lpCurrentDirectory` so it cannot pin the installation directory during upgrade replacement.
- **Session Log ZIP Export Resilience (`@deepseek-ai/dsh-session-log-export`, PR #8342)**: Pre-reads the first file chunk (`headOf()`), logs `ATTACHMENT_NOT_FOUND` and `INVALID_ATTACHMENT_REF` entries into `attachments-missing.txt` instead of failing `/api/session.export`, and closes all open file iterators via `Promise.allSettled` on early abort.
- **CI Verified Bubblewrap Cache (`scripts/ci-verified-download.sh`, PR #8383)**: Caches SHA-256-verified `bubblewrap_0.12.0-1_amd64.deb` under `~/.cache/dsh-ci/bubblewrap` on hosted Linux CI/E2E runners with bounded `curl` timeouts/retries.
- **Breaking Changes**: None for users, persisted sessions, or configurations (`0` `docs/upgrade-guide/` entries; external client-plugin types widen `DirectoryFlowSlotName` with `'workspace.picker.directoryFlow'` and `SidebarRootComponentProps` with `'sidebar.session.action'`).
