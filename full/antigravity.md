# Antigravity Latest Changes

English | [简体中文](../zh-CN/full/antigravity.md) · [Highlight](../antigravity.md) | **Full Detail**

> See [antigravity/README.md](antigravity/README.md) for the five-platform technical index (`mac`, `win`, `ubuntu`, `ios`, `android`) covering both Antigravity desktop tracks: **Antigravity Desktop (`antigravity-hub`, `2.36.0`)** and **Antigravity IDE (`2.8.0`)**.

## Antigravity Desktop (Hub) 2.36.0 (2026-11-27)

See [antigravity/2026-11-27_2.36.0.md](antigravity/2026-11-27_2.36.0.md) for full details.

- **Version-Only Shell & Rebased Go `language_server` (`2.36.0-5596661662220288`, `cl/1031268331`, Baseline `1030397722`)**
  - Third consecutive version-only Electron `44.9.1` shell: `app.asar` (`1,167` extracted files, `20,690,656` B, SHA-256 `e0571155… → d2bc25ea…`, byte-identical across all six targets including first-time `windows-arm64` [`$PLUGINSDIR/app-arm64.7z`]) differs solely in `package.json` `version`; macOS `agy-desktop-rtc` grows `+22,592` B (`10,573,520 → 10,596,112` B).
  - Rebased `language_server` (`darwin-arm` `196,625,792` B `−717,648` B, `linux-x64` `236,638,920` B `+6.6` MB, `linux-arm` `222,450,352` B; `strings` `+58,899 / −58,470`) expands Connect-RPCs `338 → 372` (`+34`, parallel `JetskiRemoteAgentProxyService` for remote agent lifecycle, files/permissions, sidecars, triggers, and blueprints), adds RemoteControl **Mesh** transport (`remotecontrol/meshclient`, WebChannel fallback), `policyguardian/sensitivity` (`+442` refs), Proctor J1/C8 supply-chain/firewall rules (`deps.dev`/GitHub advisories), `getsentry/sentry_go` (`523` symbols), `+4` named flags (`225 → 231` pairs, incl. `enable-resume-conversations-from-restart` and `enable-sidecar-pill-auto-open`), and `gemini-4-neonccpa → gemini-4-neondefault` (`44` models, `65` `*ToolConfig`, and `19` CUA actions unchanged).
- **Official `v2.36.0` Notes (`13` Improvements + `26` Fixes) & Six-Target Coverage Boundaries**
  - Remote-agent cloud automation triggers (RPC/service layer) and `~/.agents/skills` discovery (`~/.gemini` precedence) are corroborated statically in `language_server`; headline UI/Auto mode/voice-context/OAuth offline-access items and the `26` fixes are predominantly Hub webapp/server-side and not provable statically. `cl/1031268331` matches across all four macOS/Linux builds; **Windows `x64` and `arm64` `language_server` PEs remain uncovered**, and signature inspection was offline CMS chain parsing only.

---

## Prior Hub Release: 2.35.2 (2026-11-25, Package `Last-Modified`)

See [antigravity/2026-11-25_2.35.2.md](antigravity/2026-11-25_2.35.2.md) for full details.

- **Pure Maintenance Rebuild Over `2.35.1` (`2.35.2-4585983447007232`) — Version-Only Shell & Same-Size Backend Recompile**
  - `app.asar` (`1,167` extracted files, `20,690,656` B, SHA-256 `9f0aad72… → e0571155…`, byte-identical across all five downloaded targets: `darwin-arm`, `darwin-x64`, `linux-x64`, `linux-arm` [`Antigravity-arm64/`], and embedded `windows-x64`) differs solely in `package.json` `version` (`2.35.1` → `2.35.2`), with `dist/`, `node_modules/`, `7` deps, and `chrome-devtools-mcp` `1.12.0` unchanged (prior `2.35.0`/`2.35.1` changes are not attributed to `2.35.2`).
  - Go `language_server` recompiles at identical byte size (`darwin-arm` `197,343,440` B, `linux-x64` `230,003,400` B; `linux-arm` spot-check `216,421,040` B) on shared baseline `1027784732` (`cl/1029194470 → cl/1029311855`, ~2.5h later; `strings` `+6,466 / −6,307` `.rodata`/closure noise only) with zero diff across RPC (`338`), flag-pair (`225`), model (`44`), `*ToolConfig` (`65`), and CUA (`19`) inventories and zero new semantic copy; all four macOS helpers recompile at identical sizes.
- **Official Single Fix ("Switch models while a turn is running") & Coverage Boundaries**
  - The sole official `v2.35.2` fix recorded in a prior `2026-11-26` snapshot (not re-opened live here) belongs to the Hub webapp UI and **is not provable statically from client packages** (zero unannounced package-level capabilities detected). `cl/1029311855` matches across all four macOS/Linux targets (`darwin-x64` & `linux-arm` spot-checked without full `strings` diffs); **Windows `language_server` PE/CL remains uncovered**, and signature inspection was offline CMS chain parsing only.

---

## Prior Hub Release: 2.35.1 (2026-11-25, Package `Last-Modified`)

See [antigravity/2026-11-25_2.35.1.md](antigravity/2026-11-25_2.35.1.md) for full details.

- **Stage 2 (`2.35.0` → `2.35.1`, `execution_id` `4615540875067392`) — Maintenance Rebuild & Unverifiable Official `v2.35.1` Webapp Claims**
  - `app.asar` (`1,167` extracted files, `20,690,656` B, SHA-256 `99ff7f6c… → 9f0aad72…`, byte-identical across `darwin-arm`, `linux-x64`, and embedded `windows-x64`) differs solely in `package.json` `version` (`2.35.0` → `2.35.1`); Go `language_server` recompiles on shared baseline `1027784732` (`cl/1028447422 → cl/1029194470`, `darwin-arm` `+16,528` B, `linux-x64` same CL; `strings` `+799 / −792` build-metadata/closure/rodata noise only) with zero diff across RPC (`338`), flag-pair (`225`), model (`44`), `*ToolConfig` (`65`), and CUA (`19`) inventories, while macOS helper binaries recompile at identical sizes. All three official `v2.35.1` items (from a `2026-11-25` snapshot, not re-opened live) have **zero static footprint** in client packages.
- **Stage 1 (`2.34.0` → `2.35.0`, `execution_id` `6394266482769920`) — Shell Reorganization & Rebased `language_server` Refactor (Attributed to `2.35.0`, Not `2.35.1`)**
  - Shell adds `appChannel.js`, `customWindowControls.js`, `computer/idleProbe.js`, `computer/permissionGuide.js`, and macOS `bin/agy-desktop-rtc` (`10,573,520` B), removing `computer/{hud,hudAgents,hudState}.js` (`chrome-devtools-mcp` `1.12.0` unchanged). Rebased `language_server` (`1025139341 → 1027784732`, `cl/1026637980 → cl/1028447422`, `+428,288` B, `strings` `+30,776 / −29,097`) contracts RPCs `380 → 338` (removing `GetUserMemories`, `GetKnowledgeItems`, `GetUnleashData`, `ImportFromCursor`, etc.), adds `AgentRemoteSession` CRUD/watch/reaction RPCs, `ListPluginPermissionGrants`/`RevokePluginPermissionGrant`, `ListRemoteAgents`, `agentapi` conversation CLI subcommands, `openai/openai_go` (`10,475` symbols), `enable-mcp-apps` / orchestrator / swarm flags (`204 → 225`), and `Gemini 4` suffix updates (`42 → 44`). Windows `language_server` PE/CL and `darwin-x64` were not covered; signature inspection was offline CMS chain parsing only.

---

## Antigravity IDE 2.8.0 (2026-11-19)

See [antigravity/2026-11-19_ide-2.8.0.md](antigravity/2026-11-19_ide-2.8.0.md) for full details.

- **Concentrated `extensions/agy` Update (`1.11.0` → `1.12.0`, `+66.9` KB) & Frozen 3-Release Base (`2.8.0-6733682917113856`)**
  - Across `darwin-arm` (primary diff), `linux-x64`, and `windows-x64` (Code OSS `1.107.0` / `commit: 8dc5315a` / `languageServerCL: 1025045237` / Electron `39.2.3`), 100% of code changes live in `extensions/agy/{vscode/extension.js (+52,460 B, +74 literals / 0 deleted), bridge.js (+14,132 B), package.json (+660 B)}` plus macOS-only MSAL rebuilds (`libmsalruntime.dylib`, `msal-node-runtime.node`); `out/` (`27` files), `out/jetskiAgent/main.js` (`11,837,046` B, stripped `b674d91f…`), the `351`-method `LanguageServerService` descriptor (`a9f7b6f4…`), `agy/dist/extension.js` (`37` B), `node_modules/` (`2,628` comment-only diffs), and hub spawn mechanics remain frozen for a third consecutive release.
- **Backend Management, `SwitchLoginToAuthCode`, Custom CA / Proxy & `+26` Iframe Schemas**
  - Adds periodic update checks (`ANTIGRAVITY_PERIODIC_UPDATE_CHECK_INTERVAL_MS`, `ANTIGRAVITY_STALE_SERVER_UPGRADE_PROMPT_MS`, `"Restart Agent Server"`, `upgrade_prompt` telemetry) + `11` install-decision codes (`downgrade_skipped`, `same_version_rebuild`, `startup_background`, `check_deferred`, `staged_promoted`, etc.), direct `POST …/LanguageServerService/SwitchLoginToAuthCode` (outside the frozen `351`-method descriptor, targeting runtime `agy`) + `ANTIGRAVITY_REMOTE_OOB_AUTH` across `6` remote targets, `antigravity.caCertificates` + dual-prefix `geminicodeassist` CA & VS Code `http.proxy*` / env proxy reads, manifest `findInConversation` `ctrl+f`/`cmd+f`, and `+26` synchronized iframe schemas (`bridge.js` `2,137 → 2,163`: `Resolved*` customizations, `HarnessMessageStep`/experimental steps, model catalog, content layers).
- **Official `v2.8.0` Notes (`7` Improvements + `5` Fixes) Reconciliation**
  - `4` items are corroborated directly in `extensions/agy/`, `3` via static cues or manifest entry points, and `3` (*60s readiness timeout*, *Windows logoff recovery loop*, *Windows multi-window notification focus*) lie outside the static IDE package (in runtime `agy` CLI or remotely loaded webview).

---

## Prior Hub Patch: 2.32.2 (2026-11-17, Package `Last-Modified`)

See [antigravity/2026-11-17_2.32.2.md](antigravity/2026-11-17_2.32.2.md) for full details.

- **Electron Shell Version Bump & Cross-Platform `app.asar` Parity (`2.32.1` → `2.32.2`, `execution_id` `4665802025205760`)**
  - Primary static diff on official `darwin-arm` dual DMGs confirms the `1,068`-file (`18,668,119` B) `app.asar` tree (`5,656,861` B, SHA-256 `5b493943… → 056ba838…`, Electron `44.9.1`, `7` deps) differs solely in `package.json` `version` (`2.32.1` → `2.32.2`), and `app.asar.unpacked` (`chrome-devtools-mcp` `1.9.0`) returns `diff -rq` exit `0` on both `darwin-arm` and `linux-x64` (`windows-x64` inner `app.asar` hash and `376` RPC count rely on spot-checks rather than a full unpacked tree diff; `darwin-x64` was checked via HTTP `HEAD` only; not executed or verified online).
- **Go `language_server` Static Recompile (`cl/1021296516` → `cl/1022991777`) & Unchanged Extracted Text Lists**
  - Recompiled `language_server` (`darwin-arm`: `205,328,064 → 205,328,032` B, `strings` `+765 / −703`; `linux-x64`: `239,952,296` B unchanged, `strings` `+194 / −239`) shows only build-metadata updates, a telemetry CEL helper rename (`cel.WithDefaultHTTPTimeout` → `cel.withDefaultCELHTTPTimeout`), and three disappeared `telemetryclient` / `clearcutLogger` `Shutdown` closure symbol strings (static recompilation observations only—no functional bugfix claimed). Static text extractions remain unchanged (`376` RPC prefix matches, `189` flag pairs, `65` `*ToolConfig`, `9` `gemini-4-*` model tier strings, and byte-identical `9,000`-byte `run_workflow` doc and `agy_tool_safety` blocks—static binary text observations rather than runtime or server-side proof; prior `10%` tracker rollout figure is transient feed sampling, not full rollout proof).

---

## Prior Hub Patch: 2.32.1 (2026-11-14)

See [antigravity/2026-11-14_2.32.1.md](antigravity/2026-11-14_2.32.1.md) for full details.

- **`Gemini 4 Hydrogen` Default Model Catalog Addition & Backend Rebuild (`2.32.0` → `2.32.1`)**
  - Recompiled `language_server` at the exact same byte size (`239,952,296` B, `cl/1020489536 → cl/1021296516`, SHA-256 `b9a8f18d… → 4847eb00…`; deduplicated `strings` delta `+1,085 / −1,115`), adding `gemini-4-hydrogen-{low,medium,high}` (`Gemini 4 Hydrogen (High)`, `defaultmodels.Gemini4Hydrogen`, `gemini-4-hydrogenaicode_latency_ms`) alongside `gemini-4-argon-*` and `gemini-4-carbon-*`.
- **Byte-Identical Electron Shell & Zero Protocol/Flag/Tool Drift**
  - `app.asar` (`dist/` + `node_modules/`, `1,068` files, `18,668,119` B, Electron `44.9.1`, `7` deps) and unpacked `chrome-devtools-mcp` `1.9.0` are byte-for-byte identical to `2.32.0` (only `package.json` `version` bumps to `2.32.1`); all `375` real `LanguageServerService` RPCs, `112` feature flags, `49` `*ToolConfig` types, and `agy_tool_safety` entries remain unchanged.

---

## Recent Major Hub Release: 2.32.0 (2026-11-13)

See [antigravity/2026-11-13_2.32.0.md](antigravity/2026-11-13_2.32.0.md) for full details.

- **Binary & Bundle Footprint (`2.31.2` → `2.32.0`; Three-Plane MCP Baseline Unchanged)**
  - Retains Electron `44.9.1`, `CHROME_DEVTOOLS_MCP_JS` spawn wiring, `18 + 1` built-in `chrome_devtools` injected tools, and byte-identical bundled `chrome-devtools-mcp` `1.9.0`; expands `app.asar/dist` (`59 → 70` top-level entries + `30`-file `dist/remote/`) and grows Go `language_server` `206.8 → 240.0` MB (`+33,124,376` B / `+31.6` MiB, `cl/1020489536`, ~90% in `.noptrdata` protobuf descriptors).
- **Electron Shell: SSH Remote Stack (`dist/remote/`), Catcher 3-Layer Views, Browser Guardrails & `shell-env` Removal**
  - Added a `30`-file SSH remote development stack (`--ssh-host=`, `--agy-backend=ssh`, `bootstrapScript.js` secret-marker protocol, `--persistent_mode` remote LS, `27`-channel `remoteIpcChannels.js` allowlist + `localOnly` IPC guard) and a `3`-layer guest `WebContentsView` stack (`base UI + clip view + catcher overlay`, `9` `wcv:catcher-*` channels).
  - Added cross-site subframe credential stripping (`guestCrossSiteCredentials.js` + single-pipeline `guestRequestHeaders.js`), stripped `Electron/<ver>` from guest UA (`stripGuestElectronUserAgentToken` with Google BotGuard preservation), removed `shell-env ^4.0.3` (`8 → 7` deps, `−20` `node_modules` packages) in favor of custom `loginShellEnv*.js` so `execa` no longer resets Electron `SIGTERM` `before-quit` LS shutdown, and added `StorageFullError` / `EPERM`/`EACCES` rename-replace handling.
- **Go `language_server`: `computer` CUA Plugin, `CloneGitHubRepo` RPC, `+58` Flags & Dynamic Workflows Audit**
  - Added gated `cortex/ext/plugins/computer` (`0 → 896` symbols, ~40 Go files, `ComputerViewerService`, `18` `COMPUTER_ACTION_TYPE_*` actions including `AX_*`, `computer` & `browser_eval_gate` built-in agents), `LanguageServerService/CloneGitHubRepo` (`374 → 375` real RPCs), `remote_plugin` RPCs, `AgentRemoteSessionMessages` on `WatchTopic`, `openaiResponsesConverter`, *"protected sign-in or payment page"* browser block, and `+58` feature flag keys (`54 → 112`); static audit confirms `run_workflow` and `embeddedpython` (`python-build-standalone`) are byte-identical to `2.31.2` (GA rollout of pre-shipped runtime alongside `11` official improvements and `13` fixes).

---

## Prior IDE Release: Antigravity IDE 2.7.0 (Release Date Unconfirmed; Built 2026-11-11)

See [antigravity/2026-11-11_ide-2.7.0.md](antigravity/2026-11-11_ide-2.7.0.md) for full details. _(Release time is unconfirmed; `2026-11-11 12:46` UTC+8 / `2026-11-11T04:46:27.114Z` in `product.json` is the build time, not the release time.)_

- **Concentrated `extensions/agy` Update (`0.0.1` → `1.11.0`; `4` Substantive Files)**
  - Across all 6 packages (`2.6.0` → `2.7.0` on `linux-x64`, `windows-x64`, `darwin-arm`, Code OSS `1.107.0` / Electron `39.2.3`), 100% of code-level changes reside in `extensions/agy/{package.json, package.json.patch, vscode/extension.js (+90,987 B), bridge.js (+9,333 B)}`; `out/`, `out/jetskiAgent/` (`11.8 MB`), `node_modules/`, and `101` other built-in extensions differ only in 37-byte sourcemap commit hashes (`9e3a5da5… → 71bedb45…`).
- **Auth-Aware Status Bar, Loopback `GetAuthStatus`, Diff Commands & `+35` Iframe Schemas**
  - Added three-state status bar login handling (`signedOut` → `antigravity.signIn`; `unknown`/`signedIn` → `antigravity.statusMenu`), cross-window `antigravity.authSync` secret sync, 5s post-open loopback `POST /exa.language_server_pb.LanguageServerService/GetAuthStatus` (`x-codeium-csrf-token`), GCP ToS tracking (`isGcpTos`), `25 → 33` commands (splitting *Current File* vs. *All Files* `acceptAllChanges`/`rejectAllChanges`), `antigravity.isAntigravityIde` feedback/webview host tagging (`productId` `5372208`), and `+35` synchronized iframe schemas (`ManageTask`, media processing, browser recording).
- **CDE `/usr/bin/agy` Fast Path & Port-Collision Retry**
  - Added `CDE_PREINSTALLED_BINARY_PATH = "/usr/bin/agy"` for Google Cloud Workstations / Cloud Shell (`GOOGLE_CLOUD_WORKSTATIONS` / `CLOUD_SHELL`) and `canRetryPortCollision` around `agy --hub` startup, while keeping the `351`-method `LanguageServerService` descriptor (`327` unary + `23` server-streaming + `1` client-streaming) and `45` `*ToolConfigSchema` types frozen.

---

## Antigravity Desktop (Hub) 2.31.2 (2026-11-12)

See [antigravity/2026-11-12_2.31.2.md](antigravity/2026-11-12_2.31.2.md) for full details.

### Overview

Antigravity Desktop (`antigravity-hub`, `productName: "Antigravity"`, `--subclient_type hub`) `2.31.2` upgrades the Electron host from `44.5.1` (`2.29.0`, built `2026-11-04`) to `44.9.1` and expands the monolithic Go `language_server` (`third_party/jetski/cortex/*` + embedded Rust `ripgrep`, `go1.28-20261102-RC00 cl/1012564305`) from `195.9` MB to `206.8` MB while keeping the core three-plane MCP wiring (`dist/languageServer.js`, `chrome_devtools` 18-tool injection, and bundled `chrome-devtools-mcp` `1.9.0`) byte-for-byte identical to `2.29.0`.

### Electron Shell & Guest WebMCP Bridge (`dist/` `37 → 56` Files)

- **CDP Guest WebMCP Bridge (`dist/` MCP-referencing files `1 → 6`)**:
  - Added `dist/guestWebMcpController.js` (`GuestWebMcpController`, default `enabled = false`, *"Nothing is injected into guests"*) attaching to guest `WebContents` over CDP `WebMCP.{enable,disable,invokeTool,cancelInvocation}` and listening to `WebMCP.{toolsAdded,toolsRemoved,toolResponded}`.
  - Wired `enableBlinkFeatures: 'WebMCP'` in `dist/wcvBrowserRegistry.js:336-354`, 4 IPC handlers (`webview:webmcp-{set-enabled,list-tools,call-tool,cancel-tool-call}`) in `dist/ipcHandlers.js:838-850`, preload bindings (`{set,list,call,cancel}WebviewWebMcp*`) in `dist/preload.js:261-264`, and Hub main-frame authorization gating (`webmcpEnabled` on `wcv:acquire`) in `dist/wcvIpcHandlers.js:137-142`.
  - Enforces a `64` KiB output cap, `1s–120s` timeout clamping (default `30s`), HTTPS/loopback-only URL checks (`isSecureWebMcpUrl`), and `PROTECTED_PAYMENT_HOSTS` (`IDP_OR_PAYMENT_BLOCKED` blocking Stripe, PayPal, Adyen, Google Pay, and major IDP/payment hosts).
- **Local Debugging Port Hardening**:
  - Added `tightenActivePortPermissions(userData, DevToolsActivePort)` (`dist/main.js:244` → `dist/paths.js:92-110`), restricting `userDataDir` to `0o700` and `DevToolsActivePort` to `0o600` while retaining `--remote-debugging-port=0`.

### Go `language_server` Native Tool Registry, Safety & Connect-RPC (`~50 → ~60` Tools)

- **Native Swarm, Plan-Execute, Persistent Terminals & Notebooks**:
  - Primary `ToolConverter` types grew `32 → 35` and `cortex_pb.*ToolConfig` messages grew `45 → 49` (`+4`: `FileEdit`, `GrepSearch`, `ManageTask`, `RunWorkflow`), adding compile-time `ParameterSchema() encoding/json/jsontext.Value` (`core.compileParameterSchema`) alongside `invopop/jsonschema` reflection (`exa.chat_pb.ChatToolDefinition`).
  - Replaced the static `tool_schema_swarm_manage.json` template with `cortex/core/native_swarm/` (`manage_swarm`, `post_message`, `read_board`, `swarm_wait` with `join` support).
  - Added `planexecute` `enter`/`exit` gating tools, `update_focus`, `run_workflow`, `list_plugin_accounts`, `search_marketplace`, and `notebook_execution`, renamed `edit_notebook` externally to `notebook_edit`, extended `run_command` with `RunPersistent` / `RequestedTerminalID` / `NotificationTimeoutSeconds`, rewrote `execute_browser_javascript` (`observation` + `intention` + `script` + `urls` targeting `webview_browser`), and introduced the parallel `oneharness` framework (14 tools).
- **Safety Pre-Screener, `StartMcpOAuthSignIn` & Fallback Launcher**:
  - Added `sir_flash_lite` (`MODEL_TIER_FLASH_LITE`, `mode: LOG`, threat signals A–M) alongside the unchanged `agy_tool_safety` (`version: "5a260837"`) allowlist (`30` `allowed_tools`, `43` `allowed_commands`, `3` `allowed_tool_actions`).
  - Expanded Connect-RPC `LanguageServerService` from `365` to `374` methods—adding `StartMcpOAuthSignIn` for direct remote MCP OAuth sign-in alongside `CompleteMcpOAuth`, `DisconnectMcpOAuth`, and `StartPluginAuthSignIn`—and generalized Playwright Node resolution in the embedded `chrome-devtools-mcp` fallback launcher from `ms-playwright-go/1.57.0/node` to `ms-playwright-go/*/node`.
