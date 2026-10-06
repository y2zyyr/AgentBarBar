# AgentBarBar for Windows — 1.0.4 Preview

[简体中文](WINDOWS.zh-CN.md) · [Download installer](https://github.com/y2zyyr/AgentBarBar/releases/download/v1.0.4/AgentBarBar-1.0.4-Windows-x64-Preview-Setup.exe)

This is a public preview, not a completed Windows stable release. The product version matches macOS 1.0.4 (build 34); Windows compatibility and release validation have separate status.

## Install and use

1. Download the x64 EXE from the 1.0.4 release. Windows 11 x64 is the tested platform; ARM64 and older Windows versions are unverified.
2. Double-click the installer and select Chinese or English. It installs for the current user. WebView2 is required; the installer is configured to download its Evergreen bootstrapper if the runtime is missing. Missing/broken-runtime cases are not yet fully validated and may require network access.
3. Open AgentBarBar from the desktop or Start menu. Find its icon in the notification area (including hidden icons).
4. Click the icon for today’s usage, then **Open Dashboard** for full statistics. Closing the dashboard hides it; use **Quit** in the tray menu to exit the application.
5. Choose language, theme and light/dark/system mode in Dashboard Settings.

No Rust, Cargo, Node.js or Visual Studio is required at runtime. Normal application use does not require administrator privileges.

## Supported Windows sources

| Agent | Windows status |
|---|---|
| Codex | Real-source collection and system pipeline verified |
| Claude Code | Real-source collection and system pipeline verified |
| Kimi CLI | Historical ingestion verified; live accounting partial |
| DeepSeek Harness, WorkBuddy, Pi, Gemini CLI, OpenCode, Antigravity, Antigravity IDE | Unverified; not claimed as supported by this preview |

The screenshot totals depend on captured local records. Missing token fields remain unavailable; no API key is needed to read supported local usage logs.

## Data, reinstall and removal

Program files default to `%LOCALAPPDATA%\Programs\AgentBarBar`. Runtime data is separate under `%LOCALAPPDATA%\AgentBarBar`; the database currently uses `database\usage.sqlite`.

Quit from the tray before reinstalling. The installer refuses to overwrite a running installed application instead of force-terminating its collector. Do not downgrade an existing internal 1.0.5/1.0.6 installation without a data backup; that downgrade path is unverified.

Use Windows **Installed apps → AgentBarBar → Uninstall**. Normal uninstall is designed to retain usage data. Only choose the optional data-removal checkbox if you intend to delete it. Default data preservation was verified with the preceding internal 1.0.5 build; final rebuilt 1.0.4 uninstall and optional deletion remain pending. Back up important data before trying the preview.

## Integrity and known limits

This build is **unsigned** and may show a Windows/SmartScreen publisher warning. Signing and reputation validation remain pending. Verify the SHA256 before use; a checksum provides integrity, not publisher authentication.

```powershell
Get-FileHash .\AgentBarBar-1.0.4-Windows-x64-Preview-Setup.exe -Algorithm SHA256
```

Expected SHA256: `e45c2c948ad7977af8d90f0d82a845b00091f1cd37c6d57ae80dfa62eaba47a6`.

Windows automatic updates and login autostart are not implemented. Download future preview builds manually. Final 24-hour candidate endurance, sleep/wake, Explorer recovery, physical multi-monitor/mixed-DPI and full upgrade/rollback gates are incomplete; the preview is not a claim of full macOS parity.

No telemetry or conversation-body uploads are added. Statistics are read locally, and the app database does not store chat bodies. Feedback should include app/OS version and Agent name, not private logs or credentials.

## Screenshots

README images are real Windows captures from pre-packaging validation. The installer image is the earlier 1.0.4 welcome screen; the current rebuilt 1.0.4 contains subsequent safety fixes. No generated UI mockups are presented as running-app evidence.
