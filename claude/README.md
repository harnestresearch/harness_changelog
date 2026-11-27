# Claude Changelog History

English | [简体中文](../zh-CN/claude/README.md) · **Highlight** | [Full Detail](../full/claude/README.md)

Complete multi-platform version history covering **534** unified releases across `mac`, `win`, `ubuntu`, `ios`, and `android` (**245** Desktop releases + **289** Mobile releases).

## Five-Platform Coverage Overview

| Platform | Distribution / Package | Tracked Releases | Version Range | Latest Version |
|---|---|---|---|---|
| `mac` | macOS (`Claude.app` / Cask & CDN) | 228 | `0.4.8` → `5.11492.5` | [5.11492.5](2026-11-14_5.11492.5.md) |
| `win` | Windows (`Anthropic.Claude` Winget, Squirrel & MSIX) | 206 | `0.4.9` → `5.11492.5` | [5.11492.5](2026-11-14_5.11492.5.md) |
| `ubuntu` | Ubuntu / Debian APT (`claude-desktop`) | 70 | `1.17180.0` → `5.11492.5` | [5.11492.5](2026-11-14_5.11492.5.md) |
| `ios` | iOS App Store (`com.anthropic.claude`) | 171 | `1.240826.1` → `1.261109.19` | [1.261109.19](2026-11-11_1.261109.19.md) |
| `android` | Android (`com.anthropic.claude`) | 155 | `1.240805.17` → `1.261124.19` | [1.261124.19](2026-11-25_1.261124.19.md) |

## Key Architectural & Feature Milestones

| Milestone | Introduced In | Release Date | Description |
|---|---|---|---|
| Initial Desktop Release | [0.4.8](2024-10-31_0.4.8.md) | 2024-10-31 | Main window + Quick Window, and local MCP tool connection support |
| MCP Management UI & Developer Mode | [0.7.1](2024-11-22_0.7.1.md) | 2024-11-22 | Local MCP server install confirmation, log entry points, and React settings UI |
| Swift Native Addon & Quick Entry | [0.9.4](2025-06-03_0.9.4.md) / [0.12.15](2025-07-14_0.12.15.md) | 2025-06-03 | Introduced macOS system integration, voice dictation permissions and the Quick Entry bar |
| 1.0 GA Release & Built-in Terminal | [1.0.734](2025-11-21_1.0.734.md) / [1.0.2768](2026-01-05_1.0.2768.md) | 2025-11-21 | Entered the `1.x` GA release line and added integrated terminal execution in `1.0.2768` |
| Isolated Cowork Execution Mode | [1.1.280](2026-01-16_1.1.280.md) | 2026-01-16 | Introduced isolated local Cowork workspace execution on macOS |
| Computer Use Native Module | [1.1.8308](2026-03-23_1.1.8308.md) | 2026-03-23 | Added desktop screen viewing and interaction capabilities for Computer Use |
| Faster Offline-Capable Interface | [1.2.234](2026-04-01_1.2.234.md) | 2026-04-01 | Packaged interface assets locally for faster startup and smoother navigation |
| Bundled Skills | [1.15962.0](2026-06-25_1.15962.0.md) | 2026-06-25 | Shipped built-in skill packages including `docx`, `pdf`, `pptx`, `xlsx`, and `frontend-design` |
| `2.x` Major Version Upgrade | [2.110.0](2026-09-15_2.110.0.md) | 2026-09-15 | Upgraded to the `2.x` series, introducing model catalog, self-hosted third-party inference, enterprise managed policies, and cloud sessions |
| `3.x` Artifact Shell Network Bridge | [3.1623.0](2026-10-20_3.1623.0.md) | 2026-10-20 | Upgraded local document & interactive Artifact preview architecture |
| `4.x` Claude Slides, Design Artifacts & Google Connectors | [4.29.0](2026-10-27_4.29.0.md) | 2026-10-27 | Enhanced app integrity verification, followed by interactive Design/Slides Artifacts and Gmail/Drive integrations in [4.16336.0](2026-11-03_4.16336.0.md) |
| `5.x` Built-in Browser Extension Ecosystem | [5.1231.0](2026-11-10_5.1231.0.md) | 2026-11-10 | In-app Chrome Web Store extensions, 1Password login autofill, and interactive 3D Artifact rendering |

## Desktop Version Index (`mac` / `win` / `ubuntu`, Newest → Oldest)

| Version | Platforms | Release Date | Highlights |
|---|---|---|---|
| [5.11492.5](2026-11-14_5.11492.5.md) | `mac`, `win`, `ubuntu` | 2026-11-14 | Enterprise managed file-read policy, Office skill path-traversal & diff hardening, engine session storage validation, and 10-language browser extension/billing localization |
| [5.11492.2](2026-11-13_5.11492.2.md) | `mac`, `win`, `ubuntu` | 2026-11-13 | Enterprise configuration template export, standalone sandbox network permissions, SSH host settings, granular Chrome action prompts, connector OAuth modes, and Windows/Linux security hardening |
| [5.1231.2](2026-11-11_5.1231.2.md) | `mac`, `ubuntu` | 2026-11-11 | Local design system folder support, Compose previews, scheduled task title deduplication, and app update permission prompts |
| [5.1231.0](2026-11-10_5.1231.0.md) | `mac`, `ubuntu` | 2026-11-10 | 5.0 milestone: Chrome Web Store extensions in the built-in browser, 1Password credential autofill, and interactive 3D Artifacts |
| [4.23118.1](2026-11-09_4.23118.1.md) | `mac`, `ubuntu` | 2026-11-09 | Localization updates across 20+ languages, official Anthropic plugin catalog integration, and stability fixes |
| [4.23118.0](2026-11-05_4.23118.0.md) | `mac`, `ubuntu` | 2026-11-05 | Claude Slides presentation import, project-shared rules, session handoff, GitHub/SSH connection UI, and VS Code/JetBrains setup guides |
| [4.16336.0](2026-11-03_4.16336.0.md) | `mac`, `ubuntu` | 2026-11-03 | Official Gmail and Google Drive connectors, interactive Design and Slides Artifacts, MCP App views, and Cowork Linux VM support |
| [4.4212.0](2026-10-29_4.4212.0.md) | `mac`, `ubuntu` | 2026-10-29 | Remote browser connections, custom connector onboarding, Cloudflare challenge handling, and 12+ language updates |
| [4.29.0](2026-10-27_4.29.0.md) | `mac`, `ubuntu` | 2026-10-27 | 4.0 milestone: voice mode sound effects and tone previews, expanded install hub icons, and cryptographic package integrity verification |
| [3.6556.2](2026-10-23_3.6556.2.md) | `mac`, `win`, `ubuntu` | 2026-10-23 | Maintenance and stability update with no user-facing UI changes |
| [3.6556.1](2026-10-22_3.6556.1.md) | `mac`, `win`, `ubuntu` | 2026-10-22 | Google Drive and Slack Enterprise connector support, local interactive Artifact hosting, auto-update status view, and leaner app size |
| [3.1623.4](2026-10-22_3.1623.4.md) | `mac`, `win`, `ubuntu` | 2026-10-22 | Cloud task handoff copies, Claude Dispatch memory export to projects, and Cowork folder-mounting safeguard |
| [3.1623.3](2026-10-22_3.1623.3.md) | `mac`, `win`, `ubuntu` | 2026-10-22 | Refreshed Claude Code multi-cloud connectivity across Bedrock, Vertex, and Foundry, credit purchase flows, and government cloud support |
| [3.1623.1](2026-10-21_3.1623.1.md) | `mac`, `win`, `ubuntu` | 2026-10-21 | Quick Slack Connector setup, full export of chats, projects, and Artifacts, and richer map and chart visualizations |
| [3.1623.0](2026-10-20_3.1623.0.md) | `mac`, `win`, `ubuntu` | 2026-10-20 | 3.0 milestone: live voice transcription, data export folder controls, macOS Liquid Glass sidebar styling, and upgraded Cowork Artifacts |
| [2.42304.2](2026-10-19_2.42304.2.md) | `mac`, `win`, `ubuntu` | 2026-10-19 | Claude Extensions settings view, improved Microsoft Office file handling, and clearer Chrome extension and Artifact status notices |
| [2.42304.0](2026-10-15_2.42304.0.md) | `mac`, `win`, `ubuntu` | 2026-10-15 | Interactive SSH password helper for remote hosts, Slack connector setup UI, semantic memory guidance, and background launch controls |
| [2.37337.1](2026-10-13_2.37337.1.md) | `mac`, `win`, `ubuntu` | 2026-10-13 | Local folder access prompts, pre-bundled chart and diagram rendering for Artifacts, and desktop runtime upgrade |
| [2.31226.1](2026-10-09_2.31226.1.md) | `mac`, `win`, `ubuntu` | 2026-10-09 | Maintenance and stability update with no user-facing UI changes |
| [2.31226.0](2026-10-08_2.31226.0.md) | `mac`, `win`, `ubuntu` | 2026-10-08 | Claude Code settings page with session retention, enterprise tool policies, HIPAA Artifact notices, and Salesforce connector |
| [2.26454.2](2026-10-07_2.26454.2.md) | `mac`, `win`, `ubuntu` | 2026-10-07 | Direct sandbox configuration documentation link in settings and stability fixes |
| [2.26454.0](2026-10-06_2.26454.0.md) | `mac`, `win`, `ubuntu` | 2026-10-06 | Quick Write with built-in session terminal support, Windows-account Microsoft 365 sign-in, browser-only connector auth, and member spend limits |
| [2.19675.1](2026-10-05_2.19675.1.md) | `mac`, `win`, `ubuntu` | 2026-10-05 | Clearer sandbox folder isolation notices and updated PowerPoint presentation generation skills |
| [2.19675.0](2026-10-01_2.19675.0.md) | `mac`, `win` | 2026-10-01 | Repository trust prompts, Android and iOS build guidance, editable Artifact copies, and connector input approvals |
| [2.16120.0](2026-09-30_2.16120.0.md) | `mac`, `win` | 2026-09-30 | Cowork VM EDR security integration, blocked plugin server policies, GitHub Enterprise and GitLab onboarding, and Artifact retention rules |
| [2.9939.4](2026-09-28_2.9939.4.md) | `mac`, `win`, `ubuntu` | 2026-09-28 | Maintenance and stability update with no user-facing UI changes |
| [2.9939.2](2026-09-24_2.9939.2.md) | `mac`, `win` | 2026-09-24 | Maintenance and stability update with no user-facing UI changes |
| [2.9939.1](2026-09-24_2.9939.1.md) | `mac` | 2026-09-24 | Organization plugin and skill marketplace publishing, Artifact comments, and password manager support in Claude in Chrome |
| [2.7032.0](2026-09-22_2.7032.0.md) | `mac`, `win`, `ubuntu` | 2026-09-22 | Official Figma and GitLab connectors, Keep Awake and device tool controls, and enterprise repository and OIDC policies |
| [2.2553.13](2026-09-22_2.2553.13.md) | `mac`, `win`, `ubuntu` | 2026-09-22 | Maintenance and stability update with no user-facing UI changes |
| [2.2553.1](2026-09-18_2.2553.1.md) | `mac`, `win`, `ubuntu` | 2026-09-18 | Maintenance and stability update with no user-facing UI changes |
| [2.2553.0](2026-09-17_2.2553.0.md) | `mac`, `ubuntu` | 2026-09-17 | Claude Code cloud sessions and Remote Control settings, PR auto-fix and auto-archive, Auto permission mode, and plugin allowlists |
| [2.110.1](2026-09-17_2.110.1.md) | `mac`, `ubuntu` | 2026-09-17 | Maintenance and stability update with no user-facing UI changes |
| [2.110.0](2026-09-15_2.110.0.md) | `mac`, `ubuntu` | 2026-09-15 | 2.0 milestone: organization model catalogs, five-tier default effort controls, third-party/self-hosted inference, and tool approval chimes |
| [1.52386.6](2026-09-13_1.52386.6.md) | `mac`, `ubuntu` | 2026-09-13 | Retired the temporary Windows Cowork VM file-share fallback setting in the final 1.x maintenance update |
| [1.52386.4](2026-09-12_1.52386.4.md) | `mac` | 2026-09-12 | Restored Windows Cowork VM file-sharing fallback as an explicit opt-in setting (disabled by default) |
| [1.52386.3](2026-09-11_1.52386.3.md) | `mac`, `win`, `ubuntu` | 2026-09-11 | Removed the Windows Cowork VM file-sharing fallback setting alongside routine stability maintenance |
| [1.52386.1](2026-09-11_1.52386.1.md) | `mac` | 2026-09-11 | Background Git worktree checkouts, GitHub device-code sign-in, and AWS SSO status prompts in Claude Code |
| [1.52386.0](2026-09-11_1.52386.0.md) | `mac`, `ubuntu` | 2026-09-11 | Native OpenSSH engine support for remote sessions, certificate cache management feedback, and session approval notices |
| [1.49585.0](2026-09-08_1.49585.0.md) | `mac`, `win`, `ubuntu` | 2026-09-08 | macOS 13+ minimum system requirement, encrypted Microsoft 365 token storage, streamlined iOS Simulator helper, and localization updates |
| [1.46388.4](2026-09-05_1.46388.4.md) | `mac`, `win` | 2026-09-05 | Maintenance and stability update with no user-facing UI changes |
| [1.46388.3](2026-09-04_1.46388.3.md) | `mac`, `win` | 2026-09-04 | Maintenance and stability update with no user-facing UI changes |
| [1.46388.2](2026-09-04_1.46388.2.md) | `mac`, `win`, `ubuntu` | 2026-09-04 | Maintenance and stability update with no user-facing UI changes |
| [1.46388.1](2026-09-04_1.46388.1.md) | `mac`, `win` | 2026-09-04 | Configurable Remote Control environment reporting levels and Google Cloud Vertex AI support for Claude Code |
| [1.46388.0](2026-09-03_1.46388.0.md) | `mac` | 2026-09-03 | GitHub PR auto-fix and CI check monitoring, multi-format SSH key detection, and hardened Bash shell integration |
| [1.44121.4](2026-09-03_1.44121.4.md) | `mac`, `win` | 2026-09-03 | Maintenance and stability update with no user-facing UI changes |
| [1.44121.2](2026-09-02_1.44121.2.md) | `mac`, `win`, `ubuntu` | 2026-09-02 | Maintenance and stability update with no user-facing UI changes |
| [1.44121.1](2026-09-02_1.44121.1.md) | `mac` | 2026-09-02 | Clearer settings guidance for additional directory permission scopes and remote tool connectivity support |
| [1.44121.0](2026-09-02_1.44121.0.md) | `mac` | 2026-09-02 | Improved Cowork workspace skill script execution and capped per-session skill recommendations |
| [1.40609.1](2026-09-01_1.40609.1.md) | `mac`, `win`, `ubuntu` | 2026-09-01 | Maintenance and stability update with no user-facing UI changes |
| [1.40609.0](2026-08-28_1.40609.0.md) | `mac`, `win`, `ubuntu` | 2026-08-28 | Expanded Word, Excel, and PowerPoint automation skills, PR auto-fix subagents, and Artifact connection views |
| [1.37937.3](2026-08-26_1.37937.3.md) | `mac`, `win`, `ubuntu` | 2026-08-26 | Maintenance and stability update with no user-facing UI changes |
| [1.37937.2](2026-08-26_1.37937.2.md) | `mac` | 2026-08-26 | Maintenance and stability update with no user-facing UI changes |
| [1.37937.1](2026-08-26_1.37937.1.md) | `mac`, `win`, `ubuntu` | 2026-08-26 | Maintenance and stability update with no user-facing UI changes |
| [1.37937.0](2026-08-25_1.37937.0.md) | `mac`, `win`, `ubuntu` | 2026-08-25 | macOS Quick Actions, Spotlight and Handoff integration, standing PR auto-fix authorization, and 13-language updates |
| [1.34493.1](2026-08-21_1.34493.1.md) | `mac`, `win`, `ubuntu` | 2026-08-21 | Maintenance and stability update with no user-facing UI changes |
| [1.34493.0](2026-08-20_1.34493.0.md) | `mac`, `win`, `ubuntu` | 2026-08-20 | Faster app startup, dedicated Design window support, reduced installer footprint, and clearer SSH validation feedback |
| [1.32885.1](2026-08-18_1.32885.1.md) | `mac`, `win`, `ubuntu` | 2026-08-18 | Maintenance and stability update with no user-facing UI changes |
| [1.32885.0](2026-08-18_1.32885.0.md) | `mac` | 2026-08-18 | Embedded content support in Artifacts and clearer file path validation messages |
| [1.32352.1](2026-08-18_1.32352.1.md) | `mac`, `win`, `ubuntu` | 2026-08-18 | Maintenance and stability update with no user-facing UI changes |
| [1.32352.0](2026-08-17_1.32352.0.md) | `mac`, `win`, `ubuntu` | 2026-08-17 | Installed plugin and skill views, Device Hub with iPhone 17 Pro profile, interactive widget actions, and runtime upgrade |
| [1.30096.5](2026-08-15_1.30096.5.md) | `mac`, `win`, `ubuntu` | 2026-08-15 | Maintenance and stability update with no user-facing UI changes |
| [1.30096.1](2026-08-14_1.30096.1.md) | `mac`, `win`, `ubuntu` | 2026-08-14 | Maintenance and stability update with no user-facing UI changes |
| [1.30096.0](2026-08-13_1.30096.0.md) | `mac` | 2026-08-13 | Vetted plugin and skill marketplace widgets, Claude Code hook feedback, credit purchases, and government cloud sign-in |
| [1.28929.0](2026-08-12_1.28929.0.md) | `mac`, `ubuntu` | 2026-08-12 | Remote SSH host connections, GitHub CLI and App sign-in flows, Code Review onboarding, and window styling updates |
| [1.26832.0](2026-08-07_1.26832.0.md) | `mac`, `ubuntu` | 2026-08-07 | GitHub App authorization, scheduled tasks and quick reminders, and richer Artifact sharing and chart previews |
| [1.25927.0](2026-08-04_1.25927.0.md) | `mac`, `win`, `ubuntu` | 2026-08-04 | Built-in GitHub connector, local execution consent window, and expanded Microsoft 365, Box, and Slack integrations |
| [1.24012.11](2026-08-03_1.24012.11.md) | `mac`, `win`, `ubuntu` | 2026-08-03 | Maintenance and stability update with no user-facing UI changes |
| [1.24012.9](2026-07-24_1.24012.9.md) | `mac`, `win`, `ubuntu` | 2026-07-24 | Maintenance and stability update with no user-facing UI changes |
| [1.24012.1](2026-07-21_1.24012.1.md) | `mac`, `win` | 2026-07-21 | Maintenance and stability update with no user-facing UI changes |
| [1.24012.0](2026-07-21_1.24012.0.md) | `mac`, `win`, `ubuntu` | 2026-07-21 | Mobile simulator screen recording, Android Studio detection, contextual skill suggestions, and runtime upgrade |
| [1.22209.3](2026-07-19_1.22209.3.md) | `mac`, `win`, `ubuntu` | 2026-07-19 | Google Cloud Vertex endpoint support for Claude Code and clearer simulator and diff review alerts |
| [1.22209.0](2026-07-16_1.22209.0.md) | `mac`, `ubuntu` | 2026-07-16 | Claude Code iOS Simulator and Android Emulator integration with enterprise admin controls |
| [1.21459.3](2026-07-16_1.21459.3.md) | `mac`, `win`, `ubuntu` | 2026-07-16 | Maintenance and stability update with no user-facing UI changes |
| [1.21459.1](2026-07-16_1.21459.1.md) | `mac`, `win`, `ubuntu` | 2026-07-16 | Maintenance and stability update with no user-facing UI changes |
| [1.21459.0](2026-07-14_1.21459.0.md) | `mac`, `win`, `ubuntu` | 2026-07-14 | Automated routines with API triggers, connector directory policies, enterprise security controls, and transcript search |
| [1.20186.9](2026-07-14_1.20186.9.md) | `mac`, `win`, `ubuntu` | 2026-07-14 | Maintenance and stability update with no user-facing UI changes |
| [1.20186.7](2026-07-14_1.20186.7.md) | `mac`, `ubuntu` | 2026-07-14 | Maintenance and stability update with no user-facing UI changes |
| [1.20186.1](2026-07-11_1.20186.1.md) | `mac`, `win`, `ubuntu` | 2026-07-11 | Maintenance and stability update with no user-facing UI changes |
| [1.20186.0](2026-07-09_1.20186.0.md) | `mac`, `win` | 2026-07-09 | Claude Browser web automation, Cowork per-session folder prompts, and rich-text annotations |
| [1.19367.0](2026-07-07_1.19367.0.md) | `mac`, `win`, `ubuntu` | 2026-07-07 | GitHub PR workflow actions, Slack connector setup, persistent preview sessions, and document drag-and-drop |
| [1.18286.2](2026-07-07_1.18286.2.md) | `mac`, `win`, `ubuntu` | 2026-07-07 | Maintenance and stability update with no user-facing UI changes |
| [1.18286.0](2026-07-02_1.18286.0.md) | `mac`, `win`, `ubuntu` | 2026-07-02 | Chat memory generation toggle, in-session dev-server preview controls, and Office Agents model defaults |
| [1.17377.2](2026-07-01_1.17377.2.md) | `mac`, `win`, `ubuntu` | 2026-07-01 | Maintenance and stability update with no user-facing UI changes |
| [1.17377.1](2026-07-01_1.17377.1.md) | `mac`, `win`, `ubuntu` | 2026-07-01 | Maintenance and stability update with no user-facing UI changes |
| [1.17377.0](2026-06-30_1.17377.0.md) | `mac`, `ubuntu` | 2026-06-30 | Git worktree session status feedback and background task handoff workflows |
| [1.17282.0](2026-06-30_1.17282.0.md) | `mac`, `ubuntu` | 2026-06-30 | Interactive secret redaction and reveal controls, live dev-server preview, and allowed-sites management |
| [1.15962.2](2026-06-30_1.15962.2.md) | `win` | 2026-06-30 | `TODO` (`win`) — _highlights pending_ |
| [1.17180.0](2026-06-29_1.17180.0.md) | `mac`, `ubuntu` | 2026-06-29 | Computer Use watch-and-record teach workflows, role-based default models, and Cowork Always-Allow policies |
| [1.15962.1](2026-06-26_1.15962.1.md) | `mac`, `win` | 2026-06-26 | Maintenance and stability update with no user-facing UI changes |
| [1.15962.0](2026-06-25_1.15962.0.md) | `mac`, `win` | 2026-06-25 | Six built-in document and frontend design skills (docx, pdf, pptx, xlsx) and repository cloning into sessions |
| [1.15200.0](2026-06-23_1.15200.0.md) | `mac`, `win` | 2026-06-23 | Built-in Microsoft 365 admin setup, 1M-context model policy toggle, and expanded enterprise governance controls |
| [1.14271.0](2026-06-18_1.14271.0.md) | `mac`, `win` | 2026-06-18 | Spend-limit controls, organization SSO sign-in prompts, effort-level switching, and subscription management |
| [1.13576.4](2026-06-18_1.13576.4.md) | `mac`, `win` | 2026-06-18 | Maintenance and stability update with no user-facing UI changes |
| [1.13576.1](2026-06-17_1.13576.1.md) | `mac`, `win` | 2026-06-17 | Maintenance and stability update with no user-facing UI changes |
| [1.13576.0](2026-06-16_1.13576.0.md) | `mac`, `win` | 2026-06-16 | Bedrock Mantle gateway option, Claude API key credentials, and admin beta-features toggle |
| [1.12603.1](2026-06-11_1.12603.1.md) | `mac`, `win` | 2026-06-11 | Maintenance and stability update with no user-facing UI changes |
| [1.12603.0](2026-06-11_1.12603.0.md) | `mac` | 2026-06-11 | Built-in Microsoft 365 connector with native sign-in and PDF extraction, plus major runtime upgrade |
| [1.11847.5](2026-06-09_1.11847.5.md) | `mac`, `win` | 2026-06-09 | Interactive gallery view, clearer gateway model-discovery errors, and 11-language updates |
| [1.11187.4](2026-06-05_1.11187.4.md) | `mac`, `win` | 2026-06-05 | Maintenance and stability update with no user-facing UI changes |
| [1.11187.3](2026-06-05_1.11187.3.md) | `mac` | 2026-06-05 | Web interface refresh alongside routine desktop maintenance |
| [1.11187.2](2026-06-05_1.11187.2.md) | `mac` | 2026-06-05 | Web interface refresh alongside routine desktop maintenance |
| [1.11187.1](2026-06-04_1.11187.1.md) | `mac`, `win` | 2026-06-04 | Improved browser automation page inspection, safer credential saving, and localization updates |
| [1.10628.2](2026-06-03_1.10628.2.md) | `mac`, `win` | 2026-06-03 | Web interface refresh alongside routine desktop maintenance |
| [1.10628.0](2026-06-03_1.10628.0.md) | `mac`, `win` | 2026-06-03 | Admin policy toggle for Auto mode, voice playback updates, and 11-language translation refresh |
| [1.9659.4](2026-06-02_1.9659.4.md) | `mac`, `win` | 2026-06-02 | Maintenance and stability update with no user-facing UI changes |
| [1.9659.2](2026-05-29_1.9659.2.md) | `mac`, `win` | 2026-05-29 | Maintenance and stability update with no user-facing UI changes |
| [1.9659.1](2026-05-28_1.9659.1.md) | `mac`, `win` | 2026-05-28 | Box connector integration, SSO-based Claude.ai data import, and per-tab Chat and Cowork admin toggles |
| [1.9255.2](2026-05-27_1.9255.2.md) | `mac`, `win` | 2026-05-27 | Maintenance and stability update with no user-facing UI changes |
| [1.9255.0](2026-05-26_1.9255.0.md) | `mac`, `win` | 2026-05-26 | Outlook connector setup entry, in-Chat code execution policy toggle, and system tray usage groundwork |
| [1.8555.2](2026-05-23_1.8555.2.md) | `mac`, `win` | 2026-05-23 | Web interface refresh alongside routine desktop maintenance |
| [1.8555.1](2026-05-22_1.8555.1.md) | `mac`, `win` | 2026-05-22 | Maintenance and stability update with no user-facing UI changes |
| [1.8555.0](2026-05-21_1.8555.0.md) | `mac`, `win` | 2026-05-21 | Remote MCP server instruction forwarding, credential type categorization, and 11-language translation updates |
| [1.8089.1](2026-05-19_1.8089.1.md) | `mac`, `win` | 2026-05-19 | Maintenance and stability update with no user-facing UI changes |
| [1.8089.0](2026-05-19_1.8089.0.md) | `mac`, `win` | 2026-05-19 | Gateway model discovery, proactive mobile notifications, startup company announcements, and find-in-page improvements |
| [1.7196.3](2026-05-18_1.7196.3.md) | `mac`, `win` | 2026-05-18 | Maintenance and stability update with no user-facing UI changes |
| [1.7196.1+abcd6556](2026-05-16_1.7196.1+abcd6556.md) | `mac`, `win` | 2026-05-16 | Improved reliability and error diagnostics for Cowork remote SSH host connections |
| [1.7196.1+ddbeb72e](2026-05-15_1.7196.1+ddbeb72e.md) | `mac` | 2026-05-15 | Automatic session stream reconnection and workspace folder restriction alerts |
| [1.7196.0](2026-05-12_1.7196.0.md) | `mac`, `win` | 2026-05-12 | Customizable organization top banner, OIDC gateway sign-in, and Claude Opus 4 support |
| [1.6608.2](2026-05-09_1.6608.2.md) | `mac`, `win` | 2026-05-09 | Maintenance and stability update with no user-facing UI changes |
| [1.6608.1](2026-05-08_1.6608.1.md) | `win` | 2026-05-08 | `TODO` (`win`) — _highlights pending_ |
| [1.6608.0](2026-05-07_1.6608.0.md) | `mac`, `win` | 2026-05-07 | Cowork artifact sharing via deep links and cloud-synced Cowork storage |
| [1.6259.1](2026-05-06_1.6259.1.md) | `mac`, `win` | 2026-05-06 | Maintenance and stability update with no user-facing UI changes |
| [1.6259.0](2026-05-06_1.6259.0.md) | `mac`, `win` | 2026-05-06 | AWS SSO sign-in for Bedrock, admin tool approval locking, and white-label sign-in controls |
| [1.5354.0](2026-04-29_1.5354.0.md) | `mac`, `win` | 2026-04-29 | Expanded secret detection and redaction, iOS Simulator platform checks, and Chrome bridge alerts |
| [1.5220.0](2026-04-28_1.5220.0.md) | `mac`, `win` | 2026-04-28 | Live Cowork VM screen preview, extensions settings page, and external link confirmation in artifacts |
| [1.4758.0](2026-04-24_1.4758.0.md) | `mac`, `win` | 2026-04-24 | 11-language UI localization, enterprise LLM gateway settings, and Chrome extension pairing |
| [1.3883.0](2026-04-21_1.3883.0.md) | `mac`, `win` | 2026-04-21 | macOS Handoff continuity, diagnostic report generator, and enterprise OIDC bootstrap sign-in |
| [1.3561.0](2026-04-20_1.3561.0.md) | `mac`, `win` | 2026-04-20 | Buddy remote display support, skill filtering, and Windows network path error guidance |
| [1.3109.0](2026-04-16_1.3109.0.md) | `mac`, `win` | 2026-04-16 | Maintenance and stability update with no user-facing UI changes |
| [1.3036.0](2026-04-16_1.3036.0.md) | `mac`, `win` | 2026-04-16 | Admin workspace folder setup dialog and Claude Code active-session check |
| [1.2773.0](2026-04-15_1.2773.0.md) | `mac`, `win` | 2026-04-15 | Maintenance and stability update with no user-facing UI changes |
| [1.2581.0](2026-04-14_1.2581.0.md) | `mac`, `win` | 2026-04-14 | Folder access prompt, Cowork file and PDF preview, and Python MCP extension support |
| [1.2278.0](2026-04-14_1.2278.0.md) | `mac`, `win` | 2026-04-14 | Buddy BLE maker device guide, enterprise update and telemetry policies, and runtime upgrade |
| [1.1617.0](2026-04-09_1.1617.0.md) | `mac`, `win` | 2026-04-09 | Read-only default for host folder permissions and cleaner launch error messaging |
| [1.1348.0](2026-04-08_1.1348.0.md) | `mac`, `win` | 2026-04-08 | Buddy Bluetooth hardware companion window with pairing, firmware setup, and activity stats |
| [1.1062.0](2026-04-07_1.1062.0.md) | `mac`, `win` | 2026-04-07 | Enterprise LLM gateway policies, Windows Registry MCP config, and local transcript search |
| [1.569.0](2026-04-03_1.569.0.md) | `mac`, `win` | 2026-04-03 | Back and forward navigation support in Cowork artifact pages |
| [1.2.234](2026-04-01_1.2.234.md) | `mac`, `win` | 2026-04-01 | Locally bundled web interface, macOS audio capture permission, and runtime update |
| [1.1.9669](2026-03-31_1.1.9669.md) | `mac`, `win` | 2026-03-31 | Direct third-party MCP server connection support with OAuth and streaming |
| [1.1.9493](2026-03-29_1.1.9493.md) | `mac`, `win` | 2026-03-29 | Maintenance and stability update with no user-facing UI changes |
| [1.1.9310](2026-03-27_1.1.9310.md) | `mac`, `win` | 2026-03-27 | Direct MCP tool invocation from interactive Cowork artifacts |
| [1.1.9134](2026-03-27_1.1.9134.md) | `mac`, `win` | 2026-03-27 | Maintenance and stability update with no user-facing UI changes |
| [1.1.8986](2026-03-26_1.1.8986.md) | `mac` | 2026-03-26 | Built-in Cowork Examples project with preset conversations and artifacts |
| [1.1.8629](2026-03-25_1.1.8629.md) | `mac`, `win` | 2026-03-25 | Maintenance and stability update with no user-facing UI changes |
| [1.1.8359](2026-03-24_1.1.8359.md) | `mac`, `win` | 2026-03-24 | Removed temporary built-in bioinformatics skills bundle |
| [1.1.8308](2026-03-23_1.1.8308.md) | `mac` | 2026-03-23 | Computer Use teach-mode overlay and initial bioinformatics skills bundle |
| [1.1.7714](2026-03-19_1.1.7714.md) | `mac`, `win` | 2026-03-19 | HTTPS validation enforcement for URL configuration settings |
| [1.1.7464](2026-03-18_1.1.7464.md) | `mac`, `win` | 2026-03-18 | Maintenance and stability update with no user-facing UI changes |
| [1.1.7203](2026-03-17_1.1.7203.md) | `mac`, `win` | 2026-03-17 | Maintenance and stability update with no user-facing UI changes |
| [1.1.7053](2026-03-17_1.1.7053.md) | `mac`, `win` | 2026-03-17 | Cowork plugin confirmation support and Git commit signing in terminal sessions |
| [1.1.6679](2026-03-13_1.1.6679.md) | `mac`, `win` | 2026-03-13 | Maintenance and stability update with no user-facing UI changes |
| [1.1.6452](2026-03-12_1.1.6452.md) | `mac`, `win` | 2026-03-12 | Maintenance and stability update with no user-facing UI changes |
| [1.1.6041](2026-03-10_1.1.6041.md) | `mac`, `win` | 2026-03-10 | Maintenance and stability update with no user-facing UI changes |
| [1.1.5749](2026-03-08_1.1.5749.md) | `mac`, `win` | 2026-03-08 | Integrated native Computer Use capabilities and added enterprise SSL proxy certificate inheritance |
| [1.1.5368](2026-03-05_1.1.5368.md) | `mac`, `win` | 2026-03-05 | Added auto-update ownership repair with Touch ID, account-mismatch checks for Claude in Chrome, full Edit menu actions, and virtualization guidance |
| [1.1.4498](2026-02-27_1.1.4498.md) | `mac`, `win` | 2026-02-27 | Forwarded user shell configuration, custom API gateway settings, and opt-in telemetry settings to Claude Code sessions |
| [1.1.4328](2026-02-25_1.1.4328.md) | `mac`, `win` | 2026-02-25 | Added admin policy notices for Cowork and Claude Code, non-destructive extension disabling, OS compatibility prompts, and self-healing settings |
| [1.1.4173](2026-02-24_1.1.4173.md) | `mac`, `win` | 2026-02-24 | Maintenance and stability update with no user-facing UI changes |
| [1.1.4088](2026-02-24_1.1.4088.md) | `mac`, `win` | 2026-02-24 | Maintenance and stability update with no user-facing UI changes |
| [1.1.4010](2026-02-22_1.1.4010.md) | `mac`, `win` | 2026-02-22 | Maintenance and stability update with no user-facing UI changes |
| [1.1.3963](2026-02-21_1.1.3963.md) | `mac`, `win` | 2026-02-21 | Maintenance and stability update with no user-facing UI changes |
| [1.1.3918](2026-02-21_1.1.3918.md) | `mac`, `win` | 2026-02-21 | Upgraded core MCP protocol support for broader server compatibility with no UI changes |
| [1.1.3830](2026-02-20_1.1.3830.md) | `mac`, `win` | 2026-02-20 | Maintenance and stability update with no user-facing UI changes |
| [1.1.3770](2026-02-20_1.1.3770.md) | `mac`, `win` | 2026-02-20 | Maintenance and stability update with no user-facing UI changes |
| [1.1.3647](2026-02-19_1.1.3647.md) | `mac`, `win` | 2026-02-19 | Maintenance and stability update with no user-facing UI changes |
| [1.1.3541](2026-02-19_1.1.3541.md) | `mac`, `win` | 2026-02-19 | Added macOS remote host support for SSH remote sessions |
| [1.1.3363](2026-02-17_1.1.3363.md) | `mac`, `win` | 2026-02-17 | Improved Cowork VM connection stability and hardened local remote-debugging authentication |
| [1.1.3189](2026-02-14_1.1.3189.md) | `mac`, `win` | 2026-02-14 | Unified Cowork VM menu naming, native per-architecture VM images, and checksum-verified remote CLI setup |
| [1.1.3149](2026-02-13_1.1.3149.md) | `win` | 2026-02-13 | `TODO` (`win`) — _highlights pending_ |
| [1.1.2998](2026-02-12_1.1.2998.md) | `mac`, `win` | 2026-02-12 | Added Cowork workspace reinstall and 30-second network log diagnostics alongside a major runtime upgrade |
| [1.1.2685](2026-02-10_1.1.2685.md) | `mac`, `win` | 2026-02-10 | Background groundwork for deploying Claude CLI to remote SSH hosts with no UI changes |
| [1.1.2512](2026-02-10_1.1.2512.md) | `mac`, `win` | 2026-02-10 | Improved error reporting when launching local shell helpers fails, with no UI changes |
| [1.1.2321](2026-02-07_1.1.2321.md) | `mac`, `win` | 2026-02-07 | Minor desktop runtime stability update and early support for switching browsers in Claude in Chrome |
| [1.1.2156](2026-02-06_1.1.2156.md) | `mac`, `win` | 2026-02-06 | Maintenance and stability update with no user-facing UI changes |
| [1.1.2128](2026-02-05_1.1.2128.md) | `mac`, `win` | 2026-02-05 | Maintenance and stability update with no user-facing UI changes |
| [1.1.2102](2026-02-05_1.1.2102.md) | `mac`, `win` | 2026-02-05 | Drag-and-drop installation for .skill files and same-account sign-in guidance for Claude in Chrome |
| [1.1.1890](2026-02-04_1.1.1890.md) | `mac`, `win` | 2026-02-04 | Added FedStart government cloud support and upgraded the desktop runtime across two major versions |
| [1.1.1520](2026-01-30_1.1.1520.md) | `mac`, `win` | 2026-01-30 | Expanded background SSH port-forwarding support for Cowork VMs with no user-facing UI changes |
| [1.1.1200](2026-01-28_1.1.1200.md) | `mac`, `win` | 2026-01-28 | Added underlying SSH connectivity infrastructure for VM networking with no visible UI changes |
| [1.1.1093](2026-01-27_1.1.1093.md) | `mac`, `win` | 2026-01-27 | Internal groundwork for Cowork automation shortcuts and trusted folders with no visible UI changes |
| [1.1.886](2026-01-24_1.1.886.md) | `mac`, `win` | 2026-01-24 | Added support for opening and previewing local .skill files alongside rich local plugin manifests |
| [1.1.799](2026-01-23_1.1.799.md) | `mac`, `win` | 2026-01-23 | Maintenance and stability update with no user-facing UI changes |
| [1.1.762](2026-01-23_1.1.762.md) | `mac`, `win` | 2026-01-23 | One-click Claude in Chrome extension installation and browser restart directly from Claude Desktop |
| [1.1.673](2026-01-23_1.1.673.md) | `mac`, `win` | 2026-01-23 | Expanded Cowork with home-directory folder validation, built-in knowledge base tools, and local plugin support |
| [1.1.381](2026-01-18_1.1.381.md) | `mac`, `win` | 2026-01-18 | Minor internal MCP connection adjustments with no user-facing UI changes |
| [1.1.351](2026-01-17_1.1.351.md) | `mac`, `win` | 2026-01-17 | Maintenance and stability update with no user-facing UI changes |
| [1.1.329](2026-01-16_1.1.329.md) | `win` | 2026-01-16 | `TODO` (`win`) — _highlights pending_ |
| [1.1.280](2026-01-16_1.1.280.md) | `mac`, `win` | 2026-01-16 | Added View Process Logs menu option and laid hidden early groundwork for the Cowork local workspace VM |
| [1.0.3218](2026-01-12_1.0.3218.md) | `mac`, `win` | 2026-01-12 | Added VM session management menus, feedback submission with debug logs, browser site trust prompts, and initial Skills support |
| [1.0.2768](2026-01-05_1.0.2768.md) | `mac`, `win` | 2026-01-05 | Rebranded browser integration to Claude in Chrome, added integrated terminal support, and retired legacy updater prompts |
| [1.0.2339](2025-12-16_1.0.2339.md) | `win` | 2025-12-16 | `TODO` (`win`) — _highlights pending_ |
| [1.0.1768](2025-12-06_1.0.1768.md) | `win` | 2025-12-06 | `TODO` (`win`) — _highlights pending_ |
| [1.0.1656](2025-12-04_1.0.1656.md) | `win` | 2025-12-04 | `TODO` (`win`) — _highlights pending_ |
| [1.0.1405](2025-12-01_1.0.1405.md) | `win` | 2025-12-01 | `TODO` (`win`) — _highlights pending_ |
| [1.0.1307](2025-11-26_1.0.1307.md) | `win` | 2025-11-26 | `TODO` (`win`) — _highlights pending_ |
| [1.0.1217](2025-11-24_1.0.1217.md) | `win` | 2025-11-24 | `TODO` (`win`) — _highlights pending_ |
| [1.0.734](2025-11-21_1.0.734.md) | `mac`, `win` | 2025-11-21 | Claude Desktop 1.0 release with slimmer installer, Copy URL menu item, launch-failure diagnostics, and macOS 13 requirement |
| [1.0.332](2025-11-05_1.0.332.md) | `win` | 2025-11-05 | `TODO` (`win`) — _highlights pending_ |
| [1.0.211](2025-10-31_1.0.211.md) | `win` | 2025-10-31 | `TODO` (`win`) — _highlights pending_ |
| [0.14.10](2025-10-28_0.14.10.md) | `mac`, `win` | 2025-10-28 | Switched automatic updates to the new official release channel ahead of 1.0 with no UI changes |
| [0.14.7](2025-10-28_0.14.7.md) | `win` | 2025-10-28 | `TODO` (`win`) — _highlights pending_ |
| [0.14.4](2025-10-21_0.14.4.md) | `win` | 2025-10-21 | `TODO` (`win`) — _highlights pending_ |
| [0.14.1](2025-10-21_0.14.1.md) | `mac` | 2025-10-21 | Refreshed app icons and brand theme colors across windows, plus admin-disabled update notices |
| [0.13.108](2025-10-17_0.13.108.md) | `mac`, `win` | 2025-10-17 | Maintenance and stability update with no user-facing UI changes |
| [0.13.106](2025-10-17_0.13.106.md) | `mac` | 2025-10-17 | Switched Help menu feedback action to Get Support and added sign-in step to Chrome extension onboarding |
| [0.13.91](2025-10-10_0.13.91.md) | `mac` | 2025-10-10 | Step-by-step setup instructions for Claude for Chrome and clearer extension removal notifications |
| [0.13.64](2025-10-08_0.13.64.md) | `mac`, `win` | 2025-10-08 | Unveiled Claude for Chrome integration, new Anthropic Sans & Serif typography, and organization extension verification |
| [0.13.37](2025-09-25_0.13.37.md) | `mac`, `win` | 2025-09-25 | Open-document context detection for Quick Entry, improved dictation hotkey prompts, and Copy Installation ID |
| [0.13.19](2025-09-18_0.13.19.md) | `mac`, `win` | 2025-09-18 | Added drag-and-drop file attachments in Quick Entry alongside a minor desktop runtime update |
| [0.13.11](2025-09-12_0.13.11.md) | `mac`, `win` | 2025-09-12 | Added Recent Chats to menu bar and Dock, step-by-step dictation permission guidance, and a major runtime upgrade |
| [0.12.129](2025-08-30_0.12.129.md) | `mac`, `win` | 2025-08-30 | Under-the-hood runtime compatibility preparation with no user-facing UI changes |
| [0.12.125](2025-08-29_0.12.125.md) | `mac`, `win` | 2025-08-29 | Clearer, jargon-free error messages when extension installation fails |
| [0.12.112](2025-08-20_0.12.112.md) | `mac`, `win` | 2025-08-20 | Completed Quick Entry, Voice Dictation, and Drag-to-Screenshot UX across 11 languages with a faster single-bundle build |
| [0.12.55](2025-07-25_0.12.55.md) | `mac`, `win` | 2025-07-25 | Internal Quick Entry window optimization and localized formatting support with no UI changes |
| [0.12.49](2025-07-23_0.12.49.md) | `mac`, `win` | 2025-07-23 | Fixed loading local MCP servers installed in folder paths containing spaces or special characters |
| [0.12.28](2025-07-19_0.12.28.md) | `mac`, `win` | 2025-07-19 | Clearer in-app update status messages in the menu bar and native layer cleanup |
| [0.12.20](2025-07-17_0.12.20.md) | `mac`, `win` | 2025-07-17 | Added support for ES Module (ESM) local MCP servers in the built-in MCP host |
| [0.12.19](2025-07-17_0.12.19.md) | `mac`, `win` | 2025-07-17 | Bundled brand fonts at the app level for consistent typography across windows |
| [0.12.16](2025-07-14_0.12.16.md) | `mac`, `win` | 2025-07-14 | Maintenance and stability update with no user-facing UI changes |
| [0.12.15](2025-07-14_0.12.15.md) | `mac`, `win` | 2025-07-14 | Launched Voice Dictation and upgraded Quick Entry (Option+Space) with image attachments; moved Settings to the web UI |
| [0.11.6](2025-06-30_0.11.6.md) | `mac`, `win` | 2025-06-30 | Improved input stream reliability for built-in MCP servers with no user-facing UI changes |
| [0.11.4](2025-06-28_0.11.4.md) | `mac`, `win` | 2025-06-28 | Polished Markdown heading and list typography on extension detail pages |
| [0.11.3](2025-06-26_0.11.3.md) | `mac`, `win` | 2025-06-26 | Renamed extensions to Desktop Extensions (.dxt) with signature verification, blocklist protection, and extension updates |
| [0.10.38](2025-06-17_0.10.38.md) | `mac`, `win` | 2025-06-17 | Launched Desktop Extensions (.cdx), built-in MCP server hosting, API Key management, and scheduled auto-updates |
| [0.10.14](2025-06-05_0.10.14.md) | `mac`, `win` | 2025-06-05 | Added hardware acceleration toggle and cache reset dialog, plus early Studio task and skill UI components |
| [0.9.4](2025-06-03_0.9.4.md) | `mac`, `win` | 2025-06-03 | Major desktop runtime upgrade and background groundwork for native macOS and MCP permission features |
| [0.9.3](2025-04-30_0.9.3.md) | `mac`, `win` | 2025-04-30 | Automatic detection and reload recovery when the main chat window becomes unresponsive |
| [0.9.2+b2184e2c](2025-04-14_0.9.2+b2184e2c.md) | `mac`, `win` | 2025-04-14 | Maintenance and stability update with no user-facing UI changes |
| [0.9.2+d5e83a89](2025-04-08_0.9.2+d5e83a89.md) | `mac` | 2025-04-08 | Added network error fallback screen and graceful web redirect notice on connection failures |
| [0.9.1](2025-04-01_0.9.1.md) | `mac`, `win` | 2025-04-01 | Added Claude Help menu item for quick access to official help resources |
| [0.9.0](2025-03-27_0.9.0.md) | `mac`, `win` | 2025-03-27 | Added Find in Page search bar for finding text within conversations |
| [0.8.1](2025-03-14_0.8.1.md) | `mac`, `win` | 2025-03-14 | Added dedicated About Claude window with brand typography and official support links |
| [0.8.0](2025-02-28_0.8.0.md) | `mac`, `win` | 2025-02-28 | Expanded UI localization across menus, MCP settings, and update prompts alongside a major runtime upgrade |
| [0.7.9](2025-02-10_0.7.9.md) | `mac`, `win` | 2025-02-10 | Clearer MCP server startup and configuration status messages with tighter window permission controls |
| [0.7.8](2025-01-08_0.7.8.md) | `mac`, `win` | 2025-01-08 | Added native application menu bar with New Conversation shortcut and minor runtime stability updates |
| [0.7.7](2024-12-19_0.7.7.md) | `mac`, `win` | 2024-12-19 | Added Launch at Startup setting, MCP disconnection alerts, and a major desktop runtime upgrade |
| [0.7.6](2024-12-19_0.7.6.md) | `win` | 2024-12-19 | `TODO` (`win`) — _highlights pending_ |
| [0.7.5](2024-12-02_0.7.5.md) | `mac`, `win` | 2024-12-02 | Redesigned Settings interface, MCP 1.0 support, and macOS window positioning fixes |
| [0.7.1](2024-11-22_0.7.1.md) | `mac`, `win` | 2024-11-22 | First dedicated MCP management UI with installation prompts, log viewer access, and Developer Mode |
| [0.6.2](2024-11-13_0.6.2.md) | `mac`, `win` | 2024-11-13 | Multi-line input and click-outside dismissal for Quick Window, plus window focus and MCP improvements |
| [0.6.0](2024-11-11_0.6.0.md) | `win` | 2024-11-11 | `TODO` (`win`) — _highlights pending_ |
| [0.5.0](2024-11-08_0.5.0.md) | `win` | 2024-11-08 | `TODO` (`win`) — _highlights pending_ |
| [0.4.9](2024-11-02_0.4.9.md) | `mac`, `win` | 2024-11-02 | Internal logging infrastructure update with no user-facing UI changes |
| [0.4.8](2024-10-31_0.4.8.md) | `mac` | 2024-10-31 | Initial macOS desktop app launch with main chat window, global Quick Window input bar, and 10-language UI support |

## Mobile Version Index (`ios` / `android`, Newest → Oldest)

| Version | Platforms | Release Date | Highlights |
|---|---|---|---|
| [1.261124.19](2026-11-25_1.261124.19.md) | `android` | 2026-11-25 (Uptodown) | Uptodown third-party Play-split XAPK static diff (`1.261123.19 → 1.261124.19`; iOS & `120`–`122` gap uncovered, no full `apksigner` verify): GitHub integration (`connect_github_card.*`, GitHub App install prompts, PR/plan/tool-call approval error taxonomy), ~12 safeguards auto-model-switch strings, `places_list` Places panel, usage sections, `Default tab`, PHI-exclusion project instructions, read-aloud limit, `continue_on_cloud.*` removal, `28 → 21` language splits, `20/20` byte-identical native libs, zero permission/component/API endpoint changes |
| [1.261113.19](2026-11-14_1.261113.19.md) | `android` | 2026-11-14 | Play-split XAPK static diff (`1.261112.18 → 1.261113.19`): Android 12L `minSdkVersion` `32`, `27 → 30` locale splits, standalone `dictation` (incl. offline) & `readaloud` modules, CCR project sheets / GitHub SSO / 49 bottom-sheet destinations, retired Threads UI, and static promotional-credits/KYC client code |
| [1.261109.19](2026-11-11_1.261109.19.md) | `ios`, `android` | 2026-11-11 | `TODO` (`ios`, `android`) — _highlights pending_ |
| [1.261106.19](2026-11-09_1.261106.19.md) | `ios`, `android` | 2026-11-09 | `TODO` (`ios`, `android`) — _highlights pending_ |
| [1.260813.10](2026-11-09_1.260813.10.md) | `android` | 2026-11-09 | `TODO` (`android`) — _highlights pending_ |
| [1.250602.7](2026-11-09_1.250602.7.md) | `android` | 2026-11-09 | `TODO` (`android`) — _highlights pending_ |
| [1.261103.19](2026-11-08_1.261103.19.md) | `android` | 2026-11-08 | `TODO` (`android`) — _highlights pending_ |
| [1.261104.19](2026-11-07_1.261104.19.md) | `ios`, `android` | 2026-11-07 | `TODO` (`ios`, `android`) — _highlights pending_ |
| [1.261102.19](2026-11-05_1.261102.19.md) | `android` | 2026-11-05 | `TODO` (`android`) — _highlights pending_ |
| [1.260831.0](2026-11-03_1.260831.0.md) | `android` | 2026-11-03 | `TODO` (`android`) — _highlights pending_ |
| [1.261030.19](2026-11-02_1.261030.19.md) | `ios`, `android` | 2026-11-02 | `TODO` (`ios`, `android`) — _highlights pending_ |
| [1.261029.20](2026-11-01_1.261029.20.md) | `android` | 2026-11-01 | `TODO` (`android`) — _highlights pending_ |
| [1.261022.20](2026-11-01_1.261022.20.md) | `android` | 2026-11-01 | `TODO` (`android`) — _highlights pending_ |
| [1.261020.20](2026-11-01_1.261020.20.md) | `android` | 2026-11-01 | `TODO` (`android`) — _highlights pending_ |
| [1.261028.19](2026-10-30_1.261028.19.md) | `ios`, `android` | 2026-10-30 | `TODO` (`ios`, `android`) — _highlights pending_ |
| [1.261027.19](2026-10-30_1.261027.19.md) | `android` | 2026-10-30 | `TODO` (`android`) — _highlights pending_ |
| [1.261026.51](2026-10-30_1.261026.51.md) | `android` | 2026-10-30 | `TODO` (`android`) — _highlights pending_ |
| [1.261026.20](2026-10-29_1.261026.20.md) | `ios` | 2026-10-29 | `TODO` (`ios`) — _highlights pending_ |
| [1.261023.20](2026-10-25_1.261023.20.md) | `ios`, `android` | 2026-10-25 | `TODO` (`ios`, `android`) — _highlights pending_ |
| [1.261021.51](2026-10-24_1.261021.51.md) | `ios`, `android` | 2026-10-24 | `TODO` (`ios`, `android`) — _highlights pending_ |
| [1.261016.51](2026-10-24_1.261016.51.md) | `android` | 2026-10-24 | `TODO` (`android`) — _highlights pending_ |
| [1.261019.51](2026-10-23_1.261019.51.md) | `ios` | 2026-10-23 | `TODO` (`ios`) — _highlights pending_ |
| [1.261019.20](2026-10-22_1.261019.20.md) | `ios`, `android` | 2026-10-22 | `TODO` (`ios`, `android`) — _highlights pending_ |
| [1.261015.20](2026-10-21_1.261015.20.md) | `android` | 2026-10-21 | `TODO` (`android`) — _highlights pending_ |
| [1.261016.20](2026-10-19_1.261016.20.md) | `ios` | 2026-10-19 | `TODO` (`ios`) — _highlights pending_ |
| [1.250512.27](2026-10-19_1.250512.27.md) | `android` | 2026-10-19 | `TODO` (`android`) — _highlights pending_ |
| [1.261014.20](2026-10-17_1.261014.20.md) | `ios`, `android` | 2026-10-17 | `TODO` (`ios`, `android`) — _highlights pending_ |
| [1.261013.20](2026-10-16_1.261013.20.md) | `ios`, `android` | 2026-10-16 | `TODO` (`ios`, `android`) — _highlights pending_ |
| [1.261012.20](2026-10-15_1.261012.20.md) | `ios`, `android` | 2026-10-15 | `TODO` (`ios`, `android`) — _highlights pending_ |
| [1.261009.20](2026-10-12_1.261009.20.md) | `ios`, `android` | 2026-10-12 | `TODO` (`ios`, `android`) — _highlights pending_ |
| [1.240805.17](2026-10-12_1.240805.17.md) | `android` | 2026-10-12 | `TODO` (`android`) — _highlights pending_ |
| [1.260918.19](2026-10-11_1.260918.19.md) | `android` | 2026-10-11 | `TODO` (`android`) — _highlights pending_ |
| [1.261008.20](2026-10-10_1.261008.20.md) | `android` | 2026-10-10 | `TODO` (`android`) — _highlights pending_ |
| [1.261007.20](2026-10-10_1.261007.20.md) | `ios`, `android` | 2026-10-10 | `TODO` (`ios`, `android`) — _highlights pending_ |
| [1.261005.20](2026-10-08_1.261005.20.md) | `ios`, `android` | 2026-10-08 | `TODO` (`ios`, `android`) — _highlights pending_ |
| [1.261002.20](2026-10-05_1.261002.20.md) | `ios`, `android` | 2026-10-05 | `TODO` (`ios`, `android`) — _highlights pending_ |
| [1.260930.20](2026-10-04_1.260930.20.md) | `ios`, `android` | 2026-10-04 | `TODO` (`ios`, `android`) — _highlights pending_ |
| [1.260928.20](2026-09-30_1.260928.20.md) | `ios`, `android` | 2026-09-30 | `TODO` (`ios`, `android`) — _highlights pending_ |
| [1.260925.19](2026-09-29_1.260925.19.md) | `ios` | 2026-09-29 | `TODO` (`ios`) — _highlights pending_ |
| [1.260923.51](2026-09-27_1.260923.51.md) | `ios` | 2026-09-27 | `TODO` (`ios`) — _highlights pending_ |
| [1.260923.20](2026-09-26_1.260923.20.md) | `ios`, `android` | 2026-09-26 | `TODO` (`ios`, `android`) — _highlights pending_ |
| [1.260921.19](2026-09-25_1.260921.19.md) | `ios`, `android` | 2026-09-25 | `TODO` (`ios`, `android`) — _highlights pending_ |
| [1.260910.12](2026-09-22_1.260910.12.md) | `android` | 2026-09-22 | `TODO` (`android`) — _highlights pending_ |
| [1.260209.37](2026-09-21_1.260209.37.md) | `android` | 2026-09-21 | `TODO` (`android`) — _highlights pending_ |
| [1.260916.19](2026-09-18_1.260916.19.md) | `ios`, `android` | 2026-09-18 | `TODO` (`ios`, `android`) — _highlights pending_ |
| [1.260914.19](2026-09-16_1.260914.19.md) | `android` | 2026-09-16 | `TODO` (`android`) — _highlights pending_ |
| [1.260911.19](2026-09-14_1.260911.19.md) | `ios`, `android` | 2026-09-14 | `TODO` (`ios`, `android`) — _highlights pending_ |
| [1.260909.19](2026-09-12_1.260909.19.md) | `ios`, `android` | 2026-09-12 | `TODO` (`ios`, `android`) — _highlights pending_ |
| [1.260907.19](2026-09-10_1.260907.19.md) | `ios`, `android` | 2026-09-10 | `TODO` (`ios`, `android`) — _highlights pending_ |
| [1.260806.20](2026-09-10_1.260806.20.md) | `android` | 2026-09-10 | `TODO` (`android`) — _highlights pending_ |
| [1.260904.19](2026-09-07_1.260904.19.md) | `ios`, `android` | 2026-09-07 | `TODO` (`ios`, `android`) — _highlights pending_ |
| [1.260902.20](2026-09-04_1.260902.20.md) | `ios`, `android` | 2026-09-04 | `TODO` (`ios`, `android`) — _highlights pending_ |
| [1.260831.1](2026-09-03_1.260831.1.md) | `ios` | 2026-09-03 | `TODO` (`ios`) — _highlights pending_ |
| [1.260828.1](2026-09-01_1.260828.1.md) | `ios` | 2026-09-01 | `TODO` (`ios`) — _highlights pending_ |
| [1.260828.0](2026-08-31_1.260828.0.md) | `ios`, `android` | 2026-08-31 | `TODO` (`ios`, `android`) — _highlights pending_ |
| [1.260826.0](2026-08-29_1.260826.0.md) | `ios`, `android` | 2026-08-29 | `TODO` (`ios`, `android`) — _highlights pending_ |
| [1.260721.20](2026-08-29_1.260721.20.md) | `android` | 2026-08-29 | `TODO` (`android`) — _highlights pending_ |
| [1.260702.10](2026-08-29_1.260702.10.md) | `android` | 2026-08-29 | `TODO` (`android`) — _highlights pending_ |
| [1.260604.20](2026-08-29_1.260604.20.md) | `android` | 2026-08-29 | `TODO` (`android`) — _highlights pending_ |
| [1.260528.10](2026-08-28_1.260528.10.md) | `android` | 2026-08-28 | `TODO` (`android`) — _highlights pending_ |
| [1.260824.0](2026-08-27_1.260824.0.md) | `ios`, `android` | 2026-08-27 | `TODO` (`ios`, `android`) — _highlights pending_ |
| [1.260820.0](2026-08-22_1.260820.0.md) | `ios`, `android` | 2026-08-22 | `TODO` (`ios`, `android`) — _highlights pending_ |
| [1.260817.0](2026-08-20_1.260817.0.md) | `ios`, `android` | 2026-08-20 | `TODO` (`ios`, `android`) — _highlights pending_ |
| [1.260814.0](2026-08-18_1.260814.0.md) | `ios` | 2026-08-18 | `TODO` (`ios`) — _highlights pending_ |
| [1.260813.0](2026-08-14_1.260813.0.md) | `ios`, `android` | 2026-08-14 | `TODO` (`ios`, `android`) — _highlights pending_ |
| [1.260810.0](2026-08-13_1.260810.0.md) | `ios`, `android` | 2026-08-13 | `TODO` (`ios`, `android`) — _highlights pending_ |
| [1.260611.30](2026-08-13_1.260611.30.md) | `android` | 2026-08-13 | `TODO` (`android`) — _highlights pending_ |
| [1.260806.0](2026-08-12_1.260806.0.md) | `ios` | 2026-08-12 | `TODO` (`ios`) — _highlights pending_ |
| [1.260430.10](2026-08-11_1.260430.10.md) | `android` | 2026-08-11 | `TODO` (`android`) — _highlights pending_ |
| [1.260316.47](2026-08-06_1.260316.47.md) | `android` | 2026-08-06 | `TODO` (`android`) — _highlights pending_ |
| [1.260618.10](2026-08-04_1.260618.10.md) | `android` | 2026-08-04 | `TODO` (`android`) — _highlights pending_ |
| [1.250113.17](2026-07-28_1.250113.17.md) | `android` | 2026-07-28 | `TODO` (`android`) — _highlights pending_ |
| [1.260721.0](2026-07-23_1.260721.0.md) | `ios` | 2026-07-23 | `TODO` (`ios`) — _highlights pending_ |
| [1.260716.0](2026-07-19_1.260716.0.md) | `ios` | 2026-07-19 | `TODO` (`ios`) — _highlights pending_ |
| [1.260709.10](2026-07-19_1.260709.10.md) | `android` | 2026-07-19 | `TODO` (`android`) — _highlights pending_ |
| [1.260709.0](2026-07-10_1.260709.0.md) | `ios`, `android` | 2026-07-10 | `TODO` (`ios`, `android`) — _highlights pending_ |
| [1.260702.3](2026-07-10_1.260702.3.md) | `ios` | 2026-07-10 | `TODO` (`ios`) — _highlights pending_ |
| [1.260625.30](2026-07-10_1.260625.30.md) | `android` | 2026-07-10 | `TODO` (`android`) — _highlights pending_ |
| [1.260702.2](2026-07-09_1.260702.2.md) | `ios` | 2026-07-09 | `TODO` (`ios`) — _highlights pending_ |
| [1.260625.20](2026-07-09_1.260625.20.md) | `android` | 2026-07-09 | `TODO` (`android`) — _highlights pending_ |
| [1.260702.0](2026-07-07_1.260702.0.md) | `ios` | 2026-07-07 | `TODO` (`ios`) — _highlights pending_ |
| [1.260625.0](2026-07-01_1.260625.0.md) | `ios` | 2026-07-01 | `TODO` (`ios`) — _highlights pending_ |
| [1.260618.1](2026-06-24_1.260618.1.md) | `ios` | 2026-06-24 | `TODO` (`ios`) — _highlights pending_ |
| [1.260618.0](2026-06-23_1.260618.0.md) | `ios` | 2026-06-23 | `TODO` (`ios`) — _highlights pending_ |
| [1.260611.20](2026-06-20_1.260611.20.md) | `android` | 2026-06-20 | `TODO` (`android`) — _highlights pending_ |
| [1.260611.1](2026-06-17_1.260611.1.md) | `ios` | 2026-06-17 | `TODO` (`ios`) — _highlights pending_ |
| [1.260604.30](2026-06-17_1.260604.30.md) | `android` | 2026-06-17 | `TODO` (`android`) — _highlights pending_ |
| [1.260409.10](2026-06-17_1.260409.10.md) | `android` | 2026-06-17 | `TODO` (`android`) — _highlights pending_ |
| [1.260112.27](2026-06-14_1.260112.27.md) | `android` | 2026-06-14 | `TODO` (`android`) — _highlights pending_ |
| [1.250120.7](2026-06-14_1.250120.7.md) | `android` | 2026-06-14 | `TODO` (`android`) — _highlights pending_ |
| [1.260611.0](2026-06-13_1.260611.0.md) | `ios`, `android` | 2026-06-13 | `TODO` (`ios`, `android`) — _highlights pending_ |
| [1.260604.0](2026-06-09_1.260604.0.md) | `ios` | 2026-06-09 | `TODO` (`ios`) — _highlights pending_ |
| [1.260521.20](2026-06-07_1.260521.20.md) | `android` | 2026-06-07 | `TODO` (`android`) — _highlights pending_ |
| [1.260521.10](2026-06-05_1.260521.10.md) | `android` | 2026-06-05 | `TODO` (`android`) — _highlights pending_ |
| [1.260528.1](2026-06-04_1.260528.1.md) | `ios` | 2026-06-04 | `TODO` (`ios`) — _highlights pending_ |
| [1.260528.0](2026-06-03_1.260528.0.md) | `ios` | 2026-06-03 | `TODO` (`ios`) — _highlights pending_ |
| [1.260507.10](2026-05-29_1.260507.10.md) | `android` | 2026-05-29 | `TODO` (`android`) — _highlights pending_ |
| [1.260521.1](2026-05-28_1.260521.1.md) | `ios` | 2026-05-28 | `TODO` (`ios`) — _highlights pending_ |
| [1.260423.20](2026-05-28_1.260423.20.md) | `android` | 2026-05-28 | `TODO` (`android`) — _highlights pending_ |
| [1.260521.0](2026-05-27_1.260521.0.md) | `ios` | 2026-05-27 | `TODO` (`ios`) — _highlights pending_ |
| [1.241111.5](2026-05-26_1.241111.5.md) | `android` | 2026-05-26 | `TODO` (`android`) — _highlights pending_ |
| [1.260514.0](2026-05-20_1.260514.0.md) | `ios`, `android` | 2026-05-20 | `TODO` (`ios`, `android`) — _highlights pending_ |
| [1.260302.17](2026-05-14_1.260302.17.md) | `android` | 2026-05-14 | `TODO` (`android`) — _highlights pending_ |
| [1.260507.0](2026-05-13_1.260507.0.md) | `ios` | 2026-05-13 | `TODO` (`ios`) — _highlights pending_ |
| [1.250106.7](2026-05-10_1.250106.7.md) | `android` | 2026-05-10 | `TODO` (`android`) — _highlights pending_ |
| [1.260430.0](2026-05-06_1.260430.0.md) | `ios`, `android` | 2026-05-06 | `TODO` (`ios`, `android`) — _highlights pending_ |
| [1.260423.1](2026-05-01_1.260423.1.md) | `ios` | 2026-05-01 | `TODO` (`ios`) — _highlights pending_ |
| [1.260423.0](2026-04-29_1.260423.0.md) | `ios` | 2026-04-29 | `TODO` (`ios`) — _highlights pending_ |
| [1.260416.20](2026-04-27_1.260416.20.md) | `android` | 2026-04-27 | `TODO` (`android`) — _highlights pending_ |
| [1.260416.0](2026-04-21_1.260416.0.md) | `ios` | 2026-04-21 | `TODO` (`ios`) — _highlights pending_ |
| [1.260330.27](2026-04-20_1.260330.27.md) | `android` | 2026-04-20 | `TODO` (`android`) — _highlights pending_ |
| [1.250303.27](2026-04-18_1.250303.27.md) | `android` | 2026-04-18 | `TODO` (`android`) — _highlights pending_ |
| [1.260409.1](2026-04-15_1.260409.1.md) | `ios` | 2026-04-15 | `TODO` (`ios`) — _highlights pending_ |
| [1.260409.0](2026-04-14_1.260409.0.md) | `ios` | 2026-04-14 | `TODO` (`ios`) — _highlights pending_ |
| [1.260402.20](2026-04-13_1.260402.20.md) | `android` | 2026-04-13 | `TODO` (`android`) — _highlights pending_ |
| [1.260216.27](2026-04-10_1.260216.27.md) | `android` | 2026-04-10 | `TODO` (`android`) — _highlights pending_ |
| [1.260402.0](2026-04-08_1.260402.0.md) | `ios` | 2026-04-08 | `TODO` (`ios`) — _highlights pending_ |
| [1.260323.7](2026-04-03_1.260323.7.md) | `android` | 2026-04-03 | `TODO` (`android`) — _highlights pending_ |
| [1.260309.17](2026-04-03_1.260309.17.md) | `android` | 2026-04-03 | `TODO` (`android`) — _highlights pending_ |
| [1.260330.1](2026-04-01_1.260330.1.md) | `ios` | 2026-04-01 | `TODO` (`ios`) — _highlights pending_ |
| [1.260330.0](2026-03-31_1.260330.0.md) | `ios` | 2026-03-31 | `TODO` (`ios`) — _highlights pending_ |
| [1.260323.4](2026-03-27_1.260323.4.md) | `ios` | 2026-03-27 | `TODO` (`ios`) — _highlights pending_ |
| [1.260323.3](2026-03-26_1.260323.3.md) | `ios` | 2026-03-26 | `TODO` (`ios`) — _highlights pending_ |
| [1.260323.2](2026-03-25_1.260323.2.md) | `ios` | 2026-03-25 | `TODO` (`ios`) — _highlights pending_ |
| [1.260316.3](2026-03-22_1.260316.3.md) | `ios` | 2026-03-22 | `TODO` (`ios`) — _highlights pending_ |
| [1.260316.1](2026-03-20_1.260316.1.md) | `ios` | 2026-03-20 | `TODO` (`ios`) — _highlights pending_ |
| [1.260316.0](2026-03-18_1.260316.0.md) | `ios` | 2026-03-18 | `TODO` (`ios`) — _highlights pending_ |
| [1.260316.27](2026-03-17_1.260316.27.md) | `android` | 2026-03-17 | `TODO` (`android`) — _highlights pending_ |
| [1.260309.1](2026-03-12_1.260309.1.md) | `ios` | 2026-03-12 | `TODO` (`ios`) — _highlights pending_ |
| [1.260302.0](2026-03-04_1.260302.0.md) | `ios` | 2026-03-04 | `TODO` (`ios`) — _highlights pending_ |
| [1.260223.17](2026-03-02_1.260223.17.md) | `android` | 2026-03-02 | `TODO` (`android`) — _highlights pending_ |
| [1.260216.17](2026-03-01_1.260216.17.md) | `android` | 2026-03-01 | `TODO` (`android`) — _highlights pending_ |
| [1.260223.3](2026-02-28_1.260223.3.md) | `ios` | 2026-02-28 | `TODO` (`ios`) — _highlights pending_ |
| [1.260223.2](2026-02-25_1.260223.2.md) | `ios` | 2026-02-25 | `TODO` (`ios`) — _highlights pending_ |
| [1.250428.17](2026-02-24_1.250428.17.md) | `android` | 2026-02-24 | `TODO` (`android`) — _highlights pending_ |
| [1.251124.27](2026-02-23_1.251124.27.md) | `android` | 2026-02-23 | `TODO` (`android`) — _highlights pending_ |
| [1.260216.3](2026-02-22_1.260216.3.md) | `ios` | 2026-02-22 | `TODO` (`ios`) — _highlights pending_ |
| [1.260216.2](2026-02-19_1.260216.2.md) | `ios` | 2026-02-19 | `TODO` (`ios`) — _highlights pending_ |
| [1.260209.0](2026-02-11_1.260209.0.md) | `ios` | 2026-02-11 | `TODO` (`ios`) — _highlights pending_ |
| [1.260202.37](2026-02-09_1.260202.37.md) | `android` | 2026-02-09 | `TODO` (`android`) — _highlights pending_ |
| [1.260202.5](2026-02-08_1.260202.5.md) | `ios` | 2026-02-08 | `TODO` (`ios`) — _highlights pending_ |
| [1.260202.27](2026-02-05_1.260202.27.md) | `android` | 2026-02-05 | `TODO` (`android`) — _highlights pending_ |
| [1.260126.27](2026-02-05_1.260126.27.md) | `android` | 2026-02-05 | `TODO` (`android`) — _highlights pending_ |
| [1.260202.3](2026-02-04_1.260202.3.md) | `ios` | 2026-02-04 | `TODO` (`ios`) — _highlights pending_ |
| [1.260119.17](2026-01-29_1.260119.17.md) | `android` | 2026-01-29 | `TODO` (`android`) — _highlights pending_ |
| [1.260126.0](2026-01-28_1.260126.0.md) | `ios` | 2026-01-28 | `TODO` (`ios`) — _highlights pending_ |
| [1.251027.7](2026-01-28_1.251027.7.md) | `android` | 2026-01-28 | `TODO` (`android`) — _highlights pending_ |
| [1.260119.0](2026-01-21_1.260119.0.md) | `ios` | 2026-01-21 | `TODO` (`ios`) — _highlights pending_ |
| [1.260112.17](2026-01-20_1.260112.17.md) | `android` | 2026-01-20 | `TODO` (`android`) — _highlights pending_ |
| [1.241014.17](2026-01-16_1.241014.17.md) | `android` | 2026-01-16 | `TODO` (`android`) — _highlights pending_ |
| [1.260112.1](2026-01-13_1.260112.1.md) | `ios` | 2026-01-13 | `TODO` (`ios`) — _highlights pending_ |
| [1.250217.2](2026-01-11_1.250217.2.md) | `android` | 2026-01-11 | `TODO` (`android`) — _highlights pending_ |
| [1.250519.17](2026-01-06_1.250519.17.md) | `android` | 2026-01-06 | `TODO` (`android`) — _highlights pending_ |
| [1.251013.27](2026-01-04_1.251013.27.md) | `android` | 2026-01-04 | `TODO` (`android`) — _highlights pending_ |
| [1.251208.37](2026-01-01_1.251208.37.md) | `android` | 2026-01-01 | `TODO` (`android`) — _highlights pending_ |
| [1.251117.27](2025-12-31_1.251117.27.md) | `android` | 2025-12-31 | `TODO` (`android`) — _highlights pending_ |
| [1.251013.17](2025-12-29_1.251013.17.md) | `android` | 2025-12-29 | `TODO` (`android`) — _highlights pending_ |
| [1.250127.7](2025-12-29_1.250127.7.md) | `android` | 2025-12-29 | `TODO` (`android`) — _highlights pending_ |
| [1.251215.57](2025-12-28_1.251215.57.md) | `android` | 2025-12-28 | `TODO` (`android`) — _highlights pending_ |
| [1.251208.27](2025-12-22_1.251208.27.md) | `android` | 2025-12-22 | `TODO` (`android`) — _highlights pending_ |
| [1.251110.27](2025-12-22_1.251110.27.md) | `android` | 2025-12-22 | `TODO` (`android`) — _highlights pending_ |
| [1.251215.4](2025-12-20_1.251215.4.md) | `ios` | 2025-12-20 | `TODO` (`ios`) — _highlights pending_ |
| [1.251215.47](2025-12-17_1.251215.47.md) | `android` | 2025-12-17 | `TODO` (`android`) — _highlights pending_ |
| [1.251215.2](2025-12-17_1.251215.2.md) | `ios` | 2025-12-17 | `TODO` (`ios`) — _highlights pending_ |
| [1.251215.37](2025-12-16_1.251215.37.md) | `android` | 2025-12-16 | `TODO` (`android`) — _highlights pending_ |
| [1.251208.5](2025-12-13_1.251208.5.md) | `ios` | 2025-12-13 | `TODO` (`ios`) — _highlights pending_ |
| [1.251208.4](2025-12-12_1.251208.4.md) | `ios` | 2025-12-12 | `TODO` (`ios`) — _highlights pending_ |
| [1.251208.3](2025-12-10_1.251208.3.md) | `ios` | 2025-12-10 | `TODO` (`ios`) — _highlights pending_ |
| [1.251124.3](2025-11-28_1.251124.3.md) | `ios` | 2025-11-28 | `TODO` (`ios`) — _highlights pending_ |
| [1.250728.36](2025-11-28_1.250728.36.md) | `android` | 2025-11-28 | `TODO` (`android`) — _highlights pending_ |
| [1.241007.7](2025-11-27_1.241007.7.md) | `android` | 2025-11-27 | `TODO` (`android`) — _highlights pending_ |
| [1.251117.17](2025-11-25_1.251117.17.md) | `android` | 2025-11-25 | `TODO` (`android`) — _highlights pending_ |
| [1.251124.2](2025-11-24_1.251124.2.md) | `ios` | 2025-11-24 | `TODO` (`ios`) — _highlights pending_ |
| [1.251117.1](2025-11-20_1.251117.1.md) | `ios` | 2025-11-20 | `TODO` (`ios`) — _highlights pending_ |
| [1.250922.37](2025-11-19_1.250922.37.md) | `android` | 2025-11-19 | `TODO` (`android`) — _highlights pending_ |
| [1.251110.1](2025-11-11_1.251110.1.md) | `ios` | 2025-11-11 | `TODO` (`ios`) — _highlights pending_ |
| [1.250908.37](2025-11-11_1.250908.37.md) | `android` | 2025-11-11 | `TODO` (`android`) — _highlights pending_ |
| [1.240923.17](2025-11-11_1.240923.17.md) | `android` | 2025-11-11 | `TODO` (`android`) — _highlights pending_ |
| [1.250818.16](2025-11-10_1.250818.16.md) | `android` | 2025-11-10 | `TODO` (`android`) — _highlights pending_ |
| [1.250526.17](2025-11-08_1.250526.17.md) | `android` | 2025-11-08 | `TODO` (`android`) — _highlights pending_ |
| [1.250505.27](2025-11-08_1.250505.27.md) | `android` | 2025-11-08 | `TODO` (`android`) — _highlights pending_ |
| [1.251103.2](2025-11-05_1.251103.2.md) | `ios` | 2025-11-05 | `TODO` (`ios`) — _highlights pending_ |
| [1.250609.27](2025-11-04_1.250609.27.md) | `android` | 2025-11-04 | `TODO` (`android`) — _highlights pending_ |
| [1.250811.6](2025-10-30_1.250811.6.md) | `android` | 2025-10-30 | `TODO` (`android`) — _highlights pending_ |
| [1.251027.0](2025-10-29_1.251027.0.md) | `ios` | 2025-10-29 | `TODO` (`ios`) — _highlights pending_ |
| [1.251020.1](2025-10-22_1.251020.1.md) | `ios` | 2025-10-22 | `TODO` (`ios`) — _highlights pending_ |
| [1.251020.17](2025-10-21_1.251020.17.md) | `android` | 2025-10-21 | `TODO` (`android`) — _highlights pending_ |
| [1.251020.0](2025-10-21_1.251020.0.md) | `ios` | 2025-10-21 | `TODO` (`ios`) — _highlights pending_ |
| [1.251013.5](2025-10-15_1.251013.5.md) | `ios` | 2025-10-15 | `TODO` (`ios`) — _highlights pending_ |
| [1.251006.1](2025-10-08_1.251006.1.md) | `ios` | 2025-10-08 | `TODO` (`ios`) — _highlights pending_ |
| [1.251006.17](2025-10-07_1.251006.17.md) | `android` | 2025-10-07 | `TODO` (`android`) — _highlights pending_ |
| [1.250929.67](2025-10-07_1.250929.67.md) | `android` | 2025-10-07 | `TODO` (`android`) — _highlights pending_ |
| [1.250929.4](2025-10-01_1.250929.4.md) | `ios` | 2025-10-01 | `TODO` (`ios`) — _highlights pending_ |
| [1.250825.27](2025-09-25_1.250825.27.md) | `android` | 2025-09-25 | `TODO` (`android`) — _highlights pending_ |
| [1.250922.1](2025-09-23_1.250922.1.md) | `ios` | 2025-09-23 | `TODO` (`ios`) — _highlights pending_ |
| [1.250915.1](2025-09-17_1.250915.1.md) | `ios` | 2025-09-17 | `TODO` (`ios`) — _highlights pending_ |
| [1.250908.3](2025-09-09_1.250908.3.md) | `ios` | 2025-09-09 | `TODO` (`ios`) — _highlights pending_ |
| [1.250901.17](2025-09-08_1.250901.17.md) | `android` | 2025-09-08 | `TODO` (`android`) — _highlights pending_ |
| [1.250901.1](2025-09-04_1.250901.1.md) | `ios` | 2025-09-04 | `TODO` (`ios`) — _highlights pending_ |
| [1.250804.26](2025-08-30_1.250804.26.md) | `android` | 2025-08-30 | `TODO` (`android`) — _highlights pending_ |
| [1.250825.1](2025-08-27_1.250825.1.md) | `ios` | 2025-08-27 | `TODO` (`ios`) — _highlights pending_ |
| [1.250818.1](2025-08-20_1.250818.1.md) | `ios` | 2025-08-20 | `TODO` (`ios`) — _highlights pending_ |
| [1.250714.7](2025-08-20_1.250714.7.md) | `android` | 2025-08-20 | `TODO` (`android`) — _highlights pending_ |
| [1.250811.1](2025-08-13_1.250811.1.md) | `ios` | 2025-08-13 | `TODO` (`ios`) — _highlights pending_ |
| [1.250804.1](2025-08-06_1.250804.1.md) | `ios` | 2025-08-06 | `TODO` (`ios`) — _highlights pending_ |
| [1.250728.1](2025-07-30_1.250728.1.md) | `ios` | 2025-07-30 | `TODO` (`ios`) — _highlights pending_ |
| [1.250721.17](2025-07-30_1.250721.17.md) | `android` | 2025-07-30 | `TODO` (`android`) — _highlights pending_ |
| [1.250721.4](2025-07-25_1.250721.4.md) | `ios` | 2025-07-25 | `TODO` (`ios`) — _highlights pending_ |
| [1.250721.3](2025-07-23_1.250721.3.md) | `ios` | 2025-07-23 | `TODO` (`ios`) — _highlights pending_ |
| [1.250714.0](2025-07-15_1.250714.0.md) | `ios` | 2025-07-15 | `TODO` (`ios`) — _highlights pending_ |
| [1.250707.37](2025-07-13_1.250707.37.md) | `android` | 2025-07-13 | `TODO` (`android`) — _highlights pending_ |
| [1.250630.7](2025-07-12_1.250630.7.md) | `android` | 2025-07-12 | `TODO` (`android`) — _highlights pending_ |
| [1.250707.0](2025-07-09_1.250707.0.md) | `ios` | 2025-07-09 | `TODO` (`ios`) — _highlights pending_ |
| [1.250630.4](2025-07-02_1.250630.4.md) | `ios` | 2025-07-02 | `TODO` (`ios`) — _highlights pending_ |
| [1.250623.2](2025-06-25_1.250623.2.md) | `ios` | 2025-06-25 | `TODO` (`ios`) — _highlights pending_ |
| [1.250616.2](2025-06-20_1.250616.2.md) | `ios` | 2025-06-20 | `TODO` (`ios`) — _highlights pending_ |
| [1.250616.1](2025-06-18_1.250616.1.md) | `ios` | 2025-06-18 | `TODO` (`ios`) — _highlights pending_ |
| [1.250609.1](2025-06-13_1.250609.1.md) | `ios` | 2025-06-13 | `TODO` (`ios`) — _highlights pending_ |
| [1.250609.0](2025-06-11_1.250609.0.md) | `ios` | 2025-06-11 | `TODO` (`ios`) — _highlights pending_ |
| [1.250210.2](2025-06-10_1.250210.2.md) | `android` | 2025-06-10 | `TODO` (`android`) — _highlights pending_ |
| [1.250602.0](2025-06-04_1.250602.0.md) | `ios` | 2025-06-04 | `TODO` (`ios`) — _highlights pending_ |
| [1.250519.4](2025-05-24_1.250519.4.md) | `ios` | 2025-05-24 | `TODO` (`ios`) — _highlights pending_ |
| [1.250519.3](2025-05-23_1.250519.3.md) | `ios` | 2025-05-23 | `TODO` (`ios`) — _highlights pending_ |
| [1.250512.6](2025-05-14_1.250512.6.md) | `ios` | 2025-05-14 | `TODO` (`ios`) — _highlights pending_ |
| [1.250505.2](2025-05-07_1.250505.2.md) | `ios` | 2025-05-07 | `TODO` (`ios`) — _highlights pending_ |
| [1.250428.4](2025-05-01_1.250428.4.md) | `ios` | 2025-05-01 | `TODO` (`ios`) — _highlights pending_ |
| [1.250428.2](2025-04-30_1.250428.2.md) | `ios` | 2025-04-30 | `TODO` (`ios`) — _highlights pending_ |
| [1.250421.0](2025-04-24_1.250421.0.md) | `ios` | 2025-04-24 | `TODO` (`ios`) — _highlights pending_ |
| [1.250421.17](2025-04-22_1.250421.17.md) | `android` | 2025-04-22 | `TODO` (`android`) — _highlights pending_ |
| [1.250414.27](2025-04-21_1.250414.27.md) | `android` | 2025-04-21 | `TODO` (`android`) — _highlights pending_ |
| [1.250414.3](2025-04-18_1.250414.3.md) | `ios` | 2025-04-18 | `TODO` (`ios`) — _highlights pending_ |
| [1.250414.2](2025-04-16_1.250414.2.md) | `ios` | 2025-04-16 | `TODO` (`ios`) — _highlights pending_ |
| [1.250407.47](2025-04-14_1.250407.47.md) | `android` | 2025-04-14 | `TODO` (`android`) — _highlights pending_ |
| [1.240902.17](2025-04-14_1.240902.17.md) | `android` | 2025-04-14 | `TODO` (`android`) — _highlights pending_ |
| [1.250324.17](2025-04-13_1.250324.17.md) | `android` | 2025-04-13 | `TODO` (`android`) — _highlights pending_ |
| [1.241216.7](2025-04-13_1.241216.7.md) | `android` | 2025-04-13 | `TODO` (`android`) — _highlights pending_ |
| [1.240826.27](2025-04-12_1.240826.27.md) | `android` | 2025-04-12 | `TODO` (`android`) — _highlights pending_ |
| [1.241021.17](2025-04-11_1.241021.17.md) | `android` | 2025-04-11 | `TODO` (`android`) — _highlights pending_ |
| [1.250407.0](2025-04-10_1.250407.0.md) | `ios` | 2025-04-10 | `TODO` (`ios`) — _highlights pending_ |
| [1.250331.7](2025-04-10_1.250331.7.md) | `android` | 2025-04-10 | `TODO` (`android`) — _highlights pending_ |
| [1.241104.5](2025-04-10_1.241104.5.md) | `android` | 2025-04-10 | `TODO` (`android`) — _highlights pending_ |
| [1.241104.7](2025-04-08_1.241104.7.md) | `android` | 2025-04-08 | `TODO` (`android`) — _highlights pending_ |
| [1.240812.7](2025-04-08_1.240812.7.md) | `android` | 2025-04-08 | `TODO` (`android`) — _highlights pending_ |
| [1.250217.10](2025-04-07_1.250217.10.md) | `android` | 2025-04-07 | `TODO` (`android`) — _highlights pending_ |
| [1.240916.17](2025-04-03_1.240916.17.md) | `android` | 2025-04-03 | `TODO` (`android`) — _highlights pending_ |
| [1.250331.0](2025-04-02_1.250331.0.md) | `ios` | 2025-04-02 | `TODO` (`ios`) — _highlights pending_ |
| [1.250224.17](2025-03-31_1.250224.17.md) | `android` | 2025-03-31 | `TODO` (`android`) — _highlights pending_ |
| [1.250224.27](2025-03-30_1.250224.27.md) | `android` | 2025-03-30 | `TODO` (`android`) — _highlights pending_ |
| [1.250310.7](2025-03-29_1.250310.7.md) | `android` | 2025-03-29 | `TODO` (`android`) — _highlights pending_ |
| [1.241028.27](2025-03-27_1.241028.27.md) | `android` | 2025-03-27 | `TODO` (`android`) — _highlights pending_ |
| [1.250324.0](2025-03-26_1.250324.0.md) | `ios` | 2025-03-26 | `TODO` (`ios`) — _highlights pending_ |
| [1.250317.17](2025-03-24_1.250317.17.md) | `android` | 2025-03-24 | `TODO` (`android`) — _highlights pending_ |
| [1.250317.1](2025-03-20_1.250317.1.md) | `ios` | 2025-03-20 | `TODO` (`ios`) — _highlights pending_ |
| [1.250317.0](2025-03-19_1.250317.0.md) | `ios` | 2025-03-19 | `TODO` (`ios`) — _highlights pending_ |
| [1.250310.1](2025-03-13_1.250310.1.md) | `ios` | 2025-03-13 | `TODO` (`ios`) — _highlights pending_ |
| [1.250310.0](2025-03-12_1.250310.0.md) | `ios` | 2025-03-12 | `TODO` (`ios`) — _highlights pending_ |
| [1.250303.0](2025-03-05_1.250303.0.md) | `ios` | 2025-03-05 | `TODO` (`ios`) — _highlights pending_ |
| [1.250224.2](2025-02-27_1.250224.2.md) | `ios` | 2025-02-27 | `TODO` (`ios`) — _highlights pending_ |
| [1.250224.1](2025-02-26_1.250224.1.md) | `ios` | 2025-02-26 | `TODO` (`ios`) — _highlights pending_ |
| [1.250217.0](2025-02-20_1.250217.0.md) | `ios` | 2025-02-20 | `TODO` (`ios`) — _highlights pending_ |
| [1.250210.0](2025-02-12_1.250210.0.md) | `ios` | 2025-02-12 | `TODO` (`ios`) — _highlights pending_ |
| [1.250203.0](2025-02-06_1.250203.0.md) | `ios` | 2025-02-06 | `TODO` (`ios`) — _highlights pending_ |
| [1.250127.0](2025-01-30_1.250127.0.md) | `ios` | 2025-01-30 | `TODO` (`ios`) — _highlights pending_ |
| [1.250120.1](2025-01-22_1.250120.1.md) | `ios` | 2025-01-22 | `TODO` (`ios`) — _highlights pending_ |
| [1.250113.0](2025-01-15_1.250113.0.md) | `ios` | 2025-01-15 | `TODO` (`ios`) — _highlights pending_ |
| [1.250106.0](2025-01-08_1.250106.0.md) | `ios` | 2025-01-08 | `TODO` (`ios`) — _highlights pending_ |
| [1.241216.3](2024-12-19_1.241216.3.md) | `ios` | 2024-12-19 | `TODO` (`ios`) — _highlights pending_ |
| [1.241216.0](2024-12-12_1.241216.0.md) | `ios` | 2024-12-12 | `TODO` (`ios`) — _highlights pending_ |
| [1.241209.2](2024-12-11_1.241209.2.md) | `ios` | 2024-12-11 | `TODO` (`ios`) — _highlights pending_ |
| [1.241202.0](2024-12-07_1.241202.0.md) | `ios` | 2024-12-07 | `TODO` (`ios`) — _highlights pending_ |
| [1.241118.3](2024-11-27_1.241118.3.md) | `ios` | 2024-11-27 | `TODO` (`ios`) — _highlights pending_ |
| [1.241118.2](2024-11-20_1.241118.2.md) | `ios` | 2024-11-20 | `TODO` (`ios`) — _highlights pending_ |
| [1.241111.3](2024-11-16_1.241111.3.md) | `ios` | 2024-11-16 | `TODO` (`ios`) — _highlights pending_ |
| [1.241111.2](2024-11-14_1.241111.2.md) | `ios` | 2024-11-14 | `TODO` (`ios`) — _highlights pending_ |
| [1.241111.0](2024-11-07_1.241111.0.md) | `ios` | 2024-11-07 | `TODO` (`ios`) — _highlights pending_ |
| [1.241104.1](2024-11-06_1.241104.1.md) | `ios` | 2024-11-06 | `TODO` (`ios`) — _highlights pending_ |
| [1.241104.0](2024-10-31_1.241104.0.md) | `ios` | 2024-10-31 | `TODO` (`ios`) — _highlights pending_ |
| [1.241028.2](2024-10-29_1.241028.2.md) | `ios` | 2024-10-29 | `TODO` (`ios`) — _highlights pending_ |
| [1.241021.7](2024-10-23_1.241021.7.md) | `ios`, `android` | 2024-10-23 | `TODO` (`ios`, `android`) — _highlights pending_ |
| [1.241021.4](2024-10-22_1.241021.4.md) | `ios` | 2024-10-22 | `TODO` (`ios`) — _highlights pending_ |
| [1.241021.2](2024-10-18_1.241021.2.md) | `ios` | 2024-10-18 | `TODO` (`ios`) — _highlights pending_ |
| [1.241021.0](2024-10-17_1.241021.0.md) | `ios` | 2024-10-17 | `TODO` (`ios`) — _highlights pending_ |
| [1.241007.1](2024-10-08_1.241007.1.md) | `ios` | 2024-10-08 | `TODO` (`ios`) — _highlights pending_ |
| [1.240930.2](2024-10-02_1.240930.2.md) | `ios` | 2024-10-02 | `TODO` (`ios`) — _highlights pending_ |
| [1.240923.1](2024-09-26_1.240923.1.md) | `ios` | 2024-09-26 | `TODO` (`ios`) — _highlights pending_ |
| [1.240916.1](2024-09-17_1.240916.1.md) | `ios` | 2024-09-17 | `TODO` (`ios`) — _highlights pending_ |
| [1.240909.0](2024-09-10_1.240909.0.md) | `ios` | 2024-09-10 | `TODO` (`ios`) — _highlights pending_ |
| [1.240902.2](2024-09-06_1.240902.2.md) | `ios` | 2024-09-06 | `TODO` (`ios`) — _highlights pending_ |
| [1.240826.1](2024-09-01_1.240826.1.md) | `ios` | 2024-09-01 | `TODO` (`ios`) — _highlights pending_ |
