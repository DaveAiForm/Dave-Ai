# Dave Ai Metal Buildings

A simple static web demo for collecting metal building project details through a guided chat.

## Features
- Intake form (name, contact, ZIP, timeframe)
- Guided questions for key project parameters (size, eave height, roof pitch, openings, insulation, skylights)
- Chat powered by Groq AI (via Netlify function) with fallback to simulated responses
- Specific canned answers for common questions (phone, email, etc.)
- Sends collected lead + project data via Formspree

## Local Testing
Just open `index.html` in any browser.

## Deployment (GitHub + Netlify)
1. Push code to your GitHub repo.
2. In Netlify: "New site from Git" → select the repo.
3. Build settings:
   - Base directory: (leave blank)
   - Build command: (leave blank)
   - Publish directory: `.`
4. Deploy.
5. Go to Site configuration → Environment variables and add:
   - Key: `GROQ_API_KEY`
   - Value: your Groq key
6. (Optional) Redeploy.

Once the site is connected this way, every push to the main branch on GitHub will automatically trigger a new deploy on Netlify.

## Notes
- **Groq key**: You can (and are allowed to) use the **exact same key** for multiple copies or rebranded versions. Set the same `GROQ_API_KEY` env var on the new Netlify site. No new key required.
- Note: All usage shares the same Groq quota/rate limits.
- If you prefer separation (different clients, easier to revoke later), you can create a new key in the Groq console.
- **Formspree**: The endpoint is per-form. Reuse it or create a new one.
- Rebranding: Edit text in `index.html` (search for "Dave Ai", titles, contact info, etc.). Update logo if needed.
- Netlify function code does not need changes.