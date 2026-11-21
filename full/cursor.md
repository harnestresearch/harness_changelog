# Cursor Latest Changes

English | [简体中文](../zh-CN/full/cursor.md) · [Highlight](../cursor.md) | **Full Detail**

> See [cursor/README.md](cursor/README.md) for the complete five-platform index (`mac`, `win`, `ubuntu`, `ios`, `android`) covering all 446 releases (426 Desktop releases up to `3.30.14` + 20 iOS releases up to `ios-1.17.0`; standalone Android unreleased).

## 3.30.14 (2026-11-14)

See [cursor/2026-11-14_3.30.14.md](cursor/2026-11-14_3.30.14.md) for full details. _(CDN release time: `2026-11-14 04:27` UTC+8 / `2026-11-13 20:27:26` GMT; unified commit `5f54c817…`; not yet listed on the official Cursor changelog.)_

- **Default-Off "Deploy App" Live Web Publishing (`+1` Unary RPC; `+2` Gates; `+5` Dynamic Configs)**
  - Added `AppPublishService.getAppsEligibility` (`2,555 → 2,556` unary RPCs; `GetAppsEligibilityRequest/Response`, messages `5,923 → 5,925`), default-`false` gates `cloud_agent_apps` and `glass_deploy_with_cursor_pill`, `glass_apps_growth_config` (`deployIntentKeywords` + cloud repo root `publish-app` prompt), `molten` `apps-publish-CtW5oKQc.js` client store/decision state machine (`submitting`/`published`/`refused`) + `dev-server-open.ts`/`preview-card.tsx`/`forwarded-port.ts`, and `+21` desktop NLS strings (moving project files to the cloud excluding dependencies, build output, and `.env` files).
- **Daemon Repo Path Glob Governance, Caller-Window Identity & `SideChatInfo` Subagent Field**
  - Added `../local-exec/dist/services/team-repo-rules.js` in `daemon.cjs` (`+4.2 KB`), extending `getTeamRepos()` allowlist/blocklist enforcement from whole-repo URLs to fail-closed `{url, patterns[]}` glob matching (`picomatch` `{dot: true}` with `2,048`-entry LRU, `url === "*"`, `org-*` URL globs, `inCursorDataDir` exemption) and `src/identity/caller-window.ts` (`x-cursor-client-layout` / `x-cursor-glass-renderer`, `isGlassRoot`), plus `SideChatInfo.subagent_type` (`no:3`) and MCP placement error mapping (`needs_auth`/`not_reachable`/`tool_not_found`).
- **Main-Process `grokConfigFiles.js`, Electron `43.8.9` Refresh & Frozen Tool/Remote/Security Surfaces**
  - Added cross-platform `grokConfigFiles.js` in `out/main.js` reading `GROK_HOME` / `~/.grok/{managed_config,config,requirements}.toml`, validating `trace_upload_credentials_file` (absolute path, `≤64 KB`), and submitting Grok feedback; upgraded Electron `43.8.4 → 43.8.9` across `mac`, `win`, and `ubuntu` (recompiling `@parcel/watcher` & `tree-sitter`), while `agent.v1.ToolCall`, `mcpProcessMain.js`, `cursor-mcp`, Remote Control (`17` + `59` RPCs, `pairing_proof`), `x-cursor-checksum`, and window hardening remain unchanged.

---

## Previous Release: 3.30.8 (2026-11-12)

See [cursor/2026-11-12_3.30.8.md](cursor/2026-11-12_3.30.8.md) for full details. _(Package release times: Win/macOS `2026-11-12 06:23` UTC+8, Linux `2026-11-12 10:26` UTC+8; unified commit `4a44c846…`; not yet listed on the official Cursor changelog.)_

- **Protocol & Admin Governance (`+111` Unary RPCs; `+200` Messages)**
  - Expanded `DashboardService` (`+56/-3` RPCs: Step-Up secondary auth, third-party OAuth app management, `staff*` API key inventory, team/org session revocation, Grok credit packs, Sand spend/egress) and `GrokBotService` (`+48/-1` RPCs: calendar streaming, cart checkout, try-on, SMS binding, paired with default-off `glass_grok_build_unboxing` *"Cursor is now Grok Build"* UI); added QUIC probe `https://cursor-cdn.com/cdn-cgi/trace` and `voiceCallReachability.js` (`https://api.x.ai/v1/realtime`).
- **Agent Tools & MCP Policy Enforcement**
  - Added `manage_access_tool_call` (`no:95`) and server-dispatched `execute_tool_call` (`no:1000`, `ExecuteResult{success|error|rejected}`) to `agent.v1.ToolCall` (`72 → 74`); enforced admin MCP policies via `McpError.policy_blocked_reason` + `mcpSurfaceAccess.js` + `mcpRepoScope.js`; hardened `mcpProcessMain.js` (`429`/`503` OAuth discovery backoff, `NODE_DISABLE_COMPILE_CACHE=1`, warm PowerShell pool), added `McpSuccess.mcp_app_document` and `mcp_event` automation triggers, and added `kalshi` in `cursor-mcp` while lifting legacy Outlook/OneDrive/Teams blocks.
- **Remote Control `pairing_proof`, `molten` Workers & Main-Process Security**
  - Added ECDSA P-256 `pairing_proof` on `TrustControllerRequest` / `PendingControllerApproval` and `+10` `AgentHostService` RPCs (`RestoreFileCheckpoints`, `ListMcpServers`, `UpdateMcpServer`, session archive/pin/unread, `WatchDaemonReports`); added `molten` `ai-tracking-worker.cjs` (`~/.cursor/ai-tracking/ai-code-tracking.db`), `airlockEngine.js` (Docker/Podman) + `admitOrbitAirlockLocalTurn`, strict `O_NOFOLLOW`/`0600`/immediate-`unlink` daemon `--environment-file` loading, and `6` idle-relaunch updater modules among `+27` new main-process modules.

---

## Recent Architectural Baseline: 3.28.7 (2026-11-03)

See [cursor/2026-11-03_3.28.7.md](cursor/2026-11-03_3.28.7.md) for full details.

### Overview

Cursor Desktop `3.28.7` (commit `25b52e7`, built on VS Code `1.128.0`) ships a dual-workbench Electron architecture (`out/vs/workbench/workbench.desktop.main.js` for the classic IDE and `out/vs/workbench/workbench.glass.main.js` for the standalone **Agents / Glass** window), a cloud-hosted agent loop dispatching **70+ typed `agent.v1.ToolCall` client tools**, an outbound HTTP/2 Connect bidirectional relay (`aiserver.v1.RemoteAgentHostPresenceService`) secured by ECDSA P-256 DPoP proofs and 6-character pairing signatures for **Remote Control ("Steer from Phone")**, and the isolated Electron `utilityProcess` MCP host introduced in the `3.24.x` series (see [cursor/2026-10-09_3.24.12.md](cursor/2026-10-09_3.24.12.md)).

### Outbound Remote Control Tunnel & Cryptographic Pairing

- **Cloud-Loop / Local-Tool Architecture**:
  - When Remote Control (`Settings > Agents`) is enabled (desktop `>= 3.9.8`), the agent reasoning loop runs in Cursor's cloud (`*.api5.cursor.sh` / `api2.cursor.sh`) while all workspace tool executions stay on the user's machine—requiring zero inbound ports or P2P NAT traversal, with optional OS sleep prevention (`Keep this computer awake`) and bidirectional `Move to Cloud` session migration.
- **`aiserver.v1.RemoteAgentHostPresenceService` (17 Connect-RPC Methods)**:
  - Opens a persistent outbound HTTP/2 Connect bidirectional stream via `ConnectTarget` to `https://api2.cursor.sh`, multiplexing reverse tool/git/file RPCs back to the local workbench alongside registration, heartbeat, lease, pairing, and wake/presence management RPCs.
- **ECDSA P-256 Host Keys, DPoP Proof Headers & Pairing Challenge**:
  - Generates a persistent per-machine ECDSA P-256 keypair stored via Electron `safeStorage` (`cursor-safe-storage:v1:`) and signs short-lived DPoP-style JWT proofs sent in `x-cursor-agent-host-proof` on tunnel and presence requests.
  - Controller pairing displays a 6-character alphanumeric verification code and performs cryptographic challenge-signature binding between the mobile controller session and the registered computer public key.

### Authentication, Network Topology & Mobile Session Contracts

- **Multi-Origin API Topology (`aiserver.v1.*` & `origin.v1.*`)**:
  - Routes general Connect-RPC traffic to `api2.cursor.sh`, Cursor Tab completions/metrics to `api3.cursor.sh` & regional `api4.cursor.sh`, privacy-partitioned agent streams to `agent*.api5.cursor.sh`, codebase indexing/telemetry to `repo42.cursor.sh` (`repo42AuthToken`), Cloud Agents / SCM / hosted MCP to `api.origin.cursor.com` (`cursor-origin` -> `https://api.origin.cursor.com/mcp`), and OAuth/AuthKit login flows to `prod.authentication.cursor.sh` & `authenticator.cursor.sh`.
- **Desktop Login Polling & Request Headers**:
  - Desktop sign-in opens `/loginDeepControl?challenge=<sha256_b64url>&uuid=<uuid>` (with `&surface=glass` from the Agents window) and polls `/auth/poll?uuid=...&verifier=...` every 500 ms (with `cursor://cursorAuth` deep-link fallback), storing JWT `cursorAuth/accessToken` and `cursorAuth/refreshToken` in `safeStorage`.
  - Attaches `x-cursor-checksum` (chained-XOR obfuscated timestamp + `telemetry.machineId` + SHA-256 of NIC MAC), `x-cursor-client-version`, `x-cursor-client-commit`, `x-cursor-client-layout`, `x-cursor-glass-renderer`, `x-ghost-mode`, and `x-cursor-mdm-signin-policy`.
- **Mobile Session & iOS Live Activity Protobuf Surface**:
  - Shares `aiserver.v1.AuthService` mobile session RPC contracts (`CreateMobileSession`, `UpgradeMobileSession`, `RefreshMobileSession`, `RevokeMobileSessionFamily`, `ConvertMobileSessionToRefreshPair`) plus `SyncLiveActivity` and `/api/auth/registerPushNotificationToken` (`PushPlatform` covering APNs and `WEB`) powering iOS `co.anysphere.cursor` (`iOS 26.0+`, up to 8 concurrent Lock Screen / Dynamic Island Live Activities).

### Three-Generation Built-in Agent Tool Surface (70+ Tools)

- **Unified `agent.v1.ToolCall` Oneof & Legacy `ClientSideToolV2` Bridge**:
  - Supports three coexisting protobuf tool generations (`aiserver.v1.ClientSideToolV2`, transitional `CallMcpToolParams`, and current `agent.v1.ToolCall` with 70+ typed `oneof` variants):
  - **Filesystem, Search & Diagnostics**: `read_file_v2`, `edit_file_v2` / `apply_patch`, `delete_file`, `list_dir_v2`, `file_search`, `ripgrep_raw_search`, `glob_file_search`, `semantic_search_full`, `read_lints`, and notebook cell edit tools.
  - **Terminal & Sandboxed Execution**: `run_terminal_command_v2` / background shell management backed by `@anysphere/sandbox-helper` (and Linux `cursor-sandbox-apparmor` profile).
  - **Subagents, Swarms, Canvas & Code Review**: Parallel subagent/swarm spawning, tracked background tasks, `write_canvas` interactive artifacts, Pull Request **Code Tour** generation, `fetch_rules`, `web_search` / `fetch_url`, `computer_use`, and `mcp_tool_call` / `get_mcp_tools`.
  - **Context Accounting**: Tracks hierarchical prompt token budgets via `PromptContextUsageTree`.

---

## Recent Architectural Baseline: 3.24.12 (2026-10-09)

See [cursor/2026-10-09_3.24.12.md](cursor/2026-10-09_3.24.12.md) for full details.

### Overview

Cursor Desktop `3.24.12` establishes Cursor 3.x's multi-process Model Context Protocol (MCP) architecture: external MCP transports execute inside a dedicated Electron `utilityProcess` (`out/vs/code/electron-utility/mcpProcess/mcpProcessMain.js`) isolated from the renderer workbench and fortified by `@anysphere/sandbox-helper`, while two first-party automation suites (`cursor-ide-browser` and `cursor-computer-use`) run as in-process extension MCP providers bridged over `vscode.cursor.registerMcpProvider`.

### Dedicated `utilityProcess` MCP Host & Protocol Negotiation

- **Process Isolation & Sandboxed `stdio` Spawning**:
  - Launches `mcpProcessMain.js` as a shared Electron `utilityProcess` communicating with workbench windows over IPC (`mcpprocess` output channel).
  - Supports three `@modelcontextprotocol/sdk@1.25.1` client transports: `StdioClientTransport` (wrapped with `@anysphere/sandbox-helper` for filesystem/network sandboxing when server policy requires), `StreamableHTTPClientTransport` (with automatic deprecated-SSE fallback and 404 session tombstoning), and `SSEClientTransport`.
- **Handshake, Capabilities & MCP Apps UI Extension**:
  - Sends `initialize` with `protocolVersion: "2025-11-25"`, `clientInfo: { name: "cursor-vscode", version: "1.0.0" }` (HTTP `User-Agent: Cursor/<version> (<platform> <arch>)`), and capabilities `{ elicitation: { form: {} }, roots: { listChanged: false }, extensions: { "io.modelcontextprotocol/ui": { mimeTypes: ["text/html;profile=mcp-app"] } } }` (`sampling/createMessage` is intentionally unimplemented and returns `-32601`).
  - Automatically paginates `tools/list` (`nextCursor`), resets per-call idle timeouts on progress notifications (`_meta.progressToken`), and spills oversized text tool outputs to disk (`Output has been written to: <path> (<bytes> bytes, <lines> lines)`).

### `mcp.json` Configuration Schema, OAuth & Security Governance

- **Multi-Scope Discovery & Strict Schema (`vscode://schemas/mcp`)**:
  - Merges 6 server tiers (`default` -> `~/.cursor/mcp.json` chmod `0600` -> `<workspaceFolder>/.cursor/mcp.json` -> extensions -> plugins -> `mcp-provider://<id>`), plus untrusted-by-default auto-discovery (`chat.mcp.discovery.enabled`) from `<folder>/.vscode/mcp.json`, `claude_desktop_config.json`, and `~/.codeium/windsurf/mcp_config.json`.
  - Runtime JSONC parser tolerates `//` / `/* */` comments and trailing commas; supports two-stage variable expansion (`${ENV:-default}` + VS Code `${workspaceFolder}`, `${userHome}`, `${command:...}`, etc.).
  - `stdio` entries accept `{command, args?, env?, envFile?, enabledTools?}`; remote entries accept `{url, headers?, auth?: {CLIENT_ID, CLIENT_SECRET?, scopes?}, placement?: "server" | "client", enabledTools?}`.
- **OAuth 2.1 Discovery & Hosted REST-MCP**:
  - Resolves `.well-known/oauth-protected-resource` metadata (including `cursor_client_id`, `cursor_loopback_ipv4`, `cursor_backend_only_token_exchange`), static provider profiles (Google Workspace, Slack, Shopify, HubSpot, X), and loopback/deep-link callbacks (`cursor://anysphere.cursor-mcp/oauth/return`, `localhost:8787/18787/28787/31787`), while automatically injecting `x-cursor-auth: Bearer <token>` on `https://api.cursor.com/rest-mcp/<provider>/mcp` and built-in `cursor-origin` (`https://api.origin.cursor.com/mcp`).
- **Config-Hash Project Approvals & Allowlists**:
  - Hashes `{command, args, env, envFile, url, headers, auth}` into a 16-hex digest (`<identifier>:<hash16>` in `approvedProjectMcpServers`), immediately disabling project servers if `.cursor/mcp.json` is modified until re-approved.
  - Evaluates `ComposerDecisionsService.handleMcpOperation` against `composerState.mcpAllowedTools` (`serverId:toolName` with `*` wildcards), `permissions.json` (`MCP:<toolName>`, auto-translating imported `mcp__server__tool` rules), `cursor/requiresConfirmation` annotations, and enterprise `allowedMcpConfiguration`.
  - Exposes MCP tools to `agent.v1.AgentRunRequest` as `McpToolDefinition` named `${serverIdentifier}-${toolName}` (alongside `ClientSideToolV2` ops `MCP=19`, `LIST_MCP_RESOURCES=44`, `READ_MCP_RESOURCE=45`, `CALL_MCP_TOOL=49`, `MCP_AUTH=60`, `GET_MCP_TOOLS=63`).

### Built-in First-Party Extension MCP Providers

- **`cursor-ide-browser` (16 `browser_*` Tools + CDP)**:
  - Registered in-process via `mcp-provider://cursor-ide-browser`, exposing 16 Playwright/CDP-backed tools for embedded/connected browser tabs: navigation (`browser_navigate`, `browser_navigate_back`, `browser_reload`), observation (`browser_snapshot`, `browser_take_screenshot`, `browser_console_messages`, `browser_network_requests`), interaction (`browser_click`, `browser_type`, `browser_hover`, `browser_drag`, `browser_select_option`, `browser_press_key`, `browser_wait_for`, `browser_resize`), and tab management (`browser_tabs`).
- **`cursor-computer-use` (17 `computer_*` Tools on macOS & Windows)**:
  - Registered in-process via `mcp-provider://cursor-computer-use`, providing 17 desktop GUI automation tools covering display/window capture, cursor movement, single/double/right/middle clicks, drag, scroll, text entry, key combos, cursor position queries, and wait synchronization.
