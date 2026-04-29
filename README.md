# Stanford GSB Prep — Alexis (Class of 2028)

Live tracker for course planning, faculty, clubs, the 2-year roadmap, and how registration & advising work at GSB.

**Live URL:** https://romanemperor1.github.io/stanford-prep/

## What's in it

- **Courses (44)** mapped to 9 interest areas (Energy, AI, VC/Entrepreneurship, Search Fund, Consumer/Cosmetics, Tech, Leadership, Sports, Cross-cutting). Top 18 priority courses have full depth — 3-4 sentence description, format, how-to-apply badge, prereqs, insider tip.
- **Faculty (33)** — every entry has a 2-3 sentence bio plus a Notable Works list (papers, books, cases) sourced from official GSB profile pages.
- **Clubs (30)** — each tagged with scope (GSB MBA only / GSB-led broader Stanford / Stanford-wide). Filter by scope or interest area. Expandable cards include "When to join" and signature events.
- **My Plan + Roadmap** (merged) — dynamic 9-quarter timeline (Pre-arrival → Y1 quarters → Summer → Y2 quarters → Post-grad). Each quarter card auto-fills with what's required for that quarter (Y1 core + mandatory items), your starred/planned selections, and Claude's suggested template. Capacity warning when you over-allocate units. Faculty/club selections fall into a "Doesn't fit a quarter" section since they aren't time-bound.
- **How Registration Works** — bidding mechanics, Super Round vs. Open Round, lottery for famous classes (Touchy Feely, Paths to Power, Startup Garage), strategy advice, glossary, deadlines.
- **Advisors** — primer explaining the six advisor types (CMC, Academic Services, Section Faculty, Center Advisors, Leadership Coach, Peer Advisors), advisor timeline (pre-arrival → orientation → quarterly check-ins), plus 17 questions grouped by theme to bring to your meetings.
- **Resources** — grouped into Centers & Institutes / Initiatives & Labs / Conferences & Events / Programs & Fellowships / Tools. Plus a collapsible "Faculty research, papers, books & cases" subsection at the bottom — every notable work from every faculty member, browsable by interest area.

## How to mark items

Click the circle on any card to cycle:

- ☆ empty → ★ Interested → ✓ Planned in my schedule → ☆ empty

Marks save to your browser's localStorage — they persist on this device but don't sync across devices. Marking courses with ★ or ✓ auto-slots them into the My Plan + Roadmap timeline by quarter.

## How to share your plan

Click "📤 Share my plan" in the hero or in My Plan. A URL is copied to your clipboard like `...stanford-prep/#plan=eyJ...` — your selections are encoded directly in the URL. Send to anyone. They see your plan with a banner; their own plan stays untouched.

## How to update the content

Edit [`data.json`](./data.json) — the live site rebuilds in ~30 seconds.

Three ways to edit:

1. **In the browser (easiest):** Click `data.json` above → click the pencil icon (top right of the file) → make changes → "Commit changes"
2. **Full editor in browser:** Visit [github.dev/romanemperor1/stanford-prep](https://github.dev/romanemperor1/stanford-prep) — full VS Code in your browser
3. **Locally:** Clone the repo, edit, commit, push

## Common edits

- **Add a course you heard about:** Copy an existing course block, paste, edit fields. `interest` must match a key in the `interests` array. `quarters` is an array like `["Y2-Autumn", "Y2-Winter"]` — required for the timeline auto-slotting.
- **Add a person to meet:** Copy/paste a faculty block. Add `bio` (2-3 sentences) and `works` (array of objects with title/type/url) to power the expandable.
- **Add a club:** Copy/paste from the `clubs` array. `scope` is one of: "GSB MBA only" / "GSB-led, broader Stanford" / "Stanford-wide". `whenJoin` and `annualEvents` populate the expandable.
- **Add a course's depth fields:** Add `description`, `format`, `apply`, `prereqs`, `tip` — the card auto-shows the "+ Show details" toggle when these exist.
- **Edit the registration explainer:** Edit any field inside the `registration` object.
- **Edit the advisor primer:** Edit `advisorPrimer.types`, `advisorPrimer.timeline`.
- **Edit Y1 core curriculum:** `y1Core` has arrays per quarter (`Y1-Autumn`, `Y1-Winter`, `Y1-Spring`).
- **Add a resource:** Append to `resources` array. `category` controls which group it appears under (Centers & Institutes / Initiatives & Labs / Conferences & Events / Programs & Fellowships / Tools).

## Quarter codes (for the `quarters` array on courses)

Use these exact strings:

- `PRE` — Pre-arrival
- `Y1-Autumn`, `Y1-Winter`, `Y1-Spring` — Year 1 quarters
- `Summer` — between Y1 and Y2
- `Y2-Autumn`, `Y2-Winter`, `Y2-Spring` — Year 2 quarters
- `POST` — Post-graduation

A course offered Y2 fall and winter would be `"quarters": ["Y2-Autumn", "Y2-Winter"]`.

## Apply badge color coding (course cards)

The "Apply: ___" badge picks its color from the text of the `apply` field:

- Red — Mandatory / auto-enrolled
- Orange — Lottery
- Yellow — Application required / pre-qualification
- Purple — Team application
- Green — Open enrollment

## Scope badge color coding (club cards)

- Red — GSB MBA only
- Yellow — GSB-led, broader Stanford
- Blue — Stanford-wide

## If the site shows a "Couldn't load data.json" error

JSON syntax error after your last commit. To fix:

1. Copy the contents of `data.json`
2. Paste into [jsonlint.com](https://jsonlint.com) — it points to the exact line
3. Fix and commit again

Common culprits: missing comma between two items, missing closing brace, smart quotes (use `"`, not `"`).

## File structure

- `index.html` — the page (HTML + CSS + JavaScript). Don't edit unless changing layout.
- `data.json` — all the content. Edit this freely.
- `README.md` — this file.
- `SETUP.md` — first-time deploy instructions.

## Future ideas

When you want to upgrade beyond the current static setup:

- **Cleaner shareable URLs.** Today, share links look like `...stanford-prep/#plan=eyJ2I...`. We can add a URL shortener so they become e.g. `alexis.link/sp/abc123` — same plan, much shorter link. Keeps the site static, just adds a redirect layer.
- **Cross-device sync.** Stars/checkmarks live in your laptop's browser only. To sync across devices (laptop ↔ phone), we'd add a small backend (Supabase, free tier handles thousands of users) plus sign-in. About a weekend of work; the content (data.json) stays on GitHub the same way.
- **Custom domain** (e.g. `prep.alexisroman.com`): GitHub Pages supports custom domains free.
- **Photos instead of the SVG illustration.** When you visit campus, take photos of Hoover Tower, the Main Quad, GSB. Drop them in the repo and we'll swap them into the hero.
- **Make the repo private:** Pages on the free plan requires public repos. To gate the site: GitHub Pro ($4/mo) for private Pages, or put Cloudflare Access in front.
- **Live editing UI:** If editing JSON gets annoying, we can wire up a Google Sheet as the data source so you edit in a spreadsheet UI.

Built April 2026. First GitHub commit ever — nice work, Alexis.
