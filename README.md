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

- `index`: Overall architecture and relationships
- `app`: Detailed view of the application components
- `gameplay_proxy`: Dynamic gameplay connection flow

The sources are defined in `model.c4` and `views.c4`.

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
