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

<div align="center">

Self-hosted · Privacy-first · Rust-powered

**One system. All your data. One assistant.**

</div>
