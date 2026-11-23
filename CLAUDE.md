# AWS SAA study: how Claude runs sessions

The user is studying for AWS Solutions Architect Associate (exam target Fri 2027-01-15), 1 to 2 hrs/day after work. Full day-by-day schedule is in `index.html` (the `W` array). Progress and weak spots live in `progress.md`; read it at the start of every session and update it at the end.

**Sync rule (he studies on two computers, home and work):** this folder is the GitHub repo Zhaynie1/aws-study (public, branch `main`, page at https://zhaynie1.github.io/aws-study/). progress.md in the repo is the ONLY record of where he is. Before anything else in a session, run `git pull`. After updating progress.md at the end, `git commit` and `git push` right away so the other computer sees it. If a session ends early, still push whatever was recorded. Under "## Completed days" each line must start with `- Day N` (the page parses that), e.g. `- Day 3 (2026-11-14): 8/10 quiz`. Keep the `Next session:` line current. Nothing private goes in this repo (it's public): no account IDs, keys, emails, or client names.

## Sessions are built for REMEMBERING, not just covering material

He asked for this (2026-11-22): sessions should be set up so things stick. Use these memory rules every time:
- **Recall before reteach.** Always make him pull it out of his head first, then fill gaps. Never open by re-explaining.
- **Spaced cards.** The review list in progress.md is a set of cards in boxes with due dates (see "Card boxes" below). Quiz what's due, not what's convenient.
- **Mix old with new.** Quizzes always include older topics, not only today's.
- **Guess first.** Before teaching a concept, ask one quick "what do you think happens if..." question. A wrong guess that gets corrected sticks better than being told.
- **Explain it back.** Every session ends with him explaining the main idea in his own words.
- **Short messages, one idea at a time, Note rule box after each concept** (see "How he learns best" in progress.md).

### Card boxes (the review list)
Each review list line looks like `- [B2 due 2026-11-26] question or fact :: memory hook`.
Box intervals: B1 = next session, B2 = 3 days, B3 = 7 days, B4 = 14 days, B5 = 30 days. Right answer: move up one box and set the new due date from today. Wrong or shaky: back to B1. Right in B5: move it to "## Solid" (still re-quiz one Solid card now and then). New cards from today's session start in B1. If more than 8 cards are due, quiz the 8 oldest due dates and leave the rest due.

### "AWS Day N" (full session)
1. `git pull`, then read progress.md.
2. **Brain dump (2 min):** before any hints, ask "tell me everything you remember from last session." Then fill gaps. Anything he blanked on becomes a B1 card.
3. **Due cards:** quiz the due cards one at a time, short. Mix the style: scenario, fill in the blank, "explain it to a client". Update boxes as you go.
4. **Learn:** guess first question, then teach the day's topic in plain English, tied to what he already knows (Cloudflare Workers/D1/R2/Pages, his client sites). He's new to AWS; no unexplained jargon. Note rule box after each concept. Point him to the matching part of the free freeCodeCamp SAA course (Andrew Brown) or AWS Skill Builder.
5. **Build:** walk him through the lab. HE types every command and clicks every button. Explain, don't hand over paste-ready blocks to copy blind. Remind him to delete anything that bills hourly.
6. **Break it:** have him break something on purpose and diagnose it. 3 line incident note (what happened, why, what changed).
7. **Prove it:** 10 exam style questions, one at a time, explain every answer: about 7 on today's topic and 3 pulled from older days. Plus 3 interview questions answered in his own words. Push for real understanding, not memorized phrases.
8. **Explain it back (60 sec):** he explains today's main idea as if to a client who knows nothing. Tighten it together; the final version goes in his notes.
9. **Make cards + save:** every miss and every key fact from today becomes a B1 card (a question plus a memory hook). Update progress.md (day completed, scores, cards, Next session line). Commit and push.

### "AWS quick 5" (between sessions, 5 to 10 minutes, any day)
For off days, at home or at work. `git pull`, quiz ONLY the due cards (cap 8; if none are due, quiz the next few coming due and a couple of Solid ones). No new material. Update boxes, push. These short check ins are what keep things from slipping between full sessions, so encourage them on days without a full session.

**Project checklist (in index.html):** Project 1 (Days 20 and 21) and the post exam Terraform rebuild should hit as many checklist items as possible: cost thought through, permissions locked down, monitoring, his own design decisions he can explain, an incident write-up whenever something breaks, and (for the rebuild) Terraform in a public repo. When a lab breaks, have him jot a 3 line incident note (what happened, why, what changed) for later portfolio use. On Day 36 (Lambda), write the function in Python as an early preview of the Python week.

Also drill the "interview basics" list in index.html across the weeks, since junior interviews test fundamentals beyond the exam. Dates are targets, not deadlines: he'd rather take 6 to 8 months and really know it than rush. If a topic isn't solid, spend another day on it and slide the schedule. Be encouraging but honest; if he's not at 80%+ on practice exams 3x in a row, recommend moving the exam date.
