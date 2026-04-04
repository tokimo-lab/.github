<div align="center">

# Tokimo

### The AI-Native Cloud Desktop OS

**Your always-on personal assistant, living inside a cloud desktop.**

Not another chatbot. Not another CLI tool.<br>
A full operating system — where your AI assistant works, thinks, and shows you the results in real time.

</div>

---

### The Problem

**Chatbots** can talk, but can't act. **CLI Agents** can act, but you can't see — they work in a black box, and you have to check ten different apps to verify the results.

Your data is scattered everywhere. Files on the NAS. Photos on your phone. Meeting minutes in Slack. Media in Plex. Nothing talks to anything.

### The Answer

**Put the AI assistant inside a full graphical operating system.**

It's not a black box anymore. It lives in a desktop with windows, a taskbar, and a file manager. Everything it does — you see it in real time by opening a browser.

Connect it to Feishu, DingTalk, Discord, Telegram, Slack. Send a message from your phone. The assistant works on your cloud desktop silently. Open the browser — it's all done.

**The power of CLI + the visibility of GUI. One system, all your data, one assistant.**

---

### What Sets It Apart

🧠 **Personal Data Hub** — Files, media, knowledge, terminals, databases, AI conversations — all in one system. Work, entertainment, research, infrastructure — nothing lives in silos anymore.

🤖 **AI With Eyes** — Not a chatbot with a UI. The AI lives inside a windowed desktop OS. It opens windows, moves files, renders charts, plays media. Visualization is its native ability.

💬 **Always-On Assistant** — Hook into any IM. Your assistant is 7×24 on your cloud desktop, ready to act. Open the browser to see everything it's done.

⚡ **Rust-Powered** — Zero GC pauses, C-level performance. Local ONNX inference (OCR, image search, face recognition, speech-to-text). Runs on a NAS or a Raspberry Pi.

🔒 **Privacy-First** — 100% on your server. Works fully offline. One-line Docker deploy.

---

### Real-World Scenarios

🎬 **Home Media** — Auto-subscribe, download, organize, scrape metadata, transcode, stream. Movies, music, photos, novels. Compatible with Plex / Emby / Jellyfin.

💼 **Remote Work** — SSH terminals, Docker management, database queries, file operations across NAS/cloud — all in browser windows. AI summarizes meeting notes from Feishu/Slack into your knowledge base.

📸 **Photo Management** — Import from any storage → AI tags faces, extracts text (OCR), geolocates → search: "photos from the beach last summer". Zero cloud upload.

📚 **Research** — Search papers on OpenAlex/arXiv, read PDFs in-browser, AI summarizes. Same workflow for novels, e-books, technical docs.

🤖 **Personal AI** — "Organize yesterday's downloads." "What did we discuss about the migration plan last week?" — your assistant has memory, context, and can act on the desktop.

---

### Architecture

Rust (Axum) · React 19 · PostgreSQL · ONNX Runtime · WebAssembly

End-to-end type safety: Rust → ts-rs → TypeScript → React Query. Change once, updates everywhere.

```bash
docker compose up -d    # One-line deploy
```

---

### Open Source

| Repository | Description |
|------------|-------------|
| [tokimo-ffmpeg](https://github.com/tokimo-lab/tokimo-ffmpeg) | High-performance media transcoding via Rust FFI |
| [tokimo-universal-archiver](https://github.com/tokimo-lab/tokimo-universal-archiver) | Universal archive library (ZIP/TAR/7Z/RAR/ZST) |
| [tokimo-universal-im](https://github.com/tokimo-lab/tokimo-universal-im) | Enterprise IM Rust SDK — DingTalk, WeCom, Feishu |
| [tokimo-translate](https://github.com/tokimo-lab/tokimo-translate) | High-performance CN↔EN translation (GGUF + llama.cpp) |
| [kvdb](https://github.com/tokimo-lab/kvdb) | Embedded key-value database in Rust |

---

<div align="center">

**Self-hosted · Privacy-first · Rust-powered**

One system. All your data. One assistant.

</div>
