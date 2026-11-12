# Rohit Mandapalli – Product Manager portfolio

A single-page portfolio site. Plain HTML, CSS and JavaScript. No build step, no dependencies, no tracking.

## Files

| File | What it is |
| --- | --- |
| `index.html` | The whole site: content, styles, icons and the chat assistant |
| `assets/portrait.jpg` | Your photo (600 × 750, colour). Replace it with another JPG of the same name to change it |
| `.nojekyll` | Tells GitHub Pages to serve the files as they are |
| `README.md` | This file. Safe to delete; the site does not use it |

## Publish on GitHub Pages

1. Create a new **public** repository on GitHub.
   - For a site at `https://<username>.github.io/`, name the repository exactly `<username>.github.io`.
   - Any other name gives `https://<username>.github.io/<repository-name>/`.
2. Add these files, keeping the `assets` folder. In the browser: **Add file → Upload files**, then drag in `index.html`, `README.md`, `.nojekyll` and the `assets` folder.
3. Go to **Settings → Pages**. Under **Build and deployment**, choose **Deploy from a branch**, pick `main` and `/ (root)`, then **Save**.
4. Wait a minute or two. The address appears at the top of the Pages settings.

Hidden files such as `.nojekyll` can be missed when dragging folders on some systems. The site works without it, so you can skip it.

## Editing

- **Text:** open `index.html` and search for the section heading (`About`, `Case studies`, `Experience`, and so on). Each case study is one `<article>`.
- **Photo:** replace `assets/portrait.jpg`. Keep it portrait-shaped (4:5) and under about 100 KB.
- **Contact details:** the email address appears in the Contact section and in the chat script (`var EMAIL`).
- **Chat answers:** in the `<script>` at the end of the page, edit the `KB` list. Each entry has keywords (`k`), an answer (`a`), and optional follow-up questions (`next`).

## The chat assistant

It is rule-based. It matches keywords in the question against the answers in `KB`, so it only knows what is in the page. It runs in the visitor's browser and sends nothing anywhere.

To use a live language model instead, host a small server that accepts `POST { "question": "...", "history": [...] }` and returns `{ "answer": "..." }`, then set `CHAT_ENDPOINT` in the script to its address. Keep any API key on that server, never in this page. If the server fails, the page falls back to the built-in answers.

## Design and accessibility

- Follows GOV.UK Design System principles (skip link, landmarks, plain English, strong focus states, 19px body text). It is not affiliated with GOV.UK and does not use its branding.
- Black and white interface. The photo is the only colour.
- Light and dark mode follow the visitor's device setting.
- Tested with automated accessibility checks (axe-core, WCAG 2.2 AA) on desktop, tablet and phone, in light and dark mode. Automated checks do not replace testing with real assistive technology.

## Before you publish

Everything in a public repository is public. That includes your photo, your email address and the full text of the page. Check that your employer is happy for the case studies to be shared in this form.
