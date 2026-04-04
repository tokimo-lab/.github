<div align="center">

# Tokimo

### AI-Native Cloud Desktop OS

**一个永远在线的个人助理，活在你的云桌面里。**

An always-on personal AI assistant, living inside your cloud desktop.

</div>

---

### AI 时代的问题

**聊天机器人**能对话，做不了事。**CLI Agent**能做事，但结果在黑框里——你得自己去各个平台确认。

数据散落在十个 App 里，互不相通。你的文件在 NAS，照片在手机，笔记在 Notion，媒体在 Plex，终端在 SSH 客户端。没有一个系统把它们连起来。

### Tokimo 的答案

**把 AI 助理放进一个完整的图形化操作系统。**

它不是一个黑框。它活在一个有窗口、有任务栏、有文件管理器的桌面里——它做的每一件事，你打开浏览器就能**实时看到结果**。

你在飞书、钉钉、Discord、Telegram 里发一条消息给它。它在你的云桌面里默默执行。等你打开浏览器——电影已经在媒体库里，照片已经分好类，数据库查询结果已经在表格里。

**CLI 的能力 + GUI 的可视化。一个系统，所有数据，一个助理。**

---

### 核心差异

🧠 **个人数据中枢** — 文件、媒体、知识、终端、数据库、AI 对话，汇聚在一个系统。打破数据孤岛。

🤖 **AI 天然有「眼睛」** — 不是聊天框加了个 UI。AI 活在桌面 OS 里，能打开窗口、操作文件、渲染图表、播放媒体。架构级的可视化能力。

💬 **无处不在的助理** — 接入任何 IM，随时指挥。助理 7×24 在你的云桌面待命，打开浏览器即见结果。

⚡ **Rust 驱动** — 零 GC 停顿，C 级性能。本地 ONNX 推理（OCR / 图搜 / 人脸 / 语音）。NAS 和树莓派也能跑。

🔒 **隐私优先** — 数据 100% 在你的服务器。支持完全断网运行。自部署，一行 Docker 命令。

---

### 它能做什么

**桌面环境** — 拖拽窗口、任务栏、Dock、菜单栏。窗口状态实时持久化，刷新即恢复。

**媒体全链路** — 订阅 → 下载 → 整理 → 刮削 → 转码 → 播放。电影、音乐、照片、小说全覆盖。兼容 Plex / Emby / Jellyfin。

**统一文件系统** — 本地 · SFTP · SMB · FTP · NFS · S3 · WebDAV，一个入口访问所有存储。

**自动化** — Rhai 脚本 + Cron 调度。自动追剧、自动下载、自动整理。

**远程终端** — 浏览器 SSH，文件树 + 进程监控 + Docker 管理。

**多数据库** — PostgreSQL · MySQL · MongoDB · Oracle · ClickHouse 等，一个窗口全搞定。

**AI 引擎** — OpenAI · Claude · Gemini · 本地模型。Agent 模式 + MCP 工具协议。

---

### 技术

Rust (Axum) · React 19 · PostgreSQL · ONNX Runtime · WebAssembly

端到端类型安全：Rust struct → ts-rs → TypeScript → React Query，零手动同步。

```bash
docker compose up -d    # 一行部署
```

---

### 开源项目

| 仓库 | 说明 |
|------|------|
| [tokimo-ffmpeg](https://github.com/tokimo-lab/tokimo-ffmpeg) | Rust FFI 高性能媒体转码 |
| [tokimo-universal-archiver](https://github.com/tokimo-lab/tokimo-universal-archiver) | 通用解压缩库 (ZIP/TAR/7Z/RAR/ZST) |
| [tokimo-universal-im](https://github.com/tokimo-lab/tokimo-universal-im) | 企业 IM Rust SDK — 钉钉/企微/飞书 |
| [tokimo-translate](https://github.com/tokimo-lab/tokimo-translate) | 高性能中英翻译 (GGUF + llama.cpp) |
| [kvdb](https://github.com/tokimo-lab/kvdb) | Rust 嵌入式 KV 数据库 |

---

<div align="center">

**Self-hosted · Privacy-first · Rust-powered**

一个系统，所有数据，一个助理。

</div>
