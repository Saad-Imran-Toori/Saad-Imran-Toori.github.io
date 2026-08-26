# Open It on Your Phone — fix log

**Site:** https://saad-imran-toori.github.io
**Checked:** 26 August 2026, on a real Android phone in Chrome, and re-measured
in headless Chromium at 320 / 390 / 414 / 768 px.

The phone came first. Every number below was measured, not estimated — but the
two findings that mattered most were spotted by eye on the phone before any
tool caught them.

---

## What was broken

### 1. The page scrolled sideways on every phone width

The top navigation is a flex row and had no `flex-wrap`, so it could not fold.
On Home, Proof and Contact the "Email" link ran past the right edge of the
screen and the whole page scrolled horizontally.

Measured `document.scrollWidth` against viewport width:

| Page | 320px | 390px | 414px | 768px |
|---|---|---|---|---|
| index.html | 419 (**+99**) | 419 (**+29**) | 419 (**+5**) | fits |
| proof.html | 419 (**+99**) | 419 (**+29**) | 419 (**+5**) | fits |
| contact.html | 419 (**+99**) | 419 (**+29**) | 419 (**+5**) | fits |
| paper.html | 448 (**+128**) | 448 (**+58**) | 448 (**+34**) | fits |

**Fixed:** `flex-wrap:wrap` on the header nav, so it folds onto a second line
instead of overflowing. This is the same fix — and the same reason — already
written into `.flinks` in Week 5; the top nav had simply never been given it.

**After:** scrollWidth equals viewport width on all four pages at all four
widths. Zero horizontal overflow.

### 2. The paper's Contents heading sat beside its list, not above it

**Found on the phone, not by measurement.** The stylesheet had a bare `nav { }`
selector, and the paper's table of contents is marked up as
`<nav class="toc">`. So the TOC inherited `display:flex; align-items:center`
and laid its heading out as a flex sibling of the list — "CONTENTS" floating
vertically centred to the left of items 1–8. The footer link row
(`<nav class="flinks">`) was picking up the same rule by accident.

**Fixed:** scoped every top-bar rule to `header nav`, so it stops leaking onto
the other two `<nav>` elements on the page. The TOC is a normal block again.

### 3. The Results table could not fit any phone

`Method | precision@20 | precision@50 | sd across folds` renders 402px wide and
cannot shrink further without crushing the numbers. Four other tables in the
paper had the same exposure.

**Fixed:** each of the 5 tables now sits in its own `overflow-x:auto` container.
The table scrolls sideways inside its box; the page never does.

### 4. A footer contrast failure

`.fnote` (the "Built by hand in plain HTML and CSS" line, on all four pages)
was `#8a919b` on `#FAFAF8` — a contrast ratio of **3.04:1**, below the WCAG AA
minimum of 4.5:1 for text this size.

**Fixed:** `#6b7280`, which measures **4.63:1**. Still visibly quieter than
`--muted` (5.74:1), so the footer keeps its hierarchy.

Every other text pair on the site was checked and passed — body text 17.03:1,
headings 11.11:1, muted text 5.74:1, the CTA button 11.11:1, form labels
6.00:1, the error state 5.86:1.

### 5. Tap targets too small for a thumb

Measured every link and button at 390px against the 44px Apple guideline and
the 24px WCAG 2.5.8 minimum.

| Target | Before | After |
|---|---|---|
| Nav links (Home / Proof / Paper / Contact / Email) | 25px tall | **45px** |
| Footer link row | 23px tall | **43px** |
| "CV" in the footer | 19 × 23px | **31 × 43px** |
| Paper's Contents links | 18px tall | **30px** |
| "Read the case →" (a link alone in its paragraph) | 19px tall | **27px** |

Nav height was kept the same by moving the padding from the `<nav>` onto the
links themselves — the links *look* identical, the tappable box is nearly twice
as tall.

Links still measuring under 24px are all **inline inside a sentence**
("notebooks and code", "flyrank.ai", "wa.me/923216226320"). WCAG 2.5.8
explicitly exempts these, because enlarging them would break the line spacing
of the prose around them. Left alone deliberately.

### 6. Images caused layout shift, and loaded whether seen or not

None of the 11 images carried `width`/`height` attributes, so the page jumped
as each one arrived. None were lazy-loaded.

**Fixed:** intrinsic `width` and `height` on all 11, plus
`loading="lazy" decoding="async"`.

One trap worth recording: adding those attributes to an image styled
`width:100%` with no height rule makes the attribute height win, and every
figure stretches. `height:auto` had to go in at the same time. Verified after
the change — rendered aspect ratios match intrinsic ones exactly.

### 7. Work captures were crisp but unreadable

**Found on the phone.** The DecisAI compliance matrix and decision screen are
1400px files rendering into 342px of phone width. They are not blurry — they
are simply too dense to read at that size, which is the same problem from the
reader's side.

**Fixed:** all 10 figure images are now wrapped in a link to the full-size
file, so a tap opens the image and the phone can pinch-zoom it. Each link
carries an `aria-label` naming what it opens.

---

## What I checked and did NOT change

**Image compression.** The card says compress oversized images. Measured: the
eight content images total 673 KB, and re-encoding every one at JPEG q85 /
PNG optimize would save **5.2%** — 35 KB across the whole site. Meanwhile the
widest image is 1456px against a 1544px retina requirement for the 772px
column, so every image is already *under* the crispness threshold, not over it.
Shrinking them would trade a real loss of sharpness for a saving that no one
would perceive. Left alone, and recorded here rather than claimed as a fix.

**Every link.** All 7 internal links resolve to files that exist, and all 8
in-page anchors in the paper point at IDs that exist. The five notebook links
in the Reproducibility section all point at notebooks that are on `main` and
carry outputs.

**The honeypot.** `.gotcha` on the contact form renders 9,637px off the left of
the screen. That is deliberate spam defence from Week 6, not a layout bug — it
sits off-screen to the *left*, so it never contributes to rightward scrolling.
The audit flagged it; verifying it is what cleared it.

**`loading="lazy"` on the profile photo.** It sits below the fold at every
phone width tested, so lazy-loading it costs nothing.

---

## Still not perfect

- "Email" now wraps to its own line in the nav on narrow phones. Correct and
  fully visible, but it reads as slightly orphaned. A hamburger menu would be
  tidier and would also be the first build step this site has ever needed.
- The paper's tables scroll sideways rather than reflowing into stacked cards.
  Scrolling is honest and costs nothing; stacking would read better and is the
  obvious next improvement.
- Nothing here was tested on iOS Safari — only Android Chrome and headless
  Chromium. `-webkit-overflow-scrolling` is in place for it, untested.

---

## Files changed

`index.html`, `proof.html`, `contact.html`, `paper.html`, `style.css`
— 79 insertions, 40 deletions.

**Note for the internship repo:** `work/paper/paper.html` is an archived copy of
the deployed paper. It was synced on 26 August; these changes put it behind
again, so it needs re-syncing after this deploys.
