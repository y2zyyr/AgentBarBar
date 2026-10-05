<p align="center"><img src="assets/icon.png" width="100" alt="AgentBarBar"></p>
<h1 align="center">AgentBarBar</h1>
<p align="center">让 AI 用量一目了然。</p>
<p align="center"><a href="README.zh-CN.md">简体中文</a> · <a href="README.md">English</a></p>
<p align="center"><a href="https://github.com/y2zyyr/AgentBarBar/releases/latest"><strong>下载 macOS 版 →</strong></a></p>
<p align="center">Apple Silicon · macOS 14+ · 中文 / English</p>

![AgentBarBar 用量概览](assets/overview-zh.png)
<p align="center"><sub>演示数据 · Demo data</sub></p>

<p align="center"><img src="assets/popover-zh.png" width="330" alt="菜单栏预览 · 演示数据"></p>
<p align="center"><sub>菜单栏预览 · 演示数据</sub></p>

## 用了多少，打开就知道

AgentBarBar 是一个 macOS 菜单栏 AI 用量工具。今天用了多少 Token、最近趋势如何、主要用在哪些 Agent，打开就能看到。

- **随手看用量** — 菜单栏显示今日 Token，点击查看主要 Agent。
- **看清趋势** — 切换今天、7 天、30 天和全部时间。
- **统一查看** — 汇总本机受支持 Agent 的用量，提供请求明细与导出。
- **数据留在本机** — 不上传遥测，不保存对话正文。

## 安装

1. [下载最新 DMG](https://github.com/y2zyyr/AgentBarBar/releases/latest)，将 App 拖到 **Applications 应用程序**。
2. 打开 App，点击菜单栏图标即可查看用量。

![中英双语安装窗口](assets/install.png)

若 macOS 提示无法验证开发者：尝试打开后，进入 **系统设置 → 隐私与安全性 → 仍要打开**。当前下载包未经过 Apple 公证。

## 支持哪些 Agent？

支持读取 Codex、Claude Code、DeepSeek Harness、WorkBuddy、Pi、Kimi CLI、Gemini CLI、OpenCode、Antigravity 和 Antigravity IDE 的本机用量记录。

实际可显示的分项取决于 Agent 提供的记录；已有记录但缺少计数时，会显示为不可用。首次读取较多历史记录可能需要几分钟。

## 更新与反馈

- [版本更新](https://github.com/y2zyyr/AgentBarBar/releases)
- [报告问题 / 建议功能](https://github.com/y2zyyr/AgentBarBar/issues)

反馈时请说明应用版本、macOS 版本和使用的 Agent；无需提供聊天记录或账号凭证。

## 关于这个仓库

本仓库提供产品介绍和安装包，应用源码保持私有。AgentBarBar 可免费下载使用；随包附有第三方依赖许可声明。
