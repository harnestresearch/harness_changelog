# Claude Changelog History

English | [简体中文](../../zh-CN/full/claude/README.md) · [Highlight](../../claude/README.md) | **Full Detail**

Complete multi-platform version history covering **533** unified releases across `mac`, `win`, `ubuntu`, `ios`, and `android` (**245** Desktop releases + **288** Mobile releases).

## Five-Platform Coverage Overview

| Platform | Distribution / Package | Tracked Releases | Version Range | Latest Version |
|---|---|---|---|---|
| `mac` | macOS (`Claude.app` / Cask & CDN) | 228 | `0.4.8` → `5.11492.5` | [5.11492.5](2026-11-14_5.11492.5.md) |
| `win` | Windows (`Anthropic.Claude` Winget, Squirrel & MSIX) | 206 | `0.4.9` → `5.11492.5` | [5.11492.5](2026-11-14_5.11492.5.md) |
| `ubuntu` | Ubuntu / Debian APT (`claude-desktop`) | 70 | `1.17180.0` → `5.11492.5` | [5.11492.5](2026-11-14_5.11492.5.md) |
| `ios` | iOS App Store (`com.anthropic.claude`) | 171 | `1.240826.1` → `1.261109.19` | [1.261109.19](2026-11-11_1.261109.19.md) |
| `android` | Android (`com.anthropic.claude`) | 154 | `1.240805.17` → `1.261113.19` | [1.261113.19](2026-11-14_1.261113.19.md) |

## Key Architectural & Feature Milestones

| Milestone | Introduced In | Release Date | Description |
|---|---|---|---|
| Initial Desktop Release & `claude-native` | [0.4.8](2024-10-31_0.4.8.md) | 2024-10-31 | Main window + Quick Window, Rust native helper module, and MCP SDK 0.1 |
| MCP Management UI & Developer Mode | [0.7.1](2024-11-22_0.7.1.md) | 2024-11-22 | Local MCP server install confirmation, log entry points, and React settings UI |
| Swift Native Addon & Quick Entry | [0.9.4](2025-06-03_0.9.4.md) / [0.12.15](2025-07-14_0.12.15.md) | 2025-06-03 | Shipped `claude-swift` native bridge, followed by voice dictation permissions and the Quick Entry bar |
| 1.0 GA Release & Terminal `node-pty` | [1.0.734](2025-11-21_1.0.734.md) / [1.0.2768](2026-01-05_1.0.2768.md) | 2025-11-21 | Entered the `1.x` GA release line and integrated the built-in `node-pty` pseudo-terminal module in `1.0.2768` |
| Cowork VM Image `smol-bin` | [1.1.280](2026-01-16_1.1.280.md) | 2026-01-16 | Bundled lightweight Apple Virtualization VM image, inaugurating the isolated local execution architecture |
| Computer Use Native Module | [1.1.8308](2026-03-23_1.1.8308.md) | 2026-03-23 | Added the `computer_use.node` screen control module under `@ant/claude-swift` |
| Offline Web Frontend `ion-dist` | [1.2.234](2026-04-01_1.2.234.md) | 2026-04-01 | Bundled the complete web frontend offline inside client resources for the first time |
| Bundled Skills | [1.15962.0](2026-06-25_1.15962.0.md) | 2026-06-25 | Shipped built-in skill packages including `docx`, `pdf`, `pptx`, `xlsx`, and `frontend-design` |
| `2.x` Major Version Upgrade | [2.110.0](2026-09-15_2.110.0.md) | 2026-09-15 | Upgraded to the `2.x` series, introducing model catalog, self-hosted third-party inference, enterprise managed policies, and cloud sessions |
| `3.x` Artifact Shell Network Bridge | [3.1623.0](2026-10-20_3.1623.0.md) | 2026-10-20 | Electron 44.9, `artifactShell.js`, and local OOXML/Frame backend architecture took shape |
| `4.x` Full ASAR Integrity Packaging | [4.29.0](2026-10-27_4.29.0.md) | 2026-10-27 | Packaged `ion-dist.asar` with integrity verification, followed by `design`/`slides` Frame runtimes and Gmail/Drive MCP in [4.16336.0](2026-11-03_4.16336.0.md) |
| `5.x` Built-in Browser Extension Ecosystem | [5.1231.0](2026-11-10_5.1231.0.md) | 2026-11-10 | Electron 45.2.1, in-app Chrome Web Store extension installation, 1Password autofill bridge, and Three.js 3D Artifact rendering |

## Desktop Version Index (`mac` / `win` / `ubuntu`, Newest → Oldest)

| Version | Platforms | Release Date | Electron | Key Changes |
|---|---|---|---|---|
| [5.11492.5](2026-11-14_5.11492.5.md) | `mac`, `win`, `ubuntu` | 2026-11-14 | 45.2.1 | Engine minor update + Office skill hardening (zero UI changes): session storage key schema (`index.chunk-BDY2-Sqh.js`, `jobs-root`, `setSessionArchived`), `blockFileToolReadsOutsideWorkingDirectories`, `docx`/`pptx`/`xlsx` `names_another_root` + relationship containment + bounded `SequenceMatcher`, 10-locale `ion-dist` catch-up, `smol-bin` & macOS binary rotation |
| [5.11492.2](2026-11-13_5.11492.2.md) | `mac`, `win`, `ubuntu` | 2026-11-13 | 45.2.1 | New date-segment epoch (merging `5.11492.0`): `ConfigTemplateExport` window/eipc, `SandboxNetworkAccess` permission rule, `ssh_host_settings`, `readOpenedFileChunk`, `openMicrophoneSettings`, Chrome action-level prompts, 4 MCP OAuth modes, Windows `claude://` `-- "%1"` hardening, Linux `0755` perms & Artifact CDN parity |
| [5.1231.2](2026-11-11_5.1231.2.md) | `mac`, `ubuntu` | 2026-11-11 | 45.2.1 | Quick hotfix: updated permission prompts, design system folder attachment, and scheduled task details; added missing 1Password domains |
| [5.1231.0](2026-11-10_5.1231.0.md) | `mac`, `ubuntu` | 2026-11-10 | 45.2.1 | Major bump 4→5 = extension ecosystem milestone: in-app Chrome Web Store install/management, extension agentic bridge (including 1Password credential autofill), and Cowork plugin directory; added three.js 3D artifact rendering in ion-dist; upgraded Electron to 45.2.1 |
| [4.23118.1](2026-11-09_4.23118.1.md) | `mac`, `ubuntu` | 2026-11-09 | 44.9.3 | Stability patch: official plugin marketplace repository references, zod v4 internal identifiers (\$Zod* family from CLI validation library upgrade), and localization completions; no structural changes |
| [4.23118.0](2026-11-05_4.23118.0.md) | `mac`, `ubuntu` | 2026-11-05 | 44.9.3 | Web GitHub/SSH connection UI and Claude Slides integration took shape; desktop rules system, session handoff, and on-demand CLI download; guided CLI installation into VS Code/JetBrains |
| [4.16336.0](2026-11-03_4.16336.0.md) | `mac`, `ubuntu` | 2026-11-03 | 44.9.3 | Landmark update: official Google Gmail/Drive MCP endpoints, `design`/`slides` artifact frame runtimes (268 files), and MCP App view window; Linux VM download endpoints appeared, extending Cowork toward Linux virtualization |
| [4.4212.0](2026-10-29_4.4212.0.md) | `mac`, `ubuntu` | 2026-10-29 | 44.9.3 | Web feature updates (artifact empty state, browser remote connection, Cloudflare challenge handling) + routine embedded CLI refresh; new identifiers ADD_CUSTOM_CONNECTOR_ARRIVAL_* and ArtifactsNewMenu* (custom connector onboarding) |
| [4.29.0](2026-10-27_4.29.0.md) | `mac`, `ubuntu` | 2026-10-27 | 44.9.3 | Major bump 3→4 engineering milestone: web frontend and locale packs fully packaged as ASAR archives under integrity verification, dramatically consolidating the Resources directory; expanded smol-bin VM image |
| [3.6556.2](2026-10-23_3.6556.2.md) | `mac`, `win`, `ubuntu` | 2026-10-23 | 44.9.3 | No substantive functional changes (routine rebuild + embedded CLI string rotation + skills ref bump) |
| [3.6556.1](2026-10-22_3.6556.1.md) | `mac`, `win`, `ubuntu` | 2026-10-22 | 44.9.3 | Major internal 3.x release: shipped frame-local-worker (local artifact frame host + HTML rewriting), Google Drive MCP, and Slack enterprise domain integration; identifiers revealed ANTHROPIC_DEFAULT_FABLE_MODEL/MYTHOS_MODEL (new model codenames) and CLAUDE_CODE_EXPERIMENTAL_AGENT_TEAMS |
| [3.1623.4](2026-10-22_3.1623.4.md) | `mac`, `win`, `ubuntu` | 2026-10-22 | 44.9.0 | Same-day hotfix: fixes around Cowork/Dispatch cloud task replicas and mounting issues; no structural changes |
| [3.1623.3](2026-10-22_3.1623.3.md) | `mac`, `win`, `ubuntu` | 2026-10-22 | 44.9.0 | Major refresh of embedded Claude Code CLI: full OAuth flow endpoints, multi-cloud provider environment variables (ANTHROPIC_* Bedrock/Vertex/Foundry/Google Cloud and full AWS_* suite), plus federation/gateway identifiers |
| [3.1623.1](2026-10-21_3.1623.1.md) | `mac`, `win`, `ubuntu` | 2026-10-21 | 44.9.0 | Minor patch: Slack Connector, iOS Simulator status prompts, and frontend rendering library URLs |
| [3.1623.0](2026-10-20_3.1623.0.md) | `mac`, `win`, `ubuntu` | 2026-10-20 | 44.9.0 | Major bump 2→3: Electron 44.9 + anti-downgrade toggle + new artifactShell bundle (Cowork artifact network bridge) + two new internal packages (OOXML→HTML and frame-local-backend), kicking off the Cowork artifact rendering stack overhaul; no breaking UI layout changes |
| [2.42304.2](2026-10-19_2.42304.2.md) | `mac`, `win`, `ubuntu` | 2026-10-19 | 44.7.2 | Hotfix patch: enhanced OOXML parsing in Office 365 MCP and GitHub API integration; refreshed embedded Claude Code CLI (numerous CLAUDE_CODE_* proxy/certificate environment variables) |
| [2.42304.0](2026-10-15_2.42304.0.md) | `mac`, `win`, `ubuntu` | 2026-10-15 | 44.7.2 | Shipped SSH remote host support (askpass helper + ssh2 transport + session host concept); laid out strings for plugin marketplace and Slack connector; adjusted node-pty packaging |
| [2.37337.1](2026-10-13_2.37337.1.md) | `mac`, `win`, `ubuntu` | 2026-10-13 | 44.7.0 | Electron upgrade + broad rollout of Claude Code/Cowork features around folder access, PR auto-fix, and model catalog; first appearance of Figma remote MCP and model-catalog endpoints |
| [2.31226.1](2026-10-09_2.31226.1.md) | `mac`, `win`, `ubuntu` | 2026-10-09 | 44.4.3 | Minor release: landed GA agent-sdk 0.3.295; no other functional changes |
| [2.31226.0](2026-10-08_2.31226.0.md) | `mac`, `win`, `ubuntu` | 2026-10-08 | 44.4.3 | Launched enterprise Tool policy (endpoints + rules) and Cowork file-read validation; hardened SSH remote session transport layer and added HIPAA compliance copy |
| [2.26454.2](2026-10-07_2.26454.2.md) | `mac`, `win`, `ubuntu` | 2026-10-07 | 44.4.3 | Main-process fix release (web frontend frozen): RC SDK + sandbox settings documentation link |
| [2.26454.0](2026-10-06_2.26454.0.md) | `mac`, `win`, `ubuntu` | 2026-10-06 | 44.4.3 | Embedded xterm headless terminal inside heavy-work worker (paired with new dependency @xterm/headless 6.0.0 to emulate session terminals and Quick Write); new flags for Quick Write, M365 Windows account sign-in, and in-browser connector sign-in; Office MCP updates |
| [2.19675.1](2026-10-05_2.19675.1.md) | `mac`, `win`, `ubuntu` | 2026-10-05 | 44.4.3 | Minor release: SDK upgrade, pptx skill update, and one sandbox prompt |
| [2.19675.0](2026-10-01_2.19675.0.md) | `mac`, `win` | 2026-10-01 | 44.4.3 | Launched Android/iOS mobile build guides and repository trust ("trust this repository") flow; SDK 0.3.286 |
| [2.16120.0](2026-09-30_2.16120.0.md) | `mac`, `win` | 2026-09-30 | 44.4.3 | Cowork EDR integration (hallmark flag for enterprise security integration with Cowork VMs) + plugin MCP blocklist + enterprise GitHub/GitLab extensions |
| [2.9939.4](2026-09-28_2.9939.4.md) | `mac`, `win`, `ubuntu` | 2026-09-28 | 44.4.3 | No substantive functional changes (RC SDK + web rebuild / chunk reshuffle) |
| [2.9939.2](2026-09-24_2.9939.2.md) | `mac`, `win` | 2026-09-24 | 44.4.3 | Rebuild + minor SDK bump; fileIndexWorker size cut in half via bundling optimization, with no functional changes |
| [2.9939.1](2026-09-24_2.9939.1.md) | `mac` | 2026-09-24 | 44.4.3 | Launched organization plugin/skill marketplace and shared governance; added two new flags for Claude in Chrome password manager and gateway-managed Claude Code |
| [2.7032.0](2026-09-22_2.7032.0.md) | `mac`, `win`, `ubuntu` | 2026-09-22 | 44.4.3 | Electron 44.4.3 upgrade + expanded enterprise controls (corporate launcher, device tools, keep-awake, IdP OIDC), plus Figma MCP integration |
| [2.2553.13](2026-09-22_2.2553.13.md) | `mac`, `win`, `ubuntu` | 2026-09-22 | 44.2.0 | Rebuild + RC agent-sdk; no substantive functional changes |
| [2.2553.1](2026-09-18_2.2553.1.md) | `mac`, `win`, `ubuntu` | 2026-09-18 | 44.2.0 | Minor release: SDK upgrade + rebuild |
| [2.2553.0](2026-09-17_2.2553.0.md) | `mac`, `ubuntu` | 2026-09-17 | 44.2.0 | Cloud Claude Code sessions (cloud sessions + Remote Control) and organization plugin MCP governance arrived on desktop; version jumped to the 2553 internal build series |
| [2.110.1](2026-09-17_2.110.1.md) | `mac`, `ubuntu` | 2026-09-17 | 44.2.0 | No substantive functional changes (rebuild / re-sign / chunk reshuffle only) |
| [2.110.0](2026-09-15_2.110.0.md) | `mac`, `ubuntu` | 2026-09-15 | 44.2.0 | 2.0 milestone release. Second version segment switched to an internal build number (110, used as release train ID); core additions include model catalog (catalog.json + default model/effort settings) and self-hosted third-party inference (full settings suite for Azure AI Foundry / Microsoft Entra OIDC / credential helper scripts), plus a new iOS Simulator bridge binary and hardened MCP/filesystem security; web frontend switched to a new build pipeline with greatly expanded copy. Cloud Claude Code sessions had not yet surfaced in settings in this build (see 2.2553.0) |
| [1.52386.6](2026-09-13_1.52386.6.md) | `mac`, `ubuntu` | 2026-09-13 | 44.2.0 | Final 1.x release: bumped agent-sdk to 0.3.270 and updated bundler; no user-visible functional changes |
| [1.52386.4](2026-09-12_1.52386.4.md) | `mac` | 2026-09-12 | 44.2.0 | Rebuild release; the only substantive change flipped the Windows VM file-share fallback default to disabled |
| [1.52386.3](2026-09-11_1.52386.3.md) | `mac`, `win`, `ubuntu` | 2026-09-11 | 44.2.0 | Pure rebuild / re-sign release; the sole functional difference removed the Windows VM file-share fallback setting |
| [1.52386.1](2026-09-11_1.52386.1.md) | `mac` | 2026-09-11 | 44.2.0 | Significant expansion of the embedded agent runtime (Claude Code): background git worktree checkout, AWS credentials, and GitHub user info / device-code login; allowlists exposed the MYTHOS/FABLE model families and AGENT_TEAMS experimental flag (internal codenames only, not publicly enabled) |
| [1.52386.0](2026-09-11_1.52386.0.md) | `mac`, `ubuntu` | 2026-09-11 | 44.2.0 | Dual SSH engines (ssh2 + native OpenSSH) and PTY Host service naming, MCP elicitation/sampling capability negotiation, and Argon2 encryption parameters entered heavy-work worker; GitHub REST/GraphQL APIs and claude.com/claude-code links entered the main process |
| [1.49585.0](2026-09-08_1.49585.0.md) | `mac`, `win`, `ubuntu` | 2026-09-08 | 44.2.0 | Major milestone update: Electron 44.2.0 raised minimum OS to macOS 13+ and consolidated ANGLE libraries; slimmed down iOS Simulator helper (removed embedded frameworks); office365 MCP formalized its stdio entry point and hardened MSAL encrypted token storage |
| [1.46388.4](2026-09-05_1.46388.4.md) | `mac`, `win` | 2026-09-05 | 42.10.0 | No substantive functional changes (full republish of web frontend and skills) |
| [1.46388.3](2026-09-04_1.46388.3.md) | `mac`, `win` | 2026-09-04 | 42.10.0 | No substantive functional changes (rebuild) |
| [1.46388.2](2026-09-04_1.46388.2.md) | `mac`, `win`, `ubuntu` | 2026-09-04 | 42.10.0 | Essentially no substantive functional changes (rebuild + one connection prompt string) |
| [1.46388.1](2026-09-04_1.46388.1.md) | `mac`, `win` | 2026-09-04 | 42.10.0 | Minor change: Remote Control registration reporting granularity notes added to chunks; otherwise a rebuild |
| [1.46388.0](2026-09-03_1.46388.0.md) | `mac` | 2026-09-03 | 42.10.0 | Shipped GitHub PR auto-fix and SSH key detection in main process chunks; added trap/nonce guard markers to bash shell integration |
| [1.44121.4](2026-09-03_1.44121.4.md) | `mac`, `win` | 2026-09-03 | 42.10.0 | No substantive functional changes (rebuild) |
| [1.44121.2](2026-09-02_1.44121.2.md) | `mac`, `win`, `ubuntu` | 2026-09-02 | 42.10.0 | No substantive functional changes (rebuild) |
| [1.44121.1](2026-09-02_1.44121.1.md) | `mac` | 2026-09-02 | 42.10.0 | Introduced remote tool bridge environment variables including CLAUDE_REMOTE_TOOLS_BRIDGE_URL and permission scope descriptions; otherwise a rebuild |
| [1.44121.0](2026-09-02_1.44121.0.md) | `mac` | 2026-09-02 | 42.10.0 | Major renderer build pipeline refactor (chunk splitting + CSS code-splitting); substantially expanded Cowork/sandbox agent prompts embedded in the main process, and migrated MCP validation to Zod v4 |
| [1.40609.1](2026-09-01_1.40609.1.md) | `mac`, `win`, `ubuntu` | 2026-09-01 | 42.10.0 | No substantive functional changes (rebuild) |
| [1.40609.0](2026-08-28_1.40609.0.md) | `mac`, `win`, `ubuntu` | 2026-08-28 | 42.10.0 | Expanded Office document processing capabilities (skill-based Word/Excel/PPT formatting, charts, formulas) and brought GitHub PR auto-fix agent semantics into the main process; added frame-connect and frame-manage artifact frame entry points to ion-dist |
| [1.37937.3](2026-08-26_1.37937.3.md) | `mac`, `win`, `ubuntu` | 2026-08-26 | 42.10.0 | No substantive functional changes (third same-day re-release) |
| [1.37937.2](2026-08-26_1.37937.2.md) | `mac` | 2026-08-26 | 42.10.0 | No substantive functional changes (full republish of web frontend and skills) |
| [1.37937.1](2026-08-26_1.37937.1.md) | `mac`, `win`, `ubuntu` | 2026-08-26 | 42.10.0 | Essentially no substantive functional changes (rebuild); only clue is a native WebSocket client implementation embedded inside chunks |
| [1.37937.0](2026-08-25_1.37937.0.md) | `mac`, `win`, `ubuntu` | 2026-08-25 | 42.10.0 | Two highlights: upgraded Electron to 42.10.0; introduced macOS Quick Actions/Services integration (quick-actions templates). Main Info.plist NSUserActivityTypes also added `com.apple.corespotlightitem` (CoreSpotlight/Handoff support) |
| [1.34493.1](2026-08-21_1.34493.1.md) | `mac`, `win`, `ubuntu` | 2026-08-21 | 42.9.2 | No substantive functional changes (rebuild / re-sign / chunk reshuffle only), a hotfix-style re-release within a day |
| [1.34493.0](2026-08-20_1.34493.0.md) | `mac`, `win`, `ubuntu` | 2026-08-20 | 42.9.2 | Added designWindow preload and V8 compile-cache (dual-architecture bytecode); introduced versioned frame kernels (kernel-0.1.x) on web; refined SSH connection config validation copy; significantly reduced package size |
| [1.32885.1](2026-08-18_1.32885.1.md) | `mac`, `win`, `ubuntu` | 2026-08-18 | 42.9.2 | No substantive functional changes (rebuild). Back-to-back .0/.1 releases on the same day |
| [1.32885.0](2026-08-18_1.32885.0.md) | `mac` | 2026-08-18 | 42.9.2 | Near-rebuild minor release; added embed runtime module on web, with the rest being chunk reshuffles |
| [1.32352.1](2026-08-18_1.32352.1.md) | `mac`, `win`, `ubuntu` | 2026-08-18 | 42.9.2 | No substantive functional changes (rebuild) |
| [1.32352.0](2026-08-17_1.32352.0.md) | `mac`, `win`, `ubuntu` | 2026-08-17 | 42.9.2 | Upgraded Electron to 42.9.2; surfaced extensive copy for plugin/skill marketplace and Widget/Device Hub alongside 407 new web assets; switched heavy-work worker to Rolldown bundling; bundled mime-db |
| [1.30096.5](2026-08-15_1.30096.5.md) | `mac`, `win`, `ubuntu` | 2026-08-15 | 42.7.0 | No substantive functional changes (rebuild; updated skills manifest reference) |
| [1.30096.1](2026-08-14_1.30096.1.md) | `mac`, `win`, `ubuntu` | 2026-08-14 | 42.7.0 | No substantive functional changes (rebuild) |
| [1.30096.0](2026-08-13_1.30096.0.md) | `mac` | 2026-08-13 | 42.7.0 | Switched OAuth infrastructure to platform.claude.com (including CLI API key issuance and credit purchases), surfaced dedicated FedStart domains and mcp-proxy.anthropic.com; made Buddy desktop accessory repo public; converted web install-hub icons to PNG and added Apple channel icon; reverted index2 chunk experiment |
| [1.28929.0](2026-08-12_1.28929.0.md) | `mac`, `ubuntu` | 2026-08-12 | 42.7.0 | Bundled ssh2 and GitHub App/CLI auth — completing end-to-end wiring for remote development (Claude SSH) and GitHub MCP; added app-cu-helper; renamed renderer window styling system; added Code Review promotional assets and room/sample runtime modules on web |
| [1.26832.0](2026-08-07_1.26832.0.md) | `mac`, `ubuntu` | 2026-08-07 | 42.7.0 | Connected GitHub MCP (api.github.com + GitHub App auth); added scheduled/reminder task copy and Artifact sharing (auto-publish) flow; surfaced new capability identifiers for Buddy Bluetooth transport and live computer-use preview |
| [1.25927.0](2026-08-04_1.25927.0.md) | `mac`, `win`, `ubuntu` | 2026-08-04 | 42.7.0 | Major milestone update: bundled GitHub MCP server binary and permission-fixer helper; added local execution consent window (localExecConsent) and stall-sampler worker in the main process; namespaced dual-chunk bundles and bundled node-forge/rxjs/winston; introduced official Claude Code/Claude SSH binary download endpoints plus broad enterprise OAuth entry points for M365/Box/Slack/Bedrock/Google; renamed locale directory |
| [1.24012.11](2026-08-03_1.24012.11.md) | `mac`, `win`, `ubuntu` | 2026-08-03 | 42.7.0 | No substantive functional changes (rebuild). Released 10 days after the previous version as a rotation build off the same source tree |
| [1.24012.9](2026-07-24_1.24012.9.md) | `mac`, `win`, `ubuntu` | 2026-07-24 | 42.7.0 | No substantive functional changes (rebuild + web shared chunk reorganization) |
| [1.24012.1](2026-07-21_1.24012.1.md) | `mac`, `win` | 2026-07-21 | 42.7.0 | No substantive functional changes (same-day hotfix rebuild) |
| [1.24012.0](2026-07-21_1.24012.0.md) | `mac`, `win`, `ubuntu` | 2026-07-21 | 42.7.0 | Upgraded Electron to 42.7.0; significantly expanded web frame runtime (translate/downloads/mcp/permissions/user modules); added built-in MCP auth error classes (BuiltinMcpNeedsAuthError/BuiltinMcpSignInCanceledError), simulator recording, Android Studio detection, and skill recommendation prompts in the main process |
| [1.22209.3](2026-07-19_1.22209.3.md) | `mac`, `win`, `ubuntu` | 2026-07-19 | 42.5.1 | Patch release: added Anthropic on Google Cloud environment variables and device simulator platform flag copy; otherwise a full rebuild |
| [1.22209.0](2026-07-16_1.22209.0.md) | `mac`, `ubuntu` | 2026-07-16 | 42.5.1 | Introduced Claude Code mobile simulator tooling: bundled iOS Simulator control helper (Facebook idb framework) + Android Emulator (adb) integration, complete with settings, admin block policies, and Statsig dashboards ("Claude Code iOS Simulator"/"Claude Code Android Emulator" dashboard UUIDs); merged node-forge PKI and gitignore matching into heavy-work worker |
| [1.21459.3](2026-07-16_1.21459.3.md) | `mac`, `win`, `ubuntu` | 2026-07-16 | 42.5.1 | No substantive functional changes (rebuild only). Back-to-back .1/.3 hotfix builds on the same day |
| [1.21459.1](2026-07-16_1.21459.1.md) | `mac`, `win`, `ubuntu` | 2026-07-16 | 42.5.1 | No substantive functional changes (rebuild / re-sign / chunk reshuffle only) |
| [1.21459.0](2026-07-14_1.21459.0.md) | `mac`, `win`, `ubuntu` | 2026-07-14 | 42.5.1 | Added pty-host worker (service-oriented terminal host) and Swift memoryPressure native API; heavily expanded heavy-work/transcript-search/directMcpHost; completed comments/downloads/permissions/mcp modules in frame runtime; synced massive new copy on web alongside the claude.ai redesign |
| [1.20186.9](2026-07-14_1.20186.9.md) | `mac`, `win`, `ubuntu` | 2026-07-14 | 42.5.1 | No substantive functional changes (agent-sdk upgrade + hotfix rebuild) |
| [1.20186.7](2026-07-14_1.20186.7.md) | `mac`, `ubuntu` | 2026-07-14 | 42.5.1 | No substantive functional changes (rebuild + Skills refresh only) |
| [1.20186.1](2026-07-11_1.20186.1.md) | `mac`, `win`, `ubuntu` | 2026-07-11 | 42.5.1 | No substantive functional changes (rebuild + Skills refresh only) |
| [1.20186.0](2026-07-09_1.20186.0.md) | `mac`, `win` | 2026-07-09 | 42.5.1 | Large-scale update (+20MB zip, primarily ion-dist): added heavy-work worker and Claude Browser / web browsing control copy; launched Cowork session folder authorization dialog; migrated OAuth endpoints to platform.claude.com and surfaced FedStart government cloud domains |
| [1.19367.0](2026-07-07_1.19367.0.md) | `mac`, `win`, `ubuntu` | 2026-07-07 | 42.5.1 | Major dependency upgrade release: major version jump for agent SDK / TS SDK, first hash-chunked main process bundle (+48 chunks), and new file-index worker and agent-base; strings revealed local agent capabilities including GitHub PR operations, SSH remote, MCPB packaging, Slack connector, and Claude Code CLI download (mostly carried by the embedded agent-sdk) |
| [1.18286.2](2026-07-07_1.18286.2.md) | `mac`, `win`, `ubuntu` | 2026-07-07 | 42.5.1 | No substantive functional changes (agent-sdk upgrade + hotfix rebuild) |
| [1.18286.0](2026-07-02_1.18286.0.md) | `mac`, `win`, `ubuntu` | 2026-07-02 | 42.5.1 | Minor main process tweaks (shell-path worker, Callback port); web rollout for in-session dev-server preview and chat memory |
| [1.17377.2](2026-07-01_1.17377.2.md) | `mac`, `win`, `ubuntu` | 2026-07-01 | 42.5.1 | No substantive functional changes (rebuild + Skills refresh only) |
| [1.17377.1](2026-07-01_1.17377.1.md) | `mac`, `win`, `ubuntu` | 2026-07-01 | 42.5.1 | No substantive functional changes (minor agent-sdk bump + Skills refresh + rebuild) |
| [1.17377.0](2026-06-30_1.17377.0.md) | `mac`, `ubuntu` | 2026-06-30 | 42.5.1 | No substantive main process changes; added worktree session and background task handoff copy on web (laying groundwork for Cowork git workflows) |
| [1.17282.0](2026-06-30_1.17282.0.md) | `mac`, `ubuntu` | 2026-06-30 | 42.5.1 | Primarily a rebuild + Skills refresh; minor web updates (secret show/hide toggle, allowed sites management) |
| [1.15962.2](2026-06-30_1.15962.2.md) | `win` | 2026-06-30 | — | `TODO` (`win`) — _detailed diff pending_ |
| [1.17180.0](2026-06-29_1.17180.0.md) | `mac`, `ubuntu` | 2026-06-29 | 42.5.1 | Upgraded Electron to 42.5.1; added computer-use watch/record dual bundles and Swift watchRecorder native interface; refreshed bundled Skills content (agentSkillsRef 1782518167); major web update for organization roles/approval policies, with early signs of Linux packaging preparation |
| [1.15962.1](2026-06-26_1.15962.1.md) | `mac`, `win` | 2026-06-26 | 42.4.0 | No substantive functional changes (rebuild / re-sign / chunk reshuffle only) |
| [1.15962.0](2026-06-25_1.15962.0.md) | `mac`, `win` | 2026-06-25 | 42.4.0 | Bundled 6 built-in Office/document Agent Skills for the first time (docx/pdf/pptx/xlsx + pdf-reading, frontend-design) and substantially expanded directMcpHost; added @google-cloud/storage dependency (serving GCS uploads/sync, with no explicit UI yet) |
| [1.15200.0](2026-06-23_1.15200.0.md) | `mac`, `win` | 2026-06-23 | 42.4.0 | Major enterprise/cloud integration release: upgraded node-pty to dual-architecture prebuilds; shipped built-in Microsoft 365 MCP server configuration, AWS Bedrock/Vertex/Foundry cloud provider integrations, and managed-config policy UI in the main process; bumped MCP SDK to 1.29.0 |
| [1.14271.0](2026-06-18_1.14271.0.md) | `mac`, `win` | 2026-06-18 | 42.4.0 | Enterprise governance foundation release: added managed-config dependency (managed IdP/OIDC config, with issuer/authorizationUrl/tokenUrl/oidc/bootstrapUrl validation and healthy/invalid_config/auth_failed state machines visible in index.js); added organization limits and spend cap UI on web |
| [1.13576.4](2026-06-18_1.13576.4.md) | `mac`, `win` | 2026-06-18 | 42.4.0 | No substantive functional changes (full rebuild and pure hash reshuffle of app.asar and ion-dist) |
| [1.13576.1](2026-06-17_1.13576.1.md) | `mac`, `win` | 2026-06-17 | 42.4.0 | No substantive functional changes (rebuild / re-sign + IPC UUID rotation only) |
| [1.13576.0](2026-06-16_1.13576.0.md) | `mac`, `win` | 2026-06-16 | 42.4.0 | Feature release: added Bedrock Mantle gateway and Claude API credential types plus beta feature admin toggle; streamlined office365-mcp packaging layout and introduced a deb bundler for Linux distribution |
| [1.12603.1](2026-06-11_1.12603.1.md) | `mac`, `win` | 2026-06-11 | 42.4.0 | No substantive functional changes (hotfix / rebuild) |
| [1.12603.0](2026-06-11_1.12603.0.md) | `mac` | 2026-06-11 | 42.4.0 | Heavyweight release: upgraded Electron to 42.4.0 and bundled the office365-mcp server for the first time (with native Microsoft MSAL authentication and PDF extraction), increasing app size by ~8MB |
| [1.11847.5](2026-06-09_1.11847.5.md) | `mac`, `win` | 2026-06-09 | 41.6.1 | Added frame-gallery entry point on web and reorganized dynamic i18n directories; minor model discovery error-handling tweak in the main process |
| [1.11187.4](2026-06-05_1.11187.4.md) | `mac`, `win` | 2026-06-05 | 41.6.1 | No substantive functional changes (minor fix / rebuild) |
| [1.11187.3](2026-06-05_1.11187.3.md) | `mac` | 2026-06-05 | 41.6.1 | No main process functional changes; web frontend update |
| [1.11187.2](2026-06-05_1.11187.2.md) | `mac` | 2026-06-05 | 41.6.1 | Main process updated alongside SDK; primarily a web frontend update |
| [1.11187.1](2026-06-04_1.11187.1.md) | `mac`, `win` | 2026-06-04 | 41.6.1 | Iteration focused on browser tool and credential robustness; introduced @ant/browser-tool-schemas dependency and routine web frontend updates |
| [1.10628.2](2026-06-03_1.10628.2.md) | `mac`, `win` | 2026-06-03 | 41.6.1 | No substantive main process changes; web frontend update |
| [1.10628.0](2026-06-03_1.10628.0.md) | `mac`, `win` | 2026-06-03 | 41.6.1 | Feature foundation release: split out standalone frame-shell entry point and updated voice worklet on web; added Auto mode governance in the main process and removed Swift hotkey bindings |
| [1.9659.4](2026-06-02_1.9659.4.md) | `mac`, `win` | 2026-06-02 | 41.6.1 | No substantive functional changes (agent-sdk upgrade + rebuild) |
| [1.9659.2](2026-05-29_1.9659.2.md) | `mac`, `win` | 2026-05-29 | 41.6.1 | No substantive functional changes (agent-sdk upgrade + rebuild) |
| [1.9659.1](2026-05-28_1.9659.1.md) | `mac`, `win` | 2026-05-28 | 41.6.1 | Feature release: integrated Box connector endpoints, Claude.ai data import (SSO), and per-tab Chat/Cowork admin policies; hardened process-group cleanup for shell probe child processes |
| [1.9255.2](2026-05-27_1.9255.2.md) | `mac`, `win` | 2026-05-27 | 41.6.1 | No substantive functional changes (minor fix / rebuild) |
| [1.9255.0](2026-05-26_1.9255.0.md) | `mac`, `win` | 2026-05-26 | 41.6.1 | Paved the way for tray usage stats and in-Chat code execution toggle; surfaced Outlook connector install entry on web |
| [1.8555.2](2026-05-23_1.8555.2.md) | `mac`, `win` | 2026-05-23 | 41.6.1 | Minor tweaks in the main process; primarily a web frontend (ion-dist) update |
| [1.8555.1](2026-05-22_1.8555.1.md) | `mac`, `win` | 2026-05-22 | 41.6.1 | No substantive functional changes (agent-sdk upgrade + rebuild) |
| [1.8555.0](2026-05-21_1.8555.0.md) | `mac`, `win` | 2026-05-21 | 41.6.1 | Routine iteration: agent-sdk upgrade, MCP instructions passthrough, tightened shell environment allowlist, and a full sync of the web frontend and all locale packs |
| [1.8089.1](2026-05-19_1.8089.1.md) | `mac`, `win` | 2026-05-19 | 41.6.1 | No substantive functional changes (rebuild / re-sign / version bump only) |
| [1.8089.0](2026-05-19_1.8089.0.md) | `mac`, `win` | 2026-05-19 | 41.6.1 | Electron 41.6.1 + rounded out enterprise third-party inference config (Anthropic API provider, model discovery, custom inference headers, proxy support via https-proxy-agent); added NSDesktopFolderUsageDescription / NSDocumentsFolderUsageDescription ("Claude stores your scheduled tasks, live artifacts and other Cowork files here.") / NSDownloadsFolderUsageDescription in Info.plist (explicit Cowork folder permissions); admin tool policy for plugin-delivered MCP servers ("Admin policy applied to plugin-delivered MCP servers."); startup company announcements ("Company announcements to display at startup"); git commit/PR attribution settings and auto-compact session compaction settings |
| [1.7196.3](2026-05-18_1.7196.3.md) | `mac`, `win` | 2026-05-18 | 41.5.0 | No substantive functional changes (pure version bump + re-signed republish) |
| [1.7196.1+abcd6556](2026-05-16_1.7196.1+abcd6556.md) | `mac`, `win` | 2026-05-16 | 41.5.0 | Rounded out remote SSH deployment (Cowork remote host path) error handling: "failed to install claude cli" / "failed to start remote server" / "server --install" / "sftp transfer stalled" / "ssh connection setup timed out" / "cannot parse privatekey" / "vm_pre_boot_error" / "host denied" / EADDRNOTAVAIL / "text file busy" — resolving a series of remote VM deployment failures when installing claude cli on remote hosts |
| [1.7196.1+ddbeb72e](2026-05-15_1.7196.1+ddbeb72e.md) | `mac` | 2026-05-15 | 41.5.0 | Device attestation & connection resilience: DEVICE_ATTESTATION_STATUS_ / VERIFIED_BY_GATE / bridge_event_attestation (bridge event device attestation); ANTHROPIC_WORKSPACE_ID; persistent SSE keepalive (session_keepalive_heartbeat / liveness_timeout / "SSE stream ended by server, reconnecting" / cli_sse_event_filtered); background_tasks |
| [1.7196.0](2026-05-12_1.7196.0.md) | `mac`, `win` | 2026-05-12 | 41.5.0 | Enterprise identity & governance enhancements: ANTHROPIC_* credential environment variable family (ANTHROPIC_IDENTITY_TOKEN(_FILE) / SERVICE_ACCOUNT_ID / FEDERATION_RULE_ID / PROFILE / ORGANIZATION_ID / SCOPE / CONFIG_DIR, forwarded for CLI/gateway auth); MCP Elicitation support (Elicitation/ElicitationResult); admin policies "Disable claude:// deep-link handling" and "Disable model verification"; GrowthbookExperimentEvent (A/B experiment events); first appearance of model name "Claude Opus 4"; "Halo detached." (Buddy Halo floating window state) |
| [1.6608.2](2026-05-09_1.6608.2.md) | `mac`, `win` | 2026-05-09 | 41.5.0 | Minor hotfix: added permission_stall telemetry (detecting hung/pending permission requests following the 1.6608.0 release) |
| [1.6608.1](2026-05-08_1.6608.1.md) | `win` | 2026-05-08 | — | `TODO` (`win`) — _detailed diff pending_ |
| [1.6608.0](2026-05-07_1.6608.0.md) | `mac`, `win` | 2026-05-07 | 41.5.0 | Major cleanup + new capabilities: removed local drizzle/operon SQLite stack entirely (migrated to remote/web storage); added Cowork artifact sharing and SafeFs sandbox filesystem error code family (ERR_SAFE_FS_DISPOSED/ESCAPE/NOT_REGULAR/ROOT/SIZE/SYMLINK); surfaced condadata.img / condadata.vhdx (VM attached data disk names hosting conda/Python environments); added "ElectronTeamID": "Q6L2SF6YDW" in Info.plist (notification signing team ID); "Microsoft 365" string literal (office365-mcp integration entry point) |
| [1.6259.1](2026-05-06_1.6259.1.md) | `mac`, `win` | 2026-05-06 | 41.5.0 | No substantive functional changes (same-day hotfix re-release / rebuild) |
| [1.6259.0](2026-05-06_1.6259.0.md) | `mac`, `win` | 2026-05-06 | 41.5.0 | Electron 41.5.0 + Bedrock SSO (IAM Identity Center, X-Amzn-Bedrock-Service-Tier header); "Hide Anthropic sign-in" (white-label option for third-party gateways); tool approval lock ("Lock the approval state for specific tools. Unlisted tools stay user-controlled."); hard egress block ("Link-local and metadata addresses are not allowed.", SSRF protection); updated built-in tool parameter descriptions such as Edit (with agent-sdk 0.2.128) |
| [1.5354.0](2026-04-29_1.5354.0.md) | `mac`, `win` | 2026-04-29 | 41.3.0 | Major expansion of the credential type registry (github-pat/fine-grained/app-token/refresh-token, gitlab-deploy-token/pat, databricks-api-token, digitalocean-access-token/pat, gcp-api-key, aws-access-token, azure-ad-client-secret, huggingface-access-token, grafana-api-key x3, hashicorp-tf-api-token, anthropic-api-key/admin-api-key — used for sensitive credential detection and log redaction); added claude-simulator, cowork-desktop-dispatch, and get_desktop_info (desktop info MCP tool); iOS Simulator availability check ("iOS Simulator requires macOS"); enforced https on bootstrapOidc endpoint |
| [1.5220.0](2026-04-28_1.5220.0.md) | `mac`, `win` | 2026-04-28 | 41.3.0 | Deepened managed config framework: Bedrock service tier, Gateway auth scheme, credential helper (external executable printing credentials + Headers helper script + cache TTL), mandatory auto-update install window (default 72 hours), organization workspace folder allowlist ("Folders users may attach as workspace"), Cowork tool egress domain config ("Domains Cowork's tools may reach during a turn"), "Built-in tools removed from Cowork.", and PR automation (CHANGES_REQUESTED / Auto-archive on PR close); added VM framebuffer preview capability |
| [1.4758.0](2026-04-24_1.4758.0.md) | `mac`, `win` | 2026-04-24 | 41.3.0 | Heaviest release of this phase: Electron 41.3.0 + enterprise third-party inference gateways (Bedrock/Vertex/Azure AI Foundry/OIDC Gateway SSO "Gateway SSO is not configured") + end-to-end Sentry/Crashpad/winston/OTel telemetry wiring + "Open Chrome and click Connect in the Claude extension" (Chrome extension pairing guide) + Info.plist NSUserActivityTypes updated to com.anthropic.claude.code.session; web frontend localized alongside this release |
| [1.3883.0](2026-04-21_1.3883.0.md) | `mac`, `win` | 2026-04-21 | 41.2.0 | Added NSUserActivityTypes=["com.anthropic.claude.session"] in Info.plist (macOS Handoff support); SSH governance ("SSH connections are disabled by your organization's managed settings." / SshPolicyError / claude-ssh is not available for platform); Bootstrap OIDC initial config (Bootstrap config URL/server, Bootstrap sign-in (OIDC), LoopbackPkceError); plugin installer restricted to .zip/.plugin; desktop_update_rollback_detected update rollback telemetry |
| [1.3561.0](2026-04-20_1.3561.0.md) | `mac`, `win` | 2026-04-20 | 41.2.0 | Completed observability export configuration: full OTEL_EXPORTER_OTLP_* environment variable suite (including mTLS client certificate/key and per-signal endpoints for logs/metrics/traces); BuddyRemoteFeed (Buddy remote video feed/display); X-Trusted-Device-Token request header; RemotePluginSync / RemoteStdioTransport (remote plugin sync transport); artifact rate-limiting parameters (artifactMcpCallsPerMinute, artifactDataCacheTtlMs); "Not available in CCD mode" (Claude Code Desktop mode restriction); Windows UNC path error copy in folder browser |
| [1.3109.0](2026-04-16_1.3109.0.md) | `mac`, `win` | 2026-04-16 | 41.2.0 | Bundled @sentry/opentelemetry and the full @opentelemetry/instrumentation-* suite into the main bundle in one go (~25 instrumentations including pg/redis/ioredis/kafkajs/express/fastify/graphql/mongodb/mysql2/undici/dataloader/fs, with target module registries covering @langchain/*, @google/genai, @firebase/firestore, etc.) — observability SDK staged without a DSN yet, paving the way for telemetry wiring in 1.4758.0 |
| [1.3036.0](2026-04-16_1.3036.0.md) | `mac`, `win` | 2026-04-16 | 41.2.0 | Admin workspace folder creation flow + Claude Code session detection; removed custom PalantirFedStart domain (reflecting partnership adjustment) |
| [1.2773.0](2026-04-15_1.2773.0.md) | `mac`, `win` | 2026-04-15 | 41.2.0 | Enterprise capability telemetry: desktop_enterprise_host_mode_changed, probeEgressHosts/Egress connectivity probing, and lastSeenRequireCoworkFullVmSandbox; rolled back agent-sdk by one version + upgraded Sentry SDK in preparation for upcoming observability wiring |
| [1.2581.0](2026-04-14_1.2581.0.md) | `mac`, `win` | 2026-04-14 | 41.2.0 | Fast same-day follow-up: shipped folder authorization modal, Cowork file preview, and MCP Python runtime support |
| [1.2278.0](2026-04-14_1.2278.0.md) | `mac`, `win` | 2026-04-14 | 41.2.0 | Electron 41.2.0 upgrade + VM image expansion + Buddy BLE maker bridge guide; also bundled the managed configuration skeleton for enterprise telemetry and auto-update governance |
| [1.1617.0](2026-04-09_1.1617.0.md) | `mac`, `win` | 2026-04-09 | 40.8.5 | Added ro/rw modes to host_grants (read-only by default, tightening the permission model); otherwise a rolling ion-dist update and rebuild |
| [1.1348.0](2026-04-08_1.1348.0.md) | `mac`, `win` | 2026-04-08 | 40.8.5 | Major feature milestone (+15MB zip): shipped Buddy Bluetooth hardware companion (pairing, firmware flashing, gamified stats; codenamed Nibblet) in a dedicated buddy_window; added four data-layer tables including compute_usage (laying groundwork for Cowork usage metering and built-in agent configs) |
| [1.1062.0](2026-04-07_1.1062.0.md) | `mac`, `win` | 2026-04-07 | 40.8.5 | Broad rollout of enterprise features: added LLM inference gateway system to managed config (inferenceProvider / inferenceGatewayBaseUrl/ApiKey / Bedrock bearerToken+VPCE+region / Vertex project+region+credentialsFile+baseUrl / Foundry resource+apiKey / credentialHelper+TTL / token window limits / models allowlist), plus native Windows Registry reading for managed MCP configs ("Native registry reading failed", "must be a JSON array of valid MCP server configs"); added local transcript search worker and host_call_log migration; hardened file permissions in shell-path worker |
| [1.569.0](2026-04-03_1.569.0.md) | `mac`, `win` | 2026-04-03 | 40.8.5 | First release adopting the 1.<build>.0 versioning scheme; added back/forward navigation bridge on Cowork artifact pages; otherwise routine ion-dist rollout and rebuild |
| [1.2.234](2026-04-01_1.2.234.md) | `mac`, `win` | 2026-04-01 | 40.8.5 | Landmark release: upgraded Electron to 40.8.5; bundled the claude.ai frontend offline inside the app for the first time (ion-dist, 781 files); removed claude-ssh helper binary; added audio capture permission declaration; switched versioning scheme from four-segment 1.1.x to three-segment 1.2.x |
| [1.1.9669](2026-03-31_1.1.9669.md) | `mac`, `win` | 2026-03-31 | 40.4.1 | Launched direct MCP host: main process now embeds the full MCP SDK (zod v4 validation, elicitation, OAuth DCR, tasks, and SSE), providing a runtime for third-party / direct-connect MCP servers (matching the directMcpHost "direct host" architecture) |
| [1.1.9493](2026-03-29_1.1.9493.md) | `mac`, `win` | 2026-03-29 | 40.4.1 | No substantive functional changes (rebuild only) |
| [1.1.9310](2026-03-27_1.1.9310.md) | `mac`, `win` | 2026-03-27 | 40.4.1 | Shipped Cowork artifact bridge preload: artifact pages gained MCP tool invocation capabilities |
| [1.1.9134](2026-03-27_1.1.9134.md) | `mac`, `win` | 2026-03-27 | 40.4.1 | No substantive functional changes (rebuild only) |
| [1.1.8986](2026-03-26_1.1.8986.md) | `mac` | 2026-03-26 | 40.4.1 | Cowork data layer took shape: drizzle SQLite migration pipeline + 4 biology-themed sample project seeds (CRISPR screening, enzyme engineering, extremophiles, immunotherapy), paving the way for local session/project storage backed by sqlite-worker |
| [1.1.8629](2026-03-25_1.1.8629.md) | `mac`, `win` | 2026-03-25 | 40.4.1 | No substantive functional changes (rebuild only) |
| [1.1.8359](2026-03-24_1.1.8359.md) | `mac`, `win` | 2026-03-24 | 40.4.1 | Rolled back the bioknowledge skill bundle, with the rest being a rebuild; retained computer_use and sqlite-worker |
| [1.1.8308](2026-03-23_1.1.8308.md) | `mac` | 2026-03-23 | 40.4.1 | Three additions: shipped computer_use native module and teach preload; added node:sqlite worker (Cowork local database foundation); bundled 757 bioknowledge skill files in one batch (rolled back the next day — see above) |
| [1.1.7714](2026-03-19_1.1.7714.md) | `mac`, `win` | 2026-03-19 | 40.4.1 | Essentially a rebuild; added only a single https enforcement validation string (config security hardening) |
| [1.1.7464](2026-03-18_1.1.7464.md) | `mac`, `win` | 2026-03-18 | 40.4.1 | No substantive functional changes (rebuild only) |
| [1.1.7203](2026-03-17_1.1.7203.md) | `mac`, `win` | 2026-03-17 | 40.4.1 | Fixed child-process stdio descriptor cleanup in shell-path worker; otherwise a rebuild |
| [1.1.7053](2026-03-17_1.1.7053.md) | `mac`, `win` | 2026-03-17 | 40.4.1 | Shipped Cowork plugin system (in-VM shim confirmation protocol) + Git commit signing support in pty environments; also introduced imagine-server dependency (related to image generation "imagine" feature; dependency declaration only, with no standalone process file) |
| [1.1.6679](2026-03-13_1.1.6679.md) | `mac`, `win` | 2026-03-13 | 40.4.1 | No substantive functional changes (rebuild only) |
| [1.1.6452](2026-03-12_1.1.6452.md) | `mac`, `win` | 2026-03-12 | 40.4.1 | No substantive functional changes (rebuild / re-sign / chunk reshuffle only) |
| [1.1.6041](2026-03-10_1.1.6041.md) | `mac`, `win` | 2026-03-10 | 40.4.1 | Engineering release focused on agent-sdk 0.2.72 upgrade and theme design token renaming; no new feature strings |
| [1.1.5749](2026-03-08_1.1.5749.md) | `mac`, `win` | 2026-03-08 | 40.4.1 | Wired computer-use capabilities into the native channel (computer-use-mcp dependency + claude-swift bindings + computerUseEnabled config); passed certificate environment variables through for enterprise SSL-inspecting proxies |
| [1.1.5368](2026-03-05_1.1.5368.md) | `mac`, `win` | 2026-03-05 | 40.4.1 | Major milestone update: removed the Echo tray app entirely; integrated ion-preview.claude.ai preview origin (precursor to the Ion frontend migration); added conway-client and tweetnacl dependencies; shipped auto-update fixes, Claude in Chrome onboarding, and numerous user-facing flow updates |
| [1.1.4498](2026-02-27_1.1.4498.md) | `mac`, `win` | 2026-02-27 | 40.4.1 | Bridged user shell environment into Claude Code sessions: shell probe worker explicitly passes through CLI config and OTEL telemetry environment variables (including custom gateway support via ANTHROPIC_BASE_URL) |
| [1.1.4328](2026-02-25_1.1.4328.md) | `mac`, `win` | 2026-02-25 | 40.4.1 | Enterprise governance & platform compatibility release: admins can disable Cowork/Claude Code, disallowed extensions are disabled rather than removed, added corrupted-settings self-healing prompt, and formalized the Cowork support matrix (OS version / CPU architecture requirements) |
| [1.1.4173](2026-02-24_1.1.4173.md) | `mac`, `win` | 2026-02-24 | 40.4.1 | Rebuild centered on agent-sdk 0.2.51 upgrade; second build of the day |
| [1.1.4088](2026-02-24_1.1.4088.md) | `mac`, `win` | 2026-02-24 | 40.4.1 | Slight growth in main process bundle with no string- or asset-level changes (minor internal logic tweaks) |
| [1.1.4010](2026-02-22_1.1.4010.md) | `mac`, `win` | 2026-02-22 | 40.4.1 | No substantive functional changes (rebuild / re-sign / chunk reshuffle only) |
| [1.1.3963](2026-02-21_1.1.3963.md) | `mac`, `win` | 2026-02-21 | 40.4.1 | No substantive functional changes (rebuild / re-sign / chunk reshuffle only); second build of the day |
| [1.1.3918](2026-02-21_1.1.3918.md) | `mac`, `win` | 2026-02-21 | 40.4.1 | Primarily an MCP SDK upgrade to 1.26.0; no new feature strings |
| [1.1.3830](2026-02-20_1.1.3830.md) | `mac`, `win` | 2026-02-20 | 40.4.1 | No substantive functional changes (rebuild + agent-sdk dev snapshot update); second build of the day |
| [1.1.3770](2026-02-20_1.1.3770.md) | `mac`, `win` | 2026-02-20 | 40.4.1 | Engineering release promoting claude-ssh to a formal dependency and upgrading agent-sdk to 0.2.49 |
| [1.1.3647](2026-02-19_1.1.3647.md) | `mac`, `win` | 2026-02-19 | 40.4.1 | No substantive functional changes (rebuild / re-sign / chunk reshuffle + agent-sdk dev update only); second build of the day |
| [1.1.3541](2026-02-19_1.1.3541.md) | `mac`, `win` | 2026-02-19 | 40.4.1 | Added macOS claude-ssh binary for SSH remote sessions (enabling CLI deployment to remote Mac hosts), paired with an agent-sdk upgrade |
| [1.1.3363](2026-02-17_1.1.3363.md) | `mac`, `win` | 2026-02-17 | 40.4.1 | Converted claude-swift VM state APIs to async (improving Cowork VM stability); added token authentication for CDP remote debugging port (Ed25519 signatures + 5-minute TTL); introduced playwright-core (for automated testing) |
| [1.1.3189](2026-02-14_1.1.3189.md) | `mac`, `win` | 2026-02-14 | 40.4.1 | Electron 40.4.1; split VM image distribution by CPU architecture (+11MB zip) and upgraded remote CLI deployment to sha256-verified zstd archives; renamed "VM" to "Cowork VM" across user-facing copy |
| [1.1.3149](2026-02-13_1.1.3149.md) | `win` | 2026-02-13 | — | `TODO` (`win`) — _detailed diff pending_ |
| [1.1.2998](2026-02-12_1.1.2998.md) | `mac`, `win` | 2026-02-12 | 40.4.0 | Major Electron upgrade 39.5.0 → 40.4.0; added Cowork workspace reinstall and Net Log diagnostic menus, and injected opt-in OTEL telemetry config into the in-VM CLI |
| [1.1.2685](2026-02-10_1.1.2685.md) | `mac`, `win` | 2026-02-10 | 39.5.0 | Remote host Claude CLI deployment (ccd-cli) logic entered the main process for the first time (powering SSH remote sessions); second build of the day, otherwise a rebuild |
| [1.1.2512](2026-02-10_1.1.2512.md) | `mac`, `win` | 2026-02-10 | 39.5.0 | Routine iteration primarily improving error handling in shell-path worker when the disclaimer helper binary is missing; otherwise a rebuild and hash reshuffle |
| [1.1.2321](2026-02-07_1.1.2321.md) | `mac`, `win` | 2026-02-07 | 39.5.0 | Minor Electron 39.5 upgrade + preparatory code for multi-browser switching in Claude in Chrome |
| [1.1.2156](2026-02-06_1.1.2156.md) | `mac`, `win` | 2026-02-06 | 39.4.0 | No substantive functional changes (code cleanup / rebuild) |
| [1.1.2128](2026-02-05_1.1.2128.md) | `mac`, `win` | 2026-02-05 | 39.4.0 | No substantive functional changes (incremental iteration) |
| [1.1.2102](2026-02-05_1.1.2102.md) | `mac`, `win` | 2026-02-05 | 39.4.0 | User-facing skill distribution entry point (drag-and-drop .skill installation) + same-account prompt for Chrome extension |
| [1.1.1890](2026-02-04_1.1.1890.md) | `mac`, `win` | 2026-02-04 | 39.4.0 | Two headline themes: Electron 39 upgrade + FedStart government cloud deployment support; continued iteration across Chrome, SSH, and Skills |
| [1.1.1520](2026-01-30_1.1.1520.md) | `mac`, `win` | 2026-01-30 | 37.10.3 | Inlined ssh2 (including port forwarding and Unix domain socket forwarding) directly into the main process — a pivotal step for Cowork VM networking (port forwarding, editor/service connectivity) |
| [1.1.1200](2026-01-28_1.1.1200.md) | `mac`, `win` | 2026-01-28 | 37.10.3 | SSH infrastructure release: bundled dual-architecture Linux SSH binaries + ws dependency + main-process SSH session management, paving the way for VM port forwarding and remote access |
| [1.1.1093](2026-01-27_1.1.1093.md) | `mac`, `win` | 2026-01-27 | 37.10.3 | Bundled Cowork Shortcuts automation bridge layer and trusted directory settings, without user-facing copy yet |
| [1.1.886](2026-01-24_1.1.886.md) | `mac`, `win` | 2026-01-24 | 37.10.3 | Shipped local skill file (.skill, 30MB cap) open/preview support and local plugin manifest parsing (skills/commands/agents/hooks/mcpServers) |
| [1.1.799](2026-01-23_1.1.799.md) | `mac`, `win` | 2026-01-23 | 37.10.3 | No substantive functional changes (third minor patch build of the day) |
| [1.1.762](2026-01-23_1.1.762.md) | `mac`, `win` | 2026-01-23 | 37.10.3 | Launched one-click install/restart flow for Claude in Chrome, enabling the desktop app to install the extension directly into Chrome/Brave |
| [1.1.673](2026-01-23_1.1.673.md) | `mac`, `win` | 2026-01-23 | 37.10.3 | Cowork formative release: standalone cowork MCP server, knowledge base tools, local plugin directory, and home-directory restrictions; continued expansion of the Echo window |
| [1.1.381](2026-01-18_1.1.381.md) | `mac`, `win` | 2026-01-18 | 37.10.3 | No substantive functional changes (minor MCP tweaks + rebuild) |
| [1.1.351](2026-01-17_1.1.351.md) | `mac`, `win` | 2026-01-17 | 37.10.3 | No substantive functional changes (incremental rebuild / internal tweaks) |
| [1.1.329](2026-01-16_1.1.329.md) | `win` | 2026-01-16 | — | `TODO` (`win`) — _detailed diff pending_ |
| [1.1.280](2026-01-16_1.1.280.md) | `mac`, `win` | 2026-01-16 | 37.10.3 | Start of the 1.1 series = Cowork early preview build: bundled 10MiB placeholder VM image + directory-mount and file-deletion consent MCP tools, still gated behind the debug menu (hidden by default pending feature flag rollout) |
| [1.0.3218](2026-01-12_1.0.3218.md) | `mac`, `win` | 2026-01-12 | 37.10.3 | First implementation of Skills delivery/mounting infrastructure, VM session management, and log-attached feedback; user-facing copy focused on local agent mode and browser tool authorization |
| [1.0.2768](2026-01-05_1.0.2768.md) | `mac`, `win` | 2026-01-05 | 37.10.3 | Major feature release: shipped built-in terminal (node-pty), renamed Claude in Chrome with a standalone helper, and launched the Echo device window (API key pairing / notifications); removed legacy internal updater strings |
| [1.0.2339](2025-12-16_1.0.2339.md) | `win` | 2025-12-16 | — | `TODO` (`win`) — _detailed diff pending_ |
| [1.0.1768](2025-12-06_1.0.1768.md) | `win` | 2025-12-06 | — | `TODO` (`win`) — _detailed diff pending_ |
| [1.0.1656](2025-12-04_1.0.1656.md) | `win` | 2025-12-04 | — | `TODO` (`win`) — _detailed diff pending_ |
| [1.0.1405](2025-12-01_1.0.1405.md) | `win` | 2025-12-01 | — | `TODO` (`win`) — _detailed diff pending_ |
| [1.0.1307](2025-11-26_1.0.1307.md) | `win` | 2025-11-26 | — | `TODO` (`win`) — _detailed diff pending_ |
| [1.0.1217](2025-11-24_1.0.1217.md) | `win` | 2025-11-24 | — | `TODO` (`win`) — _detailed diff pending_ |
| [1.0.734](2025-11-21_1.0.734.md) | `mac`, `win` | 2025-11-21 | 37.10.0 | First 1.0 release = channel migration + major engineering cleanup: renamed packages to `@ant/*`, stripped 252 build-tool packages from distribution, rotated IPC channel signatures, and bundled Clod pet assets, Claude for Chrome entry points, and macOS 13 minimum OS requirement. Modest surface feature delta, but a complete generational shift in release packaging |
| [1.0.332](2025-11-05_1.0.332.md) | `win` | 2025-11-05 | — | `TODO` (`win`) — _detailed diff pending_ |
| [1.0.211](2025-10-31_1.0.211.md) | `win` | 2025-10-31 | — | `TODO` (`win`) — _detailed diff pending_ |
| [0.14.10](2025-10-28_0.14.10.md) | `mac`, `win` | 2025-10-28 | 37.6.0 | Appears to be a rebuild on the surface (chunk reshuffle + Sentry ID rotation), but substantively repointed the auto-update feed to downloads.claude.ai — the final preparation step for the 0.x → 1.0 channel migration |
| [0.14.7](2025-10-28_0.14.7.md) | `win` | 2025-10-28 | — | `TODO` (`win`) — _detailed diff pending_ |
| [0.14.4](2025-10-21_0.14.4.md) | `win` | 2025-10-21 | — | `TODO` (`win`) — _detailed diff pending_ |
| [0.14.1](2025-10-21_0.14.1.md) | `mac` | 2025-10-21 | 37.6.0 | Opening release of the 0.14 series: split out index.pre.js pre-boot module in the main process, refreshed brand theme color variables, updated icon assets (Assets.car), and switched to a new Sentry reporting project |
| [0.13.108](2025-10-17_0.13.108.md) | `mac`, `win` | 2025-10-17 | 37.6.0 | Same-day pure rebuild following 0.13.106 (chunk reshuffle / re-sign); no substantive functional changes |
| [0.13.106](2025-10-17_0.13.106.md) | `mac` | 2025-10-17 | 37.6.0 | Shifted Help menu from "Feedback" to "Support" and added sign-in prerequisites to Chrome extension onboarding; otherwise a rebuild |
| [0.13.91](2025-10-10_0.13.91.md) | `mac` | 2025-10-10 | 37.6.0 | Packaging regression build: MSIX packager and related build toolchain leaked into app.asar (+3,627 files, ~7MB zip increase); functionally only refined Claude for Chrome onboarding copy |
| [0.13.64](2025-10-08_0.13.64.md) | `mac`, `win` | 2025-10-08 | 37.6.0 | Electron 37.6.0; switched typography to new AnthropicSans/AnthropicSerif brand font families; added JWT dependency (organization extension signature verification); announced Claude for Chrome integration |
| [0.13.37](2025-09-25_0.13.37.md) | `mac`, `win` | 2025-09-25 | 37.5.1 | Continued polishing Quick Entry and dictation UX (Caps Lock handling, microphone permission prompts, open-document enumeration); added copyable installation ID for diagnostics |
| [0.13.19](2025-09-18_0.13.19.md) | `mac`, `win` | 2025-09-18 | 37.5.1 | Electron 37.5.1 + mime dependency; Quick Entry submissions now attach file paths. Near-pure rebuild |
| [0.13.11](2025-09-12_0.13.11.md) | `mac`, `win` | 2025-09-12 | 37.4.0 | Upgraded to Electron 37.4.0; wired up data channel for the recent chats menu; shipped guidance copy when dictation permissions are denied |
| [0.12.129](2025-08-30_0.12.129.md) | `mac`, `win` | 2025-08-30 | 36.8.1 | Technical preparation build for Electron 37 upgrade (preload import adjustments); no user-visible changes |
| [0.12.125](2025-08-29_0.12.125.md) | `mac`, `win` | 2025-08-29 | 36.8.1 | Published claude-swift as an official @anthropic-ai package and merged it into a single universal binary; polished extension installation error copy; otherwise a rebuild |
| [0.12.112](2025-08-20_0.12.112.md) | `mac`, `win` | 2025-08-20 | 36.8.1 | Landmark architectural release: upgraded Electron to 36.8.1, switched packaging from node_modules + scattered renderer assets to a fully inlined single bundle; native layer fully taken over by claude-swift (retiring claude-native node addon); completed Quick Entry, dictation, and drag-and-drop screenshot UI with 11-language localization |
| [0.12.55](2025-07-25_0.12.55.md) | `mac`, `win` | 2025-07-25 | 36.4.0 | Gave Quick Entry window its own dedicated preload (quickWindow.js), aligning with the About window; otherwise a rebuild |
| [0.12.49](2025-07-23_0.12.49.md) | `mac`, `win` | 2025-07-23 | 36.4.0 | Reshaped claude-native responsibilities (added About window preload, fixed MCP host paths, upgraded MCP SDK and zod); introduced claude.com domain into the client |
| [0.12.28](2025-07-19_0.12.28.md) | `mac`, `win` | 2025-07-19 | 36.4.0 | Native layer refactor: temporarily stepped back from the Swift addon while claude-native absorbed system read APIs (registry/plist) and bundled build dependencies inline; refined in-app updater copy |
| [0.12.20](2025-07-17_0.12.20.md) | `mac`, `win` | 2025-07-17 | 36.4.0 | Switched MCP server loading to dynamic ESM import (enabling ESM-formatted MCP servers); otherwise a rebuild |
| [0.12.19](2025-07-17_0.12.19.md) | `mac`, `win` | 2025-07-17 | 36.4.0 | Relocated bundled brand fonts (asar renderer assets → app Resources/fonts); otherwise a rebuild |
| [0.12.16](2025-07-14_0.12.16.md) | `mac`, `win` | 2025-07-14 | 36.4.0 | Same-day pure rebuild / re-sign release; no substantive functional changes (chunk reshuffle + regenerated IPC channel identifiers) |
| [0.12.15](2025-07-14_0.12.15.md) | `mac`, `win` | 2025-07-14 | 36.4.0 | Shipped voice dictation and Quick Entry (⌥Space quick input bar with image attachment support): added microphone/speech-recognition permission declarations and claude-swift submit events; retired the local settings window in favor of web settings |
| [0.11.6](2025-06-30_0.11.6.md) | `mac`, `win` | 2025-06-30 | 36.4.0 | Routine rebuild release: rewrote stdin handling in the MCP runtime + full chunk reshuffle, with no user-visible functional changes |
| [0.11.4](2025-06-28_0.11.4.md) | `mac`, `win` | 2025-06-28 | 36.4.0 | Essentially a rebuild release, with only minor markdown styling tweaks on the extension detail page; no substantive functional changes |
| [0.11.3](2025-06-26_0.11.3.md) | `mac`, `win` | 2025-06-26 | 36.4.0 | Officially renamed CDX to DXT (Desktop Extension): put extension registry, blocklist enforcement, signature verification, and auto-update framework in place; launched Statsig event telemetry channel and switched the main bundle to hash-chunked loading |
| [0.10.38](2025-06-17_0.10.38.md) | `mac`, `win` | 2025-06-17 | 36.4.0 | Pivotal release shipping the extension system (CDX) and built-in MCP Node Host: launched .cdx file association, extension install UI, API Key management, full auto-updater (scheduled + idle-aware + auto-restart), and main-process Sentry crash reporting; removed standalone claude-studio package |
| [0.10.14](2025-06-05_0.10.14.md) | `mac`, `win` | 2025-06-05 | 36.4.0 | Large-scale expansion of claude-studio; added hardware acceleration toggle and clear-cache / reset dialogs on desktop |
| [0.9.4](2025-06-03_0.9.4.md) | `mac`, `win` | 2025-06-03 | 36.2.1 | Major release spanning a month of work: upgraded to Electron 36, introduced experimental Swift native addon and the claude-studio package (bundling MCP permission server + React renderer + full TypeScript toolchain), adding +18MB to zip size |
| [0.9.3](2025-04-30_0.9.3.md) | `mac`, `win` | 2025-04-30 | 34.0.2 | Added main-window webview hang detection and automatic kill+reload watchdog mechanism (addressing freeze issues) |
| [0.9.2+b2184e2c](2025-04-14_0.9.2+b2184e2c.md) | `mac`, `win` | 2025-04-14 | 34.0.2 | No substantive functional changes (rebuild / re-sign / chunk reshuffle only; main Info.plist changed only in code-signing hash) |
| [0.9.2+d5e83a89](2025-04-08_0.9.2+d5e83a89.md) | `mac` | 2025-04-08 | 34.0.2 | Network error page and claude.ai redirect prompt; second build under the same version number (introducing the +d5e83a89 artifact suffix) |
| [0.9.1](2025-04-01_0.9.1.md) | `mac`, `win` | 2025-04-01 | 34.0.2 | Minor release: tweaked Help menu items; otherwise a hash reshuffle |
| [0.9.0](2025-03-27_0.9.0.md) | `mac`, `win` | 2025-03-27 | 34.0.2 | Added find-in-page feature (dedicated preload + renderer window) and Sentry buffer-full drop log ("Skipped sending event because buffer is full.") |
| [0.8.1](2025-03-14_0.8.1.md) | `mac`, `win` | 2025-03-14 | 34.0.2 | Added About window bundling the full Anthropic brand font suite and linking to support.anthropic.com |
| [0.8.0](2025-02-28_0.8.0.md) | `mac`, `win` | 2025-02-28 | 34.0.2 | Internationalization release: bundled react-intl + 16 locale packs, migrating all menu and settings strings to message keys; upgraded to Electron 34 |
| [0.7.9](2025-02-10_0.7.9.md) | `mac`, `win` | 2025-02-10 | 33.3.1 | MCP SDK 1.4.1; refined MCP server startup/connection status feedback and config validation, introducing an early desktop bridge permission model |
| [0.7.8](2025-01-08_0.7.8.md) | `mac`, `win` | 2025-01-08 | 33.3.1 | Added a full native menu bar for the first time (including New Conversation shortcut), minor Electron upgrade, and improved auto-updater logging flow |
| [0.7.7](2024-12-19_0.7.7.md) | `mac`, `win` | 2024-12-19 | 33.2.1 | Upgraded to Electron 33 and integrated internal design-system package; added Login Items (launch at startup) setting, significantly expanded preload layer, and bundled MCP debugging documentation links |
| [0.7.6](2024-12-19_0.7.6.md) | `win` | 2024-12-19 | — | `TODO` (`win`) — _detailed diff pending_ |
| [0.7.5](2024-12-02_0.7.5.md) | `mac`, `win` | 2024-12-02 | 32.1.2 | Upgraded MCP SDK to 1.0.1; rewrote settings page with Tailwind + Phosphor icons and slimmed/split the main process bundle |
| [0.7.1](2024-11-22_0.7.1.md) | `mac`, `win` | 2024-11-22 | 32.1.2 | First complete MCP management UI (install confirmation, local directory picker, log viewer shortcut, Developer Mode); refactored settings and main window with React |
| [0.6.2](2024-11-13_0.6.2.md) | `mac`, `win` | 2024-11-13 | 32.1.2 | Upgraded MCP SDK to 0.4.0 and added rxjs; expanded claude-native with window and accessibility APIs; added multiline input and click-outside-to-dismiss to Quick Window |
| [0.6.0](2024-11-11_0.6.0.md) | `win` | 2024-11-11 | — | `TODO` (`win`) — _detailed diff pending_ |
| [0.5.0](2024-11-08_0.5.0.md) | `win` | 2024-11-08 | — | `TODO` (`win`) — _detailed diff pending_ |
| [0.4.9](2024-11-02_0.4.9.md) | `mac`, `win` | 2024-11-02 | 32.1.2 | Two-day follow-up release: switched main-process logging to winston ("A logger for just about everything."); no user-visible functional changes |
| [0.4.8](2024-10-31_0.4.8.md) | `mac` | 2024-10-31 | 32.1.2 | Initial macOS desktop release baseline: shipped with main window, Quick Window, claude-native module, and MCP SDK 0.1 |

## Mobile Version Index (`ios` / `android`, Newest → Oldest)

| Version | Platforms | Release Date | Key Changes |
|---|---|---|---|
| [1.261113.19](2026-11-14_1.261113.19.md) | `android` | 2026-11-14 | Play-split XAPK static diff (`1.261112.18 → 1.261113.19`): `minSdkVersion` `29 → 32` (Android 10 → 12L, `targetSdkVersion` `37`), `37 → 39` XAPK entries (`27 → 30` language splits), `voice.internal.{readaloud,dictation,dictation/offline}` refactor (retaining `TTSPlaybackService`), CCR `ProjectSheet*` / `GitHubSsoRequiredException` / `CoworkTurnOutcomeWorker` / 49 bottom-sheet destinations, Threads UI & location event-scrub removal, and static promotional-credits/KYC client code |
| [1.261109.19](2026-11-11_1.261109.19.md) | `ios`, `android` | 2026-11-11 | `TODO` (`ios`, `android`) — _detailed diff pending_ |
| [1.261106.19](2026-11-09_1.261106.19.md) | `ios`, `android` | 2026-11-09 | `TODO` (`ios`, `android`) — _detailed diff pending_ |
| [1.260813.10](2026-11-09_1.260813.10.md) | `android` | 2026-11-09 | `TODO` (`android`) — _detailed diff pending_ |
| [1.250602.7](2026-11-09_1.250602.7.md) | `android` | 2026-11-09 | `TODO` (`android`) — _detailed diff pending_ |
| [1.261103.19](2026-11-08_1.261103.19.md) | `android` | 2026-11-08 | `TODO` (`android`) — _detailed diff pending_ |
| [1.261104.19](2026-11-07_1.261104.19.md) | `ios`, `android` | 2026-11-07 | `TODO` (`ios`, `android`) — _detailed diff pending_ |
| [1.261102.19](2026-11-05_1.261102.19.md) | `android` | 2026-11-05 | `TODO` (`android`) — _detailed diff pending_ |
| [1.260831.0](2026-11-03_1.260831.0.md) | `android` | 2026-11-03 | `TODO` (`android`) — _detailed diff pending_ |
| [1.261030.19](2026-11-02_1.261030.19.md) | `ios`, `android` | 2026-11-02 | `TODO` (`ios`, `android`) — _detailed diff pending_ |
| [1.261029.20](2026-11-01_1.261029.20.md) | `android` | 2026-11-01 | `TODO` (`android`) — _detailed diff pending_ |
| [1.261022.20](2026-11-01_1.261022.20.md) | `android` | 2026-11-01 | `TODO` (`android`) — _detailed diff pending_ |
| [1.261020.20](2026-11-01_1.261020.20.md) | `android` | 2026-11-01 | `TODO` (`android`) — _detailed diff pending_ |
| [1.261028.19](2026-10-30_1.261028.19.md) | `ios`, `android` | 2026-10-30 | `TODO` (`ios`, `android`) — _detailed diff pending_ |
| [1.261027.19](2026-10-30_1.261027.19.md) | `android` | 2026-10-30 | `TODO` (`android`) — _detailed diff pending_ |
| [1.261026.51](2026-10-30_1.261026.51.md) | `android` | 2026-10-30 | `TODO` (`android`) — _detailed diff pending_ |
| [1.261026.20](2026-10-29_1.261026.20.md) | `ios` | 2026-10-29 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.261023.20](2026-10-25_1.261023.20.md) | `ios`, `android` | 2026-10-25 | `TODO` (`ios`, `android`) — _detailed diff pending_ |
| [1.261021.51](2026-10-24_1.261021.51.md) | `ios`, `android` | 2026-10-24 | `TODO` (`ios`, `android`) — _detailed diff pending_ |
| [1.261016.51](2026-10-24_1.261016.51.md) | `android` | 2026-10-24 | `TODO` (`android`) — _detailed diff pending_ |
| [1.261019.51](2026-10-23_1.261019.51.md) | `ios` | 2026-10-23 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.261019.20](2026-10-22_1.261019.20.md) | `ios`, `android` | 2026-10-22 | `TODO` (`ios`, `android`) — _detailed diff pending_ |
| [1.261015.20](2026-10-21_1.261015.20.md) | `android` | 2026-10-21 | `TODO` (`android`) — _detailed diff pending_ |
| [1.261016.20](2026-10-19_1.261016.20.md) | `ios` | 2026-10-19 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.250512.27](2026-10-19_1.250512.27.md) | `android` | 2026-10-19 | `TODO` (`android`) — _detailed diff pending_ |
| [1.261014.20](2026-10-17_1.261014.20.md) | `ios`, `android` | 2026-10-17 | `TODO` (`ios`, `android`) — _detailed diff pending_ |
| [1.261013.20](2026-10-16_1.261013.20.md) | `ios`, `android` | 2026-10-16 | `TODO` (`ios`, `android`) — _detailed diff pending_ |
| [1.261012.20](2026-10-15_1.261012.20.md) | `ios`, `android` | 2026-10-15 | `TODO` (`ios`, `android`) — _detailed diff pending_ |
| [1.261009.20](2026-10-12_1.261009.20.md) | `ios`, `android` | 2026-10-12 | `TODO` (`ios`, `android`) — _detailed diff pending_ |
| [1.240805.17](2026-10-12_1.240805.17.md) | `android` | 2026-10-12 | `TODO` (`android`) — _detailed diff pending_ |
| [1.260918.19](2026-10-11_1.260918.19.md) | `android` | 2026-10-11 | `TODO` (`android`) — _detailed diff pending_ |
| [1.261008.20](2026-10-10_1.261008.20.md) | `android` | 2026-10-10 | `TODO` (`android`) — _detailed diff pending_ |
| [1.261007.20](2026-10-10_1.261007.20.md) | `ios`, `android` | 2026-10-10 | `TODO` (`ios`, `android`) — _detailed diff pending_ |
| [1.261005.20](2026-10-08_1.261005.20.md) | `ios`, `android` | 2026-10-08 | `TODO` (`ios`, `android`) — _detailed diff pending_ |
| [1.261002.20](2026-10-05_1.261002.20.md) | `ios`, `android` | 2026-10-05 | `TODO` (`ios`, `android`) — _detailed diff pending_ |
| [1.260930.20](2026-10-04_1.260930.20.md) | `ios`, `android` | 2026-10-04 | `TODO` (`ios`, `android`) — _detailed diff pending_ |
| [1.260928.20](2026-09-30_1.260928.20.md) | `ios`, `android` | 2026-09-30 | `TODO` (`ios`, `android`) — _detailed diff pending_ |
| [1.260925.19](2026-09-29_1.260925.19.md) | `ios` | 2026-09-29 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.260923.51](2026-09-27_1.260923.51.md) | `ios` | 2026-09-27 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.260923.20](2026-09-26_1.260923.20.md) | `ios`, `android` | 2026-09-26 | `TODO` (`ios`, `android`) — _detailed diff pending_ |
| [1.260921.19](2026-09-25_1.260921.19.md) | `ios`, `android` | 2026-09-25 | `TODO` (`ios`, `android`) — _detailed diff pending_ |
| [1.260910.12](2026-09-22_1.260910.12.md) | `android` | 2026-09-22 | `TODO` (`android`) — _detailed diff pending_ |
| [1.260209.37](2026-09-21_1.260209.37.md) | `android` | 2026-09-21 | `TODO` (`android`) — _detailed diff pending_ |
| [1.260916.19](2026-09-18_1.260916.19.md) | `ios`, `android` | 2026-09-18 | `TODO` (`ios`, `android`) — _detailed diff pending_ |
| [1.260914.19](2026-09-16_1.260914.19.md) | `android` | 2026-09-16 | `TODO` (`android`) — _detailed diff pending_ |
| [1.260911.19](2026-09-14_1.260911.19.md) | `ios`, `android` | 2026-09-14 | `TODO` (`ios`, `android`) — _detailed diff pending_ |
| [1.260909.19](2026-09-12_1.260909.19.md) | `ios`, `android` | 2026-09-12 | `TODO` (`ios`, `android`) — _detailed diff pending_ |
| [1.260907.19](2026-09-10_1.260907.19.md) | `ios`, `android` | 2026-09-10 | `TODO` (`ios`, `android`) — _detailed diff pending_ |
| [1.260806.20](2026-09-10_1.260806.20.md) | `android` | 2026-09-10 | `TODO` (`android`) — _detailed diff pending_ |
| [1.260904.19](2026-09-07_1.260904.19.md) | `ios`, `android` | 2026-09-07 | `TODO` (`ios`, `android`) — _detailed diff pending_ |
| [1.260902.20](2026-09-04_1.260902.20.md) | `ios`, `android` | 2026-09-04 | `TODO` (`ios`, `android`) — _detailed diff pending_ |
| [1.260831.1](2026-09-03_1.260831.1.md) | `ios` | 2026-09-03 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.260828.1](2026-09-01_1.260828.1.md) | `ios` | 2026-09-01 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.260828.0](2026-08-31_1.260828.0.md) | `ios`, `android` | 2026-08-31 | `TODO` (`ios`, `android`) — _detailed diff pending_ |
| [1.260826.0](2026-08-29_1.260826.0.md) | `ios`, `android` | 2026-08-29 | `TODO` (`ios`, `android`) — _detailed diff pending_ |
| [1.260721.20](2026-08-29_1.260721.20.md) | `android` | 2026-08-29 | `TODO` (`android`) — _detailed diff pending_ |
| [1.260702.10](2026-08-29_1.260702.10.md) | `android` | 2026-08-29 | `TODO` (`android`) — _detailed diff pending_ |
| [1.260604.20](2026-08-29_1.260604.20.md) | `android` | 2026-08-29 | `TODO` (`android`) — _detailed diff pending_ |
| [1.260528.10](2026-08-28_1.260528.10.md) | `android` | 2026-08-28 | `TODO` (`android`) — _detailed diff pending_ |
| [1.260824.0](2026-08-27_1.260824.0.md) | `ios`, `android` | 2026-08-27 | `TODO` (`ios`, `android`) — _detailed diff pending_ |
| [1.260820.0](2026-08-22_1.260820.0.md) | `ios`, `android` | 2026-08-22 | `TODO` (`ios`, `android`) — _detailed diff pending_ |
| [1.260817.0](2026-08-20_1.260817.0.md) | `ios`, `android` | 2026-08-20 | `TODO` (`ios`, `android`) — _detailed diff pending_ |
| [1.260814.0](2026-08-18_1.260814.0.md) | `ios` | 2026-08-18 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.260813.0](2026-08-14_1.260813.0.md) | `ios`, `android` | 2026-08-14 | `TODO` (`ios`, `android`) — _detailed diff pending_ |
| [1.260810.0](2026-08-13_1.260810.0.md) | `ios`, `android` | 2026-08-13 | `TODO` (`ios`, `android`) — _detailed diff pending_ |
| [1.260611.30](2026-08-13_1.260611.30.md) | `android` | 2026-08-13 | `TODO` (`android`) — _detailed diff pending_ |
| [1.260806.0](2026-08-12_1.260806.0.md) | `ios` | 2026-08-12 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.260430.10](2026-08-11_1.260430.10.md) | `android` | 2026-08-11 | `TODO` (`android`) — _detailed diff pending_ |
| [1.260316.47](2026-08-06_1.260316.47.md) | `android` | 2026-08-06 | `TODO` (`android`) — _detailed diff pending_ |
| [1.260618.10](2026-08-04_1.260618.10.md) | `android` | 2026-08-04 | `TODO` (`android`) — _detailed diff pending_ |
| [1.250113.17](2026-07-28_1.250113.17.md) | `android` | 2026-07-28 | `TODO` (`android`) — _detailed diff pending_ |
| [1.260721.0](2026-07-23_1.260721.0.md) | `ios` | 2026-07-23 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.260716.0](2026-07-19_1.260716.0.md) | `ios` | 2026-07-19 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.260709.10](2026-07-19_1.260709.10.md) | `android` | 2026-07-19 | `TODO` (`android`) — _detailed diff pending_ |
| [1.260709.0](2026-07-10_1.260709.0.md) | `ios`, `android` | 2026-07-10 | `TODO` (`ios`, `android`) — _detailed diff pending_ |
| [1.260702.3](2026-07-10_1.260702.3.md) | `ios` | 2026-07-10 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.260625.30](2026-07-10_1.260625.30.md) | `android` | 2026-07-10 | `TODO` (`android`) — _detailed diff pending_ |
| [1.260702.2](2026-07-09_1.260702.2.md) | `ios` | 2026-07-09 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.260625.20](2026-07-09_1.260625.20.md) | `android` | 2026-07-09 | `TODO` (`android`) — _detailed diff pending_ |
| [1.260702.0](2026-07-07_1.260702.0.md) | `ios` | 2026-07-07 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.260625.0](2026-07-01_1.260625.0.md) | `ios` | 2026-07-01 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.260618.1](2026-06-24_1.260618.1.md) | `ios` | 2026-06-24 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.260618.0](2026-06-23_1.260618.0.md) | `ios` | 2026-06-23 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.260611.20](2026-06-20_1.260611.20.md) | `android` | 2026-06-20 | `TODO` (`android`) — _detailed diff pending_ |
| [1.260611.1](2026-06-17_1.260611.1.md) | `ios` | 2026-06-17 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.260604.30](2026-06-17_1.260604.30.md) | `android` | 2026-06-17 | `TODO` (`android`) — _detailed diff pending_ |
| [1.260409.10](2026-06-17_1.260409.10.md) | `android` | 2026-06-17 | `TODO` (`android`) — _detailed diff pending_ |
| [1.260112.27](2026-06-14_1.260112.27.md) | `android` | 2026-06-14 | `TODO` (`android`) — _detailed diff pending_ |
| [1.250120.7](2026-06-14_1.250120.7.md) | `android` | 2026-06-14 | `TODO` (`android`) — _detailed diff pending_ |
| [1.260611.0](2026-06-13_1.260611.0.md) | `ios`, `android` | 2026-06-13 | `TODO` (`ios`, `android`) — _detailed diff pending_ |
| [1.260604.0](2026-06-09_1.260604.0.md) | `ios` | 2026-06-09 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.260521.20](2026-06-07_1.260521.20.md) | `android` | 2026-06-07 | `TODO` (`android`) — _detailed diff pending_ |
| [1.260521.10](2026-06-05_1.260521.10.md) | `android` | 2026-06-05 | `TODO` (`android`) — _detailed diff pending_ |
| [1.260528.1](2026-06-04_1.260528.1.md) | `ios` | 2026-06-04 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.260528.0](2026-06-03_1.260528.0.md) | `ios` | 2026-06-03 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.260507.10](2026-05-29_1.260507.10.md) | `android` | 2026-05-29 | `TODO` (`android`) — _detailed diff pending_ |
| [1.260521.1](2026-05-28_1.260521.1.md) | `ios` | 2026-05-28 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.260423.20](2026-05-28_1.260423.20.md) | `android` | 2026-05-28 | `TODO` (`android`) — _detailed diff pending_ |
| [1.260521.0](2026-05-27_1.260521.0.md) | `ios` | 2026-05-27 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.241111.5](2026-05-26_1.241111.5.md) | `android` | 2026-05-26 | `TODO` (`android`) — _detailed diff pending_ |
| [1.260514.0](2026-05-20_1.260514.0.md) | `ios`, `android` | 2026-05-20 | `TODO` (`ios`, `android`) — _detailed diff pending_ |
| [1.260302.17](2026-05-14_1.260302.17.md) | `android` | 2026-05-14 | `TODO` (`android`) — _detailed diff pending_ |
| [1.260507.0](2026-05-13_1.260507.0.md) | `ios` | 2026-05-13 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.250106.7](2026-05-10_1.250106.7.md) | `android` | 2026-05-10 | `TODO` (`android`) — _detailed diff pending_ |
| [1.260430.0](2026-05-06_1.260430.0.md) | `ios`, `android` | 2026-05-06 | `TODO` (`ios`, `android`) — _detailed diff pending_ |
| [1.260423.1](2026-05-01_1.260423.1.md) | `ios` | 2026-05-01 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.260423.0](2026-04-29_1.260423.0.md) | `ios` | 2026-04-29 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.260416.20](2026-04-27_1.260416.20.md) | `android` | 2026-04-27 | `TODO` (`android`) — _detailed diff pending_ |
| [1.260416.0](2026-04-21_1.260416.0.md) | `ios` | 2026-04-21 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.260330.27](2026-04-20_1.260330.27.md) | `android` | 2026-04-20 | `TODO` (`android`) — _detailed diff pending_ |
| [1.250303.27](2026-04-18_1.250303.27.md) | `android` | 2026-04-18 | `TODO` (`android`) — _detailed diff pending_ |
| [1.260409.1](2026-04-15_1.260409.1.md) | `ios` | 2026-04-15 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.260409.0](2026-04-14_1.260409.0.md) | `ios` | 2026-04-14 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.260402.20](2026-04-13_1.260402.20.md) | `android` | 2026-04-13 | `TODO` (`android`) — _detailed diff pending_ |
| [1.260216.27](2026-04-10_1.260216.27.md) | `android` | 2026-04-10 | `TODO` (`android`) — _detailed diff pending_ |
| [1.260402.0](2026-04-08_1.260402.0.md) | `ios` | 2026-04-08 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.260323.7](2026-04-03_1.260323.7.md) | `android` | 2026-04-03 | `TODO` (`android`) — _detailed diff pending_ |
| [1.260309.17](2026-04-03_1.260309.17.md) | `android` | 2026-04-03 | `TODO` (`android`) — _detailed diff pending_ |
| [1.260330.1](2026-04-01_1.260330.1.md) | `ios` | 2026-04-01 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.260330.0](2026-03-31_1.260330.0.md) | `ios` | 2026-03-31 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.260323.4](2026-03-27_1.260323.4.md) | `ios` | 2026-03-27 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.260323.3](2026-03-26_1.260323.3.md) | `ios` | 2026-03-26 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.260323.2](2026-03-25_1.260323.2.md) | `ios` | 2026-03-25 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.260316.3](2026-03-22_1.260316.3.md) | `ios` | 2026-03-22 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.260316.1](2026-03-20_1.260316.1.md) | `ios` | 2026-03-20 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.260316.0](2026-03-18_1.260316.0.md) | `ios` | 2026-03-18 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.260316.27](2026-03-17_1.260316.27.md) | `android` | 2026-03-17 | `TODO` (`android`) — _detailed diff pending_ |
| [1.260309.1](2026-03-12_1.260309.1.md) | `ios` | 2026-03-12 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.260302.0](2026-03-04_1.260302.0.md) | `ios` | 2026-03-04 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.260223.17](2026-03-02_1.260223.17.md) | `android` | 2026-03-02 | `TODO` (`android`) — _detailed diff pending_ |
| [1.260216.17](2026-03-01_1.260216.17.md) | `android` | 2026-03-01 | `TODO` (`android`) — _detailed diff pending_ |
| [1.260223.3](2026-02-28_1.260223.3.md) | `ios` | 2026-02-28 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.260223.2](2026-02-25_1.260223.2.md) | `ios` | 2026-02-25 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.250428.17](2026-02-24_1.250428.17.md) | `android` | 2026-02-24 | `TODO` (`android`) — _detailed diff pending_ |
| [1.251124.27](2026-02-23_1.251124.27.md) | `android` | 2026-02-23 | `TODO` (`android`) — _detailed diff pending_ |
| [1.260216.3](2026-02-22_1.260216.3.md) | `ios` | 2026-02-22 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.260216.2](2026-02-19_1.260216.2.md) | `ios` | 2026-02-19 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.260209.0](2026-02-11_1.260209.0.md) | `ios` | 2026-02-11 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.260202.37](2026-02-09_1.260202.37.md) | `android` | 2026-02-09 | `TODO` (`android`) — _detailed diff pending_ |
| [1.260202.5](2026-02-08_1.260202.5.md) | `ios` | 2026-02-08 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.260202.27](2026-02-05_1.260202.27.md) | `android` | 2026-02-05 | `TODO` (`android`) — _detailed diff pending_ |
| [1.260126.27](2026-02-05_1.260126.27.md) | `android` | 2026-02-05 | `TODO` (`android`) — _detailed diff pending_ |
| [1.260202.3](2026-02-04_1.260202.3.md) | `ios` | 2026-02-04 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.260119.17](2026-01-29_1.260119.17.md) | `android` | 2026-01-29 | `TODO` (`android`) — _detailed diff pending_ |
| [1.260126.0](2026-01-28_1.260126.0.md) | `ios` | 2026-01-28 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.251027.7](2026-01-28_1.251027.7.md) | `android` | 2026-01-28 | `TODO` (`android`) — _detailed diff pending_ |
| [1.260119.0](2026-01-21_1.260119.0.md) | `ios` | 2026-01-21 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.260112.17](2026-01-20_1.260112.17.md) | `android` | 2026-01-20 | `TODO` (`android`) — _detailed diff pending_ |
| [1.241014.17](2026-01-16_1.241014.17.md) | `android` | 2026-01-16 | `TODO` (`android`) — _detailed diff pending_ |
| [1.260112.1](2026-01-13_1.260112.1.md) | `ios` | 2026-01-13 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.250217.2](2026-01-11_1.250217.2.md) | `android` | 2026-01-11 | `TODO` (`android`) — _detailed diff pending_ |
| [1.250519.17](2026-01-06_1.250519.17.md) | `android` | 2026-01-06 | `TODO` (`android`) — _detailed diff pending_ |
| [1.251013.27](2026-01-04_1.251013.27.md) | `android` | 2026-01-04 | `TODO` (`android`) — _detailed diff pending_ |
| [1.251208.37](2026-01-01_1.251208.37.md) | `android` | 2026-01-01 | `TODO` (`android`) — _detailed diff pending_ |
| [1.251117.27](2025-12-31_1.251117.27.md) | `android` | 2025-12-31 | `TODO` (`android`) — _detailed diff pending_ |
| [1.251013.17](2025-12-29_1.251013.17.md) | `android` | 2025-12-29 | `TODO` (`android`) — _detailed diff pending_ |
| [1.250127.7](2025-12-29_1.250127.7.md) | `android` | 2025-12-29 | `TODO` (`android`) — _detailed diff pending_ |
| [1.251215.57](2025-12-28_1.251215.57.md) | `android` | 2025-12-28 | `TODO` (`android`) — _detailed diff pending_ |
| [1.251208.27](2025-12-22_1.251208.27.md) | `android` | 2025-12-22 | `TODO` (`android`) — _detailed diff pending_ |
| [1.251110.27](2025-12-22_1.251110.27.md) | `android` | 2025-12-22 | `TODO` (`android`) — _detailed diff pending_ |
| [1.251215.4](2025-12-20_1.251215.4.md) | `ios` | 2025-12-20 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.251215.47](2025-12-17_1.251215.47.md) | `android` | 2025-12-17 | `TODO` (`android`) — _detailed diff pending_ |
| [1.251215.2](2025-12-17_1.251215.2.md) | `ios` | 2025-12-17 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.251215.37](2025-12-16_1.251215.37.md) | `android` | 2025-12-16 | `TODO` (`android`) — _detailed diff pending_ |
| [1.251208.5](2025-12-13_1.251208.5.md) | `ios` | 2025-12-13 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.251208.4](2025-12-12_1.251208.4.md) | `ios` | 2025-12-12 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.251208.3](2025-12-10_1.251208.3.md) | `ios` | 2025-12-10 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.251124.3](2025-11-28_1.251124.3.md) | `ios` | 2025-11-28 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.250728.36](2025-11-28_1.250728.36.md) | `android` | 2025-11-28 | `TODO` (`android`) — _detailed diff pending_ |
| [1.241007.7](2025-11-27_1.241007.7.md) | `android` | 2025-11-27 | `TODO` (`android`) — _detailed diff pending_ |
| [1.251117.17](2025-11-25_1.251117.17.md) | `android` | 2025-11-25 | `TODO` (`android`) — _detailed diff pending_ |
| [1.251124.2](2025-11-24_1.251124.2.md) | `ios` | 2025-11-24 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.251117.1](2025-11-20_1.251117.1.md) | `ios` | 2025-11-20 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.250922.37](2025-11-19_1.250922.37.md) | `android` | 2025-11-19 | `TODO` (`android`) — _detailed diff pending_ |
| [1.251110.1](2025-11-11_1.251110.1.md) | `ios` | 2025-11-11 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.250908.37](2025-11-11_1.250908.37.md) | `android` | 2025-11-11 | `TODO` (`android`) — _detailed diff pending_ |
| [1.240923.17](2025-11-11_1.240923.17.md) | `android` | 2025-11-11 | `TODO` (`android`) — _detailed diff pending_ |
| [1.250818.16](2025-11-10_1.250818.16.md) | `android` | 2025-11-10 | `TODO` (`android`) — _detailed diff pending_ |
| [1.250526.17](2025-11-08_1.250526.17.md) | `android` | 2025-11-08 | `TODO` (`android`) — _detailed diff pending_ |
| [1.250505.27](2025-11-08_1.250505.27.md) | `android` | 2025-11-08 | `TODO` (`android`) — _detailed diff pending_ |
| [1.251103.2](2025-11-05_1.251103.2.md) | `ios` | 2025-11-05 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.250609.27](2025-11-04_1.250609.27.md) | `android` | 2025-11-04 | `TODO` (`android`) — _detailed diff pending_ |
| [1.250811.6](2025-10-30_1.250811.6.md) | `android` | 2025-10-30 | `TODO` (`android`) — _detailed diff pending_ |
| [1.251027.0](2025-10-29_1.251027.0.md) | `ios` | 2025-10-29 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.251020.1](2025-10-22_1.251020.1.md) | `ios` | 2025-10-22 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.251020.17](2025-10-21_1.251020.17.md) | `android` | 2025-10-21 | `TODO` (`android`) — _detailed diff pending_ |
| [1.251020.0](2025-10-21_1.251020.0.md) | `ios` | 2025-10-21 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.251013.5](2025-10-15_1.251013.5.md) | `ios` | 2025-10-15 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.251006.1](2025-10-08_1.251006.1.md) | `ios` | 2025-10-08 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.251006.17](2025-10-07_1.251006.17.md) | `android` | 2025-10-07 | `TODO` (`android`) — _detailed diff pending_ |
| [1.250929.67](2025-10-07_1.250929.67.md) | `android` | 2025-10-07 | `TODO` (`android`) — _detailed diff pending_ |
| [1.250929.4](2025-10-01_1.250929.4.md) | `ios` | 2025-10-01 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.250825.27](2025-09-25_1.250825.27.md) | `android` | 2025-09-25 | `TODO` (`android`) — _detailed diff pending_ |
| [1.250922.1](2025-09-23_1.250922.1.md) | `ios` | 2025-09-23 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.250915.1](2025-09-17_1.250915.1.md) | `ios` | 2025-09-17 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.250908.3](2025-09-09_1.250908.3.md) | `ios` | 2025-09-09 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.250901.17](2025-09-08_1.250901.17.md) | `android` | 2025-09-08 | `TODO` (`android`) — _detailed diff pending_ |
| [1.250901.1](2025-09-04_1.250901.1.md) | `ios` | 2025-09-04 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.250804.26](2025-08-30_1.250804.26.md) | `android` | 2025-08-30 | `TODO` (`android`) — _detailed diff pending_ |
| [1.250825.1](2025-08-27_1.250825.1.md) | `ios` | 2025-08-27 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.250818.1](2025-08-20_1.250818.1.md) | `ios` | 2025-08-20 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.250714.7](2025-08-20_1.250714.7.md) | `android` | 2025-08-20 | `TODO` (`android`) — _detailed diff pending_ |
| [1.250811.1](2025-08-13_1.250811.1.md) | `ios` | 2025-08-13 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.250804.1](2025-08-06_1.250804.1.md) | `ios` | 2025-08-06 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.250728.1](2025-07-30_1.250728.1.md) | `ios` | 2025-07-30 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.250721.17](2025-07-30_1.250721.17.md) | `android` | 2025-07-30 | `TODO` (`android`) — _detailed diff pending_ |
| [1.250721.4](2025-07-25_1.250721.4.md) | `ios` | 2025-07-25 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.250721.3](2025-07-23_1.250721.3.md) | `ios` | 2025-07-23 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.250714.0](2025-07-15_1.250714.0.md) | `ios` | 2025-07-15 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.250707.37](2025-07-13_1.250707.37.md) | `android` | 2025-07-13 | `TODO` (`android`) — _detailed diff pending_ |
| [1.250630.7](2025-07-12_1.250630.7.md) | `android` | 2025-07-12 | `TODO` (`android`) — _detailed diff pending_ |
| [1.250707.0](2025-07-09_1.250707.0.md) | `ios` | 2025-07-09 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.250630.4](2025-07-02_1.250630.4.md) | `ios` | 2025-07-02 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.250623.2](2025-06-25_1.250623.2.md) | `ios` | 2025-06-25 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.250616.2](2025-06-20_1.250616.2.md) | `ios` | 2025-06-20 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.250616.1](2025-06-18_1.250616.1.md) | `ios` | 2025-06-18 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.250609.1](2025-06-13_1.250609.1.md) | `ios` | 2025-06-13 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.250609.0](2025-06-11_1.250609.0.md) | `ios` | 2025-06-11 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.250210.2](2025-06-10_1.250210.2.md) | `android` | 2025-06-10 | `TODO` (`android`) — _detailed diff pending_ |
| [1.250602.0](2025-06-04_1.250602.0.md) | `ios` | 2025-06-04 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.250519.4](2025-05-24_1.250519.4.md) | `ios` | 2025-05-24 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.250519.3](2025-05-23_1.250519.3.md) | `ios` | 2025-05-23 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.250512.6](2025-05-14_1.250512.6.md) | `ios` | 2025-05-14 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.250505.2](2025-05-07_1.250505.2.md) | `ios` | 2025-05-07 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.250428.4](2025-05-01_1.250428.4.md) | `ios` | 2025-05-01 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.250428.2](2025-04-30_1.250428.2.md) | `ios` | 2025-04-30 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.250421.0](2025-04-24_1.250421.0.md) | `ios` | 2025-04-24 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.250421.17](2025-04-22_1.250421.17.md) | `android` | 2025-04-22 | `TODO` (`android`) — _detailed diff pending_ |
| [1.250414.27](2025-04-21_1.250414.27.md) | `android` | 2025-04-21 | `TODO` (`android`) — _detailed diff pending_ |
| [1.250414.3](2025-04-18_1.250414.3.md) | `ios` | 2025-04-18 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.250414.2](2025-04-16_1.250414.2.md) | `ios` | 2025-04-16 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.250407.47](2025-04-14_1.250407.47.md) | `android` | 2025-04-14 | `TODO` (`android`) — _detailed diff pending_ |
| [1.240902.17](2025-04-14_1.240902.17.md) | `android` | 2025-04-14 | `TODO` (`android`) — _detailed diff pending_ |
| [1.250324.17](2025-04-13_1.250324.17.md) | `android` | 2025-04-13 | `TODO` (`android`) — _detailed diff pending_ |
| [1.241216.7](2025-04-13_1.241216.7.md) | `android` | 2025-04-13 | `TODO` (`android`) — _detailed diff pending_ |
| [1.240826.27](2025-04-12_1.240826.27.md) | `android` | 2025-04-12 | `TODO` (`android`) — _detailed diff pending_ |
| [1.241021.17](2025-04-11_1.241021.17.md) | `android` | 2025-04-11 | `TODO` (`android`) — _detailed diff pending_ |
| [1.250407.0](2025-04-10_1.250407.0.md) | `ios` | 2025-04-10 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.250331.7](2025-04-10_1.250331.7.md) | `android` | 2025-04-10 | `TODO` (`android`) — _detailed diff pending_ |
| [1.241104.5](2025-04-10_1.241104.5.md) | `android` | 2025-04-10 | `TODO` (`android`) — _detailed diff pending_ |
| [1.241104.7](2025-04-08_1.241104.7.md) | `android` | 2025-04-08 | `TODO` (`android`) — _detailed diff pending_ |
| [1.240812.7](2025-04-08_1.240812.7.md) | `android` | 2025-04-08 | `TODO` (`android`) — _detailed diff pending_ |
| [1.250217.10](2025-04-07_1.250217.10.md) | `android` | 2025-04-07 | `TODO` (`android`) — _detailed diff pending_ |
| [1.240916.17](2025-04-03_1.240916.17.md) | `android` | 2025-04-03 | `TODO` (`android`) — _detailed diff pending_ |
| [1.250331.0](2025-04-02_1.250331.0.md) | `ios` | 2025-04-02 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.250224.17](2025-03-31_1.250224.17.md) | `android` | 2025-03-31 | `TODO` (`android`) — _detailed diff pending_ |
| [1.250224.27](2025-03-30_1.250224.27.md) | `android` | 2025-03-30 | `TODO` (`android`) — _detailed diff pending_ |
| [1.250310.7](2025-03-29_1.250310.7.md) | `android` | 2025-03-29 | `TODO` (`android`) — _detailed diff pending_ |
| [1.241028.27](2025-03-27_1.241028.27.md) | `android` | 2025-03-27 | `TODO` (`android`) — _detailed diff pending_ |
| [1.250324.0](2025-03-26_1.250324.0.md) | `ios` | 2025-03-26 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.250317.17](2025-03-24_1.250317.17.md) | `android` | 2025-03-24 | `TODO` (`android`) — _detailed diff pending_ |
| [1.250317.1](2025-03-20_1.250317.1.md) | `ios` | 2025-03-20 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.250317.0](2025-03-19_1.250317.0.md) | `ios` | 2025-03-19 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.250310.1](2025-03-13_1.250310.1.md) | `ios` | 2025-03-13 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.250310.0](2025-03-12_1.250310.0.md) | `ios` | 2025-03-12 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.250303.0](2025-03-05_1.250303.0.md) | `ios` | 2025-03-05 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.250224.2](2025-02-27_1.250224.2.md) | `ios` | 2025-02-27 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.250224.1](2025-02-26_1.250224.1.md) | `ios` | 2025-02-26 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.250217.0](2025-02-20_1.250217.0.md) | `ios` | 2025-02-20 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.250210.0](2025-02-12_1.250210.0.md) | `ios` | 2025-02-12 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.250203.0](2025-02-06_1.250203.0.md) | `ios` | 2025-02-06 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.250127.0](2025-01-30_1.250127.0.md) | `ios` | 2025-01-30 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.250120.1](2025-01-22_1.250120.1.md) | `ios` | 2025-01-22 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.250113.0](2025-01-15_1.250113.0.md) | `ios` | 2025-01-15 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.250106.0](2025-01-08_1.250106.0.md) | `ios` | 2025-01-08 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.241216.3](2024-12-19_1.241216.3.md) | `ios` | 2024-12-19 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.241216.0](2024-12-12_1.241216.0.md) | `ios` | 2024-12-12 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.241209.2](2024-12-11_1.241209.2.md) | `ios` | 2024-12-11 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.241202.0](2024-12-07_1.241202.0.md) | `ios` | 2024-12-07 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.241118.3](2024-11-27_1.241118.3.md) | `ios` | 2024-11-27 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.241118.2](2024-11-20_1.241118.2.md) | `ios` | 2024-11-20 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.241111.3](2024-11-16_1.241111.3.md) | `ios` | 2024-11-16 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.241111.2](2024-11-14_1.241111.2.md) | `ios` | 2024-11-14 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.241111.0](2024-11-07_1.241111.0.md) | `ios` | 2024-11-07 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.241104.1](2024-11-06_1.241104.1.md) | `ios` | 2024-11-06 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.241104.0](2024-10-31_1.241104.0.md) | `ios` | 2024-10-31 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.241028.2](2024-10-29_1.241028.2.md) | `ios` | 2024-10-29 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.241021.7](2024-10-23_1.241021.7.md) | `ios`, `android` | 2024-10-23 | `TODO` (`ios`, `android`) — _detailed diff pending_ |
| [1.241021.4](2024-10-22_1.241021.4.md) | `ios` | 2024-10-22 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.241021.2](2024-10-18_1.241021.2.md) | `ios` | 2024-10-18 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.241021.0](2024-10-17_1.241021.0.md) | `ios` | 2024-10-17 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.241007.1](2024-10-08_1.241007.1.md) | `ios` | 2024-10-08 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.240930.2](2024-10-02_1.240930.2.md) | `ios` | 2024-10-02 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.240923.1](2024-09-26_1.240923.1.md) | `ios` | 2024-09-26 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.240916.1](2024-09-17_1.240916.1.md) | `ios` | 2024-09-17 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.240909.0](2024-09-10_1.240909.0.md) | `ios` | 2024-09-10 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.240902.2](2024-09-06_1.240902.2.md) | `ios` | 2024-09-06 | `TODO` (`ios`) — _detailed diff pending_ |
| [1.240826.1](2024-09-01_1.240826.1.md) | `ios` | 2024-09-01 | `TODO` (`ios`) — _detailed diff pending_ |
