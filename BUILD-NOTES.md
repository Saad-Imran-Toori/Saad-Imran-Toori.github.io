# How this site is built

*Written so I can answer any question about my own site. There is no code here I can't explain.*

## The stack, and why

Plain HTML and CSS, hosted on GitHub Pages. No framework, no build step, no JavaScript at all.

I chose this in Week 4 (`Three Roads: Choose Your Stack with AI`) after comparing it against a
static site generator and React with Next.js. The deciding reason was **near-zero maintenance**: a
site with no build step cannot break because a dependency changed while I was busy with the machine
learning track. Deploying is `git push`.

## The files

| File | What it is |
|---|---|
| `index.html` | Home. The claim, the short bio and photo, both cases in summary, the call to action. |
| `proof.html` | The two cases in full, with real screenshots. |
| `contact.html` | The one action, and exactly what the call covers. |
| `style.css` | Every style rule for all three pages. One file so the look can't drift between pages. |
| `favicon.png` | The SI monogram, from my Week-3 Identity Kit. |
| `profile.jpg` | A real photo of me. |
| `decis-matrix.jpg`, `decis-decision.jpg` | Frames from my own DecisAI demo recording. |
| `ml03-lane.jpg`, `ml04-leakage.png` | Screenshots of my own executed notebooks. |

## How a page is put together

Each page has the same four parts, in this order:

1. **`<head>`** — the page title, the description search engines show, the favicon, the two Google
   Fonts, and a link to `style.css`.
2. **`<header>` with `<nav>`** — the SI monogram plus links to all three pages. The markup is
   identical on every page, which is why navigation always works in both directions.
3. **`<main class="wrap">`** — the actual content.
4. **`<footer>`** — one line and a GitHub link.

I keep the navigation identical by copying it, not by generating it. With three pages that is
honest and cheap. If it reached about six pages I would move to a static site generator so I
wasn't maintaining the same block six times — that's the trigger I wrote down in Week 4.

## Things in the CSS worth explaining

**The colour variables.** At the top of `style.css`:

```css
:root{ --navy:#1F3864; --ink:#14181F; --paper:#FAFAF8; --accent:#2F6F4E; }
```

`:root` means "the whole document." These name my four Identity Kit colours once so I never retype
a hex code, and changing one line changes it everywhere. Used later as `color: var(--navy)`.

**The dot-grid background.**

```css
background-image:radial-gradient(rgba(31,56,100,.06) 1px, transparent 1px);
background-size:34px 34px;
```

This draws one faint navy dot and repeats it every 34 pixels. It's the texture from my Week-3
image curation, produced in CSS instead of loading an image file — so it costs nothing to download
and stays sharp on any screen. I rejected a generated "glowing AI brain" hero for reasons I wrote
up in Week 3; a quiet grid does the one job a background needs.

**The monogram's green underline.**

```css
.mark::after{ content:""; position:absolute; bottom:8px; left:10px; right:10px; height:2px; }
```

`::after` adds a small extra box inside the monogram. `position:absolute` places it against the
monogram, and the four offsets make it a short 2-pixel bar near the bottom. That's the green
underline in my logo, drawn rather than shipped as an image.

**`clamp()` for headings.**

```css
h1{ font-size:clamp(30px,6vw,46px); }
```

Three values: never smaller than 30px, never larger than 46px, and 6% of screen width in between.
This is how the type scales on a phone without me writing separate mobile rules.

**`max-width:68ch` on paragraphs.** `ch` is the width of a "0" in the current font, so this caps a
line at about 68 characters. Long lines are hard to read; this is the whole of my responsive text
strategy.

**`.wrap`** sets one shared 820px column with 24px of side padding, so every page lines up and
nothing touches the edge of a phone screen.

## The call to action

Every CTA on the site is the same single action — *email me to set up a call* — decided in Week 1
and mapped in my Week-3 content map. The link is a pre-filled `mailto:`:

```
mailto:s0078678600@gmail.com?subject=Setting%20up%20a%20call&body=Hi%20Saad%2C...
```

`?subject=` and `&body=` pre-write the email so a visitor doesn't face a blank message. `%20` is a
space and `%2C` is a comma — URLs can't contain those characters directly.

## Accessibility

Every image has real `alt` text describing what is in it. The current page in the navigation is
marked `aria-current="page"`. The monogram link has an `aria-label` because "SI" alone doesn't tell
a screen reader it goes home.

## What I did not use, and why

- **No JavaScript.** Nothing on the site needs to change after it loads.
- **No cookies, no analytics, no tracking.** Nothing to disclose, nothing to consent to.
- **No CSS framework.** The whole stylesheet is about 120 lines. Loading a framework would ship far
  more code than I use, and I couldn't explain most of it.
- **The three generated icons from my Week-3 curation** are not on the site yet. They were optional
  connective tissue and the pages read fine without them; adding decoration I don't need would
  contradict my own style note.

## Deploying

The site lives in the repository `Saad-Imran-Toori.github.io`. GitHub Pages serves whatever is on
the `main` branch at `https://saad-imran-toori.github.io`. Pushing a change updates the live site
within about a minute. There is no build stage that can fail.
