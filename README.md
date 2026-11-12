# Bloom English — AI-ready edition

## Free public deployment with Netlify + Gemini

1. Create a free Gemini API key at https://aistudio.google.com/api-keys. Do not share the key.
2. Create a GitHub account if needed. Create a repository and upload all files from this folder, preserving `netlify/functions/review.mjs` and `netlify.toml`. Do NOT upload a key.
3. Sign in at https://app.netlify.com/. Select Add new project > Import an existing project > GitHub, and choose your repository.
4. Build settings: no build command; publish directory `.` (root). Deploy.
5. In Netlify project configuration > Environment variables, create `GEMINI_API_KEY` with your key. Redeploy your site to activate the new variable.
6. Open the generated `.netlify.app` address, go to My diary, enter at least five words, select Review my writing. When the connection works, you'll get AI-specific corrections and a question.

The HTML-only demo can be hosted through Netlify Drop, but this AI version uses a serverless function and should be deployed via GitHub import (or Netlify CLI). The site falls back to simple demo feedback when the AI is unavailable.

## Safety and limitations
- This is a prototype, not a production-ready children's service. Public backend endpoints can be abused. Add rate limiting and bot protections before wider sharing.
- Browser storage is per device, not an account. No syncing or automatic emailed reports.
- Diary text and the limited context (age/grade/interests) are sent to Google's API when the AI feature is used. Free-tier Gemini usage may be used to improve Google's products. Avoid identifiable children's data; obtain relevant parent/guardian consent and check privacy rules before involving real children.
- Free usage is subject to quotas and Netlify limits. Don't enable paid billing if you wish to remain strictly free.
