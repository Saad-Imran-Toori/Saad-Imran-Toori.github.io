[CRIT.md](https://github.com/user-attachments/files/31653568/CRIT.md)
# Survive the Crit — design review of the live portfolio

**Week 6 · General AI Fluency · Muhammad Saad Imran**
**Site reviewed:** https://saad-imran-toori.github.io
**Reviewed:** 31 August 2026 · **Reviewer:** Zia ur Rehman, classmate
**All five must-fixes are live at the time of writing.**

---

## 1 · The reviewer

**Who:** Zia ur Rehman — a classmate and friend.

**Why him:** he is in my field, so he can judge whether the claim lands on someone who would
recognise the work — but he was not part of DecisAI and has not reviewed the site before, so the
ten-second question was a first impression rather than a recall.

**The caveat I am recording rather than leaving out:** he is not a stranger, and he says himself
that he answered stage 2 by going through the pages "rather than answering from what I already knew
about you" — which tells me he did already know something about my work. So the ten-second answer
is not the clean test it would be with someone who had never met me. It is still worth something,
because he reached the refusal behaviour in his own words, but I should not claim it as an
independent result.

**Why not Mansoor:** he reviewed the site in Week 5 for *Ship the Ugly One*, and he built DecisAI
with me. Asking him "in ten seconds, what do I do?" would test his memory, not my site.

**What I gave him:** the live link and two questions, with no hint about what the site was meant to
say. The proof statement was deliberately held back until after he had answered — showing it first
would have told him the answer I was testing for.

---

## 2 · The ten-second test (asked before the proof statement)

### Q1 — In about ten seconds, what do you think I actually do?

> You're a software engineering student who builds AI/retrieval systems, especially systems that
> work with company documents like RFPs, contracts, and policies. The main thing I get is that you
> focus on making AI answer from real evidence instead of making things up.

### Q2 — Would you believe I'm good at it? Why, or why not?

> Yes, I'd believe you're good at it, mainly because the site doesn't just say "I'm an AI
> developer." It immediately shows specific things you've built, like DecisAI, and explains the
> actual problem you solved. The line about AI saying "no match" instead of guessing also makes
> your approach feel thoughtful and technically serious.

### Did the claim land?

The proof statement says the site should read as: *I build RAG systems that answer strictly from a
company's own documents and refuse to invent anything.*

**It landed.** Zia reached the refusal behaviour on his own — *"you focus on making AI answer from
real evidence instead of making things up"* — before he had seen the proof statement and without
reusing my wording. That is the specific thing I most wanted to test, and it is the second time it
has held with a reader who was given no hint (Mansoor described the same behaviour back in Week 5).

On believability he did not simply say yes; he named what convinced him — the specific projects
rather than a job title, and the "no match" line. Reasons tied to things actually on the page are
worth more than the verdict itself.

**Two things I am recording rather than burying:**

**He is a friend, so "would you believe I'm good at it" is not an independent answer.** People say
yes to that question when they know you. What partly rescues it is that his reasons cite specific
page content rather than being general praise — but the answer is not evidence in the way the Q1
answer is, and I should not treat it as though it were.

**The first words of his answer were "software engineering student."** My proof statement aims at a
founder or operations lead deciding whether to put me in front of their clients, and in that
context "student" is a hedge, not a credential. The site does state it — it appears in the opening
paragraph on the home page. I am not counting this as a finding on the strength of one word in one
answer; question 6 of stage 2 ("if you were that founder, what would stop you emailing me?") tests
it properly. Noted here so that if it surfaces again in stage 2 I do not get to pretend I had not
seen it coming.

---

## 3 · The rest of the feedback, verbatim

Asked after the proof statement was revealed, with Zia reading as the founder/operations person the
proof statement names. His words, unedited.

### Q3 — What was confusing, or made you stop and re-read?

> The main message is clear, but some of the wording gets more technical than it needs to be. On the
> Home page, I understand "AI that answers only from your documents" immediately. That's strong. But
> then I hit "I work on the retrieval layer…" and the explanation about the second case being a
> ranking and validation problem. As a normal business person, I don't really care about the
> distinction there. I had to stop and think "Okay, what exactly can this guy do for my company?"
>
> The Proof page is where this happens more. Things like Sentence Transformers, ChromaDB, Claude
> Haiku, Ollama phi3:mini, GroupKFold, precision@50, etc. are good evidence for a technical
> reviewer, but they're not immediately useful to the founder you're trying to get on a call.
>
> So my blunt version is: **I can tell what you build. I don't immediately know what you'd do for my
> company.**

### Q4 — Was anything broken or looked wrong?

> From the pages I could inspect, I didn't find an obvious dead link or broken page. The navigation
> works, and the Contact page exists. The site also explicitly says the contact form sends the
> message to you without requiring the visitor to open a mail app.
>
> I can't honestly claim I physically tested the rendered site on a phone, though, so I wouldn't
> pretend I verified every mobile visual detail or took a screenshot.

### Q5 — What was boring, or what did you skip past?

> The Paper. Not because it's bad — actually, it looks very serious. But if I'm the founder you
> described, I've got contracts and RFPs piling up. I'm not going to sit down and read a research
> paper before deciding whether to contact you. The paper gets very deep into methodology, leakage
> checks, folds, feature importance, limitations, etc. That's excellent proof, but it's not
> something I'd consume before contacting you. I'd probably skim title → abstract → results →
> limitations and leave.
>
> The second FlyRank project on the Proof page also pulled my attention away from your main pitch.
> It's impressive, but I came to understand "Can this guy build a trustworthy document AI system for
> me?" and suddenly I'm reading about ranking 16,726 search pages.

### Q6 — If you were that founder, what would stop you emailing me?

> This is probably my biggest criticism. I don't know whether you're offering to solve my problem or
> whether you're showing me your university/internship work. The Home page eventually says "If your
> team is buried in documents and you need an assistant you can put in front of a client…" — that's
> actually the sentence that makes me think "Okay, maybe I should contact this guy." I'd move that
> idea much earlier.
>
> I'd also wonder: "Has he built something that works outside a hackathon?" DecisAI is explicitly
> labelled CUST Hackathon 2026, and you honestly say you didn't place. That's actually refreshing,
> but as a potential client I'd still wonder how close this is to something I could actually use.
>
> And I'd want to know: "If I email him, what happens next?" You say we'll set up a call, but I'd
> make the call feel less like a commitment. Something like: "Send me your document problem. I'll
> tell you in 15 minutes whether this approach fits." That would make me much more comfortable
> clicking the button.

### Q7 — Was there anything you just didn't believe?

> The core claim? Yes, I believe it. The reason is actually the part where you show the system
> refusing to answer. You don't just say "my AI doesn't hallucinate." You show a real run where
> unsupported requirements become "No match found" / "EVIDENCE GAP", including the 9 compliance
> gaps. That's much more convincing than a generic AI portfolio claim.
>
> I also believe the research work more because you openly show where your first idea failed. You
> say the tier rule was only 5.6% better than a flat prediction, then explain that you threw it out.
> That's the kind of thing that makes me trust the person writing it.
>
> But I don't yet believe the stronger business claim: "I can build an assistant you can put in
> front of a client." You've shown me that you can build and evaluate a prototype. You haven't quite
> shown me that you can take my company's messy real documents and turn that into a reliable
> production system. And honestly, that's okay for an internship portfolio. I wouldn't expect you to
> prove that yet.

### His overall verdict

> "I understand what you do within about 10 seconds. That's a win." But then: "You start talking
> like a researcher when you need to keep talking like someone who can solve a business problem."
>
> Your strongest message is actually very simple: you build AI assistants that answer from a
> company's own documents and refuse to make things up when the evidence isn't there. That's the
> thing I'd remember after closing the site.
>
> The Proof and Paper make me believe you're technically serious. The biggest missing piece is
> making me, as a founder, think: "This person understands my problem, and I have nothing to lose by
> having a 15-minute conversation with him." That's where I'd focus.

---

## 4 · The sort

Sorting rule, decided before reading the feedback so it could not be bent to suit it:

**must-fix** — it is confusing, it is broken, it gets in the way of the one action (email me to set
up a call), or the proof does not land.
**nice-to-have** — everything else. Real, but it can wait.

### Must-fix

| # | What he said | Which test it fails |
|---|---|---|
| 1 | "I can tell what you build. I don't immediately know what you'd do for my company." | **The proof does not land** — and it fails on exactly the reader my proof statement names. |
| 2 | The "If your team is buried in documents…" line is what makes him consider contacting me, and it sits near the bottom of the page. | **Hurts the one action.** The sentence that triggers the action arrives after most readers have gone. |
| 3 | "If I email him, what happens next?" — the call feels like a commitment. | **Hurts the one action.** He named the fix himself: say what they get, and make it small. |
| 4 | "I work on the retrieval layer…" and the ranking-vs-validation distinction on Home. | **Confusing.** He stopped and re-read. A founder does not know or care what a retrieval layer is. |
| 5 | "I don't yet believe you can build an assistant to put in front of a client — you've shown a prototype." | **The proof does not land**, because the claim was bigger than the evidence. |

### Nice-to-have

| # | What he said | Why it can wait |
|---|---|---|
| 1 | Jargon on the Proof page — ChromaDB, GroupKFold, precision@50. | The Proof page legitimately serves a technical reader as well. Worth plain-language lead-ins later, not a rewrite now. |
| 2 | The Paper is too deep to read before deciding to make contact. | It is a capstone deliverable and cannot be gutted to suit a sales page. A three-line "what this says" above the link would help, later. |
| 3 | The second FlyRank case pulls attention away from the main pitch. | Real, but it is a structural decision about the Proof page rather than a quick edit. |

### Cannot be fixed by editing

"Has he built something that works outside a hackathon?" — that is a fact about my experience, not a
wording problem. Recorded rather than answered with a copy change, because a copy change would only
disguise it.

### Anything I was tempted to demote

**Item 5, and I nearly took the escape he offered.** Zia let me off it himself — "that's okay for an
internship portfolio, I wouldn't expect you to prove that yet." It would have been easy to file it
under nice-to-have on his own authority.

I put it in must-fix because the whole standard I have applied to my work all internship is that the
claim has to match the number. I reported 0.037 instead of 0.874 and I reported that the tier rule
was only 5.6% better than a flat guess. A site promising "an assistant you can put in front of a
client" off the back of a hackathon prototype is the same kind of overstatement, and I do not get to
apply the standard only where it flatters me.

**Item 2, the Paper being "boring".** The instinct was to demote it because I spent six hours on
that paper and it is my capstone. It genuinely does belong in nice-to-have — the paper's job is
proof, not persuasion — but I want it on the record that I wanted it there for the wrong reason
before it turned out to be the right place.

---

## 5 · Fix log — what actually changed on the live site

One entry per must-fix. Before, after, and how it was verified. A fix that is not on the live site
is not a fix.

### Fix 1 — must-fix 5: the claim now matches the evidence

**Files:** `index.html` and `proof.html` in the `Saad-Imran-Toori.github.io` repo, `main` branch.
The sentence appeared once in each.

**Before:**

> If your team is buried in documents and you need an assistant you can put in front of a client,
> send me a message and we'll set up a call.

**After:**

> If your team is buried in documents — contracts, RFPs, policies — I build the part that answers
> only from what is actually in them, and says "no match" when the evidence isn't there.
>
> I have proved that in a working system, on a 500-page tender. I have not yet run it against a
> company's live document set — and I would rather say so here than discover it with you on the
> call.

An HTML comment was added above it recording why the wording changed, in the same style as the other
decision comments in that file.

**Why this wording rather than a softer claim.** The fix is not an apology. It states the thing I
actually proved and names the gap myself. That second sentence also does double duty: the product I
am describing is a system that admits when the evidence is not there, so a page that admits what I
have not done yet is the claim demonstrating itself rather than undermining it.

**Verified:** the committed files on github.com were read back after pushing — the new text is
present in both, and "put in front of a client" survives only inside the HTML comment. The live
pages were then re-read and both carry the new wording. Checking the repo rather than trusting the
commit message is deliberate: three times this internship a commit looked right and the deployed
file was not (a stale duplicate site copy being served, a figure committed as `ml09-split.png.png`,
and a push of four pre-fix files).

**Evidence:** _[phone screenshot filename]_

### Fix 2 — must-fix 2 and 3: the offer moved up, and the next step is now stated

**File:** `index.html`, immediately after the opening sub-line and above the photo.

**Before:** the only offer on the page was the "Work with me" block at the very bottom. Zia named
that block as the thing that made him consider making contact — after he had already read past
everything else.

**After** — new paragraph near the top:

> **Buried in documents right now?** Send me the problem itself — not a meeting request. I'll read
> it and tell you straight whether this approach fits, and say so plainly if it doesn't.
> [Send me a message →]

That single paragraph closes both items. Must-fix 2 because the offer now arrives before the reader
has to earn it, and must-fix 3 because it answers "if I email him, what happens next?" — the answer
being a read and a straight verdict, not a meeting.

**On the timing promise I did not make.** Zia's suggested wording was "I'll tell you in 15 minutes
whether this approach fits." I left the number out deliberately. A response-time promise I might
miss would be a small over-claim sitting on a page whose entire argument is that I do not over-claim.
The promise as written is one I can keep every time.

**Verified:** live on saad-imran-toori.github.io. _[Add phone screenshot.]_

### Fix 3 — must-fix 4: the jargon a founder reads first

**File:** `index.html`, the second paragraph of the about block.

**Before:**

> I work on the retrieval layer — the part that decides whether there is enough evidence to answer
> at all. That's where I go deepest, but not all of it: the second case below is a ranking and
> validation problem, not a retrieval one. Same standard applies to both.

**After:**

> The two cases below are the same discipline in two settings — knowing when there is enough
> evidence to answer, and checking my own results honestly before reporting them.

"Retrieval layer", "ranking" and "validation" are gone from the part a founder reads first. The
honesty is kept: the sentence still says the two cases are different settings rather than pretending
they are the same piece of work.

**Verified:** live on saad-imran-toori.github.io. _[Add phone screenshot.]_

### Must-fix 1 — addressed through the others, and not mine to close

"I can tell what you build. I don't immediately know what you'd do for my company" was the umbrella
finding; items 2 to 5 are the specific ways the page produced it. All four are now fixed. Whether
the umbrella is actually closed is not something I get to decide by looking at my own page, which is
the whole premise of this assignment — so it goes back to Zia, and his answer is recorded below.

_[Re-review response to be added.]_

---

## 6 · The reply I sent back

Sent once all five must-fixes were live.

> Thanks again — that was genuinely useful, and blunter than I'd have got from most people. Here's
> what I changed. All of it is live now.
>
> **1. You said you couldn't tell what I'd do for your company, and that the one line that made you
> think about contacting me was buried at the bottom.** It's near the top now: *"Buried in documents
> right now? Send me the problem itself — not a meeting request. I'll read it and tell you straight
> whether this approach fits, and say so plainly if it doesn't."*
>
> **2. You asked what happens if you email.** That line is the answer — you send the problem, I read
> it, you get a straight yes or no. No meeting needed to find that out. I left your "15 minutes" out
> on purpose: I didn't want to promise a response time I might miss on a site whose whole point is
> not over-claiming.
>
> **3. You stopped at "I work on the retrieval layer" and the ranking-versus-validation bit.** Both
> gone. That paragraph now reads: *"The two cases below are the same discipline in two settings —
> knowing when there is enough evidence to answer, and checking my own results honestly before
> reporting them."*
>
> **4. You didn't believe "an assistant you can put in front of a client" from a hackathon
> prototype.** You were right. You actually let me off this one — you said it was fine for an
> internship portfolio — and I decided not to take that. The site now says I've proved it in a
> working system on a 500-page tender, and that I haven't run it against a company's live documents
> yet.
>
> **What I didn't change, and why:**
>
> - The jargon on the Proof page (ChromaDB, GroupKFold, precision@50). That page has to satisfy a
>   technical reader too, so I've left it rather than flatten it. A plain-language lead-in is the
>   better fix and it can wait.
> - The Paper being too deep to read before contacting me. Fair, but it's my capstone — its job is
>   proof, not persuasion. I'd rather put a short plain summary above it than cut it down.
> - The second FlyRank case pulling attention off the pitch. Agreed, but that's a structural
>   decision about the Proof page and I want to think about it rather than react to it.
> - "Has he built something outside a hackathon?" I can't fix that with wording, and I'm not going
>   to try. It's a real gap, and the honest answer is not yet.
>
> If you get two minutes: have another look at the home page and tell me whether you now know what
> I'd do for your company. That was your sharpest point and it's the one I most want to know I
> actually fixed rather than just moved.
>
> Also — could you open it on your phone this time? You said you hadn't, and I'd rather find out
> from you than assume.

---

## 7 · What I take from it

**What the review found that I would not have.** Nothing on the site was broken. Five days earlier I
had measured this same site at four phone widths, checked eighteen colour pairs against WCAG AA,
fixed every tap target and removed all horizontal overflow. None of that work could ever have found
what Zia found, because every sentence on the page was true and well-formed. The problem was the
order and the register: the page talks like a researcher to somebody who arrived with a business
problem, and it does not become an offer until the reader has already had the chance to leave. You
cannot measure that with a script. It took a person telling me they did not know what I would do for
their company.

**What I got wrong about my own site.** Two things. I thought the "Work with me" block was my call
to action, and in a sense it was — it was just at the bottom of a page nobody had a reason to finish.
The line I was most pleased with was the one Zia read last. And I had written "an assistant you can
put in front of a client" in week 1 and never gone back to check it against what I had actually
built by week 6. It quietly became an over-claim while I was busy proving I do not make those.

The second one bothers me more, because it is exactly the failure I have spent this internship
learning to catch in data. I reported 0.037 instead of 0.874, and I reported that my own tier rule
was only 5.6% better than a flat guess. Then I let a sentence about my own competence sit unchecked
for five weeks. The standard was easier to apply to the model than to myself.

**Where I nearly let myself off.** Zia excused the over-claim — "that's okay for an internship
portfolio, I wouldn't expect you to prove that yet." That was the moment the assignment was actually
testing. Taking the excuse would have been defending the original with the reviewer's own permission,
which is the most comfortable way to fail this. I fixed it instead, and the fixed version is stronger
than the claim it replaced: the page now demonstrates the behaviour it is selling, because a site
that says what it has not proved is doing the same thing as a system that says "no match".

**What I chose not to fix, and why.** The jargon on the Proof page stays for now, because that page
has a technical reader too and flattening it would cost more than it gains. The Paper stays deep,
because its job is proof and not persuasion. The second FlyRank case stays where it is, because
moving it is a structural decision about the Proof page and I would rather think about it than react
to it. And "has he built something that works outside a hackathon?" is not a wording problem at all —
it is a true statement about my experience, and the only honest response is to go and change the
fact rather than the sentence.

**A caveat on the result.** Zia is a classmate and a friend, and he already knew something about my
work. The ten-second answer is worth a lot — he reached the refusal behaviour in his own words,
unprompted — but it is not the clean test it would have been with a stranger. I am recording that
rather than presenting the pass as stronger than it is.

---

## Self-check against the pass criteria

- [x] The portfolio was submitted with its proof statement, and real feedback was received
- [x] The reviewer could state what I do and felt the work backed it up — Q1 and Q2, section 2
- [x] Feedback is sorted honestly into must-fix vs nice-to-have — section 4, including the two items
      I was tempted to demote
- [x] The must-fixes are actually fixed on the live site, not just acknowledged — all five verified
      live, section 5
- [x] I engaged with the feedback rather than defending the original — no explanation was offered
      during collection, and the one excuse I was handed was declined
- [ ] Phone evidence — the site's real-phone testing is recorded in `FIX-LOG.md` (26 August, on an
      Android phone in Chrome, re-measured at 320 / 390 / 414 / 768 px). _[Add a phone screenshot of
      the new offer paragraph.]_
- [ ] Re-review — Zia asked whether he can now tell what I would do for his company. _[Answer to be
      added.]_
