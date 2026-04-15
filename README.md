# AXA XL Finance AI Platform (Prototype)

A professional enterprise-style demo web application for an insurance finance AI system.

The prototype simulates how AXA XL finance teams could manage report deadlines, review regulatory change, and use AI-assisted workflows from one controlled operating layer. All AI functionality is mocked and deterministic, so the app can be demonstrated safely without external API keys or live model calls.

## Live Demo

- Public URL: https://axa-xl-ai-platform-niuv.vercel.app
- Deployment target: Vercel
- Data posture: sanitized AXA XL-style demo data with mocked APIs

## Features

- Dashboard with KPI cards, AI insight cards, and upcoming report visibility
- Report Manager with owners, progress, statuses, and mocked AI draft support
- Compliance Engine with regulation review and simulated impact analysis
- AI Assistant with suggested prompts, chat history, loading states, and typed responses
- System Overview with architecture, rollout gates, KPI targets, and adoption tracking
- Realistic mock data including overdue reports, version-conflict scenarios, and regulation-linked impacts

## How To Run

### Requirements

- Python 3.9+
- A modern browser

### Start the app

```bash
python3 server.py
```

Then open [http://127.0.0.1:8000](http://127.0.0.1:8000).

## Deployment

This repository is now aligned to Vercel.

Hosted deployment uses:

- `vercel.json` for rewrites and headers
- `api/index.py` for hosted `/api/*` routes
- `static/` for the frontend shell

See:

- `docs/deployment.md`
- `docs/github_push.md`

## Demo Flow

1. Open `Dashboard` to review KPI cards, AI insights, and upcoming reports.
2. Open `Report Manager` to inspect report details and generate a mocked AI draft summary.
3. Open `Compliance Engine` and select a regulation such as `REG-UK-2026-021` to see impacted reports.
4. Open `AI Assistant` and try a suggested prompt.
5. Open `System Overview` for programme architecture, KPIs, rollout phases, and adoption metrics.

## Project Structure

- `server.py` — local Python server and shared backend logic
- `api/index.py` — Vercel Python API entrypoint
- `vercel.json` — Vercel rewrites and headers
- `data/demo_data.json` — report, bulletin, knowledge, KPI, and adoption demo data
- `data/regulations.json` — regulation dataset used by the compliance experience
- `data/imports/README.md` — import-layer guidance for sanitized extracts
- `data/imports/reports.csv` — sample sanitized report extract
- `data/imports/regulations.json` — sample sanitized regulation extract
- `static/index.html` — enterprise app shell
- `static/styles.css` — enterprise UI styling
- `static/app.js` — frontend rendering and mocked AI interactions
- `docs/architecture.md` — system architecture overview
- `docs/demo_script.md` — presentation walkthrough script
- `docs/deployment.md` — Vercel deployment notes
- `docs/github_push.md` — GitHub push and Vercel handoff steps

## Mock API Endpoints

- `GET /api/bootstrap`
- `GET /api/reports`
- `GET /api/all_reports`
- `GET /api/regulations`
- `POST /api/assistant/query`
- `POST /api/assistant/draft_summary`
- `POST /api/regulations/impact`

## Notes

- The app uses only the Python standard library and browser APIs.
- AI behaviour is mocked intentionally for safe portfolio demos.
- Report and regulation data are file-backed, so changes in `data/` are reflected on refresh.
- The live Vercel deployment is public unless protected in Vercel project settings.

## Shareable Demo Notes

- The repository is prepared as a shareable codebase with mocked APIs and sanitised AXA XL-style data.
- `data/demo_data.json` and `data/regulations.json` act as safe fallback seed data.
- `data/imports/reports.csv` and `data/imports/regulations.json` demonstrate the import/mapping layer for sanitised extracts.
- Owner names and escalation references are generalised to role-based labels for safer sharing.
- No external API keys or live AI integrations are required.

## Importing Sanitised Extracts

Replace the files in `data/imports/` with approved, sanitised CSV or JSON extracts and restart `python3 server.py`. The mocked API routes stay the same, so the UI will continue to work without frontend changes.

## Troubleshooting

- If the UI looks stale after a code change, do a hard refresh in the browser.
- If port `8000` is already in use, stop the existing process and restart `python3 server.py`.
