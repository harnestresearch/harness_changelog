# Grok Bot Latest Changes

English | [简体中文](../zh-CN/full/grok-bot.md) · [Highlight](../grok-bot.md) | **Full Detail**

> See [grok-bot/README.md](grok-bot/README.md) for the complete five-platform index (`mac`, `win`, `ubuntu`, `ios`, `android`) covering all 115 historical releases (92 Desktop + 23 iOS; standalone Android unreleased).

## 1.2.0 (2026-11-17, CDN `Last-Modified` UTC+8)

See [grok-bot/2026-11-17_1.2.0.md](grok-bot/2026-11-17_1.2.0.md) for full details.

- **Protocol Diffs, Main-Process Network Stack Migration & Evidence Scope**
  - Official update API & `HEAD` metadata confirm `1.2.0` (`commitSha: cf0aa5097b8fdfea8f2ecd33ce9f71a72655ef08`) across `darwin-arm64`, `linux-x64`, and `win32-x64-user`, while static binary diffing covers **Linux `x64` `.deb`** (via update API `debUrl`; `aptrepo` `Packages` no longer lists `grok-bot`) and **macOS `arm64` `.dmg`** only (Windows `Setup.exe` checked via metadata without downloading; `darwin-x64` and `AppImage` unanalyzed; no runtime execution; static client surfaces do not confirm backend rollout).
  - Expanded `aiserver.v1.GrokBotService` `515 → 529` methods (`+14 / −0`, all 14 `Unary`; `509 → 523` `Unary` + `6` `ServerStreaming`), protobuf messages `3,087 → 3,127` (`+43 / −3`), and enums `470 → 476` (`+6 / −0`), with **4 protobuf field removals** (`GetTeamPrepaidBillingResponse.uncovered_spend_cents`, `GetUserPrepaidBillingResponse.uncovered_spend_cents`, `SendMessageArgs.to_main_chat`, and `ComposerCapabilityContext.GithubPRContext.conflict_resolution` + 3 nested messages).
  - Relocated networking/proxy runtime code (`undici` / `EnvHttpProxyAgent` / `ProxyAgent`, `239` migrated strings) from `main-app.cjs` (`−509` KB) into `main-core.cjs` (`+433` KB), adding default-off Statsig gates `sand_system_proxy_auto` and `sand_system_proxy_auto_kill_switch` (`trustSystemRoots`).
- **Slack Workspace Install, Third-Party Connections, Skill Revisions & Public Changelog**
  - Added `Get/Start/UninstallGrokBotSlackWorkspaceInstall` (`StartOutcome` / `State` / `UninstallOutcome`), `List/DisconnectGrokBotThirdPartyConnection` (`grok_bot_connected_apps_settings`), `ListGrokBotSkillRevisions` / `RevertGrokBotSkill` (`GrokBotSkillRevisionAuthor`, `chunk-skill-change-diff`, `grok_bot_skill_links_in_chat`, team publishing copy), `ListPublicGrokBotChangelog`, internal `Get/SetGrokBotPaperTermsInternal` (`covered_by_paper_addendum`), `GetGrokBotShoppingOrderState`, `GetGrokBotMessagingContactPhoto`, `AdminMoveGrokBotMessagingUserLines`, and `ResolveGrokBotAgentFileReads` (`GrokBotAgentFileStore`, `grok_bot_files_open_preview`, `grok_bot_library_tree/writes`).
- **MCP Security, `AppSecrets` Preload Wiring, `AndroidControlDevice` & Client Surface Contraction**
  - Added MCP `grok_sso_sign_in` & `blocked_reason_text`, team `mcp_allowlist_*` settings, `grok_connectors_only_*` (`grokConnectorsOnly`), built-in `mcp.squarespace.com`, and 5 Microsoft 365 SVGs + tenant `adminConsentUrl` copy, while removing `grok_bot_mcp_app_unsafe_eval_desktop` and preload `allowEval`.
  - Wired **5 concrete `CloudAgentAppSecret*` preload methods** (`createCloudAgentAppSecret`, `getCloudAgentAppSecrets`, `listCloudAgentAvailableAppSecrets`, `declineCloudAgentAppSecrets`, `widenCloudAgentAppSecretScope`; extracted preload identifiers move `701 → 709` `+14 / −6`, including property keys), `dismissUpdateRestart`, `logoutCursor(..., switchToAccountId)`, enterprise seat grants (`TeamEnterpriseGrantState`) & `DESIGNATED` Bot sharers, Castle invite tokens, and 5 flight i18n strings.
  - Updated `node-agent-coordinator` static tool registry `201 → 198` (`+AndroidControlDevice`, `−CreateTask` / `ReadTask` / `UpdateTask` / `DeleteTrackedTasks`, retaining `UpdateTrackedTaskTags`), contracted client-side Factory surfaces (`−grok_bot_factories`, `−4` preload telemetry methods, `−chunk-factory-layout` / `chunk-automation-run-rows`, `main-app` `factory` strings `84 → 14`) while retaining Factory RPCs/protobufs, reorganized standalone `telegram.png` / `whatsapp.png` assets, and recorded static descriptor parity across 6 checked RPCs (`0` mismatches) and `UserComputer` / `lexec` frames (`proto.cjs` / `preload.cjs` / `lexec` byte-identical across `.deb` and `.dmg`; static parity does not prove runtime compatibility).

---

## Previous Release: 1.1.0 (2026-11-14)

See [grok-bot/2026-11-14_1.1.0.md](grok-bot/2026-11-14_1.1.0.md) for full details.

- **Purely Additive Protocol Expansion & Runtime Upgrade**
  - Expanded `aiserver.v1.GrokBotService` from `493 → 515` methods (`+22 / −0`), ConnectRPC services from `7 → 11` (`+AppPublishService`, `+UnifiedDashboardService`, `+XaiAccountClosurePartnerService`, `+XaiUnificationPartnerService`), protobuf messages from `2,829 → 3,087` (`+258 / −0`), and enums from `411 → 470` (`+59 / −0`) with zero removals (`proto.cjs` `1,589,070 → 1,730,908` B; `UserComputer` frames byte-identical).
  - **Upgraded Electron `43.8.4 → 43.8.9`** (Chromium `150.0.7871.250`); added `local-meeting-recorder.cjs` (`135,396` B), `preload-spotlight-element-pick-overlay.cjs` (`17,989` B), `watch_scroll_finger_lift` in `sand_notification_settings.node`, AppImage `verifySignature`, and `@anysphere/cursor-icons`.
- **Factories, Cloud Agent Apps & Page Publishing**
  - Launched declarative YAML **Factories** (`List/Save/Run/DeleteGrokBotFactory`, `UpdateFactory` tool, step/schedule validation, `chunk-factory-layout`, gate `grok_bot_factories`).
  - Added Cloud Agent app hosting (`PublishApp`/`UnpublishApp`, `AppDeployment`, `AppAccessList`, `8` preload `CloudAgentPublish*` methods), the **`AppSecrets`** lifecycle (`Create/List/Set/Delete/Bind/Unbind/Widen/Sync/Decline/Request/ApplyAppSecrets`), and **Page Publishing / Security Review / Audience Sharing** (`ProposePublish`, `PublishReview`/`PublishReviewOverride`, `Get/UpdatePublishedPageShare`, `PublishMerge`).
- **Cursor ↔ xAI Unification, Phone/Purchase Controls & Enterprise Security**
  - Added Cursor ↔ xAI account/team merge and checkout ceremonies (`Start/Get/CancelCursorTeamMerge`, `Prepare/FinalizeCursorTeamMergeCheckout`, `CreateUnifiedDashboardTeam`, `CompleteXaiUnificationAfterPurchase`, `XaiCloseAccount`/`XaiReopenAccount`), account phone verification & SMS form submission (`Send/ConfirmGrokBotAccountPhoneCode`, `StartFormLinkOwnerCode`, `SubmitTextedFormLink`), mobile QR pairing (`getPhoneAppQrUrl`), purchase auto-approval & spend limits (`Get/SetGrokBotPurchaseAutoApprove`, `SetGrokBotPurchaseSpendLimit`, `"Approve in the X app"` across 37 locales), `TeamOrganizationNetworkBlocklist`, team `TeamTailnetExitNode` routing, `SandboxingMode.ENFORCED`, `MintSandBoxPluginSyncGitToken`, STT speaker diarization (`SttConfig.diarize`, `SttSpeakerTurn`), `StartGrokBotLocalPitman`, GitHub SCM connect flows, task↔transcript linking, `+8` agent tools (`194 → 202`), and Statsig gates `168 → 184` (`+17 / −1`).

---

## Recent Major Baseline: 1.0.1 (2026-11-11)

See [grok-bot/2026-11-11_1.0.1.md](grok-bot/2026-11-11_1.0.1.md) for full details.

- **Dual-Branch Merge & Runtime Upgrade**
  - Merged the entire `0.78.2 – 0.79.4` feature branch into the `1.0` stable channel, expanding `GrokBotService` from 414 methods in `1.0.0` to **493 methods** (including 30 brand-new methods).
  - **Upgraded Electron to `43.8.4`** (first major upgrade from `42.11.16`), recompiling all 13 native modules.
- **Desktop Experience & Code Rendering**
  - Added a Spotlight-style quick input panel (with focus grace and fallback dismissal policies), window geometry persistence, `tree-sitter`-based chat syntax highlighting (`CodeTokenizerProvider`), and `country-flag-icons` for language selectors.
- **Voice Reachability Probing & Status Chimes**
  - Added `api.x.ai/v1/realtime` reachability probing with granular block reason classification (regional refusal, tunnel refusal, certificate errors, etc.); introduced **Status Chimes** audio cues across four lifecycle events (task sent, result returned, awaiting decision, error).
- **iMessage Group Chats, Commerce Checkout & Car Rental Cards**
  - Added iMessage group chat log retrieval, group leave RPCs, and SMS verification code phone linking flows.
  - Added shopping cart checkout initiation/cancellation RPCs (`Start/CancelGrokBotCartCheckout`), car rental UI cards (`car_rentals` / `car_rental_locations` / `car_rental_detail`), airline logo assets, gift delivery date validation, and click-to-book flight flows.
- **Agent Preference Layers & Team Governance**
  - Added multi-layer Agent preferences, auto-review toggles, private file/skill controls, Slack sharing governance, immediate automation execution, and card-level reruns.
  - Added admin side-by-side dual-model evaluation (`ModelComparison`), team sandbox setup self-tests, enterprise spend limits, blocked-connector policy gates, and restored QuickBooks MCP and Tailscale integrations.
- **Capabilities Graduated from the 0.79.x Branch**
  - User privacy mode and training data opt-in dialogs, Passkey sign-in ceremonies, calendar and server-side meeting protocols, interactive iMessage approval cards, full-text transcript search (`SearchGrokBotTranscripts`), Agent Store marketplace, and 1Password service-account vault connectors.
