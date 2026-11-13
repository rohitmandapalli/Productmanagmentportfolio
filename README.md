# Rohit Mandapalli – Product Manager portfolio

One page, two versions. A switch at the top right flips between them.

- **Hi-fi** (the moon): the colour version. The page runs from night to sunrise as you scroll.
- **Lo-fi** (the sun): the plain black and white version, built on GOV.UK Design System principles.

Plain HTML, CSS and JavaScript. No build step, no dependencies, no tracking.

## Files

| File | What it is |
| --- | --- |
| `index.html` | The whole site: content, both designs, icons, font and the chat assistant |
| `social.jpg` | The picture shown when the link is shared on LinkedIn, WhatsApp, Slack and similar. Optional |
| `README.md` | This file. The site does not use it |

Everything sits in the main folder of the repository. There are no sub-folders.

## Publish an update

1. Open the repository on GitHub. Choose **Add file → Upload files**.
2. Drag in `index.html` and `social.jpg`. Choose **Commit changes**.
3. Open the **Actions** tab. Wait for a green tick next to "pages build and deployment". It takes a minute or two.
   A red cross means GitHub did not publish. Open the run and choose **Re-run all jobs**.
4. Open the site in a private window, or press Ctrl+Shift+R (Cmd+Shift+R on a Mac).
   Browsers keep the old page for up to ten minutes otherwise.

If you can see the sun and moon switch at the top right, you are looking at this version.

Files from the first version that are no longer used and can be deleted: `portrait.jpg` and `download`.

## The two versions

- New visitors get hi-fi. The switch remembers each visitor's choice in their browser.
- To link straight to one version, add `?mode=lofi` or `?mode=hifi` to the address.
- Visitors who ask their device for reduced motion get hi-fi without the movement.
- Visitors who ask their device for more contrast get lo-fi.
- Without JavaScript, and in print, the page is lo-fi.
- In hi-fi, the pause button in the icon bar stops all background movement.

To make lo-fi the default, open `index.html`, find `m = 'hifi';` near the top and change it to `m = 'lofi';`.

## Editing

- **Text:** search `index.html` for the section heading (`About`, `Case studies`, `Experience`, and so on). Each case study is one `<article>`.
- **Contact details:** the email address appears in the Contact section and in the chat script (`var EMAIL`).
- **Chat answers:** in the `<script>` at the end of the page, edit the `KB` list. Each entry has keywords (`k`), an answer (`a`) and optional follow-up questions (`next`).
- **Hi-fi colours:** search for `.hifi {`. The named colours (`--night`, `--violet`, `--orange` and so on) are set there once and used everywhere.
- **Web address:** the full address of the site is written near the top of `index.html` in the lines starting `og:url`, `og:image` and `canonical`. Update all three if you rename the repository or move to your own domain.

## The chat assistant

It is rule-based. It matches keywords in the question against the answers in `KB`, so it only knows what is on the page. It runs in the visitor's browser and sends nothing anywhere.

To use a live language model instead, host a small server that accepts `POST { "question": "...", "history": [...] }` and returns `{ "answer": "..." }`, then set `CHAT_ENDPOINT` in the script to its address. Keep any API key on that server, never in this page. If the server fails, the page falls back to the built-in answers.

## Checks

Both versions were tested with automated accessibility checks (axe-core, WCAG 2.2 AA rules) on eight screen sizes, from a small phone to a wide desktop. In hi-fi, text contrast was also measured from the rendered page. Automated checks do not replace testing with real assistive technology.

## Credits

The hi-fi typeface is Bricolage Grotesque, © The Bricolage Grotesque Project Authors, used under the SIL Open Font License 1.1. A subset is embedded in `index.html`.

## Before you publish

Everything in a public repository is public. Check that your employer is happy for the case studies to be shared in this form.
