<h1 align="center">miii — Local AI Coding Agent for Your Terminal</h1>

<p align="center">
  <strong>The open-source, offline alternative to Claude Code, Cursor, and GitHub Copilot.</strong><br>
  A private AI pair programmer that runs on your machine with Ollama — no API keys, no cloud.<br>
  Private by default. Free forever. Works offline.
</p>

<p align="center">
  <a href="https://www.npmjs.com/package/miii-agent"><img src="https://img.shields.io/npm/v/miii-agent" alt="miii-agent npm version"></a>
  <a href="LICENSE"><img src="https://img.shields.io/badge/license-MIT-blue.svg" alt="MIT license"></a>
  <a href="https://nodejs.org"><img src="https://img.shields.io/badge/node-%3E%3D18-brightgreen" alt="requires Node 18 or newer"></a>
  <a href="https://ollama.com"><img src="https://img.shields.io/badge/powered%20by-Ollama-black" alt="powered by Ollama"></a>
</p>

<p align="center">
  <img src="demo3.gif" alt="miii local AI coding agent running in a terminal, powered by Ollama">
</p>

<p align="center">
  🔒 <strong>100% local</strong> — your code never leaves your machine &nbsp;·&nbsp;
  💸 <strong>Free</strong> — no API keys, no per-token billing &nbsp;·&nbsp;
  ⚡ <strong>Offline</strong> — runs on your own GPU
</p>

## Install

```bash
ollama pull qwen2.5-coder:14b   # any coding model works
npm i -g miii-agent
miii
```

Windows: `irm https://raw.githubusercontent.com/maruakshay/miii-cli/main/install.ps1 | iex`

## Then just talk to it

```
> refactor the auth module to use async/await
> @src/server.ts add rate limiting to all POST routes
> why are my tests failing in utils/parser.ts
```

miii reads your files, writes the code, runs your tests, and fixes what breaks — planning before it acts, and verifying after.

## Why local-first?

|            | Cloud agents          | **miii**                     |
|------------|-----------------------|------------------------------|
| Your code  | Sent to a third party | Never leaves your machine    |
| Cost       | Per-token billing     | Free — runs on your hardware |
| Setup      | API keys, accounts    | `npm i -g miii-agent`        |
| Offline    | No                    | Yes                          |
| Latency    | Network + queue       | Your GPU only                |

## Key Features

- **🧠 Model-Aware** — Repairs malformed tool calls from small models and optimizes prompts for your context window.
- **📋 Plan Mode** — `/plan` makes the session read-only. miii researches and proposes a plan before touching any code.
- **🔒 Permission-Gated** — You approve every write or command. Saved rules persist in `.miii/permissions.json`.
- **🧩 Subagents** — Delegated `task` loops for search or specialized jobs, preserving the main context window.
- **🔌 MCP Support** — Connect to GitHub, Postgres, or internal services via Model Context Protocol.
- **⟲ /rewind** — Undo agent changes and rewind the conversation to any previous turn.
- **🖥️ Headless** — Use `miii -p "prompt"` for scripts, CI, or piping git diffs.

---

**Picking a model:** 8GB VRAM → `qwen2.5-coder:7b` · 16–24GB → `qwen2.5-coder:14b` (sweet spot) · 48GB+ → `qwen2.5-coder:32b`.

MIT © [maruakshay](https://github.com/maruakshay)
