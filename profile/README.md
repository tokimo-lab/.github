<div align="center">

# TokimoOS

### The AI-Native Cloud Desktop OS

Your always-on personal assistant, living inside a cloud desktop.

A lightweight, self-hosted operating system that runs in the browser —<br>
where your AI assistant works, thinks, and shows you the results in real time.

</div>

---

### The Problem

**CLI agents are powerful, but blind.** Claude Code, Codex, and MCP-powered tools can execute complex workflows — but the results live in a black box. You still verify everything yourself, across ten different apps.

Even with skills that chain services together, your raw data is still scattered across vendor platforms. Meetings in Feishu, notes in Notion, media in Plex, files on a NAS. These platforms don't expose your personal activity to AI. Stitching fragments into coherent personal memory is complex and entirely at the mercy of each vendor's API.

**Traditional OS is the wrong abstraction.** Bloated, closed, single-device. Want your AI agent to do real work? It needs your data — but your data is trapped on one machine. Upgrade your laptop? Hours of migrating drives and reconfiguring. Work from another device? Too bad — everything is stuck over there.

**Computer-use agents are a dead end.** Feeding screenshots to a vision model so it can click buttons is slow, brittle, and burns tokens on pixel parsing. The right answer isn't bolting AI vision onto a legacy GUI. It's building an OS where AI has native API access from day one.

### The Answer

A cloud-native desktop OS built for the AI era. Every app exposes structured APIs. AI doesn't read pixels — it calls functions. Results appear instantly in the GUI.

Your assistant lives on a cloud computer that's always on. Connect it to any IM — Feishu, DingTalk, Discord, Telegram, Slack. Send a message from your phone. Open the browser when you're ready — everything is done.

CLI power + GUI visibility. Not tied to one device. One system, all your data, one assistant.

---

### What Sets It Apart

**Personal Data Hub** — Work, entertainment, knowledge, infrastructure converge in one system. AI cross-references everything — what you downloaded last week, what you read yesterday, what you discussed a month ago. No vendor lock-in, no fragmented memory.

**AI With Native APIs** — Not pixel-pushing computer-use. Every app has typed endpoints. AI opens windows, moves files, renders charts, queries databases — directly, instantly, no vision model overhead.

**Always-On, Any Device** — Your assistant lives on the cloud desktop 24/7. Connect via any IM. Open from any browser. Upgrade your laptop — nothing changes. Your digital life is a Docker volume, not a hard drive.

**Rust-Powered** — Zero GC, C-level throughput. Local ONNX inference for OCR, image search, face recognition, speech-to-text. Runs on a NAS or Raspberry Pi.

**Your Data, Forever** — 100% local. Works offline. One-line Docker deploy. No vendor, no telemetry, no lock-in.

---

### The Agent — Built From Scratch, Not Stitched Together

Most "AI agent" products are wrappers — `openai` SDK + LangChain + a vector DB SaaS + someone else's UI framework. When any vendor breaks, the product breaks.

**TokimoOS's agent is written from scratch.** The agent loop, the tool dispatcher, the sandbox, the sub-agent runtime, the MCP client, the memory store — all in-house Rust. No LangChain, no LangGraph, no AutoGen, no third-party orchestration. The only external call is the LLM endpoint *you* choose.

Capability parity with frontier coding agents — every primitive native:

| Capability | Implemented |
|---|---|
| **Sandboxed shell** | Bash · PowerShell with AST-based read-only classification, container-bounded execution |
| **File ops** | Read · Write · Edit with multi-edit conflict detection, all routed through the same VFS the GUI uses |
| **Search** | Glob · Grep (ripgrep) · ToolSearch (runtime skill discovery) |
| **Web** | WebFetch with content extraction, WebSearch with pluggable AI providers |
| **Sub-agents** | DispatchAgent — parallel background workers, isolated tool budgets and turn limits |
| **Planning** | TodoWrite · Plan mode — structured todos visible live in the GUI |
| **Skills** | Project-local + global skill packs, on-demand load via `Skill` tool |
| **MCP** | Native client — connect any MCP server, tools auto-registered |
| **Memory** | PostgreSQL + pgvector — sessions resume across devices, semantic recall, automatic context compaction |
| **Multi-provider LLM** | OpenAI · Anthropic · DeepSeek · Gemini · Ollama · any OpenAI-compatible endpoint, switchable per conversation |
| **Worktree isolation** | Risky changes run in a git worktree, merge when verified |

**Built like LEGO.** Every layer — model, tools, skills, MCP servers, storage backends, IM bridges, sandbox rules, memory, even the desktop shell — is a swappable block with a typed contract. Add a driver, every app sees it. Replace a panel, the rest keeps working. Walk away with a Postgres dump and a Docker volume — that's the entire product state.

---

### Scenarios

**Media Autopilot** — Auto-subscribe, download, organize, scrape metadata, transcode, stream. Plex/Emby/Jellyfin compatible. You didn't lift a finger.

**DevOps Dashboard** — SSH, Docker, databases, file management across NAS and cloud — parallel browser windows on one desktop. AI alerts on anomalies.

**AI Photo Library** — Face clustering, OCR, geo-tagging, semantic search. "Sunset photos with Sarah from 2024." All processed locally.

**Research** — Papers from OpenAlex and arXiv, PDFs in-browser, AI summaries. Same workflow for novels, e-books, technical docs.

**Personal Assistant** — "What did we discuss about the migration plan last week? Also, download the top sci-fi from 2025." Memory, context, action.

---

### Architecture

Rust (Axum) · React 19 · PostgreSQL · ONNX Runtime · WebAssembly

End-to-end type safety: Rust → ts-rs → TypeScript → React Query.

```bash
docker compose up -d
```

---

## Repositories

### Core

| Repository | CI | Maintainer | Commits |
|---|---|---|---|
| [tokimo](https://github.com/tokimo-lab/tokimo) | — | William Chan | 2,420 |

### Packages

| Repository | CI | Maintainer | Commits |
|---|---|---|---|
| [tokimo-package-anysql](https://github.com/tokimo-lab/tokimo-package-anysql) | [![CI](https://github.com/tokimo-lab/tokimo-package-anysql/actions/workflows/ci.yml/badge.svg)](https://github.com/tokimo-lab/tokimo-package-anysql/actions/workflows/ci.yml) | William Chan | 5 |
| [tokimo-package-channel](https://github.com/tokimo-lab/tokimo-package-channel) | — | William Chan | 1 |
| [tokimo-package-ffmpeg](https://github.com/tokimo-lab/tokimo-package-ffmpeg) | — | William Chan | 3 |
| [tokimo-package-hls](https://github.com/tokimo-lab/tokimo-package-hls) | — | William Chan | 2 |
| [tokimo-package-mcp](https://github.com/tokimo-lab/tokimo-package-mcp) | — | William Chan | 2 |
| [tokimo-package-rootfs](https://github.com/tokimo-lab/tokimo-package-rootfs) | [![CI](https://github.com/tokimo-lab/tokimo-package-rootfs/actions/workflows/build.yml/badge.svg)](https://github.com/tokimo-lab/tokimo-package-rootfs/actions/workflows/build.yml) | William Chan | 10 |
| [tokimo-package-sandbox](https://github.com/tokimo-lab/tokimo-package-sandbox) | — | William Chan | 20 |
| [tokimo-package-sdk](https://github.com/tokimo-lab/tokimo-package-sdk) | — | William Chan | 15 |
| [tokimo-package-ssh](https://github.com/tokimo-lab/tokimo-package-ssh) | — | William Chan | 2 |
| [tokimo-package-thumbnail](https://github.com/tokimo-lab/tokimo-package-thumbnail) | — | William Chan | 3 |
| [tokimo-package-universal-archiver](https://github.com/tokimo-lab/tokimo-package-universal-archiver) | — | William Chan | 2 |
| [tokimo-package-vfs](https://github.com/tokimo-lab/tokimo-package-vfs) | [![CI](https://github.com/tokimo-lab/tokimo-package-vfs/actions/workflows/ci.yml/badge.svg)](https://github.com/tokimo-lab/tokimo-package-vfs/actions/workflows/ci.yml) | William Chan | 5 |
| [tokimo-package-web-fetch](https://github.com/tokimo-lab/tokimo-package-web-fetch) | [![CI](https://github.com/tokimo-lab/tokimo-package-web-fetch/actions/workflows/ci.yml/badge.svg)](https://github.com/tokimo-lab/tokimo-package-web-fetch/actions/workflows/ci.yml) | William Chan | 4 |
| [tokimo-package-web-search](https://github.com/tokimo-lab/tokimo-package-web-search) | — | William Chan | 3 |

### Apps

| Repository | CI | Maintainer | Commits |
|---|---|---|---|
| [tokimo-app-apple-music](https://github.com/tokimo-lab/tokimo-app-apple-music) | — | William Chan | 14 |
| [tokimo-app-helloworld](https://github.com/tokimo-lab/tokimo-app-helloworld) | — | William Chan | 10 |
| [tokimo-app-home-assistant](https://github.com/tokimo-lab/tokimo-app-home-assistant) | — | Emil Zhai | 50 |

### Libraries & Tools

| Repository | CI | Maintainer | Commits |
|---|---|---|---|
| [tokimo-ui](https://github.com/tokimo-lab/tokimo-ui) | [![CI](https://github.com/tokimo-lab/tokimo-ui/actions/workflows/ci.yml/badge.svg)](https://github.com/tokimo-lab/tokimo-ui/actions/workflows/ci.yml) | William Chan | 213 |
| [tokimo-perception](https://github.com/tokimo-lab/tokimo-perception) | — | Emil Zhai | 128 |
| [tokimo-bus](https://github.com/tokimo-lab/tokimo-bus) | — | William Chan | 4 |
| [tokimo-viewers](https://github.com/tokimo-lab/tokimo-viewers) | — | Emil Zhai | 2 |
| [tokimo-kvm](https://github.com/tokimo-lab/tokimo-kvm) | — | William Chan | 1 |
| [tokimo-translate](https://github.com/tokimo-lab/tokimo-translate) | — | William Chan | 1 |
| [tokimo-universal-im](https://github.com/tokimo-lab/tokimo-universal-im) | — | William Chan | 4 |
| [kvdb](https://github.com/tokimo-lab/kvdb) | — | William Chan | 1 |

### Private (暂未开源)

| Repository | CI | Maintainer | Commits |
|---|---|---|---|
| bookfinder | [![CI](https://github.com/tokimo-lab/bookfinder/actions/workflows/ci.yml/badge.svg)](https://github.com/tokimo-lab/bookfinder/actions/workflows/ci.yml) | William Chan | 5 |
| cc | — | William Chan | 1 |
| novel-downloader-rs | — | William Chan | 8 |
| paperhunt | — | William Chan | 3 |
| subtitle-aggregator | — | William Chan | 1 |
| tokimo-server | — | William Chan | 0 |

---

<div align="center">

Self-hosted · Privacy-first · Rust-powered

**One system. All your data. One assistant.**

</div>
