# 沙禾项目终端 4.4.1 安装说明

请从 [GitHub Releases](https://github.com/olikahn11/shaihe-ai-project-terminal-public/releases/latest) 下载对应平台的文件。

## macOS 完整工作端

1. 下载并打开 `沙禾项目终端-4.4.1-macOS.dmg`。
2. 把“沙禾项目终端”拖入“应用程序”。
3. 首次打开后，按引导检测并登录自己使用的官方模型 CLI。
4. 项目统一放在 `~/Documents/AI/<项目名>`。

当前 DMG 为 ad-hoc 签名、未做 Developer ID 公证。其他 Mac 首次打开可能显示 Gatekeeper 提示。

## Windows 遥控端

1. 下载并运行 `沙禾项目终端遥控-4.4.1-Windows-Setup.exe`。
2. 在 Mac 工作端打开“设置 → 手机远程”。
3. 把配对地址输入 Windows 遥控端并连接。

安装器尚无 Authenticode 发行证书，Windows SmartScreen 可能提示未知发布者。

## Android 遥控端

1. 下载 `沙禾项目终端遥控-4.4.1-Android.apk`。
2. 允许浏览器或文件管理器“安装未知应用”，然后安装 APK。
3. 在 Mac 工作端打开“设置 → 手机远程”，扫码或输入配对地址。

APK 已通过 v2 签名，可用于侧载测试；当前使用开发测试证书，不用于应用商店发行。

## iPhone 遥控端

`沙禾项目终端遥控-4.4.1-unsigned.ipa` 是 arm64 未签名构建，不能直接安装到普通 iPhone。需要使用目标设备所属 Apple Developer 团队的证书和描述文件重新签名。

没有证书时，可直接在 iPhone 浏览器打开 Mac“设置 → 手机远程”提供的地址，并把响应式 Web App 添加到主屏幕。

## 连接方式

- 同一网络：Mac 与遥控设备在同一局域网，直接使用配对二维码或地址。
- 不同网络：Mac 与遥控设备登录同一个 Tailscale 账号，再使用设置页提供的异网地址。

## 校验下载文件

下载 `SHA256SUMS.txt` 后，在文件所在目录执行：

```bash
shasum -a 256 -c SHA256SUMS.txt
```
