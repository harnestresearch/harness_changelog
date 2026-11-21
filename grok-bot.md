# Grok Bot Latest Changes

English | [简体中文](zh-CN/grok-bot.md) · **Highlight** | [Full Detail](full/grok-bot.md)

> See [grok-bot/README.md](grok-bot/README.md) for the complete five-platform index (`mac`, `win`, `ubuntu`, `ios`, `android`) covering all 115 historical releases (92 Desktop + 23 iOS; standalone Android unreleased).

## 1.2.0 (2026-11-17, CDN `Last-Modified` UTC+8)

See [grok-bot/2026-11-17_1.2.0.md](grok-bot/2026-11-17_1.2.0.md) for highlights, or [full/grok-bot/2026-11-17_1.2.0.md](full/grok-bot/2026-11-17_1.2.0.md) for full technical details.

> **Verification Scope**: Official update API & `HEAD` metadata confirm `1.2.0` across `mac`, `ubuntu`, and `win`, while static binary diffing covers **Linux `x64` `.deb`** and **macOS `arm64` `.dmg`** only (Windows `Setup.exe` was checked via metadata without downloading; `darwin-x64` and `AppImage` were not analyzed, and binaries were not executed—client protocol/preload/gate/copy additions do not confirm backend rollout).

- **Slack Workspace Install Flow & Third-Party Connections**: Added client protocol state machines and UI copy (`"Connect Slack"`, `"Return to Slack"`) for team-level Slack workspace installation, status checks, and uninstallation, plus per-Bot listing and disconnection of authorized third-party apps (`grok_bot_connected_apps_settings` gate).
- **Skill Revisions, Public Changelog, Order State, File Previews & Flight Copy**: Added client endpoints for listing and reverting Skill revisions with a change-diff view and team publishing prompts, a public read-only changelog feed, shopping order state and contact photo lookups, Bot vs. User file-store read resolution with preview/library gates, five flight-search progress strings, and updated `"Grok's servers did not report a status"` fallback copy.
- **MCP Governance, Microsoft 365 Admin Consent & Squarespace Connector**: Added Grok SSO sign-in flags and organization block-reason text on MCP servers, team MCP allowlist admin fields, a `"connectors-only"` restricted access mode, a built-in Squarespace MCP host (`mcp.squarespace.com`), and Microsoft 365 (Excel, OneDrive, Outlook, Power BI, SharePoint) icons with tenant admin-consent approval prompts, while removing the desktop MCP iframe `unsafe-eval` gate (`allowEval`).
- **Cloud Agent App Secrets Preload Wiring, Account Switch on Sign-Out & Security Controls**: Wired five desktop preload methods for `1.1.0`'s Cloud Agent **App Secrets** subsystem, added optional account switching on sign-out (`switchToAccountId`), a dismissible update-restart prompt, designated team Bot sharers and enterprise seat grant states, tighter local-tool approval target wording, and a default-off sandbox system-proxy auto-follow gate (`sand_system_proxy_auto`).
- **Android Control Tool Slot & Client Surface Adjustments**: Added `AndroidControlDevice` to the static agent tool registry and local approval enum while removing four task CRUD tool entries (`CreateTask`, `ReadTask`, `UpdateTask`, `DeleteTrackedTasks`—retaining `UpdateTrackedTaskTags` and task status descriptions rather than retiring all product task features); removed client-side Factory UI chunks, preload telemetry hooks, and the `grok_bot_factories` gate while retaining Factory RPC/protobuf definitions; and reorganized standalone `telegram.png` / `whatsapp.png` icon files while keeping their bundle identifiers.

---

## Previous Release: 1.1.0 (2026-11-14)

See [grok-bot/2026-11-14_1.1.0.md](grok-bot/2026-11-14_1.1.0.md) for highlights, or [full/grok-bot/2026-11-14_1.1.0.md](full/grok-bot/2026-11-14_1.1.0.md) for full technical details.

- **Factories Multi-Step Pipelines**: Added declarative YAML **Factories** to create, schedule, run, and manage multi-step automated Agent workflows directly in Grok Bot.
- **Cloud Agent Apps & Page Publishing**: Added end-to-end hosting and publishing for Cloud Agent apps and pages, complete with scoped **App Secrets**, pre-publish security reviews and overrides, live previews, and team/organization audience sharing controls.
- **Spotlight Screen Element Picker, Local Meeting Recorder & Speaker Diarization**: Added an interactive screen element picker overlay to Spotlight, local meeting recording with a **Local Pitman** meeting assistant flow, and speaker diarization (`speaker` turn separation) in speech-to-text transcripts.
- **Purchase Auto-Approval, Spend Limits & X App Approval**: Added configurable purchase auto-approval with per-currency spend limits, X Money spend challenges, **"Approve in the X app"** confirmation prompts, and richer order, place, and shopping status cards.
- **Phone Verification, QR Pairing, GitHub Connect & Enterprise Governance**: Added account SMS verification and SMS-authenticated form links, mobile-to-desktop QR pairing, GitHub/SCM repository connection flows, guided Cursor ↔ xAI team unification, organization network blocklists, team Tailscale exit nodes, policy-enforced sandboxing, task-to-transcript linking, and threaded chat replies.

---

## Recent Major Baseline: 1.0.1 (2026-11-11)

See [grok-bot/2026-11-11_1.0.1.md](grok-bot/2026-11-11_1.0.1.md) for highlights, or [full/grok-bot/2026-11-11_1.0.1.md](full/grok-bot/2026-11-11_1.0.1.md) for full technical details.

- **Spotlight Quick Input & Desktop Polish**: Added a Spotlight-style quick input bar, window size/position memory across restarts, syntax-highlighted code blocks in chat, country flags in language menus, and a major desktop runtime upgrade.
- **Status Chimes & Voice Diagnostics**: Added optional audio cues for task sent, result returned, awaiting decision, and errors, plus clear network/region/certificate diagnostics when voice calls cannot connect.
- **iMessage Group Chats, Commerce & Travel Cards**: Added iMessage group chat history and leave actions, SMS phone verification linking, shopping cart checkout, car rental and click-to-book flight cards, and virtual try-on photo management.
- **Privacy, Passkeys, Agent Store & Team Governance**: Brought privacy mode and training opt-in controls, Passkey sign-in, 1Password vault connections, interactive calendar/meeting & messaging approval cards, the Agent Store marketplace, and enterprise spend/connector governance into the `1.0` stable channel.
