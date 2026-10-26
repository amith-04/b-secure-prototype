# B-Secure (Round 2 prototype)

Static site (`index.html`) plus one serverless function (`api/check.js`). No build step.

## Run / deploy
1. Push this folder to GitHub (the `.env` file is git-ignored; never commit keys).
2. Import the repo in Vercel (framework: Other). It serves `index.html` and detects `/api`.
3. Vercel > Project > Settings > Environment Variables: add `GEMINI_API_KEY` (from Google AI Studio). Optional: `GEMINI_MODEL` (default `gemini-2.5-flash`; confirm it exists in the Gemini docs).
4. Redeploy, then test the public URL in a private window.
Local test: `npx vercel dev` with a `.env` file containing `GEMINI_API_KEY=...`.

## What works
Three roles (Creator, Manager, Admin), rule engine, AI analysis via `/api/check`, evidence-linked findings, human decisions with override reasons, audit log, insights.

## Known limits (disclose in the submission)
- Roles are a switcher, not real login. Data lives in the browser's local storage (no shared database).
- Rate limiting is in-memory and best-effort. Set a spending cap in Google AI Studio.
- Free-tier Gemini content may be used by Google to improve products. Use fictional content in the demo.
- Optional font: place `InstrumentSerif-Regular.woff2` in `/fonts` to self-host it. Otherwise a system serif is used.
