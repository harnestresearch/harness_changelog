# Cursor Latest Changes

English | [简体中文](zh-CN/cursor.md) · **Highlight** | [Full Detail](full/cursor.md)

> See [cursor/README.md](cursor/README.md) for the complete five-platform index (`mac`, `win`, `ubuntu`, `ios`, `android`) covering all 446 releases (426 Desktop releases up to `3.30.14` + 20 iOS releases up to `ios-1.17.0`; standalone Android unreleased).

## 3.30.14 (2026-11-14)

See [cursor/2026-11-14_3.30.14.md](cursor/2026-11-14_3.30.14.md) for highlights, or [full/cursor/2026-11-14_3.30.14.md](full/cursor/2026-11-14_3.30.14.md) for full technical details. _(CDN release time: `2026-11-14 04:27` UTC+8 / `2026-11-13 20:27:26` GMT; not yet listed on the official Cursor changelog.)_

### Highlights

- **Live Web App Publishing ("Deploy App", Feature-Gated)**: Ships default-off client support for turning prototypes built in chat into live, shareable web apps (*"Build Live, Shareable Apps with Cursor"* / *"Deploy Folder"*), including deploy-intent suggestions in chat, cloud project migration (excluding dependencies, build output, and `.env` files), publish proposal confirmation, app update/redeploy/unpublish controls, and local dev-server preview cards.
- **Granular Team Repository & Path Glob Governance**: Expands enterprise team repository allowlists and blocklists from whole-repository URL matching to wildcard repositories (`*`), organization URL globs (`org-*`), and in-repository file path glob rules—defaulting to blocking unapproved paths when a team allowlist is active (while exempting Cursor's own data directory).
- **Zen Mode Option, Grok Config Support & Electron `43.8.9` Update**: Adds *"Hide Tab Bar in Zen Mode"* copy in the Agents surface, records subagent types on side chats, distinguishes calling window layouts in the local agent daemon, adds desktop support for reading `~/.grok` configs and submitting Grok feedback, and upgrades Electron `43.8.4` → `43.8.9` across macOS, Windows, and Linux.

---

## Previous Release: 3.30.8 (2026-11-12)

See [cursor/2026-11-12_3.30.8.md](cursor/2026-11-12_3.30.8.md) for highlights, or [full/cursor/2026-11-12_3.30.8.md](full/cursor/2026-11-12_3.30.8.md) for full technical details. _(Package release times: Win/macOS `2026-11-12 06:23` UTC+8, Linux `2026-11-12 10:26` UTC+8; not yet listed on the official Cursor changelog.)_

### Highlights

- **Enterprise MCP Policies, Step-Up Auth & Session Governance**: Enforces team MCP server allowlists, denylists, Cloud Agent allowlists, and per-tool/read-only access policies in the desktop client with clear block explanations, alongside Step-Up secondary authentication, third-party OAuth app controls, API key inventory, and member session revocation.
- **Expanded Remote Control Actions & Cryptographic Pairing Proof**: Remote controllers (including Cursor iOS) can now archive, pin, or mark sessions unread, restore local file checkpoints, manage local MCP servers, and monitor daemon reports—backed by a new cryptographic `pairing_proof` pairing step.
- **MCP Event-Triggered Automations, Team Access Tool & Airlock Controls**: Trigger background automations from MCP server events, return interactive MCP app documents, connect to Kalshi, share MCP state across Git worktrees, manage collaborator access (`manage_access`), gate local turns with Orbit Airlock (Docker/Podman), and relaunch updates while idle—plus default-off *"Cursor is now Grok Build"* and `molten` Agents Window rollouts.

---

## Recent Architectural Baseline: 3.28.7 (2026-11-03)

See [cursor/2026-11-03_3.28.7.md](cursor/2026-11-03_3.28.7.md) for highlights, or [full/cursor/2026-11-03_3.28.7.md](full/cursor/2026-11-03_3.28.7.md) for full technical details.

### Highlights

- **Dedicated Agents Window Alongside Classic IDE**: Work in either the full code editor or the streamlined Agents Window optimized for managing parallel local and cloud agent conversations, reviewing diffs, and configuring remote access.
- **Steer Local Agents from Your Phone (Remote Control)**: Pair your computer with the Cursor iOS app using a verified 6-character display code so you can direct local tasks remotely while file edits, searches, and terminal commands continue executing on your own machine—complete with an optional "Keep this computer awake" toggle and one-tap handoff to move local sessions to the cloud.
- **Multi-Agent Swarms, Tracked Tasks, Canvas & PR Code Tours**: Orchestrate parallel subagents and background tasks, collaborate on visual Canvas artifacts, generate interactive Pull Request Code Tours, inspect context token usage breakdowns, and search semantically across repositories.
- **Built-in Browser Automation & Desktop Computer Use**: Inspect, navigate, click, type, and debug live web apps through the built-in IDE browser (including console/network logs and screenshots) and automate authorized desktop GUI workflows on macOS and Windows.
- **Mobile Live Activity Sync & Enterprise Governance**: Supports lock-screen Live Activity progress updates for up to 8 concurrent agents on iOS, granular tool/connector allowlists, and organization-level self-hosted/remote-control administrative policies.

---

## Recent Architectural Baseline: 3.24.12 (2026-10-09)

See [cursor/2026-10-09_3.24.12.md](cursor/2026-10-09_3.24.12.md) for highlights, or [full/cursor/2026-10-09_3.24.12.md](full/cursor/2026-10-09_3.24.12.md) for full technical details.

### Highlights

- **Isolated & Sandboxed MCP Host Process**: Runs external MCP tool servers inside a dedicated background process with OS-level filesystem and network sandboxing so slow or misbehaving integrations never freeze the editor.
- **Built-in IDE Browser & Desktop Computer Use**: Ships two zero-setup built-in automation providers—a 16-tool IDE Browser controller (navigation, accessibility snapshots, clicking, typing, tab management, console messages, and network request inspection) and a 17-tool Desktop Computer Use controller on macOS and Windows.
- **Remote Connectors with OAuth, Placement Control & Interactive UI**: Supports remote HTTP/SSE connectors with automatic OAuth sign-in, server-vs-client execution placement options, per-server tool filtering, `.env` variable loading, and rich interactive HTML app views inside chat.
- **Project Server Security Approvals & Cross-App Discovery**: Automatically requires user re-approval whenever a project's shared MCP configuration changes, supports wildcard allowlists and enterprise admin policies, and optionally discovers existing MCP configs from Claude Desktop, Windsurf, and VS Code workspaces.
