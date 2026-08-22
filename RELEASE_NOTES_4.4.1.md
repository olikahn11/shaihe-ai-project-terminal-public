# 沙禾项目终端 4.4.1

4.4.1 是当前公开的四平台可安装测试发行版。macOS 提供完整工作端，Windows、Android 和 iPhone 提供远程控制端。

## 本次更新

- 统一管理 Codex、Claude Code、Gemini CLI、Grok CLI、Kimi Code 和 Qwen Code 的官方终端任务。
- 项目、对话、Markdown 任务清单和交接文件统一从本地项目读取，支持新建、继续、恢复和跨模型接力。
- 真实 PTY/tmux 会话支持独立终端大窗口，以及最多 8 格终端平铺。
- 平铺后的每个终端都支持点击聚焦、输入、滚屏、选择文字和右键复制/粘贴/全选。
- 调整终端颜色为低饱和高对比方案，减少非必要动画和多终端同时绘制的额外负担。
- 账号登录、退出、换号和模型选择交给各家官方 CLI；不建立密码、Token 或 Cookie 仓库。
- 提供 macOS 完整工作端，以及 Windows、Android、iPhone 远程控制端；异地连接支持 Tailscale。

## 已知发行限制

- macOS 尚未使用 Developer ID 公证。
- Windows 尚未使用 Authenticode 证书。
- Android 使用开发测试签名。
- iOS IPA 未签名，需要开发者证书重签；也可直接使用手机 Web App。
- 同时运行 8 个重量级 AI CLI 会增加 CPU、内存和网络消耗，应根据设备资源逐步增加并发数。
