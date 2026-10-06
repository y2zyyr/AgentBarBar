# AgentBarBar for Windows — 1.0.6

[简体中文](WINDOWS.zh-CN.md) · [Download installer](https://github.com/y2zyyr/AgentBarBar/releases/download/v1.0.6/AgentBarBar-1.0.6-Windows-x64-Setup.exe)

Windows x64 system-tray application, version 1.0.6 (build 38). Installer titles, instructions and buttons display Chinese and English together on each page.

## Install and use

1. Quit the current AgentBarBar from its tray menu before reinstalling.
2. Download and run the x64 installer. It installs for your Windows account; normal use requires no administrator privileges. Windows 11 x64 is the validated platform; ARM64 and older versions are unverified.
3. WebView2 is required. The installer is configured to download its Evergreen bootstrapper if needed; missing/broken-runtime scenarios remain incompletely validated and can require network access.
4. Open AgentBarBar from the desktop or Start menu. Click its notification-area icon for today's usage and **Open Dashboard** for full statistics.
5. Choose Chinese/English, Forest/Paper/Ocean/Mono and light/dark/system modes in Dashboard Settings. Closing the dashboard hides it; **Quit** in the tray menu exits the application.

No Rust, Cargo, Node.js or Visual Studio is required at runtime.

## Collectors

| Agent | Validation |
|---|---|
| Codex | Real Windows source collection verified |
| Claude Code | Real Windows source collection verified |
| Kimi CLI | Real Windows historical records verified; live accounting remains partial |
| DeepSeek Harness | Real Windows canonical SQLite ledger independently reconciled; replay does not double-count |
| Qwen Code | Versioned monthly Token ledger parsed and deduplicated by ledger record ID; no usable source on the validation host, fixture validation only |
| Cline (legacy tasks) | Merges per-request start/finish records from `ui_messages.json`; no usable source on the validation host, fixture validation only |
| WorkBuddy, Pi, Gemini CLI, OpenCode, Antigravity, Antigravity IDE | Implemented and matched against macOS anonymous fixtures; no usable source on the validation host for real-source system validation |

All twelve collectors support source-path overrides and enable/disable switches. Missing sources and counters remain unavailable. No API key is required to read local usage records. DSH adopts one authoritative ledger, handles exclusions/downward corrections and does not add session-log counts to ledger totals.

**Find Token sources** now works on Windows, saves metadata-only survey reports and restores them after reload. History coverage uses retained records and their date range; zero new rows in the last scan do not mean zero history.

Manual sync now changes its start notice to **Sync completed**, even when no new records are found. First import of a large history can take time.

Gemini records keep their real source line and byte positions, and the shared cursor format is now `gemini-session-v2.0.1`; existing source files are replayed under the new format. In the tray app, the Tibo Codex Monitor link is opened by the system default browser; only fixed HTTPS resources are handed over, and a message is shown when that fails.

## Data and removal

Program files default to `%LOCALAPPDATA%\Programs\AgentBarBar`; runtime data remains separate under `%LOCALAPPDATA%\AgentBarBar`, with `database\usage.sqlite`.

The installer refuses to overwrite a running installed application. Normal uninstall is designed to preserve usage data; the optional data-removal checkbox deletes it only when selected. The existing data-protection logic is retained; final updated-package uninstall/deletion and full upgrade/rollback validation remain incomplete. Earlier internal 1.0.5/1.0.6 downgrades remain unverified.

## Integrity and current limitations

The installer is **unsigned**. A SHA256 checksum verifies file integrity, not publisher identity.

```powershell
Get-FileHash .\AgentBarBar-1.0.6-Windows-x64-Setup.exe -Algorithm SHA256
```

Expected SHA256: `da17eac90175b9387a370ae35e19b56a8fc0cc4b50df9aa2b0fe163a15869808`.

Windows login autostart and automatic updates are not implemented. Long-run endurance, sleep/wake, Explorer recovery, physical mixed-DPI/multi-monitor and full upgrade/rollback validation remain incomplete. Download updates from GitHub manually.

Statistics stay local; conversation bodies and telemetry are not uploaded. Feedback needs app/OS version and Agent name, not private logs or credentials.

## Screenshots

README Windows screenshots are earlier real application captures. The bilingual installer image shows the 1.0.4 package's layout, which the 1.0.6 package retains; it is not a new capture of the updated binary.
