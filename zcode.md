# ZCode Desktop Latest Changes

English | [简体中文](zh-CN/zcode.md) · **Highlight** | [Full Detail](full/zcode.md)

> See [zcode/README.md](zcode/README.md) for the complete five-platform index (`mac`, `win`, `ubuntu`, `ios`, `android`) covering all 123 historical releases (`0.1.7` → `3.18.2` across `mac` / `win` / `ubuntu`; standalone `ios` / `android` unreleased).

## 3.18.2 (2026-11-13)

Official public release succeeding [3.17.2](zcode/2026-11-02_3.17.2.md) (`Released Nov 13, 2026`, accumulating preview builds `3.18.0` and `3.18.1` below). See [zcode/2026-11-13_3.18.2.md](zcode/2026-11-13_3.18.2.md) for highlights, or [full/zcode/2026-11-13_3.18.2.md](full/zcode/2026-11-13_3.18.2.md) for full technical details.

- **Seamless Sign-In Preservation After Data Directory Migration**: Automatically shares the OS keyring decryption key with the newly copied credentials folder when switching data storage directories so accounts stay signed in without re-authenticating.
- **Linux Login Fallback Without System Keyring**: Automatically falls back to a permission-hardened (`0600`) local private key file on Linux desktops when no system Secret Service keyring is available.
- **Standalone Start Plan Access for Mainland China (`zai_cn`) Accounts**: Decouples Start Plan session credentials from full OAuth tokens and maps `zai_cn` accounts into the BigModel Start Plan family so China accounts can use Start Plan benefits without linking BigModel first.
- **Windows Update Check Fix**: Fixed checking for updates failing on Windows under system restrictions or when paths contain special characters.

---

## 3.18.1 (2026-11-11)

See [zcode/2026-11-11_3.18.1.md](zcode/2026-11-11_3.18.1.md) for highlights, or [full/zcode/2026-11-11_3.18.1.md](full/zcode/2026-11-11_3.18.1.md) for full technical details.

- **Guided Microphone Permission Reset & macOS Font Smoothing**: Added a multi-step voice permission guide popover supporting one-click macOS microphone permission reset across 5 languages, plus a macOS-exclusive "Font Smoothing" toggle in Settings.
- **Sidebar, Browser Picker & Updater Fixes**: Allowed dragging the chat bar narrower, stopped browser element selection from switching to full view or blocking content, fixed mainland China website login and leftover updater process issues, and included sanitized memory snapshots in exported logs.

---

## Recent Major Release: 3.18.0 (2026-11-10)

See [zcode/2026-11-10_3.18.0.md](zcode/2026-11-10_3.18.0.md) for highlights, or [full/zcode/2026-11-10_3.18.0.md](full/zcode/2026-11-10_3.18.0.md) for full technical details.

- **Voice Input, Parallel Git Worktrees & Extensions**: Added real-time composer voice dictation, isolated Git Worktree parallel tasks & message forking, an Extensions marketplace with tiered session permissions, and a built-in Design system with visual click-to-edit inside the built-in browser.
- **Multi-Session Coordination, Share Management & Global Languages**: Added multi-session orchestration, proactive plugin recommendations, in-place message editing, expiring share links with a Share Management page, bulk permanent archive cleanup, `zai_cn` multi-account switching, OS keyring protection, Japanese/Korean/Russian UI locales, and ZCode Sites traffic analytics.
