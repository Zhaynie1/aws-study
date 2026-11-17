# AWS SAA progress

Exam target: Fri 2027-01-15 (not booked yet; book on Day 41, Dec 28)
Next session: Day 3, Linux command line part 1 (needs Ubuntu via WSL on his Windows PC). Warm-up first: CIDR size ('big number, small house'), DNS-first rule, public vs private subnet.

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

## Review list (things to re-quiz)
- MISSED: CIDR size is backwards from intuition. Slash counts LOCKS. /8 huge, /16 big, /24 small, /32 = 1 address. Hook: 'Big number, small house.'
- Still foggy twice: 'site can't be reached, no status code' -> check DNS first (nslookup). Hook: 'If nobody picked up, check you have the right number.'
- Private ranges: '10, 172, 192 stay home'. 10.x is NOT 'AWS' - it's private for everyone, AWS just uses it a lot.
- Subnet = network under a network (building = network, floors = subnets). Public subnet = internet needs to reach it (web server); private = no (database, backups). Wrong placement: website private = broken (loud); database public = exposed (quiet).
- NAT: 'Out yes, in no, replies only.' AWS NAT Gateway bills hourly.
- UDP glitch = dropped piece, not delay. TCP is the one that waits/delays to resend.
- Reread answers for typos that flip meaning (wrote 'can' meant 'can't').
- UDP is less RELIABLE, not less SAFE. NAT = router translates private->public ('hide behind'), not 'spoof'. Website sees home public IP, never 192.168.x (missed once).
- MISSED: A vs CNAME when the host's IP can change -> CNAME (points to a name; the host keeps its IP current). A record holds only an IP, never a name.
- MISSED: request order = find it (DNS) -> connect (port 443 + encryption) -> ask (GET /) -> get (200). Pizza analogy.
- Ports: 80 HTTP, 443 HTTPS, 22 SSH. Status families: no code = never reached server (check DNS), 4xx = your request (401 no ID, 403 not allowed, 404 not found), 5xx = server broke. Say 500, not 505.
- Interview polish: the cloud is renting compute/storage/databases, not just site hosting; give 2+ reasons. HTTPS = encryption AND proves site identity (certificate).
- Read answer letters carefully (said 'C' but meant CNAME = B).
- Grey cloud (DNS only) vs orange cloud (proxied): his site resolves straight to Vercel (76.76.21.21), not Cloudflare. Ties to Route 53 vs CloudFront.
- Don't assume who owns an IP; look it up (ipinfo.io).
- A record (name -> IP, used on apex zackhaynie.com) vs CNAME (name -> name, www -> cname.vercel-dns.com). Route 53 "Alias" exists because CNAME isn't allowed at the apex.
- DNS only sees the domain name, never the path. 404 = DNS worked, server reached, page not found. DNS failure = no status code at all.
- 307 Internal Redirect = browser upgraded http->https itself because of HSTS. 308 = server (Vercel) said "moved permanently" (apex -> www).
- Caching: "from memory cache" = browser never contacted the server; x-vercel-cache HIT/MISS = server-side cache.
- nslookup is a tool for a human to ask DNS manually; the browser does the same lookup automatically.
