# AgentParty

AgentParty is a Windows desktop app for running and coordinating multiple AI coding sessions in one workspace.

This repository contains the application source code and the files required to build and verify it. Product planning notes, internal research documents, generated output, and local runtime data are intentionally kept outside this repository.

## Features

- Run Claude Code, Codex, Cursor, and supported provider models side by side
- Organize sessions as parties, members, tab groups, and split workbench panels
- Let members message, interrupt, and delegate work to one another
- Review commands, file changes, approvals, and Message Gate decisions in the UI
- Run members on Windows, WSL, or a registered SSH server
- Connect subscription accounts and API-key providers including OpenRouter and B.AI
- Drive user-facing capabilities through the local automation API

## Requirements

- Windows 10 or later
- Node.js 22 or later
- npm
- At least one supported coding-agent CLI and its required account or API key

## Development

```powershell
npm install
npm run build
npm run start
```

For renderer hot reload:

```powershell
npm run dev
npm run start:dev
```

## Build a Windows package

```powershell
npm run dist:win
```

Build output is written to `release/` and is not committed.

## Project layout

- `src/core` — harness adapters, routing, model, and cost logic
- `src/main` — Electron main process, persistence, sessions, SSH, and automation API
- `src/preload` — the renderer's IPC bridge
- `src/renderer` — React desktop UI
- `src/shared` — contracts shared across processes
- `guide/knowledge` — runtime knowledge used by the in-app guide
- `scripts` — build, packaging, verification, and test utilities
- `build` — installer and application icon assets

## Releases

Windows installers and portable builds are published in the [AgentParty releases repository](https://github.com/JioBani/AgentParty-releases/releases).

## License

No license has been selected for this public source repository yet. Until a license is added, copyright law reserves all rights to the copyright holder.
