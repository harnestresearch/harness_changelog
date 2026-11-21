# WorkBuddy Latest Changes

English | [简体中文](../zh-CN/full/workbuddy.md) · [Highlight](../workbuddy.md) | **Full Detail**

> See [workbuddy/README.md](workbuddy/README.md) for the complete five-platform index (`mac`, `win`, `ubuntu`, `ios`, `android`) covering all 133 releases (`5.9.4` Global GA, `5.11.0` CN grayscale, `2.9.0` iOS, and `2.9.1` Android).

## 5.9.4 (2026-10-29, Global Desktop GA)

See [workbuddy/2026-10-29_5.9.4.md](workbuddy/2026-10-29_5.9.4.md) for full details.

### Overview

WorkBuddy Desktop `5.9.4` (`5.9.4.42593613`, commit `fa0a0901`) ships Tencent's `@genie/workbuddy-desktop` Electron host combining an embedded `app-server` (`main/server.js`) exposing **28 built-in MCP tools** with lazy `defer_loading` and automatic credential redaction, a secondary `ClientToolRegistry` (`wb-client:*`), embedded `codebuddy-lite-wb.mjs` CLI and `deep-research.workflow.js` engines, `@agentclientprotocol/sdk@1.7.0` ACP support, a ~340-operation Office editor SDK (`@tencent/tencent-docs-ai-engine@0.2.220-wb`), five enterprise IM connectors backed by Rust `im-napi.node`, and multi-backend `llama.cpp` local model execution.

### Built-in MCP Tool Surface (`main/server.js` — 28 Tools)

Tools are instantiated via `createXxxTool` factories and registered onto `workbuddyConnector.registerBuiltinTool({...tool, defer_loading})` over standard JSON-RPC MCP (`tools/list` / `tools/call`), carrying `promptCacheStability: "stable"`, runtime `isAvailable(ctx)` session-permit gates, and optional `meta: { sensitiveResultPolicy: "automatic-protection" }`:

- **Artifact Presentation & Generative UI (3)**:
  - `present_files` (ordered artifact/URL preview cards; `.genie` entries sorted last), `show_widget` (inline bare SVG/HTML interactive widgets with `0 0 680` viewBox convention and progressive `loading_messages`), and `widget_guidelines` (on-demand CSS/typography/layout specs for `diagram`, `mockup`, `interactive`, `art`, `chart`).
- **Search, Memory & Enterprise Knowledge (3)**:
  - `domain_search` (delegated multi-step vertical research agent), `conversation_search` (cross-session cloud memory search with ISO-8601 date bounds, dynamically synced via `syncConversationSearchBuiltinTool`), and `knowledge_search` (authenticated enterprise retrieval across `workbuddy_library`, `ima`, `tencent_docs`, `tencent_meeting`, and `tencent_drive` with `created_after/before` and `updated_after/before` metadata filters).
- **Connector, Expert & Skill Lifecycle (7, `defer_loading: true`)**:
  - `search_plugins` (`connector` / `expert`), `suggest_plugin_install` (1–3 inline install cards validated against recent search IDs), `list_installed_plugins`, `reconnect_plugin`, `uninstall_plugin` (batched confirmation dialog), plus `search_and_install_skills` and `skill_management` (`list` / `disable`).
- **Scheduled Automations (2)**:
  - `automation_update` (`list` / `view` / `create` / `update` / `delete` supporting RFC 5545 `rrule`, `scheduledAt`, multi-directory `cwds`, `expertId`, and `connectorIds`, gated by `isAutomationWbSdkRefactorEnabled`) and permit-gated `send_automation_result`.
- **Full-Stack Sites, Serverless Cloud & Mini Program Scaffolding (4, `defer_loading: true`)**:
  - `workbuddy_sites_deploy` (publishes `node` / `python` / `go` / `static` apps to `<=32`-char ASCII `domainPrefix` subdomains, requiring `userAskedToPublish`), `workbuddy_sites_unpublish`, `workbuddy_cloud_service` (`inspect` / `activate` managed Serverless DB/auth/storage/LLM backend for `wbapp_*` web or miniprogram apps), and `workbuddy_miniprogram_scaffold` (expands versioned native WeChat Mini Program templates inside workspace-relative paths).
- **Auth Bridges, Agent Mail, IM Reader & Session Utilities (9)**:
  - `connect_cloud_service` (mints temporary `clientTempToken` for Miora media generation with `sensitiveResultPolicy: "automatic-protection"`), `connect_open_platform` (mints short-lived `op_xxx` skill backend tokens), `workbuddy_request_mcp_connection` (blocking multi-server authorization card), `agent_mail_upload_attachment`, `agent_mail_download_attachment` (auto-quarantines downloaded files as non-executable), `im_list_conversations`, `im_get_messages` (up to 50 messages), desktop-only `pick_location` (interactive map POI picker), and `workbuddy_app_set_conversation_title`.

### Secondary Tool Registries, Embedded Engines & Native Subsystems

- **`ClientToolRegistry` & Office Editor SDK**:
  - `main/conversations.js` maintains `ClientToolRegistry` addressing renderer/extension tools as `wb-client:<conversationId>:<providerId>:<toolId>` with structured `{status, error: {message, code}, duration}` envelopes (`CLIENT_TOOL_NOT_FOUND`, `CLIENT_TOOL_TIMEOUT`, `CLIENT_TOOL_EXECUTION_FAILED`).
  - Integrates `@tencent/tencent-docs-ai-engine@0.2.220-wb` exposing ~340 internal Office document operations across `doc_*` (~120), `sheet_*` (~110), `slide_*` (~110), and `smartsheet_*`.
- **Embedded Coding CLI, Deep Research & ACP**:
  - Bundles `cli/codebuddy-lite-wb.mjs`, `deep-research.workflow.js`, and `@agentclientprotocol/sdk@1.7.0` alongside background daemon supervisors (`daemon-bootstrap.js`, `daemon-app-server-main.js`).
- **Multi-IM Channels & Native Addons**:
  - Connects to WeCom (`@wecom/aibot-node-sdk@1.0.7`, `@tencent/wwapi-electron@0.1.25`), Feishu/Lark (`@larksuiteoapi/node-sdk@1.60.0`), DingTalk (`dingtalk-stream@2.1.5`), Slack (`@slack/socket-mode@2.0.7`, `@slack/web-api@7.0.0`), and QQ Bot (`@tencent-connect/qqbot-connector@1.1.0`), accelerated by the Rust NAPI addon `im-napi.node`.
  - Ships native sidecars/addons for `computer-use-launcher`, `wechat-copydata-decoder`, `turing-sdk`, `qimei` (`@tencent/qimei-node@1.2.2`), `perf-metrics`, `default-open-handler`, and `@lydell/node-pty@1.2.0-beta.14`.
- **Local LLM Engine, Release `5.9.4` Product Updates & Self-Updater**:
  - Supports local GGUF model inference via on-demand `llama.cpp` backend packages spanning CPU, CUDA, ROCm, Vulkan, and Intel GPU.
  - `5.9.4` release delta adds 7 UI locales (`ja`, `ko`, `fr`, `es-ES`, `vi`, `th`, `ar`), Message Center, local PPT Presenter View, system theme sync, `high-credit-tools.json` pre-call confirmation gates on Miora media tools, Security Center network policy enforcement on HTTP MCP transports, incremental Gmail OAuth scopes + background token refresh, per-conversation workspace memory opt-out, post-compaction/subagent task state fixes, WPS lock handling, and Windows registry / macOS interrupted-update / V8 compile-cache crash fixes.
  - Implements platform-specific differential/full updaters across macOS (`darwin-arm64` / `darwin-x64`), Windows (`win32-x64` with Authenticode signature verification), and Linux (`.deb`, AppImage self-update, and UOS/Kylin packages) backed by `/v2/update`.
