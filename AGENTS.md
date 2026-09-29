# Base44 Dev Environment

## Project Overview
This is a static single-page website (Snapchat-inspired landing page) consisting of a single `index.html` file with inline CSS and JavaScript. No build step, no backend, no dependencies.

## Running the App
```bash
docker compose -f docker-compose.base44.yml up -d
```
Serves `index.html` via nginx:alpine on host port 3000.

## Notes
- The `index.html` was brought over from the `feature/add-snapchat-webpage` branch; the initial commit only contained a README.
- The repo root directory has restrictive permissions (700), so only `index.html` is bind-mounted (not the whole directory) to avoid nginx 403 errors.
- Edits to `index.html` are reflected immediately (nginx serves the file directly from the bind mount).
- No secrets or external services are required.
