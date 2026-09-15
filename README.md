Tanatswa Manyika — Profile / Mini-Portfolio

A one-page, semantic HTML5 personal profile and mini-portfolio site built as
coursework for Web Technologies, featuring an About Me section, a skills list, a
project entry, and a working, natively-validated Contact Me form. 

Live Page

Open `My Profile.html` in a browser, or view it directly on GitHub Pages (if
enabled) at: `https://tmanyika487.github.io/tanatswa-manyika-profile/`

Accessibility: Peer Review Issue & Fix

Issue found by peer reviewer (Thursday's practical session):
My peer reviewer flagged that images on my draft page had missing or poor
`alt` text, meaning screen reader users would either hear nothing useful
or hear a meaningless filename when reaching an image.

Fix applied:
- The avatar graphic in the header is a purely decorative inline SVG, so I
  gave it `alt=""` and `aria-hidden="true"` so screen readers skip over it
  entirely instead of announcing something meaningless.
- I audited every other visual element on the page (icons, decorative
  markers) and applied the same rule consistently: meaningful `alt` text
  for anything that conveys information, and `alt=""`/`aria-hidden="true"`
  for anything purely decorative.
- Going forward, any real photo I add to this page (e.g. a profile photo)
  will get descriptive `alt` text describing what's actually in the image,
  not just a filename or "photo of me."

AI-Assisted Content

The About Me section copy was drafted with AI assistance and then
critically revised. See [`PROMPT_LOG.md`](./PROMPT_LOG.md) for:
1. The exact structured prompt used (context + goal + constraints + format)
2. The AI's raw, unedited output
3. My final, hand-edited version
4. A short reflection on what I changed and why

Structure

- `My Profile.html` — the semantic HTML5 page (header, nav, main with sections,
  an aside, an article, and a footer)
- `style.css` — page styling, including layout, color contrast, and a
  small responsive breakpoint
- `PROMPT_LOG.md` — AI prompt/output/edit log for the About section
- `README.md` — this file

Notes on Requirements Covered

- **Semantic structure:** `<header>`, `<nav>`, `<main>`, multiple
  `<section>`s, an `<aside>` (Quick Facts), an `<article>` (Project entry),
  and `<footer>`, with heading levels nested `h1 → h2 → h3` without skipping.
- **Contact form:** name (`text`), `email`, `tel`, a `select` dropdown, and
  a `textarea`, each with a properly associated `<label for="">`/`id` pair
  and native HTML5 validation (`required`, `pattern`, `minlength`,
  `maxlength`) — no JavaScript involved.
- **Accessibility:** all inputs labelled, decorative graphic marked
  `alt=""`/`aria-hidden`, and text/background color pairings checked for
  readable contrast (dark teal on white/near-white, and white on dark
  teal).
