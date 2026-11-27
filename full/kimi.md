# Kimi Latest Changes

English | [简体中文](../zh-CN/full/kimi.md) · [Highlight](../kimi.md) | **Full Detail**

> See [kimi/README.md](kimi/README.md) for the complete five-platform index (`mac`, `win`, `ubuntu`, `ios`, `android`) covering all 186 releases (up to `3.2.29` Desktop across `mac` and `win`, and `3.1.8` on iOS; standalone Linux unreleased; intermediate desktop versions between `3.2.25` and `3.2.29` are not all cataloged or analyzed in this repository).

## Latest Analyzed Desktop Release: 3.2.29 (2026-11-26, `mac`, `win`)

See [kimi/2026-11-26_3.2.29.md](kimi/2026-11-26_3.2.29.md) for full details. Static dual-package diff of **`3.2.28` (2026-11-18) → `3.2.29` (2026-11-26)** across official versioned macOS `arm64` (`com.moonshot.kimichat`, `3.2.28.27 → 3.2.29.35`) and Windows `x64` (`PE FileVersion` `3.2.28.33 → 3.2.29.38`) installers (shared Sentry build ID `3.2.28+e69611da7c → 3.2.29+9f88ce6cda`; intermediate desktop versions after `3.2.25` are not all cataloged—`3.2.28` has no entry yet and `3.2.26`/`3.2.27` remain Windows-only `TODO` placeholders—so `3.2.25` is **not** the baseline; macOS Intel not sampled; Linux officially not provided; iOS/Android out of scope; not executed):

- **Unannounced `restic`-Backed Local File Version History (Not in Official Changelog)**: Adds `0 → 13` distinct `kimi-agent:file-history-*` IPC channels (`list`, `read-version`, `image`, `image-cancel`, `diff`, `summary`, `restore`, `status`, `changed`, `attach`, `edit-sessions-ack`, `edit-sessions-freeze`, `edit-sessions-unfreeze`), bundled `restic` `0.19.1` (`darwin-arm64/restic` `29,603,376` B / `win32-x64/restic.exe` `31,670,288` B) + `restic-bsd-2-clause.txt`, `18` new `out/main/chunks/` stems (`file-history-client`, `version-diff`, `version-summary`, `restic-resolver`, `repository-key-store`, `maintenance-scheduler`, `process-supervisor`, `lease`, `ab-gate`, etc.), `out/build-manifest.json` `flavor.features.fileHistory: true`, main-process strings (`file_history_restic`, `ResticCommandError`, `fileHistoryAbEligible`, `isFileHistoryRuntimeEnabled`), and `111` of the `113` new `zh-CN` locale keys (the other `2` are global search keys). A/B markers indicate rollout may be gated and not immediately visible to all users.
- **Official `3.2.29` Release Notes Stratification**: Confirmed statically—Markdown preview outline navigation (`obsidianToc` `0 → present` in `WorkbenchPanel` & `en-US`/`zh-CN` locales) and global search UI/interaction (`showMoreMatches`, `searchOlderConversations`, updated `GlobalSearchModal` JS + new CSS). Module-level only (not line-by-line verified)—workbench file tree (`WorkbenchFileSurface`), remote-control permission sync & full-auto approval (`preload-permission-flow.mjs`, `permission-flow*`, `RemoteControl*`, `ApprovalPrompt`), dictation post-send refill (`MessageList`, `ConversationView`), and marketplace plugin authorization expiry (`use-plugin-install-flow`, `Plugin*`). Official-only without independently located in-package targets—mobile keyboard obscuring plugin/skill list, sidebar order jumping on profile refresh, and image preview zooming wrong target (`pinch-zoom` preload removal is not cited as line-level zoom-fix evidence).
- **Runtime, Archives, Dependencies & Signature Scope**: Electron `43.7.7` / Chromium `150.0.7871.250` unchanged; `daimon` `1.0.14 → 1.0.15`; `app.asar` diff counts match on macOS and Windows (`+915 / −885 / 44`, with identical `44` changed paths; de-hashed path-set isomorphism not independently reproduced); `gateway.asar` `+6.4` MB on both platforms; `runtime/npm.asar` byte-identical; `package.json` bumps `pnpm` `9.15.0 → 12.21.0`, `@doc-k/embed-sdk` `0.5.0 → 0.6.1`, adds `geographiclib-mgrs` `1.0.7`, and removes the `pnpm` overrides/patches block. Signatures: macOS main binary Team ID `2J9472RW75` (`com.moonshot.kimichat`, `Developer ID Application`, prior report's `3/3` CodeDirectory page-hash match not recomputed here, no Apple root/notarization validation); Windows installers share the same Sectigo EV subject (`北京月之暗面科技有限公司`) with RFC3161 timestamp, Authenticode PE digest **not** recomputed, and no Sectigo root/timestamp trust validation.

---

## Earlier Analyzed Desktop Release: 3.2.25 (2026-11-05, macOS)

See [kimi/2026-11-05_3.2.25.md](kimi/2026-11-05_3.2.25.md) for full details.

### Overview

Kimi Desktop `3.2.25` unifies five subsystems inside a single Electron `43.7.7` host: (1) an embedded agent kernel (`daimon-bundle` `v1.0.6` wrapping `kimi-code` `v0.5.1` plus standalone Node.js `24.15.0`, CPython `3.12`, and `uv` toolchains), (2) five distinct MCP integration pipelines spanning cloud gateways, local `stdio`/`StreamableHTTP` servers, OAuth PKCE flows, Chromium 150's native `WebMCP` CDP domain, and Computer Use (`kimi-cu`), (3) seven Rust/Swift NAPI `.node` addons for macOS system integration, (4) a 196 MB `gateway.asar` OpenClaw messaging gateway (`kimiim-cli`), and (5) sandboxed WASM engines for LaTeX, genomics, and 3D CAD files.

### Embedded Agent Kernel & Runtime Toolchains

- **`daimon-bundle` (`v1.0.6`) & `kimi-code` (`v0.5.1`)**
  - Ships `resources/daimon-bundle/` (`kernel-bundle.mjs`) alongside an isolated runtime distribution bundling Node.js `24.15.0`, CPython `3.12`, and `uv` so local coding, shell, and Python workflows execute reproducibly without host PATH pollution.
  - Exposes core workspace primitives (`Shell`/`Bash`, file read/write/patch, glob/ripgrep search, todo/task tracking, subagent delegation, and web search/fetch) coordinated over local IPC between the Electron main process and the `daimon` daemon.
- **Bundled Companion Binaries**
  - `kimiim-cli`: CLI bridge managing multi-channel IM bot bindings and gateway lifecycle.
  - `kimi-slides`: Local presentation deck rendering and export helper.
  - `kimi-webbridge` (`~/.kimi-webbridge`): Local browser/workspace bridge daemon.
- **Desktop Claw (`gateway.asar`)**
  - Ships a standalone `196 MB` `gateway.asar` bundle derived from OpenClaw (`Desktop Claw`), routing inbound/outbound IM channel conversations and remote-control commands to local agent workspaces.

### Five-Path MCP Architecture

- **Path 1 — Cloud & Gateway MCP (`agent-gw.kimi.com`)**: Connects to Moonshot-hosted MCP connectors and remote agent tools over authenticated HTTPS/SSE streams via `agent-gw.kimi.com`.
- **Path 2 — Local & Remote User MCP Servers (`stdio` / `SSE` / `StreamableHTTP`)**: Manages user-configured MCP servers in the Electron host using `@modelcontextprotocol/sdk`, supporting JSON-RPC `initialize`, `tools/list`, `tools/call`, `resources/*`, `prompts/*`, and interactive `elicitation/create` user approval dialogs.
- **Path 3 — `MCPOAuthService`**: Implements OAuth 2.1 + PKCE authorization discovery (`.well-known/oauth-authorization-server` / `.well-known/oauth-protected-resource`), loopback/custom-scheme callback capture, secure token persistence, and automatic token refresh for remote MCP connectors.
- **Path 4 — Chromium 150 `WebMCP` CDP Integration**: Attaches to embedded `WebContents` via Chrome DevTools Protocol and enables Chromium 150's `WebMCP` domain, discovering structured tools declared by live web pages and exposing them to the active agent turn.
- **Path 5 — Computer Use MCP (`kimi-cu`)**: Exposes desktop GUI observation and input actions (`screenshot`, `click`, `double_click`, `move`, `drag`, `scroll`, `type`, `key`, `wait`) backed by native macOS screen-capture and input addons.

### Native macOS NAPI Addons & Sandboxed WASM Engines

- **7 Native `.node` Addons (Rust `napi-rs` + Swift/Objective-C Frameworks)**:
  - `kimi-darwin.node`: macOS window management, Accessibility/Screen Recording TCC permission checks, and system appearance/power hooks.
  - `kimi-screen-capture.node`: High-performance ScreenCaptureKit/CGWindowList display and window capture for Computer Use and region snipping.
  - `kimi-ocr.node`: On-device Apple Vision framework (`VNRecognizeTextRequest`) optical character recognition.
  - `kimi-scroll-input.node` & `kimi-global-input.node`: Synthetic CGEvent smooth scrolling, pointer control, keyboard injection, and global hotkey listeners.
  - `kimi-file-manager-selection.node`: Queries active Finder window paths and selected file URLs via ScriptingBridge/Accessibility so prompts can reference current Finder selections.
  - `kimi-keyboard-environment.node`: Inspects IME/input-source layout state to avoid garbled keystroke synthesis during CJK input.
- ** Embedded Domain WASM Modules**:
  - `tectonic.wasm`: Sandboxed client-side TeX/LaTeX typesetting engine compiling `.tex` artifacts directly to PDF.
  - `samtools.wasm`: In-app bioinformatics BAM/SAM/CRAM alignment inspection without external native dependencies.
  - `occt-import-js.wasm`: OpenCASCADE WebAssembly kernel importing STEP/IGES/BREP 3D CAD assemblies for interactive viewport rendering.

---

## Recent Analyzed Android Release: 3.1.5 (2026-10-23)

See [kimi/2026-10-23_android-3.1.5.md](kimi/2026-10-23_android-3.1.5.md) for full details.

### Overview

Kimi Android `3.1.5` (`versionCode 382`) pairs mobile chat with a structured Remote Control client for desktop Kimi / Kimi Claw hosts, a ConnectRPC authentication gateway matrix (`/apiv2/kimi.gateway.*`), cross-app Kimi Claw OAuth handoff (`AuthActivity3`), and device-shielded token rotation.

### Remote Control Protocol & Media Pipeline

- **Remote Control Action Protocol (`i00.*` Package)**:
  - Implements a typed JSON command/state channel driving remote desktop workspaces across six core operations: `pick` (remote file/target selection), `read` (workspace file/state inspection), `upload` (transferring mobile files/photos into the remote session), `preview` (rendering remote artifacts/images), `release` (detaching/releasing remote control lock), and `status` (heartbeat & host availability tracking).
  - Adds `RcReadOnlyImageActivity` as a dedicated read-only surface for inspecting remote desktop screenshots and visual outputs without accidental edit mutations.
- **Real-Time Voice & Screen Media (`TRTC`)**:
  - Integrates Tencent Real-Time Communication (`TRTC`) native SDK libraries for low-latency audio/video streaming during live voice conversations and remote session supervision.

### Authentication Matrix & Session Security

- **ConnectRPC Gateway Login Matrix (`/apiv2/kimi.gateway.*`)**:
  - Consolidates mobile sign-in methods onto ConnectRPC endpoints under `/apiv2/kimi.gateway.*`, covering SMS OTP login, Chinese carrier one-click number verification SDKs, WeChat OpenSDK OAuth, and email/password or OTP sign-in.
  - Exposes `AuthActivity3` to handle incoming deep-link / intent authorization requests for **Kimi Claw** cross-app and companion gateway binding.
- **`AccountSessionManager`, MMKV Persistence & Shielded Token Refresh**:
  - Persists active credentials and user profile state in encrypted MMKV store `kimi_cache_user_info` managed by `AccountSessionManager`.
  - Executes proactive and 401-triggered token rotation via `POST /api/account.gateway.v1.AuthService/RefreshToken`, attaching device fingerprint and anti-abuse telemetry in the `X-Msh-Shield-Data` header alongside `X-Msh-Device-Id`, `X-Msh-Platform`, and `X-Msh-Version`.
