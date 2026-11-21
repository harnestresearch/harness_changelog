# Grok Bot Changelog History

English | [简体中文](../zh-CN/grok-bot/README.md) · **Highlight** | [Full Detail](../full/grok-bot/README.md)

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

| Version | Platforms | Release Date | Highlights |
|---|---|---|---|
| [1.2.0](2026-11-17_1.2.0.md) | `mac`, `ubuntu`, `win` (`win` metadata only) | 2026-11-17 (Last-Modified) | Static `.deb`/`.dmg` diff: Slack workspace install/uninstall state machine, per-Bot third-party connections, Skill revisions/rollback & team publish prompts, public changelog RPC, MCP allowlist/connectors-only/Microsoft 365 admin consent/Squarespace, 5 `CloudAgentAppSecret*` preload methods, `AndroidControlDevice` tool slot (`−4` static task CRUD tools), default-off `sand_system_proxy_auto` gate, and contracted client Factory UI/gate surfaces |
| [1.1.0](2026-11-14_1.1.0.md) | `mac`, `win`, `ubuntu` | 2026-11-14 | YAML Factories pipelines, Cloud Agent Apps & Page publishing with App Secrets, Spotlight element picker & local meeting recorder, STT speaker diarization, purchase auto-approval & spend limits, account phone/QR pairing, GitHub connect, Cursor ↔ xAI team unification, and team network blocklists & Tailscale exit nodes |
| [1.0.3](2026-11-13_1.0.3.md) | `mac`, `win`, `ubuntu` | 2026-11-13 | Cross-platform rebuild of 1.0.2 rolling out the personal X account read-access toggle and cumulative 1.0.x desktop features to Ubuntu/Debian APT |
| [1.0.2](2026-11-13_1.0.2.md) | `mac`, `win` | 2026-11-13 | Added "Use my X account for reads" toggle to choose between shared Grok Bot access and your own connected X account |
| [1.0.1](2026-11-11_1.0.1.md) | `mac`, `win`, `ubuntu` | 2026-11-11 | Spotlight quick input bar, Status Chimes, voice reachability diagnostics, iMessage group chats & SMS linking, cart checkout & car rental cards, team model comparison, and upgraded desktop runtime |
| [0.79.4](2026-11-10_0.79.4.md) | `mac`, `win`, `ubuntu` | 2026-11-10 | Fixed Google sign-in callback timeouts for tool connections, refreshed plugin catalogs on team switch, and added Outlook & OneDrive icons |
| [0.79.3](2026-11-06_0.79.3.md) | `mac`, `win`, `ubuntu` | 2026-11-06 | Added fallback toggle for legacy 1Password integration and improved connector badge contrast across light and dark themes |
| [0.79.2](2026-11-05_0.79.2.md) | `mac`, `win`, `ubuntu` | 2026-11-05 | Streamlined offline status banner for clearer localized disconnect notifications |
| [0.79.1](2026-11-05_0.79.1.md) | `mac`, `win` | 2026-11-05 | 1Password service-account vault connector with automatic vault creation and team Bot memories list view |
| [0.79.0](2026-11-05_0.79.0.md) | `mac`, `win` | 2026-11-05 | In-app shopping cart, virtual try-on & flight booking, Agent Store marketplace, Google Calendar & interactive iMessage cards, and full-text transcript search |
| [0.78.5](2026-11-03_0.78.5.md) | `mac`, `win`, `ubuntu` | 2026-11-03 | Fixed missing trial quota exhaustion banner and added localized quota-reset countdowns across 38 languages |
| [0.78.4](2026-11-02_0.78.4.md) | `mac`, `win`, `ubuntu` | 2026-11-02 | Added confirmation feedback and clear error notifications for training data sharing settings |
| [0.78.3](2026-11-02_0.78.3.md) | `mac`, `win` | 2026-11-02 | Interactive training data sharing opt-in modal and usage limit reset dialog in the desktop UI |
| [0.78.2](2026-11-02_0.78.2.md) | `mac`, `win` | 2026-11-02 | User privacy mode toggle, training data opt-in dialog with quota reset option, and voice call feedback cards |
| [0.78.1](2026-10-28_0.78.1.md) | `mac`, `win`, `ubuntu` | 2026-10-28 | Team Bot credential Vault interface for managing shared Bot logins, plus clearer Tailscale troubleshooting guidance |
| [1.0.0](2026-10-27_1.0.0.md) | `mac`, `win` | 2026-10-27 | First 1.0 General Availability release consolidating cross-device linking, computer control, iMessage & phone calls, team credential vaults, and Mail/Teams integrations |
| [0.78.0](2026-10-27_0.78.0.md) | `mac`, `win` | 2026-10-27 | macOS Mail setup wizard, mail/phone/app control permissions, Stripe Link & Shop Pay wallets, and stronger authorization security |
| [0.77.0](2026-10-26_0.77.0.md) | `mac`, `win`, `ubuntu` | 2026-10-26 | QR cross-device linking, voice dictation, outbound call recording, Bot share invites, order tracking, Usage & Billing page, and retirement of Chrome cookie import |
| [0.75.8](2026-10-24_0.75.8.md) | `mac`, `win`, `ubuntu` | 2026-10-24 | Added deployment-level cloud network tunnel controls and automatic wake-up retries for sleeping cloud workspaces |
| [0.75.7](2026-10-24_0.75.7.md) | `mac`, `win` | 2026-10-24 | Improved cloud workspace startup and network connectivity checks when no custom outbound policy is set |
| [0.75.6](2026-10-24_0.75.6.md) | `mac`, `win` | 2026-10-24 | Fixed a background hang in cloud workspace network policy synchronization |
| [0.75.5](2026-10-23_0.75.5.md) | `mac`, `win`, `ubuntu` | 2026-10-23 | Security hardening blocking unauthorized private-network access from cloud tasks unless allowlisted by organization policy |
| [0.75.3](2026-10-22_0.75.3.md) | `mac`, `win`, `ubuntu` | 2026-10-22 | Bot knowledge base management screen, team Bot service account setup wizard, connector shared-space allowlists, and new chat wallpapers |
| [0.75.2](2026-10-22_0.75.2.md) | `mac`, `win`, `ubuntu` | 2026-10-22 | Fixed an account-switching race condition when loading Canvas workspaces |
| [0.75.1](2026-10-21_0.75.1.md) | `mac`, `win` | 2026-10-21 | Clearer sign-in error messages when the authentication service is unreachable or login is interrupted |
| [0.75.0](2026-10-21_0.75.0.md) | `mac`, `win`, `ubuntu` | 2026-10-21 | X, Shop & Cloudflare connectors, memory import, quoted message replies, richer tray animations, and browser sign-in link recovery |
| [0.73.1](2026-10-20_0.73.1.md) | `mac` | 2026-10-20 | Stable macOS build released the same day as 0.72.1 and superseded by 0.75.0 the following day; the 0.73.x builds were skipped by the stable-CDN archive and no per-version release notes were published |
| [0.72.1](2026-10-20_0.72.1.md) | `mac`, `win`, `ubuntu` | 2026-10-20 | Added automatic system proxy and SOCKS proxy support for improved network connectivity |
| [0.72.0](2026-10-18_0.72.0.md) | `mac`, `win`, `ubuntu` | 2026-10-18 | Animated menu bar tray Bot avatar, payment card vault with macOS card scan, Gmail/Outlook/QuickBooks connectors, and screen capture overlay |
| [0.71.2](2026-10-14_0.71.2.md) | `mac`, `win`, `ubuntu` | 2026-10-14 | Routine maintenance build with no user-facing changes |
| [0.71.1](2026-10-13_0.71.1.md) | `mac`, `win` | 2026-10-13 | Routine maintenance build with no user-facing changes |
| [0.71.0](2026-10-13_0.71.0.md) | `mac`, `win` | 2026-10-13 | Canvas user & group sharing permissions, auto-review approval UI, multi-workspace Slack status, and Linux package update checks |
| [0.70.2](2026-10-11_0.70.2.md) | `mac`, `win`, `ubuntu` | 2026-10-11 | Routine maintenance and stability improvements |
| [0.70.1](2026-10-11_0.70.1.md) | `mac`, `win` | 2026-10-11 | Improved task execution reliability with graceful cloud fallback when local computer connection fails |
| [0.70.0](2026-10-10_0.70.0.md) | `mac`, `win` | 2026-10-10 | Conversation rollback & fresh restart, per-tool connector permissions, team service accounts UI, Linux computer control, and admin email governance |
| [0.69.1](2026-10-09_0.69.1.md) | `mac`, `win` | 2026-10-09 | Improved loading reliability for embedded connector app views with automatic retry on transient network errors |
| [0.69.0](2026-10-08_0.69.0.md) | `mac`, `win` | 2026-10-08 | Microsoft Teams app & chat integration, configurable tool approval modes, recurring calendar validation, and balance top-up modal |
| [0.68.1](2026-10-06_0.68.1.md) | `mac`, `win`, `ubuntu` | 2026-10-06 | Fixed departed member names lingering in auto-named group chats and improved @mention matching |
| [0.68.0](2026-10-05_0.68.0.md) | `mac`, `win` | 2026-10-05 | Low-latency streaming voice calls, ElevenLabs/Cloudflare/Runway connectors, Notion write tools, Buy Credits shortcut, and Word/Markdown viewers |
| [0.67.0](2026-10-02_0.67.0.md) | `mac`, `win` | 2026-10-02 | Cloud-hosted meeting participation, inline draft revision highlighting, "Always allow" local tool permissions, and live Bot status phrases |
| [0.66.0](2026-10-01_0.66.0.md) | `mac`, `win`, `ubuntu` | 2026-10-01 | Granular Bot access sharing, profile picture updates, macOS Move-to-Applications prompt, and default cloud task secure tunneling |
| [0.65.0](2026-09-30_0.65.0.md) | `mac`, `win` | 2026-09-30 | Microsoft Teams meeting support, Finance & Shopify connectors, macOS notification sync, and time zone/theme/language preferences |
| [0.64.0](2026-09-30_0.64.0.md) | `mac`, `win` | 2026-09-30 | Rich document link cards across 16+ apps, Bot co-manager assignment, drafting toggle, and voice memo waveforms |
| [0.63.0](2026-09-29_0.63.0.md) | `mac`, `win`, `ubuntu` | 2026-09-29 | Bot document library, X handle search filters, system root certificate support, and more natural voice call task updates |
| [0.62.0](2026-09-28_0.62.0.md) | `mac`, `win` | 2026-09-28 | Visual Bot avatars in Google Meet & Zoom, spell-check dictionary additions, and Simplified/Traditional Chinese & Cantonese support |
| [0.61.0](2026-09-26_0.61.0.md) | `mac`, `win`, `ubuntu` | 2026-09-26 | Image and tiled attachment previews inside desktop Bot widgets, plus edit permission checks for shared Canvas documents |
| [0.60.0](2026-09-26_0.60.0.md) | `mac` | 2026-09-26 | Team Skill & Agent Store publishing, store directory browsing, Slack account unlinking, and cloud sandbox sleep/wake improvements |
| [0.59.1](2026-09-26_0.59.1.md) | `mac`, `win`, `ubuntu` | 2026-09-26 | Routine maintenance and stability improvements |
| [0.59.0](2026-09-25_0.59.0.md) | `mac` | 2026-09-25 | Google Meet & Zoom live transcription and meeting summaries, X & HubSpot connectors, 1Password OAuth sign-in, and Bot cloning to teams |
| [0.58.0](2026-09-22_0.58.0.md) | `mac`, `win`, `ubuntu` | 2026-09-22 | Floating desktop Bot widget, organization Bot template publishing & share cards, redesigned team setup wizard, and 4 new languages |
| [0.57.1](2026-09-18_0.57.1.md) | `mac`, `win`, `ubuntu` | 2026-09-18 | Routine maintenance and stability improvements |
| [0.57.0](2026-09-18_0.57.0.md) | `mac`, `ubuntu` | 2026-09-18 | Rich Notion/GitHub/Slack link previews, cloud PR monitoring & CI failure investigation workflows, and team Bot starter tasks |
| [0.56.1](2026-09-17_0.56.1.md) | `mac`, `win`, `ubuntu` | 2026-09-17 | Upgraded default real-time voice call model to Grok Voice 3.0 and improved call connection reliability |
| [0.56.0](2026-09-17_0.56.0.md) | `mac`, `win` | 2026-09-17 | Streamlined GitHub connection flow, Bot email & team policy settings, secret carry-over to team Bots, and network proxy support |
| [0.55.0](2026-09-16_0.55.0.md) | `mac`, `win`, `ubuntu` | 2026-09-16 | GitHub connection unlinking, synchronized voice playback timestamps, and automatic tool refresh on account switch |
| [0.54.0](2026-09-16_0.54.0.md) | `mac`, `win` | 2026-09-16 | Email attachment reading for Bots, rich status tags in the prompt editor, and clearer secret saving feedback |
| [0.53.0](2026-09-15_0.53.0.md) | `mac`, `win`, `ubuntu` | 2026-09-15 | GitHub Pull Request chat rooms, Slack DM permissions, automatic 1Password sync on app focus, and team sandbox templates |
| [0.52.0](2026-09-15_0.52.0.md) | `mac`, `win` | 2026-09-15 | Connectors & Plugins settings pages, Slack setup wizard, Bot email inboxes, group room member invites, and model picker badges |
| [0.51.0](2026-09-14_0.51.0.md) | `mac`, `win`, `ubuntu` | 2026-09-14 | Cloud sync for pinned Bots & sidebar sections, Bot to-do lists, fullscreen file viewer, voice memo bubbles, and smoother voice calls |
| [0.50.0](2026-09-11_0.50.0.md) | `mac`, `win` | 2026-09-11 | Routine maintenance release with no user-facing changes |
| [0.49.0](2026-09-11_0.49.0.md) | `mac`, `win` | 2026-09-11 | Bot Canvas read/write tools, live GitLab/Bitbucket/Azure DevOps sign-in, Linear & BigQuery integrations, and Bot skill management |
| [0.47.0](2026-09-09_0.47.0.md) | `mac`, `win`, `ubuntu` | 2026-09-09 | Routine maintenance release with no user-facing changes |
| [0.46.0](2026-09-09_0.46.0.md) | `mac`, `win` | 2026-09-09 | 1Password integration, GitLab/Bitbucket/Azure DevOps connectors, PR & CI webhooks, plugin marketplace, and network diagnostics |
| [0.44.0](2026-09-06_0.44.0.md) | `mac`, `win`, `ubuntu` | 2026-09-06 | Account merging, team-level Bot management, in-chat credential submission prompts, auto-review controls, and Linux self-updates |
| [0.43.0](2026-09-04_0.43.0.md) | `mac`, `win`, `ubuntu` | 2026-09-04 | Routine maintenance build with no user-facing functional changes |
| [0.42.0](2026-09-04_0.42.0.md) | `mac`, `win` | 2026-09-04 | Routine maintenance build with no user-facing functional changes |
| [0.41.0](2026-09-04_0.41.0.md) | `mac`, `win` | 2026-09-04 | Interactive shared Canvas rendering, personal prepaid billing & auto top-up, and GitHub Enterprise authorization |
| [0.40.0](2026-09-03_0.40.0.md) | `mac`, `win` | 2026-09-03 | Team prepaid balances & auto top-up rules, admin cloud session management, and Urdu, Thai & Bengali language support |
| [0.39.0](2026-09-03_0.39.0.md) | `mac`, `win`, `ubuntu` | 2026-09-03 | Contacts lookup for Messages, workspace layout persistence across restarts, and Vietnamese, Indonesian & Cantonese localization |
| [0.38.0](2026-09-03_0.38.0.md) | `mac`, `win` | 2026-09-03 | Persistent per-Bot memory folders, improved prompt editor shortcuts & list formatting, and more reliable sign-in profile loading |
| [0.37.0](2026-09-03_0.37.0.md) | `mac`, `win` | 2026-09-03 | X Money connector, email & Slack draft sending/discarding, connector card views, and cloud sync for tool server settings |
| [0.36.0](2026-09-02_0.36.0.md) | `mac`, `win`, `ubuntu` | 2026-09-02 | Multi-Bot group chat rooms, Bot automations list, preset role categories, voice picker, and private inference settings |
| [0.35.0](2026-09-02_0.35.0.md) | `mac`, `win` | 2026-09-02 | Real-time voice call transcription, natural interruption handling, and Dutch & Spanish authorization prompts |
| [0.34.0](2026-09-01_0.34.0.md) | `mac`, `win` | 2026-09-01 | Redesigned Bot creation & character picker, live computer screen preview, and Bot template editor dialogs |
| [0.33.0](2026-09-01_0.33.0.md) | `mac`, `win` | 2026-09-01 | macOS computer control, voice call speech routing, iMessage setup retry, and one-time tool approvals |
| [0.32.0](2026-09-01_0.32.0.md) | `mac`, `win` | 2026-09-01 | macOS permission onboarding checks for Messages and browser import, plus cloud onboarding improvements |
| [0.31.0](2026-09-01_0.31.0.md) | `mac`, `win` | 2026-09-01 | Stripe Link payments, form autofill vault, team onboarding & settings copy tools, and connector status indicators |
| [0.30.0](2026-08-28_0.30.0.md) | `mac`, `win`, `ubuntu` | 2026-08-28 | macOS iMessage integration, live voice calls, Canvas workspace, virtual card approvals, usage dashboard, and 14 app connectors |
| [0.29.0](2026-08-27_0.29.0.md) | `mac`, `win` | 2026-08-27 | Bot Marketplace listing & review workflow, computer control panel, Slack app reinstall, and website anti-bot block detection |
| [0.28.0](2026-08-26_0.28.0.md) | `mac`, `win` | 2026-08-26 | Slack app install & draft workflow, Jira & Linear integrations, privacy mode, and Bot visibility settings |
| [0.27.0](2026-08-25_0.27.0.md) | `mac`, `win` | 2026-08-25 | Bot template visibility controls, granular sharing permissions, composer draft persistence, and local Chrome web automation |
| [0.26.0](2026-08-25_0.26.0.md) | `mac`, `win` | 2026-08-25 | Organization service accounts, Bot file recycle bin, PR Code Tours, web link previews, and 80+ language syntax highlighting |
| [0.25.0](2026-08-25_0.25.0.md) | `mac`, `win` | 2026-08-25 | Bot templates, remote computer control, Chrome login import, multi-member chat rooms, and custom notification sounds |
| [0.24.0](2026-08-21_0.24.0.md) | `mac`, `win` | 2026-08-21 | Initial desktop release with an AI agent workspace, cloud sandbox execution, document reading, and Google Workspace & Slack integrations |
| [0.23.0](2026-08-20_0.23.0.md) | `mac`, `win` | 2026-08-20 | Last preview-era build before 0.24.0 (2026-08-21), the first version captured by the stable-CDN archive; shipped for both macOS and Windows |
| [0.22.0](2026-08-20_0.22.0.md) | `mac` | 2026-08-20 | Routine macOS-only build in the initial preview era; no per-version release notes were published |
| [0.21.0](2026-08-19_0.21.0.md) | `mac`, `win` | 2026-08-19 | First desktop release to ship a Windows build — the `win` channel begins with this version alongside the existing macOS release, Preview-era build; no per-version release notes were published |
| [0.20.0](2026-08-14_0.20.0.md) | `mac` | 2026-08-14 | Routine macOS build in the initial preview era; no per-version release notes were published |
| [0.19.0](2026-08-14_0.19.0.md) | `mac` | 2026-08-14 | Routine macOS build in the initial preview era; no per-version release notes were published |
| [0.18.0](2026-08-12_0.18.0.md) | `mac` | 2026-08-12 | Routine macOS build in the initial preview era (macOS-only — the Windows channel did not exist yet); no per-version release notes were published |
| [0.17.0](2026-08-12_0.17.0.md) | `mac` | 2026-08-12 | Routine macOS build in the initial preview era, released one day after 0.16.0; no per-version release notes were published |
| [0.16.0](2026-08-11_0.16.0.md) | `mac` | 2026-08-11 | Earliest tracked release of the Grok Bot desktop client, published for macOS only in the initial preview era; no per-version release notes were published |

## Mobile Version Index (`ios`, Newest → Oldest)

| Version | Platforms | Release Date | Highlights |
|---|---|---|---|
| [1.25.0](2026-11-12_1.25.0.md) | `ios` | 2026-11-12 | Routine bug fixes and improvements, as published in the App Store release notes |
| [1.24.1](2026-11-06_1.24.1.md) | `ios` | 2026-11-06 | General bug fixes and stability improvements |
| [1.19.1](2026-11-05_1.19.1.md) | `ios` | 2026-11-05 | Routine bug fixes and stability improvements |
| [1.19.0](2026-10-29_1.19.0.md) | `ios` | 2026-10-29 | Routine bug fixes and stability improvements |
| [1.18.0](2026-10-24_1.18.0.md) | `ios` | 2026-10-24 | General bug fixes and app stability improvements |
| [1.17.0](2026-10-22_1.17.0.md) | `ios` | 2026-10-22 | Improved the design of the Connect Apps screen |
| [1.16.0](2026-10-19_1.16.0.md) | `ios` | 2026-10-19 | Fixed the + button sometimes being incorrectly grayed out, Improved overall app performance |
| [1.14.0](2026-10-07_1.14.0.md) | `ios` | 2026-10-07 | Messages send faster and bots start replying faster, Getting started is quicker, so you can meet your first bot and start chatting sooner, Improved the information hierarchy of your bot's profile |
| [1.13.1](2026-10-02_1.13.1.md) | `ios` | 2026-10-02 | Routine bug fixes and stability improvements |
| [1.13.0](2026-10-01_1.13.0.md) | `ios` | 2026-10-01 | Reactions are more lively and easier to reach, Smarter haptics and smoother photo viewing |
| [1.12.0](2026-09-25_1.12.0.md) | `ios` | 2026-09-25 | Improved the performance of launching voice chat |
| [1.11.1](2026-09-19_1.11.1.md) | `ios` | 2026-09-19 | Fixed the voice chat audio routing issue, Improved the performance of audio processing in voice chat |
| [1.11.0](2026-09-18_1.11.0.md) | `ios` | 2026-09-18 | Tap a photo you have attached to preview it full screen before sending, Unsent message text is kept per chat when you leave and come back, Two photos stack and three or more fan out with a tappable count that opens a grid; full-screen photos show a loading or "couldn't load" state instead of staying black, Improved first sign-in time |
| [1.10.0](2026-09-16_1.10.0.md) | `ios` | 2026-09-16 | Improved performance in long chats, Fixed markdown table rendering, an image carousel bug, and chat attach-menu positioning |
| [1.8.0](2026-09-10_1.8.0.md) | `ios` | 2026-09-10 | Message text can now be selected and copied, Sharing a bot as a template now includes a confirm step, and a notification-sound setting was added, Opening a notification now switches to the matching account first |
| [1.6.0](2026-09-05_1.6.0.md) | `ios` | 2026-09-05 | The app now supports iPad, Bot replies now render LaTeX and diagrams, Improved the image viewer and voice dictation support, with overall performance improvements |
| [1.4.0](2026-08-28_1.4.0.md) | `ios` | 2026-08-28 | The home list loads faster, long conversations use less memory, and chat scrolls more smoothly, A diagram in a bot's reply now draws as a picture instead of showing its raw code, Long-press a bot on the home list to duplicate it, and attaching HEIC images is now supported |
| [1.3.2](2026-08-27_1.3.2.md) | `ios` | 2026-08-27 | General bug fixes and stability improvements |
| [1.3.1](2026-08-23_1.3.1.md) | `ios` | 2026-08-23 | A routine maintenance release with general bug fixes and stability improvements |
| [1.3](2026-08-22_1.3.md) | `ios` | 2026-08-22 | Fixed a blank launch screen that could prevent using the app, and fixed large file and audio attachments, Dictation was redesigned so recording and sending are clearer, and a Haptics setting was added, Plugin integrations now return straight into the app, sharing from other apps is supported, and chat, notifications, and computer reconnect were improved |
| [1.2](2026-08-19_1.2.md) | `ios` | 2026-08-19 | Routine bug fixes and stability improvements across the app |
| [1.1](2026-08-15_1.1.md) | `ios` | 2026-08-15 | Setup is faster and clearer, with polished chat scrolling, message transitions, and home screen, Creating and managing bots is simpler, with more control over remote computers and clearer plans, account linking, and usage, Added Send Feedback in Settings; fixed broken tables in chat, computer reconnect issues, stale background chats, and text jumping back after send |
| [1.0](2026-08-13_1.0.md) | `ios` | 2026-08-13 | Grok Bot's first App Store release for iOS; no release notes were published for this version |
