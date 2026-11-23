# DSH (DeepSeek Harness) Latest Changes

English | [简体中文](../zh-CN/full/dsh.md) · [Highlight](../dsh.md) | **Full Detail**

> See [dsh/README.md](dsh/README.md) for the five-platform technical index (`mac`, `win`, `ubuntu`, `ios`, `android`) covering DeepSeek Harness (`@deepseek-ai/dsh` CLI/Web & `@deepseek-ai/dsh-desktop`, currently tracking prerelease `0.2.3-alpha.2`).

## 0.2.3-alpha.2 — Prerelease (2026-11-22)

See [dsh/2026-11-22_0.2.3-alpha.2.md](dsh/2026-11-22_0.2.3-alpha.2.md) for full details.

### Overview

`dsh-v0.2.3-alpha.2` (official GitHub Release `published_at` `2026-11-22 19:00:39 UTC+8` / `2026-11-22T11:00:39Z` UTC; git merge commit `4b399c39a6d` at `2026-11-22 16:50:28 +0800`) is a runtime-floor and dependency-alignment **alpha prerelease** succeeding `dsh-v0.2.3-alpha.1` (`d98f5d68519`, published `2026-11-22 11:19:36 UTC+8`) across `5` commits (`3` first-parent merges: PR #8837, PR #8960, PR #8961) and `488` changed files (`3` added, `485` modified; `+806 / -707` lines; `413` `package.json` manifests + `75` non-manifest files; verified strictly from read-only git tag objects and official Release metadata without runtime execution).

### Node.js Floor `^24.22.3 || >=26.13.1`, Enforcement Boundaries & Bundled Runtime Alignment

- **Declared Semver Range & Check Locations (`package.json:9`, `apps/cli/package.json:191`, PR #8837)**: Replaces `>=24.9.0` with `^24.22.3 || >=26.13.1` (`>=24.22.3 <25.0.0-0 || >=26.13.1`): allows `24.x >= 24.22.3` (not strict equality) and `>=26.13.1` (including `27.x+` under semver, though CI only tests `24.22.3`, latest `24`, and floating `26`), while excluding `<24.22.3`, all `25.x`, and `26.0.0`–`26.13.0`. No `.npmrc` / `engineStrict`, no CLI startup `process.versions.node` blocker (`apps/cli/src/{bin,installed-bin,profile-boot}.ts`), and no Python `node --version` check (`python/sdk-runtime/src/deepseek_harness_runtime/__init__.py:14,147-152` updates missing-binary hint text only). Strict `=== '24.22.3'` is enforced in `scripts/run-gates.ts:113,496-501` (when `DSH_NODE_COMPAT_BUILD=1`), `scripts/primary-runtime/lock.json:2` + `prepare.ts:278`, and `scripts/build-exe-for-python-sdk.ts:33-35,112-114,127-129,412-417` (`pkg --sea --targets node24.22.3-...`; `scripts/build-exe-for-ssh-helper.ts` remains floating `node24`).
- **Security Dependencies, Electron `^44.11.5`, Vendor Bumps & Upgrade Guide (PR #8837, PR #8960, PR #8961)**: Adds `pnpm-workspace.yaml:19-23` `undici` overrides (`6.29.1` / `7.30.2` / `8.12.4`) and bumps 4 direct `undici` deps to `8.12.4`; bumps Desktop `electron` `^44.7.0` → `^44.11.5` (`apps/desktop/package.json:76`, `verified-versions.json:3,8`) and `node-addon-require-builtin` `^0.1.9` → `^0.1.10` (`4` manifests + `minimumReleaseAgeExclude`); updates `27` `.github/workflows/*.yml` files, `scripts/wine-windows-gates.sh`, and `3` comment-only TS files (`packages/boot/{app-boot,hmr}`, `packages/ptc-runtime/ptc-runtime-node`); adds `docs/upgrade-guide/v0.2.3-alpha.1/node-24-22-3/guide.{md,zh.md,i18n.yaml}`; bumps `9` `vendor/*` packages to `*-alpha.1` (PR #8960) and `404` workspace manifests to `0.2.3-alpha.2` (PR #8961). Zero product, UI, CLI, protocol, or plugin runtime logic changes over `alpha.1`.

---

## Prior Prerelease: 0.2.3-alpha.1 (2026-11-22)

See [dsh/2026-11-22_0.2.3-alpha.1.md](dsh/2026-11-22_0.2.3-alpha.1.md) for full details.

### Overview

`dsh-v0.2.3-alpha.1` (official GitHub Release `published_at` `2026-11-22 11:19:36 UTC+8` / `2026-11-22T03:19:36Z` UTC; git merge commit `d98f5d68519` at `2026-11-22 00:45:52 +0800`; covers `alpha.1` only, not npm `alpha.2`) is the first `0.2.3` **alpha prerelease** succeeding ancestor tag `dsh-v0.2.2-rc.5` (`9c2670d3bce`, published `2026-11-18 20:51:39 UTC+8`) across `2,343` commits (`240` first-parent merges) and `7,260` changed files (`+302,202 / -83,093` lines; `25` new production packages + `apps/desktop-publisher`, `2` removed packages, `55` added + `2` updated `docs/upgrade-guide` entries; verified strictly from read-only git tag objects and official Release metadata without runtime execution).

### Connectors, Remote Auth, Session Surfaces, Experimental Bundles & Security Migrations

- **Connector Accounts, MCP OAuth, On-Demand MCP Loading & 7 Standalone Connectors**: Mounts `@deepseek-ai/dsh-client-ui-connector-account`, `@deepseek-ai/dsh-mcp-account`, `@deepseek-ai/dsh-cli-account`, and `@deepseek-ai/dsh-upstream-skills` by default (`dsh-base`/`dsh-web-app`), adds explicit MCP OAuth + background refresh and opt-in `toolLoading: 'on-demand'` (`mcp__<server>__load_tools`; general servers default to `'eager'`), and introduces 7 standalone optional connector packages (NOT in `OPTIONAL_BUNDLES`): MCP OAuth `@deepseek-ai/dsh-{linear,notion,tencent-docs}` (defaulting to `'on-demand'`) and CLI wrappers `@deepseek-ai/dsh-{feishu,wecom,tencent-meeting,dingtalk}` (`feishu` & `wecom` support macOS & Windows `x64` only; `@larksuite/cli` install script requires pnpm approval).
- **Web Remote Login, Pluggable Auth & Session Surfaces**: Default-on in `dsh-web-app`: `@deepseek-ai/dsh-client-remote-connection` (one-use QR login, tokenized links, owner-approved browser pairing; omitted in Desktop window), extracted `@deepseek-ai/dsh-host-authentication-{token,desktop}` (private Desktop IPC cookie, 17-authority per-hostname cookie cap preventing HTTP 431), `webServer` default `auth: 'required'`, dockable `@deepseek-ai/dsh-client-ui-session-panel`, and extracted `@deepseek-ai/dsh-client-ui-session-status` (Host-shared read/unread + `completionFailed`, requiring `inject: ['uiSession.sessionStatus']`).
- **Experimental Bundles (OFF by Default)**: Extends `@deepseek-ai/dsh-experimental-plugin-market-bundle` with Git repo index sources (private repos via Host Git/SSH creds, locked bare partial clones); adds `@deepseek-ai/dsh-timeline` (task trees, blockers, clickable progress bar, `/timeline`, `.timeline.json`, timed model-billed reports, `Follow chat` language); expands `@deepseek-ai/dsh-experimental-forge-bundle` with a **Code review** page (GitHub PRs only via `forge-github`'s `viewer` / Host `gh` CLI), forge extension seams (lenses, annotations, slots, `forge/review-changed`), and `@deepseek-ai/dsh-forge-gitlab` (Session-bound GitLab MRs via Host `glab` CLI, not global review lists); expands optional `@deepseek-ai/dsh-cua-bundle` to `["darwin", "win32"]` with `@deepseek-ai/dsh-cua-windows` (no `systemInput` yet), renamed `@deepseek-ai/dsh-cua-macos` (`useSystemInput`), hidden optional `@deepseek-ai/dsh-cua-mcp`, and default `cua_run_code` in Standard/SDK/headless when a CUA provider is mounted.
- **Security, Runtime & Contract Migrations (`55` New + `2` Updated Upgrade Guides)**: Removes `working_directory` & subagent `cwd`, aligns `workspace-write` to live Session `cwd` (worktree `.git` writes need extra approval or `additionalWritableRoots`, ignored on Windows), switches worktrees to `enter_worktree`/`exit_worktree`, runs archive worktree cleanup outside read-only sandboxes; introduces `ctx.deepseekAuth` (relabeling API-key provider to **DeepSeek API** while preserving `rc.5`'s route-based automatic search and billing boundary—no per-search fee, still consumes auxiliary `deepseek-v4-flash` tokens); upgrades Cordis Core to `4.0.0-rc.12`, Loader `1.0.0-rc.9`, Include `1.2.0` (YAML 1.2, strict entry validation), adds `dsh-client-config`, HMR `--patch` reload, and default Standard-mode `cordis_inspect`; switches Node PTC to `persistent-in-memory` scoped REPL by default and removes `@deepseek-ai/dsh-experimental-ptc-runtime-python`; retires `@deepseek-ai/dsh-personalized-recommendations` into default-on `dsh-web-app`/`dsh-sdk-app` rows; consolidates `/office` + `pypdf`; restores persistent terminal toggle (still off by default); and adds manual-config `@deepseek-ai/dsh-session-persistence-sqlite` (JSONL remains default).

---

## Prior Prerelease: 0.2.2-rc.5 (2026-11-18)

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
