<div align="center">

# Tokimo

### Your AI agent. Your hardware. Your rules.

A self-hosted personal assistant assembled from building blocks you own and can swap out.<br>
No vendor account. No cloud lock-in. No black box.

</div>

---

## The problem with everyone else's "AI agent"

Look at what's actually shipping in 2025:

| Project | What it really is |
|---|---|
| **OpenAI Codex / ChatGPT Agent** | Hardwired to GPT. You can't swap the model. Your code, your prompts, your tool calls — all routed through OpenAI's servers. |
| **Anthropic Claude Code** | Hardwired to Claude. Beautiful CLI, single vendor. The day Anthropic changes pricing or policy, your workflow changes with it. |
| **Cursor / Windsurf / GitHub Copilot** | Closed-source IDE shells over a proprietary cloud. Your model, your context, your code go through their pipeline. |
| **Most "AI desktop" startups** | A thin wrapper around `openai` SDK + LangChain + a vector DB SaaS + a frontend framework. When any vendor changes, the product breaks. |

The pattern is identical: **their model, their cloud, their TOS, their roadmap**. The agent is "yours" right up until the bill arrives, the model gets nerfed, the API breaks, the company pivots, or the policy changes. Migration cost is total — when you leave, you leave with nothing.

## What Tokimo is instead

**Pure in-house. Pure open source. Zero vendor lock-in.**

- Not a wrapper around someone's SDK — the agent loop, the tool dispatcher, the sandbox, the VFS, the desktop shell are all written from scratch in Rust + TypeScript.
- Not married to any model — point it at OpenAI, Anthropic, DeepSeek, Gemini, or your own Ollama box. Switch mid-conversation.
- Not dependent on any SaaS — no LangSmith, no Pinecone, no Vercel AI, no third-party "agent platform". One container, one Postgres, done.
- Not a closed product — every line of code is on GitHub, every protocol is documented, every layer is replaceable.

Tokimo is built for the person who asks: *"why does my AI agent need a corporate sponsor?"*

---

## Built like LEGO

Every part of the stack is a swappable block:

| Block | Pick anything | You control |
|---|---|---|
| **Model** | OpenAI · Anthropic · DeepSeek · Gemini · **Ollama (local)** · any OpenAI-compatible endpoint | API key, base URL, routing rules, per-conversation override |
| **Tools** | 20+ built-in (Bash, Read/Write/Edit, Grep, Glob, WebFetch, DispatchAgent, …) + your own | Tool registry is open — disable any, add any |
| **Skills** | Project-local skill packs · global skills · `Skill` tool for on-demand load | Drop a folder in, the agent picks it up |
| **MCP servers** | Any Model Context Protocol server (filesystem, GitHub, Slack, custom) | Configure in settings, instantly available to every agent |
| **Storage** | Local · SFTP · SMB · FTP · S3 · WebDAV · NFS · Aliyundrive · Baidu · 115 · 189 · Quark | Unified VFS API; add a driver, every app sees it |
| **IM bridge** | Feishu · DingTalk · Discord · Telegram · Slack · custom webhook | Talk to your agent from anywhere |
| **Sandbox** | Bash · PowerShell · git worktree isolation · container-bounded | You set the safety rules, you control the override |
| **Memory** | PostgreSQL + pgvector | Your DB. Your backups. Dump it, move it, query it. |
| **Front-end shell** | Browser-rendered desktop OS — every app is a window with typed APIs | Open-source UI; replace any panel, add your own apps |

Every block has a typed API contract. Every contract is documented. Nothing is closed off. **If you don't like a piece, replace it.**

---

## Full control, end to end

| You own | Tokimo guarantees |
|---|---|
| **The model.** Pick frontier API, pick Ollama, pick a fine-tune. Switch mid-conversation. | No hardcoded provider, no usage telemetry, no rate-limit handcuffs. |
| **The data.** Your photos, files, chats, memories live in PostgreSQL + a Docker volume. | Zero cloud upload. Zero outbound calls except the LLM endpoint you choose. |
| **The agent's behavior.** System prompt, tool set, memory policy, sandbox rules — all configurable. | No "trust the platform" black boxes. Every prompt and tool call is logged and auditable. |
| **The runtime.** Single Docker container. Runs on a NAS, VPS, Raspberry Pi, homelab box. | One `docker compose up`. No SaaS dependency. Works air-gapped. |
| **The exit.** Walk away with your DB dump and your data volume — that's the whole product state. | No vendor lock-in. No format prison. No "export limited to last 90 days". |

---

## What it can do today

Tokimo started as a personal media + knowledge OS. All of those apps are still here, exposed to the agent through typed APIs as native tools:

- **Media** — Movies / TV / anime: subscribe, download, scrape (TMDB · Bangumi · Douban), transcode (FFmpeg), stream (HLS). Plex / Emby / Jellyfin compatible.
- **Photos** — Local face clustering, OCR, geo-tagging, CLIP semantic search ("sunset photos with Sarah from 2024"). All ONNX-local, zero cloud upload.
- **Music** — Streaming, synced lyrics, visualizer.
- **Docs** — Real-time collaborative editor, version history, whiteboard.
- **Terminal** — Multi-session SSH client.
- **Database browser** — PostgreSQL · MySQL · SQLite · MongoDB · Oracle · ClickHouse · Elasticsearch.
- **Email** — IMAP IDLE push, multi-account.
- **Knowledge** — Academic papers (OpenAlex · CrossRef · arXiv), books (Libgen), web novels.
- **Workflow** — Cron + Rhai scripting + JSONPath filters.

The agent doesn't *use* a cloud service to access these — they're part of the same process, sharing the same database, the same VFS, the same window manager. You use them as apps. The agent uses them as tools. **One system, one source of truth.**

---

## Architecture

Rust (Axum + Tokio) backend · React 19 + Tailwind v4 frontend · PostgreSQL 16 + pgvector · ONNX Runtime · WebAssembly · WebSocket streaming.

End-to-end type safety: Rust struct → ts-rs → TypeScript DTO → React Query.

```bash
docker compose up -d
```

One container. One port. One volume. Everything else is yours.

---

## Repositories

| Repo | What it is |
|---|---|
| **[tokimo](https://github.com/tokimo-lab/tokimo)** | Main monorepo — agent engine, desktop shell, all apps |
| **[tokimo-package-vfs](https://github.com/tokimo-lab/tokimo-package-vfs)** | Async unified VFS (local + SFTP/FTP/SMB/S3/NFS/WebDAV) with a handwritten NTLMv2 SMB client |

---

<div align="center">

Self-hosted · Vendor-neutral · Composable · Auditable

**Your agent. Your hardware. Your rules.**

</div>
