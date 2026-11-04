# Card City website — instructions for AI assistants (ChatGPT / Codex)

This repo is the Card City website (cardcity.com). It is a plain static site: `index.html`, one stylesheet, one script, and images. There is no build step. Every change merged into `main` is published automatically by Netlify within about a minute.

## Updating the payout guide (most common task)

The payout guide is ONE file: `images/payout-guide.pdf`.

To update it:
1. Replace `images/payout-guide.pdf` with the new PDF the user provides. Keep the exact same file name and folder.
2. Do NOT rename the file, add a date or version to the name, or add a second copy.
3. Do NOT change any links in `index.html`. Both links on the site (the "Payout Guide" menu item and the "see our full payout guide" link) already point to `/images/payout-guide.pdf`, so they show the new guide automatically.
4. Confirm the new file is a real PDF (it opens and is not empty) before committing.
5. Commit message: `Update payout guide (<month year>)`.

The short link `cardcity.com/payout-guide` also points to this file (set in `netlify.toml`).

## Making website edits

- Almost all content lives in `index.html`: hours, phone numbers, addresses, the retailer list, about text, community logos, team members.
- Store hours and phone numbers appear in more than one place (the Locations section AND the Contact section). When changing one, search the whole file and update every copy.
- New images go in `images/` (or the matching subfolder such as `images/partners/` or `images/community/`). Use lowercase, hyphenated file names with no spaces.
- Keep the existing look: do not change `stylesheets/app-b887648a.css` or `javascripts/all-ab9b3b57.js` unless the user specifically asks for a design or behavior change.
- Keep changes small and limited to what the user asked for. Do not reformat or "clean up" unrelated parts of the file.

## Do not touch

- The three contact forms: keep `data-netlify="true"`, the `form-name` hidden inputs, and the `bot-field` honeypot. Without them, form submissions stop arriving.
- `netlify.toml`, unless the user asks about redirects or caching.
- The Google Maps script tag and map code at the bottom of `index.html`.

## Before you finish

- Describe in plain language what changed, so the user can review the pull request before merging.
- After merge, the live site updates on its own. Remind the user to check https://cardcity.com once it's published.
