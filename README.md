# Arogya AI – Disease Prediction & Healthcare Assistance System

AD4V71 Machine Learning Operations project · Chennai Institute of Technology
Team: Rakshitha L (24AD0232), Renuga M (24AD0237) · Section D

Arogya AI is a web prototype with four connected modules:

| Module | What it does |
|---|---|
| Symptom Checker | Plain-language symptoms → possible conditions, risk level, interactive red-flag triage |
| AI Doctor Chat | Conversational health guidance powered by Claude (guidance only, not diagnosis) |
| Hospital & Doctor Finder | Live location / typed place → nearby hospitals & clinics (OpenStreetMap: Nominatim + Overpass) |
| First-Aid Guide | Severity-tiered first-response steps, 108 emergency integration |

## Run locally (VS Code)

```bash
git clone <your-repo-url>
cd arogya-ai
cp .env.example .env        # then paste your Anthropic API key into .env
node server.js
```
Open http://localhost:3000

Without an API key, everything except AI Doctor Chat still works.

## Deploy (free live link with Vercel)

1. Push this repo to GitHub.
2. vercel.com → Add New Project → import the repo.
3. Settings → Environment Variables → add `ANTHROPIC_API_KEY`.
4. Deploy. `api/chat.js` runs as the secure proxy.

## Structure

```
index.html     front-end (all four modules)
server.js      local dev server + /api/chat proxy
api/chat.js    same proxy as a Vercel serverless function
.env.example   copy to .env (never commit .env)
```

## Disclaimer
AI-generated guidance, not a medical diagnosis. In an emergency call 108.
