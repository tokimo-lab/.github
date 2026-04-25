<div align="center">

# Tokimo

### Your self-hosted AI agent — with a desktop attached

A Codex-grade personal assistant that runs on **your** server.<br>
Full virtual filesystem, sandboxed shell, persistent memory, and a real GUI<br>
where you can watch every action it takes.

</div>

---

## Why Tokimo

Modern coding agents — Codex, Claude Code, and friends — are spectacular at running tools in a terminal. But every action lives behind a CLI scroll: did the file land where you expected? Did the migration succeed? You verify it yourself, in another window.

The vendor "agent" platforms solve visibility but lock everything to their cloud, their data formats, their token budgets. Your photos, notes, downloads, and meeting transcripts stay scattered across ten apps, none of which expose enough to the agent for it to *actually* know you.

**Tokimo runs the same kind of agent — sandboxed shell, virtual filesystem, parallel sub-agents, MCP, persistent memory — but on hardware you own, sitting next to all of your personal data, with a browser-based desktop OS you can open at any time to see exactly what it's doing.**

---

## Capability parity with frontier coding agents

Every primitive a serious autonomous agent needs, implemented natively in Rust:

| Capability | Tokimo | Notes |
|---|---|---|
| **Sandboxed shell** | ✅ Bash · PowerShell | AST-based read-only classification, isolated cwd, container-bounded |
| **File ops** | ✅ Read · Write · Edit | Multi-edit with conflict detection |
| **Search** | ✅ Glob · Grep · ToolSearch | ripgrep-backed; tool index for skill discovery |
| **Web** | ✅ WebFetch · WebSearch | Content extraction + AI search APIs |
| **Sub-agents** | ✅ DispatchAgent | Parallel background workers with their own tool budgets |
| **Planning** | ✅ TodoWrite · Plan mode | Structured todo state visible to user in real time |
| **Skills** | ✅ Skill tool | Project-local + global skill packs |
| **MCP** | ✅ Native client | Connect any MCP server; tools auto-registered |
| **Persistent memory** | ✅ PostgreSQL + pgvector | Sessions resume across devices, semantic recall |
| **Multi-provider LLM** | ✅ OpenAI · Anthropic · DeepSeek · Gemini · Ollama | Per-conversation switching, capability-aware routing |
| **Virtual filesystem** | ✅ Local · SFTP · SMB · FTP · S3 · WebDAV · NFS · Aliyun · Baidu · 115 · 189 · Quark | Single API, all your storage |
| **Worktree isolation** | ✅ Worktree tool | Run risky changes in a git worktree, merge when verified |
| **Always-on** | ✅ | Lives on a server, reachable from any browser or IM |

---

## What Tokimo adds on top

### A real desktop, not a chat box

Every agent action shows up as a window on a browser-rendered macOS/Windows-style desktop — taskbar, dock, menu bar, drag-and-drop, multi-window. The agent opens a file manager when it edits files. It opens a terminal when it runs commands. It opens a database browser when it queries SQL. **CLI power, GUI visibility.**

### One unified data layer

All your personal data converges in one PostgreSQL database and one virtual filesystem. The agent has the same view you do — across local disk, NAS shares, S3, cloud drives, photo library, music collection, chat history, and email. It can reason across any of them in a single turn.

### Reach it from anywhere

Bridge your agent into Feishu, DingTalk, Discord, Telegram, Slack — any IM you already use. Send a message from your phone: *"Organize this week's downloads and summarize today's meeting notes."* Tokimo works silently on your server. Open the browser when you're back at a desk — everything is done, every step visible.

### Privately yours, forever

100% self-hosted. One Docker container. Runs on a NAS, VPS, Raspberry Pi, or homelab box. No telemetry, no vendor account, no cloud tier. Your data is a Docker volume — your agent's memory is a database row — both portable, both yours.

---

## What it can do today (beyond the agent itself)

Tokimo has been a personal media + knowledge OS long before the agent layer landed. All of those apps are still here, and the agent has direct API access to every one of them:

- **Media autopilot** — Movies, TV, anime: subscribe, download, scrape metadata (TMDB / Bangumi), transcode (FFmpeg), stream (HLS). Plex/Emby/Jellyfin compatible.
- **Photo library** — Local face clustering, OCR text search, geo-tagging, CLIP semantic search ("sunset photos with Sarah from 2024"). All inferred locally via ONNX, zero cloud upload.
- **Music** — Streaming with lyrics, visualizer, MusicBrainz/Spotify metadata.
- **Documents** — Real-time collaborative editor with version history and whiteboard.
- **Terminal** — Multi-session SSH client with remote script execution.
- **Database browser** — PostgreSQL · MySQL · SQLite · MongoDB · Oracle · ClickHouse · Elasticsearch.
- **Email** — IMAP IDLE push, multi-account.
- **Knowledge** — Academic papers (OpenAlex · CrossRef · arXiv), books (Libgen), web novels.
- **File manager** — Unified VFS finder over every storage type listed above.

The agent uses these as tools. You use these as apps. Same data, same windows.

---

## Architecture

Rust (Axum + Tokio) backend · React 19 + Tailwind v4 frontend · PostgreSQL 16 + pgvector · ONNX Runtime · WebAssembly · WebSocket streaming.

End-to-end type safety: Rust struct → ts-rs → TypeScript DTO → React Query. Change a response shape once, everything updates.

```bash
docker compose up -d
```

One container. One port. Your data, your hardware, your agent.

---

## Repositories

| Repo | What it is |
|---|---|
| **[tokimo](https://github.com/tokimo-lab/tokimo)** | Main monorepo — agent engine, desktop shell, all apps |
| **[tokimo-package-vfs](https://github.com/tokimo-lab/tokimo-package-vfs)** | Async VFS for local/SFTP/FTP/SMB/S3/NFS/WebDAV with handwritten NTLMv2 SMB client |

---

<div align="center">

Self-hosted · Privacy-first · Rust-powered · Codex-grade

**Your agent. Your data. Your hardware.**

</div>
