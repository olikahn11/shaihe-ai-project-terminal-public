# 沙禾项目终端 4.4.2 安装说明

请从 [GitHub Release v4.4.2](https://github.com/olikahn11/shaihe-ai-project-terminal-public/releases/tag/v4.4.2) 下载 macOS 工作端。下载后建议先按照本文的校验步骤验证 SHA-256。4.4.1 遥控端继续兼容 4.4.2 工作端。

## macOS 完整工作端

1. 下载 [沙禾项目终端-4.4.2-macOS.dmg](https://github.com/olikahn11/shaihe-ai-project-terminal-public/releases/download/v4.4.2/%E6%B2%99%E7%A6%BE%E9%A1%B9%E7%9B%AE%E7%BB%88%E7%AB%AF-4.4.2-macOS.dmg)。
2. 打开 DMG，把“沙禾项目终端”拖入“应用程序”。
3. 首次打开时选择项目根目录；可以使用 `~/Documents/AI`，也可以选择其他文件夹、外置磁盘或已有项目根目录。
4. 按引导检查并登录自己使用的官方 CLI。应用不收集密码、Cookie 或 Token。
5. 需要同时处理多个任务时，选择多个任务进入“终端平铺”；每一格都可以点击、输入、滚屏和复制粘贴。
6. 大终端右下角可使用“快 一键功能”和“/ 命令助手”；`!` 只显示用途，不向终端发送内容。

Token 保护默认开启且不能被后台刷新绕过：应用不注入隐藏提示，不自动执行 `/usage`、`/stats` 或其他模型请求。模型与推理默认跟随官方 CLI；高推理档位和并发任务会在界面标明更高消耗。

当前 DMG 使用 ad-hoc 签名，未使用 Developer ID 公证。其他 Mac 首次打开可能显示 Gatekeeper 提示；请确认文件来自本公开仓库后，在系统设置中允许打开。

最低系统版本：macOS 13.0。

工作端不依赖 Ghostty，正常启动不会弹出 Terminal.app 或 `.command` 窗口。应用自身不需要照片图库权限；只有用户或模型任务主动访问受保护目录、麦克风等资源时，macOS 才可能按实际操作显示系统授权框。

终端支持最多 8 格平铺和多个独立窗口，使用 macOS 原生 `⌘C`、`⌘V`、`⌘A` 及右键复制/粘贴。把图片或文件拖进终端时，只插入路径，不自动执行。

## Windows 远程控制端

1. 下载并运行 [Windows Setup](https://github.com/olikahn11/shaihe-ai-project-terminal-public/releases/download/v4.4.1/Shaihe-Project-Terminal-Remote-4.4.1-Windows-Setup.exe)。
2. 在 Mac 工作端打开“设置 → 手机远程”。
3. 将配对地址输入 Windows 遥控端并连接。

Windows 端连接的是 Mac 工作端，不在 Windows 本地运行 macOS AI CLI。安装器尚无 Authenticode 发行证书，SmartScreen 可能提示未知发布者。

## Android 远程控制端

1. 下载 [Android APK](https://github.com/olikahn11/shaihe-ai-project-terminal-public/releases/download/v4.4.1/Shaihe-Project-Terminal-Remote-4.4.1-Android.apk)。
2. 允许浏览器或文件管理器“安装未知应用”，然后安装 APK。
3. 在 Mac 工作端打开“设置 → 手机远程”，扫码或输入配对地址。

APK 使用开发测试证书并通过 APK v2 签名，可用于侧载测试，不代表应用商店发行签名。

## iPhone 远程控制端

[iOS IPA](https://github.com/olikahn11/shaihe-ai-project-terminal-public/releases/download/v4.4.1/Shaihe-Project-Terminal-Remote-4.4.1-iOS-unsigned.ipa) 是 arm64 未签名构建，不能直接安装到普通 iPhone。需要使用目标设备所属 Apple Developer 团队的证书和描述文件重新签名。

没有证书时，在 iPhone 浏览器打开 Mac“设置 → 手机远程”提供的地址，并把响应式 Web App 添加到主屏幕。

## 连接方式

- **同一网络**：Mac 与遥控设备在同一局域网，使用配对二维码或地址。
- **不同网络**：Mac 与遥控设备登录同一个 Tailscale 账号，再使用设置页提供的异网地址。
- **运行条件**：Mac 工作端必须保持运行；手机或 Windows 断线不会结束后台 tmux 任务。

## 校验下载文件

把 [SHA256SUMS.txt](https://github.com/olikahn11/shaihe-ai-project-terminal-public/releases/download/v4.4.2/SHA256SUMS.txt) 下载到安装包所在目录，在终端执行：

```bash
shasum -a 256 -c SHA256SUMS.txt
```

所有文件都显示 `OK` 后再安装。校验失败时不要运行该文件，请重新下载。

## 隐私提醒

发行包不包含开发者的项目、账号、额度、Token、Cookie 或会话。首次使用时请只登录自己的官方 CLI 账号，并确认远程配对地址只分享给你信任的设备。
