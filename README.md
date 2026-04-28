# Stanford GSB Prep — Alexis (Class of 2028)

Live tracker for course planning, faculty to meet, and the 2-year roadmap.

**Live URL:** https://romanemperor1.github.io/stanford-prep/

## How to update the content

Edit [`data.json`](./data.json) — the live site rebuilds in ~30 seconds.

You can edit it three ways:

1. **In the browser (easiest):** Click `data.json` above → click the pencil icon (top right of the file) → make changes → scroll down → "Commit changes"
2. **Full editor in browser:** Visit [github.dev/romanemperor1/stanford-prep](https://github.dev/romanemperor1/stanford-prep) — opens VS Code in your browser
3. **Locally:** Clone the repo, edit, commit, push

## Common edits

- **Mark a course you've taken:** Add `"taken": true` to that course entry
- **Add a course you heard about:** Copy an existing course block, paste, edit the fields
- **Add a person to meet:** Same — copy/paste a faculty block
- **Update the roadmap after registration:** Edit any quarter's `body` or `notes`

## If the site shows a "Couldn't load data.json" error

That means the JSON has a syntax error. To fix:
1. Copy the contents of `data.json`
2. Paste into [jsonlint.com](https://jsonlint.com)
3. It will point to the exact line — usually a missing comma or quote
4. Fix and commit again

## File structure

- `index.html` — the page itself (don't edit unless you want to change the layout)
- `data.json` — all the content (edit this freely)
- `README.md` — this file

Built April 2026.
