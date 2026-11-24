# OpenGames Architecture

C4 architecture model for the OpenGames platform, built with [LikeC4](https://likec4.dev/).

## Overview

The model covers the following systems and infrastructure:

- Browser client
- Node.js application with a React frontend and Fastify web server
- Node.js game runtime
- PostgreSQL database
- Valkey cache
- Amazon S3 bucket
- SMTP server

It documents HTTP, Socket.IO, and Colyseus/WebSocket communication, including the proxying of gameplay connections between the browser, application, and runtime.

## Views

- `index`: Container landscape and protocol boundaries
- `context`: System context with actors and external services
- `browser`: Two-origin browser boundary (`play.*` shell vs. `games.*` iframe & engines)
- `app`: Detailed view of the 9 application modules
- `runtime`: Game server runtime components and boundaries
- `valkey`: Valkey coordination namespaces and callers
- `ecosystem`: Plugin authoring, SDKs/CLI, GitHub catalogs/releases, and GHCR images
- `gameplay_proxy`: Dynamic gameplay connection proxy flow
- `flow_install`: Sequence flow for plugin installation and pool activation
- `flow_join`: Sequence flow for match join and targeted room routing
- `flow_restore`: Sequence flow for crash recovery and snapshot restore
- `deploy_docker`: Single-host Docker Compose deployment
- `deploy_kubernetes`: Multi-replica Kubernetes deployment

The sources are split across `specification.c4`, `model*.c4`, `views.c4`, `flows.c4`, and `deployment.c4`.

## Requirements

- Node.js 22.23.3 or newer
- npm

## Getting Started

```bash
npm install
npm run dev
```

Open http://localhost:5173/ to browse the architecture diagrams.

## Commands

```bash
npm run dev       # Start the interactive local website
npm run build     # Build the static site into dist/
npm run validate  # Validate the LikeC4 model
```

The LikeC4 project name and title are configured in `likec4.config.json`.
