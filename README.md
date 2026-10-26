# Paperwise MVP
Mobile-first handwritten exam evaluation prototype.

## Run
1. Install Node.js 20+
2. `npm install`
3. `npm run dev`

## Free deployment
Push this project to GitHub. Create a Cloudflare Pages project from the repository. Build command: `npm run build`; output directory: `dist`. Add `GEMINI_API_KEY` as a server-side Pages Function secret. If Gemini 3.8 Flash is unavailable, the evaluator tries Gemini 3.5 Flash-Lite, then OpenRouter's free model router, which selects an available free model that supports image understanding. Add `OPENROUTER_API_KEY` as a server-side Pages Function secret to enable the OpenRouter backup. If those fail, it can use OpenAI GPT-6.1 Sol through the Responses API when `OPENAI_API_KEY` is configured. For local Pages development, put the keys you have in `.dev.vars`. `functions/api/evaluate.ts` serves `/api/evaluate`.

The OpenRouter free endpoint has request limits and no service-level guarantee. Its provider may log submitted data and use it to improve its services, so do not submit identifiable student papers unless you have reviewed the current provider terms and have appropriate consent.

Exam history is stored locally in the current browser (not synced). Uploaded images are sent to Gemini and, after a Gemini failure, to configured OpenRouter and OpenAI backups as needed. Use non-identifiable sample papers until you have reviewed provider data terms and obtained appropriate consent. AI grading is a prototype and should be reviewed by a human.
