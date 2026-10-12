Tanatswa Manyika — Profile / Mini-Portfolio

A one-page, semantic HTML5 personal profile and mini-portfolio site built as
coursework for Unit II, featuring an About Me section, a skills list, a
project entry, and a working, natively-validated Contact Me form. This page
will be extended with responsive CSS3 and Tailwind styling in Unit III.

Live Page

Open `My Profile.html` in a browser, or view it directly on GitHub Pages at: `https://tmanyika487.github.io/tanatswa-manyika-profile/`

Accessibility: Peer Review Issue & Fix

Issue found by peer reviewer:
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

- `index.html` — the semantic HTML5 page (header, nav, main with sections,
  an aside, an article, and a footer), with all CSS in a `<style>` block
  in the document `<head>`
- `PROMPT_LOG.md` — AI prompt/output/edit log for the About section
- `README.md` — this file

Notes on Requirements Covered

- Semantic structure: `<header>`, `<nav>`, `<main>`, multiple
  `<section>`s, an `<aside>` (Quick Facts), an `<article>` (Project entry),
  and `<footer>`, with heading levels nested `h1 → h2 → h3` without skipping.
- Contact form: name (`text`), `email`, `tel`, a `select` dropdown, and
  a `textarea`, each with a properly associated `<label for="">`/`id` pair
  and native HTML5 validation (`required`, `pattern`, `minlength`,
  `maxlength`) — no JavaScript involved.
- Accessibility: all inputs labelled, decorative graphic marked
  `alt=""`/`aria-hidden`, and text/background color pairings checked for
  readable contrast (dark teal on white/near-white, and white on dark
  teal).

Responsive Notes

Breakpoints tested 

The page uses a mobile-first base layout and custom `min-width` media queries in
`style.css` at `48rem` (tablet) and `64rem` (desktop). The intended test widths
are 375px (mobile), 768px (tablet), and 1280px (desktop). At each width,
check that the navigation wraps cleanly, the page has no horizontal scrollbar,
form controls stay inside the page, and text remains readable. Re-test these
three widths in the browser's device toolbar before submitting and update this
note if you find and fix any issues.

Flexbox and Grid choices

- Flexbox: the navigation list uses `flex`, `flex-wrap`, and `gap` so links
  can wrap onto another line on narrow screens without overflowing. The skills
  list also uses Flexbox so skill labels flow naturally across available space.
  The contact form's individual field groups use a vertical Flexbox layout to
  keep labels above their controls.
- CSS Grid: the contact form uses a one-column grid on mobile and two columns
  from the tablet breakpoint; the message field and submit button span both
  columns. The About section becomes a two-column layout on tablet and wider
  screens, with the Quick Facts aside alongside the main text.

Tailwind utilities and custom CSS

Tailwind CSS is loaded in `index.html` using the Tailwind Play CDN script. This
keeps the coursework page simple to run without a separate build step. Tailwind
utilities are used in the header/navigation (`px-*`, `py-*`, `flex`, `flex-wrap`,
`gap-*`, and `sm:` / `lg:` responsive variants), the main content container
(`max-w-6xl`, `mx-auto`, and responsive padding), and the contact form
(`grid`, `grid-cols-1`, `md:grid-cols-2`, `gap-4`, and `md:col-span-2`).

The external `style.css` file handles the site's colour palette, typography,
card styling, focus states, field appearance, and the custom mobile-first media
queries. This split is intentional: Tailwind handles common layout/spacing
utilities, while custom CSS handles the page's visual identity and responsive
behaviour that needs more control. The semantic HTML structure and labelled
form controls from Assignment 1 have been kept.
