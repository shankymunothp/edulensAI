# Paperwise MVP
Mobile-first handwritten exam evaluation prototype.

## Run
1. Install Node.js 20+
2. `npm install`
3. `npm run dev`

## Free deployment
Push this project to GitHub. Create a Cloudflare Pages project from the repository. Build command: `npm run build`; output directory: `dist`. Add `GEMINI_API_KEY` as a server-side Pages Function secret. To enable automatic fallback when Gemini is unavailable, also add `OPENAI_API_KEY`; the fallback uses OpenAI GPT-6.1 Sol through the Responses API. For local Pages development, put both keys in `.dev.vars`. `functions/api/evaluate.ts` serves `/api/evaluate`.

Exam history is stored locally in the current browser (not synced). Uploaded images are sent to Gemini and, if Gemini fails and the optional backup is configured, OpenAI for evaluation. Use non-identifiable sample papers until you have reviewed provider data terms and obtained appropriate consent. AI grading is a prototype and should be reviewed by a human.
