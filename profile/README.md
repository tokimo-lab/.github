<div align="center">

# Tokimo

### The AI-Native Web Desktop OS

**Your entire digital life — in one browser tab.**

A high-performance, self-hosted operating system that runs in the browser.<br>
Not another dashboard. A real desktop — with windows, a taskbar, a dock, and an AI agent that can see and operate it all.

<br>

`Rust` · `React 19` · `WebAssembly` · `ONNX Runtime` · `PostgreSQL`

---

**27 Built-in Apps** · **14 Rust Packages** · **40+ API Modules** · **9 Languages**<br>
**7 Storage Backends** · **9 Database Types** · **15+ External Integrations**

</div>

---

## The Vision

Most self-hosted tools solve one problem — media, files, terminals — each in isolation. Tokimo reimagines them as **apps inside an operating system**.

Open a terminal, drag a file to the media library, run a SQL query on your remote database, ask AI to analyze your photos — **all in parallel windows on the same desktop**. Every app shares the same window manager, file system, auth, and AI engine.

### AI Gets a Desktop

Here's the paradigm shift: when AI lives inside a desktop OS, it doesn't just output text. It gains a second superpower — **visualization**.

AI can open windows, render charts, browse files, play media, manage databases, and orchestrate workflows — through the same GUI you use. Not a chatbot sidebar. A **desktop agent**.

This is the first system designed from the ground up to give AI a visual interface — and we believe it's the future of human-AI interaction.

---

## What's Inside

### 🖥️ Desktop Environment
A real windowed OS — drag, resize, minimize, maximize, snap. macOS or Windows style. Window state persists to DB via WebSocket. Full recovery on refresh.

### 🤖 AI Engine
Multi-provider (OpenAI · Claude · Gemini · local LLMs) + MCP tool protocol + agent mode. Local inference via ONNX Runtime: OCR, CLIP image search, face recognition, speech-to-text — on your own hardware.

### 🎬 Media Pipeline
Movies · TV · Anime · Music · Photos · Novels. Metadata scraping from 10+ sources. HLS adaptive streaming with FFmpeg transcoding. Auto-download, auto-organize, auto-subscribe.

### 📁 Unified File System
Local · SFTP · SMB · FTP · NFS · S3 · WebDAV — one API, seamless cross-storage transfer.

### 🖥️ Remote Terminal
Full SSH terminal (xterm.js + WebGL), file tree, process monitor, Docker management — in the browser.

### 🗄️ Database Browser
PostgreSQL · MySQL · SQLite · SQL Server · MongoDB · Oracle · ClickHouse · Elasticsearch — query any database from one window.

### 📥 Automation
Rhai scripting + Cron scheduling + JSONPath filtering. qBittorrent · Transmission · Deluge · Aria2 · rTorrent. PT site tracking. YouTube / Bilibili ingest.

### 📚 Reader Suite
EPUB · MOBI · PDF · Web novels · Academic papers (OpenAlex / CrossRef / arXiv) · Book search (Libgen).

---

## Architecture

| Layer | Technology |
|---|---|
| **Frontend** | React 19 · TypeScript · Vite 7 · Tailwind CSS v4 · TanStack Query |
| **Backend** | Rust (Axum) · Sea-ORM 2.0 · PostgreSQL 16 + pgvector |
| **AI/ML** | ONNX Runtime · sherpa-onnx · OpenAI / Claude / Gemini |
| **Type Safety** | Rust DTO → ts-rs → TypeScript (end-to-end, zero manual sync) |
| **Deploy** | Docker Compose — single Rust binary with embedded frontend |

**14 Rust packages** powering the backend:

| Package | Purpose |
|---------|---------|
| `rust-ai` | Multi-provider AI abstraction + streaming |
| `rust-models` | Local inference — OCR · CLIP · Face · STT |
| `rust-hls` | HLS adaptive streaming + transcoding |
| `rust-next-fs` | Unified VFS (7 storage backends) |
| `rust-workflow` | Automation engine (Rhai + Cron) |
| `rust-anysql` | Multi-database session manager |
| `rust-ssh-terminal` | SSH client + PTY management |
| `rust-client-api` | 15+ external API integrations |
| `rust-image-processor` | On-the-fly image processing |
| `rust-subtitle` | Multi-format subtitle parser |
| `tokimo-ffmpeg` | FFmpeg Rust FFI bindings |
| `tokimo-universal-archiver` | Universal archive library |
| `tokimo-wasm` | Browser-side WASM modules |
| `license-core` | License verification |

---

## Deploy

```bash
docker compose up -d    # That's it.
```

One container. Rust binary serves the API + embedded frontend. PostgreSQL for persistence.

Runs on: **Linux VPS · Synology · QNAP · UGREEN · Unraid · Raspberry Pi**

---

## Open Source from Tokimo Lab

| Repository | Description |
|------------|-------------|
| [tokimo-ffmpeg](https://github.com/tokimo-lab/tokimo-ffmpeg) | High-performance media transcoding via Rust FFI to FFmpeg |
| [tokimo-universal-archiver](https://github.com/tokimo-lab/tokimo-universal-archiver) | Universal archive library — ZIP, TAR, 7Z, RAR, GZ, XZ, ZST |
| [tokimo-universal-im](https://github.com/tokimo-lab/tokimo-universal-im) | Enterprise IM Rust SDK — DingTalk, WeCom, Feishu (21 services) |
| [tokimo-translate](https://github.com/tokimo-lab/tokimo-translate) | High-performance CN↔EN translation via GGUF models + llama.cpp |
| [kvdb](https://github.com/tokimo-lab/kvdb) | Embedded key-value database in Rust |

---

<div align="center">

**Privacy-first · Self-hosted · Buy once, own forever**

One system. Every tool you need. Powered by Rust.

</div>
