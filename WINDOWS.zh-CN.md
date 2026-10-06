# AgentBarBar Windows — 1.0.4 测试版

[English](WINDOWS.md) · [下载安装包](https://github.com/y2zyyr/AgentBarBar/releases/download/v1.0.4/AgentBarBar-1.0.4-Windows-x64-Preview-Setup.exe)

这是公开测试版，不是已完成全部验收的 Windows 稳定版。产品版本与 macOS 同步为 1.0.4（Build 34），平台支持与发布验证分别记录。

## 安装和使用

1. 下载 1.0.4 Release 中的 Windows x64 EXE。已测试 Windows 11 x64；ARM64 和较旧 Windows 尚未确认。
2. 双击安装包，安装标题、说明与按钮在同一页面同时显示中文和 English。安装到当前用户目录。需要 WebView2；安装包配置为缺失时下载 Evergreen 引导程序，此时可能需要网络。Runtime 缺失 / 损坏场景尚未完整验证。
3. 从桌面或开始菜单启动，在任务栏通知区域（包括隐藏图标）找到 AgentBarBar。
4. 点击图标查看今日用量，再点击“打开仪表盘”。关闭仪表盘仅隐藏窗口；真正退出请使用托盘菜单“退出”。
5. 在仪表盘设置中切换语言、主题和明暗模式。

运行安装版不需要 Rust、Cargo、Node.js 或 Visual Studio。正常使用不需要管理员权限。

## Windows Agent 支持范围

| Agent | Windows 状态 |
|---|---|
| Codex | 真实数据源及系统采集链已验证 |
| Claude Code | 真实数据源及系统采集链已验证 |
| Kimi CLI | 历史导入已验证；实时计数部分验证 |
| DeepSeek Harness、WorkBuddy、Pi、Gemini CLI、OpenCode、Antigravity、Antigravity IDE | 尚未确认，本测试版不宣称支持 |

缺失 Token 字段不会猜测补齐。读取受支持的本机用量日志不需要 API Key。

## 数据、覆盖安装与卸载

程序默认位于 `%LOCALAPPDATA%\Programs\AgentBarBar`；运行数据独立位于 `%LOCALAPPDATA%\AgentBarBar`，当前数据库为 `database\usage.sqlite`。

覆盖安装前先从托盘退出。安装程序发现已安装应用仍在运行时会拒绝覆盖，不会强制终止正在采集的应用。已安装内部 1.0.5 / 1.0.6 的用户请勿在未备份数据时降级；此降级路径尚未验证。

通过 Windows“已安装的应用 → AgentBarBar → 卸载”移除程序。普通卸载设计为保留用量数据；只有主动选择删除数据选项才会删除。此前内部 1.0.5 已验证普通卸载保留数据库；当前重打包 1.0.4 的最终卸载与可选删除尚待补验。试用前请备份重要数据。

## 校验与已知限制

当前安装包**未签名**，可能出现 Windows / SmartScreen 发布者提示。代码签名与信誉验证尚未完成。SHA256 只用于完整性校验，不代表已完成发布者身份认证。

```powershell
Get-FileHash .\AgentBarBar-1.0.4-Windows-x64-Preview-Setup.exe -Algorithm SHA256
```

SHA256：`b2fb434900ec1afe86b6c54021b49748996716af4d1ab0db45511486b8dbfce5`。

暂不提供 Windows 自动更新与登录自动启动；后续测试包需手动下载。最终候选 24 小时耐久、睡眠恢复、Explorer 恢复、物理多屏 / 混合 DPI、完整升级回滚等验收尚未完成，不能据此宣称与 macOS 完全对等。

不增加遥测或对话上传；统计在本地读取，数据库不保存聊天正文。反馈仅需应用 / 系统版本和 Agent 名称，请勿提交私密日志或凭据。

## 截图来源

README 使用打包前验证时的真实 Windows 界面截图。安装图为当前重打包 1.0.4 的同页中英双语欢迎界面，来自真实 Windows 安装程序窗口。截图不是 AI 生成界面或静态 Demo。
