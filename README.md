# Paperwise MVP
Mobile-first handwritten exam evaluation prototype.

## Run
1. Install Node.js 20+
2. `npm install`
3. `npm run dev`

## Free deployment
Push this project to GitHub. Create a Cloudflare Pages project from the repository. Build command: `npm run build`; output directory: `dist`. Add `GEMINI_API_KEY` as a server-side Pages Function secret. `functions/api/evaluate.ts` serves `/api/evaluate`.

Exam history is stored locally in the current browser (not synced). Uploaded images are sent to Gemini for evaluation. Use non-identifiable sample papers until you have reviewed provider data terms and obtained appropriate consent. AI grading is a prototype and should be reviewed by a human.
