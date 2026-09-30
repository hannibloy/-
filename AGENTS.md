# AGENTS.md

## Project overview

Single static HTML file (`canva-dashboard.html`) — a Hebrew (RTL) Canva project dashboard with embedded CSS and vanilla JavaScript. No backend, no build step, no dependencies.

## Running

```bash
docker compose -f docker-compose.base44.yml up -d
```

Served by nginx:alpine on host port 3000. The repo is bind-mounted read-only; nginx serves `canva-dashboard.html` as the index.

## Editing

Edits to `canva-dashboard.html` are served immediately by nginx (no rebuild). Call `reload_preview` after edits so the browser picks up changes — there is no HMR for plain static HTML.

## Verification

- `curl -s http://localhost:3000/ | head -5` should return the HTML doctype.
- No external credentials or secrets are required.
