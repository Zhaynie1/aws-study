# AWS SAA progress

Exam target: Fri 2027-01-15 (not booked yet; book on Day 41, Dec 28)
Next session: Day 3, Linux command line part 1 (needs Ubuntu via WSL on his Windows PC). Start with the brain dump, then the 5 due B1 cards.

## Completed days
- Day 2 (2026-11-17): 9/10 quiz, 3/3 interview Qs (good, polished). Missed: which CIDR is biggest (picked /32).
- Day 1 (2026-11-13): 9/10 quiz, 3/3 interview Qs answered (solid, needed tightening). Missed: request order. Also missed A vs CNAME in warm-up.

## How he learns best
- HIS GOAL: by ~Day 60, explain every topic out loud easily enough to pass a junior interview. So EVERY session: start with a refresher recap + re-quiz 2-3 items, mixing recent ones with older ones (spaced repetition), not just yesterday's. Keep revisiting until they're effortless.
- Big tables + code blocks + several new terms in one message = shuts down (happened on CIDR). For math topics: ONE small idea per message, short, check, then next. Keep messages short in general.
- CIDR clicked once taught as: dots split 4 numbers -> same first 3 = same house -> /24 shorthand -> 'slash / 8 = numbers locked'. Each number = 8 bits (on/off switches) explained only after he asked.
- ALWAYS end each new concept with a short "Note rule" box he can copy straight into his notes (one-line rule + memory hook). He asked for this for everything going forward.
- He takes handwritten notes; resend a section in full when he asks so he can copy it.
- Plain-English story first, labels/jargon after. Too many terms at once = frustration.
- Show a worked example before asking open questions; fill-in-the-blank works better than "explain everything".
- Explain why something matters (troubleshooting a broken client site) before drilling it.
- Windows laptop: curl/PowerShell commands failed; browser DevTools (F12 > Network, Disable cache, Preserve log, Incognito) worked well.

## Day 2 notes
- Learn: TCP/UDP, public vs private IPs, NAT, CIDR, subnets. Build: ran ipconfig (private 192.168.x, gateway = router, public IP different via 'what is my ip'). Break: spot-the-mistake (web server private / DB public).

## Day 1 notes
- Learn: AWS Cloud Practitioner Essentials Module 1 + freeCodeCamp SAA intro (first ~35 min), took notes.
- Build/Break: nslookup, DevTools headers, 404 path, 307 HSTS -> 308 apex->www redirect chain. x-vercel-id iad1 = AWS us-east-1 (Vercel runs on AWS).
- Prefers giving letter only; keep asking for the 'why'. The text box shows suggested replies; remind him not to look during quizzes.

## Practice exam scores
(none yet)

## Review list (cards: see "Card boxes" in CLAUDE.md)
- [B1 due 2026-11-23] Which CIDR is biggest, /8, /16, /24 or /32? :: Slash counts the LOCKED numbers. /8 huge, /32 = 1 address. "Big number, small house."
- [B1 due 2026-11-23] Site "can't be reached", no status code. What do you check first? :: DNS first (nslookup). "If nobody picked up, check you have the right number."
- [B1 due 2026-11-23] Host's IP can change. A record or CNAME? :: CNAME (name -> name, host keeps its IP current). A record holds only an IP, never a name.
- [B1 due 2026-11-23] Put the request steps in order. :: Find it (DNS) -> connect (443 + encryption) -> ask (GET /) -> get (200). Pizza analogy.
- [B1 due 2026-11-23] Does a website see your 192.168.x address? :: No, it sees your home PUBLIC IP. NAT hides you behind the router.
- [B2 due 2026-11-25] Which IP ranges are private? Is 10.x "AWS's"? :: "10, 172, 192 stay home." Private for everyone; AWS just uses 10.x a lot.
- [B2 due 2026-11-25] Public vs private subnet: what goes where, and what happens if you flip them? :: Web server public, database private. Website private = broken (loud). Database public = exposed (quiet).
- [B2 due 2026-11-25] What does NAT allow? :: "Out yes, in no, replies only." Router translates private -> public. AWS NAT Gateway bills hourly.
- [B2 due 2026-11-25] UDP glitch vs TCP glitch. Is UDP less safe? :: UDP drops the piece; TCP waits and resends (delay). UDP is less RELIABLE, not less safe.
- [B2 due 2026-11-26] Ports 80, 443, 22? :: HTTP, HTTPS, SSH.
- [B2 due 2026-11-26] No code vs 4xx vs 5xx. What's 401 vs 403 vs 404? :: No code = never reached server (check DNS). 4xx = your request (401 no ID, 403 not allowed, 404 not found). 5xx = server broke. Say 500, not 505.
- [B2 due 2026-11-26] Interview: what is "the cloud"? What does HTTPS do? :: Renting compute, storage, databases (give 2+ reasons). HTTPS = encryption AND proves the site's identity (certificate).
- [B2 due 2026-11-26] Why does Route 53 have "Alias" records? :: CNAME isn't allowed at the apex (zackhaynie.com uses an A record, www uses CNAME).
- [B2 due 2026-11-27] Grey cloud vs orange cloud in Cloudflare? :: Grey = DNS only (goes straight to Vercel). Orange = proxied through Cloudflare. Ties to Route 53 vs CloudFront.
- [B2 due 2026-11-27] Does DNS see the path (/about)? What does a 404 tell you? :: DNS only sees the domain. 404 = DNS worked, server reached, page missing.
- [B2 due 2026-11-27] 307 vs 308 redirect? :: 307 = browser upgraded to https itself (HSTS). 308 = server said "moved permanently" (apex -> www).
- [B2 due 2026-11-27] "from memory cache" vs x-vercel-cache HIT? :: Memory cache = browser never contacted the server. HIT/MISS = server side cache.
- [B3 due 2026-11-30] Subnet in one line? :: Network under a network (building = network, floors = subnets).
- [B3 due 2026-11-30] How do you find out who owns an IP? :: Look it up (ipinfo.io), don't assume.
- [B3 due 2026-11-30] nslookup vs the browser? :: nslookup = a human asking DNS manually; the browser does the same lookup automatically.

## Habits to watch (not cards)
- Reread answers for typos that flip meaning (wrote "can" meant "can't").
- Read answer letters carefully (said "C" but meant CNAME = B).

## Solid
(none yet)
