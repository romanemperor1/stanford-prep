# Stanford GSB Prep — Alexis (Class of 2028)

Live tracker for course planning, faculty, clubs, the 2-year roadmap, and how registration works at GSB.

**Live URL:** https://romanemperor1.github.io/stanford-prep/

## What's in it

- **Courses** — 44 mapped to interest areas (Energy, AI, VC/Entrepreneurship, Search Fund, Consumer/Cosmetics, Tech, Leadership, Sports, Cross-cutting). Top 18 have full depth: description, format, how-to-apply badge (Lottery / Open / Mandatory / Application), prereqs, insider tip.
- **Faculty** — 33 people to meet, with what they teach and why they're worth meeting.
- **Clubs** — 16 GSB clubs mapped to interests.
- **2-Year Roadmap** — suggested quarter-by-quarter shape of two years.
- **How Registration Works** — bidding mechanics, Super Round vs. Open Round, lottery for famous classes (Touchy Feely, Paths to Power, Startup Garage), strategy advice, glossary, deadlines.
- **My Plan** — everything you've marked, with share-as-link and copy-as-text.
- **Advisor Questions** — 17 questions to bring to Academic Services / CES / Doerr / your faculty advisor.
- **Resources** — centers, programs, joint degrees, tools.

## How to mark items

Click the circle on any card to cycle:

- ☆ empty → ★ Interested → ✓ Planned in my schedule → ☆ empty

Marks save to your browser's localStorage — they persist on this device but don't sync across devices.

## How to share your plan

Click "📤 Share my plan" in the hero or in the My Plan tab. The site copies a URL to your clipboard like `...stanford-prep/#plan=eyJ...` — your selections are encoded directly in the URL. Send the link to anyone. They see your plan with a banner; their own plan stays untouched.

## How to update the content

Edit [`data.json`](./data.json) — the live site rebuilds in ~30 seconds.

Three ways to edit:

1. **In the browser (easiest):** Click `data.json` above → click the pencil icon (top right of the file) → make changes → scroll down → "Commit changes"
2. **Full editor in browser:** Visit [github.dev/romanemperor1/stanford-prep](https://github.dev/romanemperor1/stanford-prep) — opens VS Code in your browser
3. **Locally:** Clone the repo, edit, commit, push

## Common edits

- **Mark a course you took (in the data, not just the marker):** Add `"taken": true` to that course entry.
- **Add a course you heard about:** Copy an existing course block, paste, edit the fields. The `interest` field MUST exactly match one of the keys in the `interests` array.
- **Add a person to meet:** Copy/paste a faculty block.
- **Add a club:** Same — copy/paste from the `clubs` array.
- **Update the roadmap after registration:** Edit any quarter's `body` or `notes`.
- **Add a course's depth fields:** Add `description`, `format`, `apply`, `prereqs`, `tip` to any course. The card auto-shows the "+ Show details" toggle when these exist.
- **Edit the registration explainer:** Edit any field inside the `registration` object — sections, items, glossary, deadlines.

## Apply badge color coding

The "Apply: ___" badge on course cards picks its color from the text:

- Red — Mandatory / auto-enrolled
- Orange — Lottery
- Yellow — Application required / pre-qualification
- Purple — Team application
- Green — Open enrollment

## If the site shows a "Couldn't load data.json" error

JSON syntax error after your last commit. To fix:

1. Copy the contents of `data.json`
2. Paste into [jsonlint.com](https://jsonlint.com) — it points to the exact line
3. Fix and commit again

Common culprits: missing comma between two items, missing closing brace, smart quotes (use `"`, not `"`).

## File structure

- `index.html` — the page itself (HTML + CSS + JavaScript). Don't edit unless you're changing layout.
- `data.json` — all the content. Edit this freely.
- `README.md` — this file.
- `SETUP.md` — first-time deploy instructions.

## Future ideas

When you want to upgrade beyond the current static setup:

- **Cleaner shareable URLs.** Today, share links look like `...stanford-prep/#plan=eyJ2I...`. We can add a URL shortener so they become e.g. `alexis.link/sp/abc123` — same plan, much shorter link. Keeps the site static, just adds a redirect layer.
- **Cross-device sync.** Today your stars/checkmarks live in your laptop's browser only. To make them follow you across devices (laptop ↔ phone), we'd add a small backend (Supabase, free tier handles thousands of users) plus sign-in. About a weekend of work; the content (data.json) stays on GitHub the same way.
- **Custom domain** (e.g. `prep.alexisroman.com`): GitHub Pages supports custom domains free. Set up later via Settings → Pages → Custom domain.
- **Make the repo private:** Pages on the free GitHub plan requires public repos. To gate the site, you'd need GitHub Pro ($4/mo) and use a private repo, OR put Cloudflare Access in front.
- **Live editing UI:** If editing JSON gets annoying, we can wire up a Google Sheet as the data source so you edit in a spreadsheet UI.

Built April 2026. First GitHub commit ever — nice work, Alexis.
