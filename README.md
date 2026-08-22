# 沙禾项目终端

沙禾项目终端（Shaihe Project Terminal）是一套面向官方 AI CLI 的本地项目与真实终端工作驾驶舱。它把项目、任务清单、官方账号状态、模型选择和真实终端会话放到一个可操作的桌面入口中：macOS 运行工作端，Windows、Android 和 iPhone 作为远程控制端。

> 当前公开版本：**4.4.1**
>
> [下载 4.4.1 安装包](https://github.com/olikahn11/shaihe-ai-project-terminal-public/releases/tag/v4.4.1) · [安装说明](INSTALL.md) · [更新记录](RELEASE_NOTES_4.4.1.md) · [SHA-256 校验值](SHA256SUMS.txt)

## 它解决什么问题

当多个 AI 编程任务同时运行时，单独打开一堆 Terminal 窗口很难管理：不知道每个窗口属于哪个项目，也不容易继续旧对话、查看任务清单或安全地切换模型。沙禾项目终端以项目文件和 Git 为真实来源，把这些任务组织起来，同时保留官方 CLI 的真实交互，不建立一套假聊天界面。

## 主要功能

- **多模型官方终端**：统一管理 Codex、Claude Code、Gemini CLI、Grok CLI、Kimi Code 和 Qwen Code；登录、退出、换号交给对应官方 CLI。
- **真实 PTY/tmux 会话**：终端不是截图或模拟输出。输入、ANSI 颜色、中文、滚屏和 CLI 自己的交互界面都通过真实终端通道传输；关闭窗口或远程端断线不会自动结束后台任务。
- **最多 8 格终端平铺**：选择多个任务后进入平铺工作区，每一格都可以单独点击、输入、滚屏和切换焦点；也可以打开对应的独立终端大窗口。
- **输入和剪贴板**：支持终端输入、选中文字、右键菜单中的复制/粘贴/全选，以及 macOS 常用的 `⌘C`、`⌘V`、`⌘A` 和 `Shift+Insert`；没有选中文本时 `Ctrl+C` 仍保留为终端中断。
- **终端可读性**：使用低饱和、高对比的终端色板，尽量保留 AI CLI 的 ANSI 语义颜色；可关闭非必要动效，减少多窗口同时运行时的额外绘制。
- **项目记忆同源**：从 `TASKS.md`、`AGENTS.md`、`HANDOVER.md` 等项目文件读取任务和交接信息，不把聊天记录当成项目记忆。
- **项目与会话管理**：支持新建、继续、恢复、跨模型接力、项目详情、任务进度和运行状态查看。
- **静默原生后台**：macOS 工作端不依赖 Ghostty，正常启动不会弹出 Terminal.app 或 `.command` 窗口。
- **文件拖入与项目范围**：图片或文件拖入后只插入安全路径，不自动执行；首次设置由用户选择项目根目录，应用只扫描其一级项目。
- **远程控制**：Windows、Android 和 iPhone 可通过局域网或同一 Tailscale 网络连接正在运行的 Mac 工作端；手机也可以使用响应式 Web App。

## 平台与下载

| 平台 | 形态 | 下载 | 说明 |
| --- | --- | --- | --- |
| macOS | 完整工作端 | [DMG](https://github.com/olikahn11/shaihe-ai-project-terminal-public/releases/download/v4.4.1/Shaihe-Project-Terminal-4.4.1-macOS.dmg) | 在本机运行官方 CLI、项目扫描、终端和远程服务 |
| Windows | 远程控制端 | [Setup.exe](https://github.com/olikahn11/shaihe-ai-project-terminal-public/releases/download/v4.4.1/Shaihe-Project-Terminal-Remote-4.4.1-Windows-Setup.exe) | 连接正在运行的 Mac 工作端 |
| Android | 远程控制端 | [APK](https://github.com/olikahn11/shaihe-ai-project-terminal-public/releases/download/v4.4.1/Shaihe-Project-Terminal-Remote-4.4.1-Android.apk) | 侧载测试包 |
| iPhone | 远程控制端 / Web App | [未签名 IPA](https://github.com/olikahn11/shaihe-ai-project-terminal-public/releases/download/v4.4.1/Shaihe-Project-Terminal-Remote-4.4.1-iOS-unsigned.ipa) | IPA 需要重签；没有证书时使用 Web App |

## 快速开始

### macOS

1. 下载 DMG，把“沙禾项目终端”拖入“应用程序”。
2. 首次打开时选择项目根目录；推荐使用 `~/Documents/AI/<项目名>`。
3. 按引导检查并登录自己使用的官方 CLI。应用不收集密码、Cookie 或 Token。
4. 选择“新建任务”或继续历史任务。需要同时处理多个任务时，选择多个任务并进入“终端平铺”。
5. 点击任意终端格即可输入和滚屏；右键可复制、粘贴和全选。关闭视图只会断开显示，不会自动结束 tmux 任务。

### Windows、Android、iPhone

在 Mac 工作端打开“设置 → 手机远程”，使用二维码或配对地址连接。局域网内可直接连接；异地使用时，让 Mac 和遥控设备登录同一个 Tailscale 网络。Mac 工作端必须保持运行。

## 运行要求与发行状态

- macOS 工作端最低系统版本为 **macOS 13.0**。
- macOS 安装包是当前可安装工作版，但使用 ad-hoc 签名，尚未使用 Developer ID 公证；首次打开可能需要在系统设置中允许。
- Windows 安装器没有 Authenticode 发行证书，SmartScreen 可能显示未知发布者。
- Android 使用开发测试签名，适合侧载测试，不代表应用商店发行签名。
- iOS IPA 是 arm64 未签名构建，不能直接安装到普通 iPhone；没有 Apple Developer 证书时，可以在 iPhone 浏览器打开配对地址并添加到主屏幕。
- 同时运行 8 个重量级 AI CLI 会自然增加 CPU、内存和网络消耗。平铺本身只负责显示与输入，建议根据设备资源逐步增加并发数。

## 隐私与安全边界

公开发行包不包含开发者的项目文件、账号状态、会话记录、Token、Cookie 或模型密钥。模型登录和授权由对应官方 CLI 完成；本机凭据由系统安全存储或官方 CLI 管理。远程控制只连接用户自己启动的 Mac 工作端。

本公开仓库只发布软件介绍、截图、安装说明、校验值和发行附件，不包含源代码。源代码位于不公开的开发仓库，未附开源许可证，保留所有权利。

## 校验下载文件

下载 [SHA256SUMS.txt](SHA256SUMS.txt) 和对应安装包，在同一目录执行：

```bash
shasum -a 256 -c SHA256SUMS.txt
```

校验值必须与文件完全匹配；如果不匹配，请删除文件并重新从本仓库的 Release 下载。

## 已知限制

- 当前版本的桌面端仍使用系统 WebKit 承载 xterm.js 终端，不是 Ghostty 或 iTerm2 内核。
- 原生 macOS 的系统剪贴板行为会受操作系统权限和焦点状态影响；应用同时提供右键菜单作为可见的复制/粘贴入口。
- 各家 CLI 的模型目录、额度窗口和账号显示以官方当前可读取的信息为准；官方没有提供的数值不会由本软件估算。

## 界面预览

### macOS 首次设置

![macOS 首次设置](screenshots/macos-first-run.png)

### Android 与 iPhone 配对

<p>
  <img src="screenshots/android-pairing.png" alt="Android 配对" width="360">
  <img src="screenshots/ios-pairing.png" alt="iPhone 配对" width="360">
</p>

## 发布验证

最终 macOS 4.4.1 构建完成了 Python `147/147`、TypeScript 类型检查、Vite 生产构建、Swift 编译、DMG CRC/只读挂载、应用深度签名与从镜像实际启动验收；隔离环境下 8 格终端和 8 个原生窗口逐项输入、滚屏、切换、系统剪贴板与右键粘贴均已验证。真实 AI CLI、账号和项目文件仍由安装者自己的本机环境提供。
