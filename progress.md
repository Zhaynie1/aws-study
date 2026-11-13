# AWS SAA progress

Exam target: Fri 2027-01-15 (not booked yet; book on Day 41, Dec 28)
Next session: Finish Day 1: quick recap of the 5-step URL story, then 10 exam questions + 3 interview questions. Then Day 2.

## Completed days
(none yet)

## How he learns best
- Plain-English story first, labels/jargon after. Too many terms at once = frustration.
- Show a worked example before asking open questions; fill-in-the-blank works better than "explain everything".
- Explain why something matters (troubleshooting a broken client site) before drilling it.
- Windows laptop: curl/PowerShell commands failed; browser DevTools (F12 > Network, Disable cache, Preserve log, Incognito) worked well.

## Day 1 notes (in progress)
- Done: Learn (AWS Cloud Practitioner Essentials Module 1 + freeCodeCamp SAA intro, took notes), Build (nslookup, DevTools headers), Break (404 path, http->https->www redirect chain). Told the 5-step URL story back correctly in his own words.
- Not done yet: 10 exam questions + 3 interview questions.
- Neat find: x-vercel-id shows iad1 = Washington DC, i.e. AWS us-east-1. Vercel runs on AWS.

## Practice exam scores
(none yet)

## Review list (things to re-quiz)
- Grey cloud (DNS only) vs orange cloud (proxied): his site resolves straight to Vercel (76.76.21.21), not Cloudflare. Ties to Route 53 vs CloudFront.
- Don't assume who owns an IP; look it up (ipinfo.io).
- A record (name -> IP, used on apex zackhaynie.com) vs CNAME (name -> name, www -> cname.vercel-dns.com). Route 53 "Alias" exists because CNAME isn't allowed at the apex.
- DNS only sees the domain name, never the path. 404 = DNS worked, server reached, page not found. DNS failure = no status code at all.
- 307 Internal Redirect = browser upgraded http->https itself because of HSTS. 308 = server (Vercel) said "moved permanently" (apex -> www).
- Caching: "from memory cache" = browser never contacted the server; x-vercel-cache HIT/MISS = server-side cache.
- nslookup is a tool for a human to ask DNS manually; the browser does the same lookup automatically.
