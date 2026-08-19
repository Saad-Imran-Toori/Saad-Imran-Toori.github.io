# What I Learned from My Own CSS

**Explain It Like You Built It · General AI Fluency · Week 5 · Muhammad Saad Imran**

Live site: https://saad-imran-toori.github.io — the file I am explaining is `style.css`.

---

## Why I picked this

I picked the styling in `style.css` because I wanted to understand what was actually happening
behind the design, instead of using CSS lines simply because they worked. I had used some of these
lines before without fully understanding them, and this is the part of my build I understood least.
Working through them properly showed me why they were written the way they were.

I had an AI tutor me on three pieces and then quiz me on them, which is where I found out that some
of what I thought I knew was wrong.

## The dot grid background

```css
background-image: radial-gradient(rgba(31,56,100,.06) 1px, transparent 1px);
background-size: 34px 34px;
```

The thing that made this click was realising that **a gradient is treated as an image by the
browser**. It is not a colour. `background-image` usually points at a photo file, but here the
browser generates the picture itself.

The gradient draws a single tiny dot. `background-size: 34px 34px` then shrinks that generated image
down to a 34-by-34 pixel tile, and because backgrounds repeat by default, that one tile is stamped
across the whole page. I never drew a grid — the grid is what repetition produces.

The two numbers do completely different jobs, and this is the part I got wrong:

- The **`1px` inside the gradient** controls **how big each dot is**.
- **`background-size`** controls **how far apart the dots are**, because it sets the size of the tile
  the dot sits in.

So to make the dots thicker I change the gradient. To spread them out I change `background-size`.

The `.06` is 6% opacity, which is deliberate — my style note says the design should stay quiet, so
the texture should read as depth rather than decoration.

## The green bar in my logo

```css
.mark{ position: relative; }

.mark::after{
  content: "";
  position: absolute;
  bottom: 8px; left: 10px; right: 10px;
  height: 2px;
  background: var(--accent);
}
```

The strangest part is that **this bar does not exist anywhere in my HTML**. It is created entirely
by CSS through the `::after` pseudo-element.

Two positions are working together here, on two different elements. `.mark` — the navy square with
"SI" in it — uses `position: relative`, which makes it the reference point. The bar uses
`position: absolute`, which lets it be placed against that reference point. If `position: relative`
were removed from `.mark`, the bar would search upward for another positioned parent, find none, and
end up measuring from the whole page — appearing as a green line across the bottom of the site
instead of inside the logo.

`content: ""` is required. Without it the pseudo-element is not created at all, so there is nothing
to style and nothing appears — not an empty box, but no box.

I also understand now why the bar sets `left` and `right` but never `width`. Setting both edges lets
the width work itself out, so the same rule fits the 38px logo in my navigation bar and the 96px
version in my identity kit. A fixed width would only have been correct at one of those sizes.

## `clamp()` for text that resizes itself

```css
h1{ font-size: clamp(30px, 6vw, 46px); }
```

`clamp()` takes three values: a minimum, a preferred value, and a maximum. The preferred value here
is `6vw`, which means 6% of the browser window's width, so the text scales as the window changes.
The browser uses that preferred size whenever it can, but never goes below 30px or above 46px.

On a 1000px-wide window, 6vw works out to 60px, which is over the limit, so the heading is capped at
46px. On a phone the calculated size would be too small, so the 30px minimum takes over.

The reason this matters is that it does the whole job in one line. Without it I would need media
queries — separate blocks of CSS for different screen sizes, all of which have to be kept in step
with each other.

## What I got wrong while learning this

I am including these because they are the real evidence that I learned something rather than copied
an answer.

**I thought `background-size` controlled the size of the dots — and I got this wrong twice.** My
first answer was that increasing it from 34px to 80px would make the dots bigger. After being
corrected I still answered a rephrased version of the same question the same way. The dots never
change size; only the spacing between them does. What fixed it for me was a physical comparison:
carving a bigger dot into a rubber stamp is not the same as using a bigger stamp block. A bigger
block just leaves more empty space around the same carving.

**I thought only one positioning value was involved.** When asked about `position: relative` being
removed, I replied that we were using `absolute`, not `relative`. Both are used, on two different
elements, and each is useless without the other — `absolute` has to be positioned against something,
and `relative` on the parent is what gives it that something.

## Where I ended up

I can now explain these lines without looking them up, and I know what would break if each were
changed. That was the point of the exercise: not to have styling that works, but to have styling I
can account for. My build notes for the site already avoided any code I had not written, and this
closes the remaining gap between code I wrote and code I actually understood.
