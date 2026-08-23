# How the contact form works

*Plain words, for anyone who has never built a site. Written for "Make It Do Something",
General AI Fluency track, FlyRank AI internship, Week 6.*

---

My contact form gives visitors a simple way to reach me, and whatever they write ends up in my
inbox. A backend is the part that can remember or do things that a plain webpage cannot, so I'm
essentially renting a backend from Formspree instead of building one myself.

When someone clicks Send, the message travels from their browser to Formspree's server and then to
my Gmail inbox. My own website is not one of those stops — it never directly touches or stores the
message.

Before the message leaves their computer, the browser checks that the required fields aren't empty.
There's also a hidden honeypot field that normal visitors never fill in, but spam bots might, which
helps Formspree catch them.

The form also has its normal submission address written into it, so the browser knows where to send
the form even if the JavaScript doesn't work. This gives the form a backup way to submit instead of
depending completely on the script.

---

**Where it lives:** the form is on [contact.html](https://saad-imran-toori.github.io/contact.html).
Free tier, no server of my own, tested with a real message that arrived in my inbox.
