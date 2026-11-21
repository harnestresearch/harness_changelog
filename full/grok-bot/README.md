# Grok Bot Changelog History

English | [简体中文](../../zh-CN/full/grok-bot/README.md) · [Highlight](../../grok-bot/README.md) | **Full Detail**

Complete multi-platform version history covering **115** unified releases of Grok Bot (`co.anysphere.sand`) across `mac`, `win`, `ubuntu`, `ios`, and `android` (**92** Desktop releases + **23** iOS releases).

## Five-Platform Coverage Overview

| Platform | Distribution / Package | Tracked Releases | Version Range | Latest Version |
|---|---|---|---|---|
| `mac` | macOS (`Grok Bot.app` CDN & Cask) | 92 | `0.16.0` → `1.2.0` | [1.2.0](2026-11-17_1.2.0.md) |
| `win` | Windows (`xAI.GrokBot` Setup & Winget) | 82 | `0.21.0` → `1.2.0` | [1.2.0](2026-11-17_1.2.0.md) (`1.2.0` metadata only) |
| `ubuntu` | Ubuntu / Debian (`.deb` via APT / Update API) | 38 | `0.30.0` → `1.2.0` | [1.2.0](2026-11-17_1.2.0.md) |
| `ios` | iOS App Store (`co.anysphere.sand`) | 23 | `1.0` → `1.25.0` | [1.25.0](2026-11-12_1.25.0.md) |
| `android` | Standalone Grok Bot (`co.anysphere.sand`) | 0 | _No standalone Android release yet_ | — |

## Desktop Version Index (`mac` / `win` / `ubuntu`, Newest → Oldest)

| Version | Platforms | Release Date | Key Changes |
|---|---|---|---|
| [1.2.0](2026-11-17_1.2.0.md) | `mac`, `ubuntu`, `win` (`win` metadata only) | 2026-11-17 (Last-Modified) | Static `.deb`/`.dmg` diff: `GrokBotService` `515 → 529` (`+14 / −0` `Unary`), messages `3,087 → 3,127` (`+43 / −3`, `4` field removals); `main-app → main-core` network/proxy stack migration (`+433` KB) with default-off `sand_system_proxy_auto`; Slack workspace install RPCs, third-party connections, Skill revisions/publishing, `ListPublicGrokBotChangelog`, MCP allowlist/connectors-only/Microsoft 365 admin consent/`mcp.squarespace.com`, 5 `CloudAgentAppSecret*` preload methods, `AndroidControlDevice` (`201 → 198` static tools, `−CreateTask`/`ReadTask`/`UpdateTask`/`DeleteTrackedTasks`), and contracted client Factory UI/gate/telemetry surfaces |
| [1.1.0](2026-11-14_1.1.0.md) | `mac`, `win`, `ubuntu` | 2026-11-14 | Expanded `GrokBotService` `493 → 515` (`+22 / −0`), services `7 → 11`, and messages `2,829 → 3,087` (`+258 / −0`); added YAML Factories, `AppPublishService` & `AppSecrets`, Page publish/review/sharing, Cursor ↔ xAI unification, Local Pitman & `local-meeting-recorder.cjs`, Spotlight element-pick overlay, STT diarization, purchase spend limits, team network blocklists & Tailscale exit nodes, `SandboxingMode.ENFORCED`, and Electron `43.8.9` |
| [1.0.3](2026-11-13_1.0.3.md) | `mac`, `win`, `ubuntu` | 2026-11-13 | Cross-platform rebuild of 1.0.2 (zero code/wire-schema diffs vs. 1.0.2; Sentry UUID & chunk hash rotation only), rolling out cumulative 0.79.4 → 1.0.3 desktop changes to Ubuntu/Debian `aptrepo` `.deb` |
| [1.0.2](2026-11-13_1.0.2.md) | `mac`, `win` | 2026-11-13 | Wired up `GrokBotXToolAccess` (`getXToolAccess` / `setXToolAccess`: `own` vs. `shared`) across preload, main process, coordinator watch dispatch, and Settings UI (zero wire-schema changes) |
| [1.0.1](2026-11-11_1.0.1.md) | `mac`, `win`, `ubuntu` | 2026-11-11 | Dual-branch convergence release: merged the entire 0.79.x feature line and upgraded Electron to 43.8.4 for the first time, expanding `GrokBotService` to 493 methods |
| [0.79.4](2026-11-10_0.79.4.md) | `mac`, `win`, `ubuntu` | 2026-11-10 | Fixed MCP Loopback OAuth Google sign-in callback timeout; added toggle to preserve plugin directory across team switches |
| [0.79.3](2026-11-06_0.79.3.md) | `mac`, `win`, `ubuntu` | 2026-11-06 | Added fallback to legacy implementation for 1Password integration; cleaned up dual-write cache for sandbox attachment pre-uploads |
| [0.79.2](2026-11-05_0.79.2.md) | `mac`, `win`, `ubuntu` | 2026-11-05 | Simplified Offline Banner rendering logic |
| [0.79.1](2026-11-05_0.79.1.md) | `mac`, `win` | 2026-11-05 | Launched 1Password vault connector |
| [0.79.0](2026-11-05_0.79.0.md) | `mac`, `win` | 2026-11-05 | Launched end-to-end e-commerce workflow, Agent Store marketplace, calendar/meeting and message card protocols, plus Realtime voice event stream |
| [0.78.5](2026-11-03_0.78.5.md) | `mac`, `win`, `ubuntu` | 2026-11-03 | Adjusted trial quota exhaustion banner display logic; added localized quota reset countdown formatting |
| [0.78.4](2026-11-02_0.78.4.md) | `mac`, `win`, `ubuntu` | 2026-11-02 | Completed data sharing (training opt-in) result feedback flow and failure toast notifications |
| [0.78.3](2026-11-02_0.78.3.md) | `mac`, `win` | 2026-11-02 | Implemented frontend data sharing (`dataSharing`) state management and wired up the training opt-in modal |
| [0.78.2](2026-11-02_0.78.2.md) | `mac`, `win` | 2026-11-02 | Training opt-in modal + user privacy mode protocol |
| [0.78.1](2026-10-28_0.78.1.md) | `mac`, `win`, `ubuntu` | 2026-10-28 | Shipped team Bot credential Vault UI |
| [1.0.0](2026-10-27_1.0.0.md) | `mac`, `win` | 2026-10-27 | First 1.0 GA release: branded release built on the stable 0.78.1 baseline |
| [0.78.0](2026-10-27_0.78.0.md) | `mac`, `win` | 2026-10-27 | Introduced jose/JWKS token verification and ML-DSA post-quantum signatures; expanded tool permission model to email, phone, and app control |
| [0.77.0](2026-10-26_0.77.0.md) | `mac`, `win`, `ubuntu` | 2026-10-26 | Connected cross-device capabilities ("device linking + local execution daemon + iMessage/outbound phone calls"); launched Bot share invites and usage billing page |
| [0.75.8](2026-10-24_0.75.8.md) | `mac`, `win`, `ubuntu` | 2026-10-24 | Shipped cloud deployment egress tunnel policy flag and wake retry mechanism |
| [0.75.7](2026-10-24_0.75.7.md) | `mac`, `win` | 2026-10-24 | Streamlined cloud sandbox egress policy polling stop logic when policy is empty |
| [0.75.6](2026-10-24_0.75.6.md) | `mac`, `win` | 2026-10-24 | Fixed cloud sandbox egress policy polling hang |
| [0.75.5](2026-10-23_0.75.5.md) | `mac`, `win`, `ubuntu` | 2026-10-23 | Added private and reserved IP blocking (SSRF protection) to cloud sandbox egress tunnel |
| [0.75.3](2026-10-22_0.75.3.md) | `mac`, `win`, `ubuntu` | 2026-10-22 | Launched Bot knowledge management UI and team Bot service account setup flow |
| [0.75.2](2026-10-22_0.75.2.md) | `mac`, `win`, `ubuntu` | 2026-10-22 | Fixed account-switching race condition in Canvas storage resolution |
| [0.75.1](2026-10-21_0.75.1.md) | `mac`, `win` | 2026-10-21 | Refined login state error classification (added `login-unreachable` and related states); same-evening hotfix |
| [0.75.0](2026-10-21_0.75.0.md) | `mac`, `win`, `ubuntu` | 2026-10-21 | Added X/Shop/Cloudflare connectors and pele charting engine; introduced memory import, admin RPCs, and login watchdog |
| [0.73.1](2026-10-20_0.73.1.md) | `mac` | 2026-10-20 | Short-lived stable macOS build between 0.72.1 (2026-10-20) and 0.75.0 (2026-10-21); not captured by the stable-CDN archive, so its changes are only observable folded into the 0.75.0 cumulative diff |
| [0.72.1](2026-10-20_0.72.1.md) | `mac`, `win`, `ubuntu` | 2026-10-20 | Added system proxy resolution (including SOCKS detection) in the networking layer, alongside bug fixes |
| [0.72.0](2026-10-18_0.72.0.md) | `mac`, `win`, `ubuntu` | 2026-10-18 | Major release (asar 668→874 files): three new native modules bringing device attestation, card OCR, and window capture; shipped menu bar tray Bot avatar system and significantly expanded connector catalog |
| [0.71.2](2026-10-14_0.71.2.md) | `mac`, `win`, `ubuntu` | 2026-10-14 | Routine build update: refreshed build identifier and frontend chunk hashes |
| [0.71.1](2026-10-13_0.71.1.md) | `mac`, `win` | 2026-10-13 | Routine build update: refreshed version number and build metadata |
| [0.71.0](2026-10-13_0.71.0.md) | `mac`, `win` | 2026-10-13 | Added disconnect watchdog and message worker to the local execution daemon, laying the groundwork for local Computer Use (CUA) |
| [0.70.2](2026-10-11_0.70.2.md) | `mac`, `win`, `ubuntu` | 2026-10-11 | Routine build update: refreshed frontend asset chunk hashes and build identifier |
| [0.70.1](2026-10-11_0.70.1.md) | `mac`, `win` | 2026-10-11 | Optimized local execution daemon credential minting order and failure fallback strategy |
| [0.70.0](2026-10-10_0.70.0.md) | `mac`, `win` | 2026-10-10 | Bot outbound email governance (suppression list, quota, and delivery status management APIs) + team service account UI + MCP tool-level permissions and session rollback |
| [0.69.1](2026-10-09_0.69.1.md) | `mac`, `win` | 2026-10-09 | Added automatic retry on transient transport errors for frontend MCP app resource reads |
| [0.69.0](2026-10-08_0.69.0.md) | `mac`, `win` | 2026-10-08 | Official Microsoft Teams integration (Teams app installation, DMs, group chats, threads), tri-state tool permission modes, local tool scope system, and recurring calendar event validation |
| [0.68.1](2026-10-06_0.68.1.md) | `mac`, `win`, `ubuntu` | 2026-10-06 | Fixed group chat auto-naming retaining departed member names; added frontend lazy-loading guards |
| [0.68.0](2026-10-05_0.68.0.md) | `mac`, `win` | 2026-10-05 | Real-time voice call protocol (OpenAI Realtime-style command/event stream) + ElevenLabs and Cloudflare/Runway MCP connectors; unified billing "Buy Credits" entry |
| [0.67.0](2026-10-02_0.67.0.md) | `mac`, `win` | 2026-10-02 | Retired local meeting windows entirely (removed all `meetings-main`/`preload-meeting*` in favor of server-side meetings); added draft revision highlighting |
| [0.66.0](2026-10-01_0.66.0.md) | `mac`, `win`, `ubuntu` | 2026-10-01 | Agent access principal and cloud sandbox storage stats APIs; enabled Box outbound tunnel (`sand_box_egress_tunnel`) by default |
| [0.65.0](2026-09-30_0.65.0.md) | `mac`, `win` | 2026-09-30 | Added native notification settings module and Microsoft Teams meeting provider; launched meeting transcription/recording APIs and finance connector |
| [0.64.0](2026-09-30_0.64.0.md) | `mac`, `win` | 2026-09-30 | Established connector document deep-link type registry (16 types including GitHub/Jira/Linear/Google/Slack); added agent admin assignment and draft deactivation |
| [0.63.0](2026-09-29_0.63.0.md) | `mac`, `win`, `ubuntu` | 2026-09-29 | Generalized voice call harness naming; added agent document library API and conversational "queued acknowledgment" prompts |
| [0.62.0](2026-09-28_0.62.0.md) | `mac`, `win` | 2026-09-28 | Enabled bots to join Google Meet / Zoom meetings as avatar personas; introduced the `dune` reliability telemetry subsystem |
| [0.61.0](2026-09-26_0.61.0.md) | `mac`, `win`, `ubuntu` | 2026-09-26 | Minor release: expanded `desktop-mount` panel attachment rendering (image/tile renditions) |
| [0.60.0](2026-09-26_0.60.0.md) | `mac` | 2026-09-26 | Launched Agent/Skill Store (`aiserver.v1.AgentStoreService` + chunked upload publishing) and cloud sandbox "park/hibernate" state machine; added `@anysphere/orbit-client` |
| [0.59.1](2026-09-26_0.59.1.md) | `mac`, `win`, `ubuntu` | 2026-09-26 | Routine build update: refreshed frontend asset chunk hashes |
| [0.59.0](2026-09-25_0.59.0.md) | `mac` | 2026-09-25 | Major release: launched meeting agent (`meetings-main.cjs` for Google Meet/Zoom join, transcription, STT) and xAI prepaid commerce module |
| [0.58.0](2026-09-22_0.58.0.md) | `mac`, `win`, `ubuntu` | 2026-09-22 | Shipped `desktop-mount` panel: agents can mount as persistent 320x176 desktop widgets; added organization publish/unpublish support for bot templates |
| [0.57.1](2026-09-18_0.57.1.md) | `mac`, `win`, `ubuntu` | 2026-09-18 | Routine build update: refreshed main process and native module build artifacts |
| [0.57.0](2026-09-18_0.57.0.md) | `mac`, `ubuntu` | 2026-09-18 | Major release: brought Notion/Slack/GitHub connector domain recognition and `notion-fetch` tool into the main process; established cloud agent task type taxonomy (babysit PR, BugBot auto-fix, parallel multi-tasking) and `BackgroundComposer`/`Dashboard` services |
| [0.56.1](2026-09-17_0.56.1.md) | `mac`, `win`, `ubuntu` | 2026-09-17 | Voice model hotfix: switched default model to `grok-voice-3.0` and removed client-side model allowlist validation |
| [0.56.0](2026-09-17_0.56.0.md) | `mac`, `win` | 2026-09-17 | Launched GitHub connection flow and connector OAuth code exchange (`grok.com/connectors-oauth-exchange-code`); added proxy environment variable support in the main process |
| [0.55.0](2026-09-16_0.55.0.md) | `mac`, `win`, `ubuntu` | 2026-09-16 | Minor release: added voice memo telemetry channel `sand.voice_memo` and GitHub disconnect support |
| [0.54.0](2026-09-16_0.54.0.md) | `mac`, `win` | 2026-09-16 | Enabled bots to read email attachment contents (`ReadGrokBotEmailAttachment`); added credential change notifications |
| [0.53.0](2026-09-15_0.53.0.md) | `mac`, `win`, `ubuntu` | 2026-09-15 | Launched Pull Request chat rooms and fine-grained OAuth scopes; enabled admins to enumerate email inboxes and sync 1Password connections |
| [0.52.0](2026-09-15_0.52.0.md) | `mac`, `win` | 2026-09-15 | Connector/plugin settings page took shape: added `@anysphere/marketplace-category` alongside connector cards, native plugin details, Slack installation flow, and related settings components |
| [0.51.0](2026-09-14_0.51.0.md) | `mac`, `win`, `ubuntu` | 2026-09-14 | Cloud sync for user runtime settings (pinned agents / sidebar sections), agent to-do lists, and voice call turn-taking prompt system |
| [0.50.0](2026-09-11_0.50.0.md) | `mac`, `win` | 2026-09-11 | Routine version bump release; no functional changes |
| [0.49.0](2026-09-11_0.49.0.md) | `mac`, `win` | 2026-09-11 | Exposed Canvas read/write as agent tools; expanded team agent management UI, skill/secret CRUD, and Linear/BigQuery connectors |
| [0.47.0](2026-09-09_0.47.0.md) | `mac`, `win`, `ubuntu` | 2026-09-09 | Routine version bump release; no functional changes |
| [0.46.0](2026-09-09_0.46.0.md) | `mac`, `win` | 2026-09-09 | Major release: 1Password credential integration, GitLab/Bitbucket/Azure DevOps connectors, `sand-canvas`/`sand-media` custom protocols, and app auto-update system (+269 files in zip) |
| [0.44.0](2026-09-06_0.44.0.md) | `mac`, `win`, `ubuntu` | 2026-09-06 | Account Collapse, team-level agents, and agent secret submission flow |
| [0.43.0](2026-09-04_0.43.0.md) | `mac`, `win`, `ubuntu` | 2026-09-04 | Routine build update; functionally identical to 0.42.0 |
| [0.42.0](2026-09-04_0.42.0.md) | `mac`, `win` | 2026-09-04 | Routine build update; functionally identical to 0.41.0 |
| [0.41.0](2026-09-04_0.41.0.md) | `mac`, `win` | 2026-09-04 | Shipped shared Canvas (`@anysphere/canvas-shared`, `bundle-v1` format + `canvas-frame` rendering) and `AgentDefinition` blueprint protocol |
| [0.40.0](2026-09-03_0.40.0.md) | `mac`, `win` | 2026-09-03 | Launched cloud Session Box/Pod management system and team prepaid billing |
| [0.39.0](2026-09-03_0.39.0.md) | `mac`, `win`, `ubuntu` | 2026-09-03 | Desktop realtime voice credential minting (`MintDesktopRealtimeVoiceSecret`), Anthropic EFS approval flow, and local UI state persistence key family |
| [0.38.0](2026-09-03_0.38.0.md) | `mac`, `win` | 2026-09-03 | Introduced agent persistent Memory Shard/Folder protocol |
| [0.37.0](2026-09-03_0.37.0.md) | `mac`, `win` | 2026-09-03 | Integrated X Money connector and `mcp.money.x.com` MCP service; added email/Slack draft send protocol and multi-agent room turn-taking mechanism |
| [0.36.0](2026-09-02_0.36.0.md) | `mac`, `win`, `ubuntu` | 2026-09-02 | Multi-agent rooms (group chats), Agent automation list, and preset functional roles (customer support, finance, recruiting) |
| [0.35.0](2026-09-02_0.35.0.md) | `mac`, `win` | 2026-09-02 | Minor release shipping real-time voice call transcription protocol (streaming STT segments) |
| [0.34.0](2026-09-01_0.34.0.md) | `mac`, `win` | 2026-09-01 | Major UI overhaul for new-agent creation and template editor; `messages-helper` helper process took over iMessage handling |
| [0.33.0](2026-09-01_0.33.0.md) | `mac`, `win` | 2026-09-01 | Split main process into three layers (`main`/`main-app`/`main-core`) + connected Mac remote control and voice process routing |
| [0.32.0](2026-09-01_0.32.0.md) | `mac`, `win` | 2026-09-01 | macOS permission onboarding minor release: Full Disk Access, Finder automation, and Chrome Safe Storage authorization checks |
| [0.31.0](2026-09-01_0.31.0.md) | `mac`, `win` | 2026-09-01 | Payments & team management: Stripe Link payment method, form vault, and team settings copy/invite/inventory |
| [0.30.0](2026-08-28_0.30.0.md) | `mac`, `win`, `ubuntu` | 2026-08-28 | Heavyweight release: shipped both iMessage read/write (`@anysphere/messages-mac`) and voice call harness (`wss://api.x.ai/`), alongside local agent mailboxes and virtual cards |
| [0.29.0](2026-08-27_0.29.0.md) | `mac`, `win` | 2026-08-27 | Shipped Marketplace (bot store) listing system: listing CRUD, review status, and image uploads |
| [0.28.0](2026-08-26_0.28.0.md) | `mac`, `win` | 2026-08-26 | End-to-end Slack app install/uninstall flow + Jira integration + privacy mode — formalizing the messaging connector suite |
| [0.27.0](2026-08-25_0.27.0.md) | `mac`, `win` | 2026-08-25 | Refined template permission model: visibility controls and four-level ACL (`read`/`write`/`share`/`delete`) |
| [0.26.0](2026-08-25_0.26.0.md) | `mac`, `win` | 2026-08-25 | Packaging refactor cutting asar size in half + organization/team management protocol + PR Code Tour — same-day architecture and team-enablement major release |
| [0.25.0](2026-08-25_0.25.0.md) | `mac`, `win` | 2026-08-25 | Introduced Agent template system, remote "user computer" control channel, and Chrome data import — evolving from single-agent chat into a distributable, remotely controllable bot platform |
| [0.24.0](2026-08-21_0.24.0.md) | `mac`, `win` | 2026-08-21 | Baseline release: initial desktop version of Grok Bot (internal package name `sand`, author `SpaceXAI`) — single-bundle main process desktop agent already featuring sandbox execution, MCP, Slack/Google integrations, and an early template store |
| [0.23.0](2026-08-20_0.23.0.md) | `mac`, `win` | 2026-08-20 | Last preview-era build before the 0.24.0 baseline (first build captured by the stable-CDN archive); macOS and Windows builds were published the same day |
| [0.22.0](2026-08-20_0.22.0.md) | `mac` | 2026-08-20 | Routine preview-era build on macOS; no per-version release notes were published for this build |
| [0.21.0](2026-08-19_0.21.0.md) | `mac`, `win` | 2026-08-19 | First release of the Windows channel (`win` begins at 0.21.0 per the desktop release index); no per-version release notes were published |
| [0.20.0](2026-08-14_0.20.0.md) | `mac` | 2026-08-14 | Routine preview-era build on macOS; a Wayback-archived Linux .deb artifact shows Linux packaging was already being produced at this point in the preview era |
| [0.19.0](2026-08-14_0.19.0.md) | `mac` | 2026-08-14 | Routine preview-era build on macOS; no per-version release notes were published for this build |
| [0.18.0](2026-08-12_0.18.0.md) | `mac` | 2026-08-12 | Routine preview-era build on macOS, confirmed by a Wayback-archived CDN snapshot of its installer; no per-version release notes were published |
| [0.17.0](2026-08-12_0.17.0.md) | `mac` | 2026-08-12 | Routine preview-era build on macOS; no per-version release notes were published for this build |
| [0.16.0](2026-08-11_0.16.0.md) | `mac` | 2026-08-11 | Earliest tracked desktop release of the preview era; no per-version release notes were published for this build |

## Mobile Version Index (`ios`, Newest → Oldest)

| Version | Platforms | Release Date | Key Changes |
|---|---|---|---|
| [1.25.0](2026-11-12_1.25.0.md) | `ios` | 2026-11-12 | Routine bug fixes and improvements |
| [1.24.1](2026-11-06_1.24.1.md) | `ios` | 2026-11-06 | Routine bug fixes and improvements |
| [1.19.1](2026-11-05_1.19.1.md) | `ios` | 2026-11-05 | Routine bug fixes and improvements |
| [1.19.0](2026-10-29_1.19.0.md) | `ios` | 2026-10-29 | Routine bug fixes and improvements |
| [1.18.0](2026-10-24_1.18.0.md) | `ios` | 2026-10-24 | Routine bug fixes and improvements |
| [1.17.0](2026-10-22_1.17.0.md) | `ios` | 2026-10-22 | Improved design of the Connect Apps screen |
| [1.16.0](2026-10-19_1.16.0.md) | `ios` | 2026-10-19 | Fixed the + button graying out incorrectly and improved overall performance |
| [1.14.0](2026-10-07_1.14.0.md) | `ios` | 2026-10-07 | Faster message sending and replies, quicker onboarding, and a cleaner bot profile hierarchy |
| [1.13.1](2026-10-02_1.13.1.md) | `ios` | 2026-10-02 | Routine bug fixes and improvements |
| [1.13.0](2026-10-01_1.13.0.md) | `ios` | 2026-10-01 | Livelier, easier-to-reach reactions plus smarter haptics and smoother photo viewing |
| [1.12.0](2026-09-25_1.12.0.md) | `ios` | 2026-09-25 | Faster voice chat launch |
| [1.11.1](2026-09-19_1.11.1.md) | `ios` | 2026-09-19 | Voice chat audio routing fix and improved audio processing performance |
| [1.11.0](2026-09-18_1.11.0.md) | `ios` | 2026-09-18 | Full-screen photo preview before sending, per-chat saved drafts, improved multi-photo display, and faster first sign-in |
| [1.10.0](2026-09-16_1.10.0.md) | `ios` | 2026-09-16 | Long-chat performance improvements and fixes for markdown tables, the image carousel, and attach-menu positioning |
| [1.8.0](2026-09-10_1.8.0.md) | `ios` | 2026-09-10 | Select-and-copy message text, share-as-template confirmation, a notification-sound setting, and smarter notification account switching |
| [1.6.0](2026-09-05_1.6.0.md) | `ios` | 2026-09-05 | iPad support, LaTeX and diagram rendering in replies, plus image viewer, dictation, and performance improvements |
| [1.4.0](2026-08-28_1.4.0.md) | `ios` | 2026-08-28 | Performance gains on the home list and long chats, diagrams rendered as pictures, bot duplication, and HEIC image support |
| [1.3.2](2026-08-27_1.3.2.md) | `ios` | 2026-08-27 | Routine bug fixes and improvements |
| [1.3.1](2026-08-23_1.3.1.md) | `ios` | 2026-08-23 | Routine bug fixes and improvements |
| [1.3](2026-08-22_1.3.md) | `ios` | 2026-08-22 | Launch-screen and attachment fixes, redesigned dictation, smoother plugin integrations, sharing support, and a Haptics setting |
| [1.2](2026-08-19_1.2.md) | `ios` | 2026-08-19 | Routine bug fixes and improvements |
| [1.1](2026-08-15_1.1.md) | `ios` | 2026-08-15 | Faster first-run setup, polished chat and home UI, simplified bot management, and a batch of bug fixes |
| [1.0](2026-08-13_1.0.md) | `ios` | 2026-08-13 | Initial App Store release of Grok Bot for iOS; no release notes were published for this version |
