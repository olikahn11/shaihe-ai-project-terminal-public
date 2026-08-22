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
- 修复 Claude 官方重置时间省略分钟时无法显示的问题；额度窗口现在标注订阅/API来源，并支持包月订阅、API 按量和混合显示口径。
- macOS 内嵌终端恢复系统快捷键：`⌘C` 复制、`⌘V` 粘贴、`⌘A` 全选；普通 `Ctrl+C` 仍作为 CLI 中断。
- Grok 接入官方 `/usage`，Gemini/Qwen 在官方 `/stats` 可读时显示本机会话用量；官方未提供机器可读余额的 Provider 会明确说明，不估算订阅额度。

## macOS 最终构建更新（2026-08-22）

- 终端平铺扩展至最多 8 格，并完成 8 个原生独立窗口逐窗输入、滚屏、切换和关闭验收。
- 删除 Ghostty、Terminal.app、`.command` 和后台跳板依赖；工作端改为单一原生静默后台，关闭 App 后不留孤儿服务。
- 最小化、隐藏或完全遮挡时释放 xterm/WebSocket/PTY 显示附着，后台 tmux 与官方 CLI 任务继续工作，恢复窗口后自动重连。
- 补齐 macOS 原生编辑菜单、`⌘C`、`⌘V`、`⌘A` 和终端右键粘贴；保留普通 `Ctrl+C` 的 CLI 中断语义。
- 修复后台额度探针错误继承文件系统根目录导致的照片权限误触；正常额度刷新不需要照片图库权限。
- 支持 Finder 图片/文件路径拖入、ANSI 分类配色、非焦点终端降频和高频输出限流，在保留全部 CLI 功能的同时降低多任务资源消耗。
- 本次只替换 macOS 完整工作端；Windows、Android、iPhone 4.4.1 遥控端附件保持不变。

## 已知发行限制

- macOS 尚未使用 Developer ID 公证。
- Windows 尚未使用 Authenticode 证书。
- Android 使用开发测试签名。
- iOS IPA 未签名，需要开发者证书重签；也可直接使用手机 Web App。
- 同时运行 8 个重量级 AI CLI 会增加 CPU、内存和网络消耗，应根据设备资源逐步增加并发数。
