# n9ho.com

Justin Rogers' (N9HO) personal ham radio site, served by GitHub Pages (`CNAME` = n9ho.com). Plain static HTML/CSS in a single `index.html`, no build step, no framework. A sub-page lives in `wfd/` (Winter Field Day). Keep it that way: no dependencies, no bundlers.

This repo holds only what Justin wants published. Do not copy project notes, memory, or private details into it.

## How this repo gets used

Justin attaches this repo from his other Claude projects and says something like "add this to the site." The job is:

1. Read this file and the relevant part of `index.html`.
2. Draft the entry from what you know about the project in that conversation.
3. **Show Justin the entry (and which section it goes in) before committing or pushing.** Only commit and push after he approves.
4. Make the smallest edit that works. Don't restyle or reorganize the page.

## Page structure (`index.html`)

Sections, in order: hero (callsign, "Station" panel), `#latest` (Latest update), `#building`, `#air`, `#cw`, `#watch`, footer (which has its own "Projects" link list).

The site has these pages: `index.html` (home), `projects/index.html` (every project: the cards plus the bench rows), `qrz-photo/index.html` (a write-up), and `wfd/index.html`. The sticky nav bar is the same markup on the home, projects and write-up pages. Its Projects link goes to `projects/`, and on sub-pages its other links are prefixed with `../`. Copy the nav from `index.html` when you make a new page.

Where new things go:

- **A real project with its own identity** (an app, a product, something people can install or use): a card in `#building` inside `<div class="projects">`. Copy an existing `<article class="proj">`: `proj-top` with a `glyph` and a `pill`, an `<h3>`, one paragraph, and a `<ul>` of links.
  - Pill: `pill live` (green) for released or beta, `pill brass` for shipped/featured, plain `pill` for design stage or in progress.
  - Glyph: either Morse in `&middot;` / `&minus;` or a short label like `144 MHz`.
- **A smaller tool, utility, script, or "I built this for my own shack" item**: a row in the `.bench` list under the cards, using `<div class="bench-row">` with `name`, `what`, and a `go` link. If it was built with Jay (W6JV), add the `<span class="with">with ...</span>` as the existing rows do.
- **Operating info or where to find Justin on air**: `#air` (the `ul.find` list).
- **Videos or follow links**: `#watch`.
- If a project has several pages of write-up, give it its own folder like `wfd/` (own `index.html`) and link to it from a card or bench row. Reuse the CSS variables and look from the main page.
- If you add a card or bench row for something notable, also check the footer "Projects" list and add a matching link if the others are there.
- **Every new project card or bench row goes in two places:** `index.html` and `projects/index.html`. On the projects page, relative links need the `../` prefix.
- **Latest update (`#latest`):** one card with a date, a short title, a few plain sentences, and a link. When Justin adds something notable (a project, a write-up), replace its content with the new item. Use today's date. Don't invent updates he didn't ask for.

## Voice

Justin writes in first person, plain and direct, like a ham talking to another ham. Practical over promotional.

- Say what it is, what problem it solves, and what state it's in. Be honest about status (the Brass Knuckle Node card says "Modeled, not yet built").
- One short paragraph per entry, two or three sentences is normal. Real numbers and specifics beat adjectives.
- No hype words, no "revolutionary", no marketing tone. No em dashes. Keep it readable by someone who has never seen his other projects.
- Credit collaborators (Jay, W6JV) where the existing entries do.
- Links: external links use `target="_blank" rel="noopener"`. Use `&amp;` and HTML entities in markup as the file already does.

## Technical write-ups

Every technical write-up (a project "how it works" page like `qrz-photo/`) carries a short, friendly disclaimer near the top, in a `.note` box. It says Justin did the project for fun, posts write-ups to give readers ideas for their own projects, and can't help with someone's own version or with troubleshooting. Don't promise support or invite questions on those pages. Copy the wording from `qrz-photo/index.html` and keep that tone.

## Privacy and safety

This is a public site. Never add: home address, phone numbers, email addresses, IP addresses or hostnames of his home network, API keys, tokens, QRZ or other credentials, or anything about his family or his restoration business (ADS) unless he explicitly asks. If a project involves a home server or network, describe what it does, not how to reach it.

## Images

Put images in the repo next to the page that uses them (the `wfd/` page keeps its logo alongside it). Keep them small (resize before committing) and give them descriptive `alt` text. Don't hotlink images from elsewhere.

## Before finishing

- Open the edited HTML and check tags are balanced and the new block matches its siblings.
- Don't touch unrelated sections, `CNAME`, or the `wfd/` page unless asked.
- Commit with a short message describing the addition (for example "Add QRZ photo shortcut to bench"). Push to the default branch only after Justin has approved the draft, since pushing publishes the site.
