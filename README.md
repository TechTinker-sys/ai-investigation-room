# 🕵️ AI Investigation Room

An AI-powered web app where Gemini generates a brand-new mystery each time. Examine the evidence, interrogate AI-driven suspects, and accuse the culprit.

## How it works
- `POST /api/generate` asks Gemini for a structured case (suspects, evidence, hidden culprit). The full case, including the answer, stays on the server.
- `POST /api/interrogate` role-plays a suspect with Gemini. The guilty suspect lies and cracks under contradicting evidence; innocents answer honestly.
- `POST /api/accuse` checks your accusation and reveals the solution.

## Tech stack
Node.js, Express, vanilla JS frontend, Google Gemini API.

## Setup
1. Install Node.js 18 or newer.
2. Get a free Gemini API key from https://aistudio.google.com/apikey.
3. Clone this repo, then:
   ```bash
   npm install
   cp .env.example .env   # add your GEMINI_API_KEY
   export $(cat .env | xargs) && npm start
   ```
4. Open http://localhost:3000.

## Deployment (Render)
Create a Web Service from this repo: build command `npm install`, start command `npm start`, and add `GEMINI_API_KEY` (and optionally `GEMINI_MODEL`) as environment variables.

## Notes
Cases are stored in server memory, so a restart clears active games.
