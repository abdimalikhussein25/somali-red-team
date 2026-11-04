# Learning Roadmap · Jidka Waxbarashada

Six stages. Don't skip ahead: every stage builds on the one before. Rough times assume ~10 hours a week.

```
0 Foundations → 1 Networking → 2 Web → 3 Pentest workflow → 4 Bug bounty / CTF → 5 Red team
   (4 wks)        (4 wks)      (8 wks)       (6 wks)              (ongoing)          (advanced)
```

## Stage 0: Foundations · Aasaaska
- Linux command line: files, permissions, processes, pipes, `grep`/`find`/`awk`
- Bash scripting and basic Python (requests, files, loops)
- How a computer boots, what an OS does, users and privileges
- **Done when:** you can write a script that reads a list of URLs and saves each status code.

## Stage 1: Networking · Shabakadaha
- OSI vs TCP/IP, IP addressing and subnets, TCP vs UDP, ports
- DNS, HTTP/HTTPS, TLS basics
- Tools: `ping`, `traceroute`, `dig`, `nmap`, Wireshark
- **Done when:** you can explain what happens, packet by packet, when you open a website.

## Stage 2: Web Application Security · Amniga Websaydhada
- HTTP in depth: methods, headers, cookies, sessions, CORS
- OWASP Top 10: broken access control, injection (SQLi), XSS, SSRF, authentication flaws, misconfiguration
- Burp Suite: proxy, repeater, intruder
- Practise every class on PortSwigger Web Security Academy
- **Done when:** you have solved the Apprentice labs for every OWASP Top 10 category.

## Stage 3: Penetration Testing Workflow · Habka Pentest-ka
- Methodology: recon → enumeration → exploitation → post-exploitation → reporting
- Linux and Windows privilege escalation basics
- Active Directory fundamentals
- Writing a professional report (see [methodology](../methodology/web-app-pentest.md))
- **Done when:** you have rooted 20 easy/medium machines and written a writeup for each.

## Stage 4: Bug Bounty & CTF
- Pick one program with a wide scope, learn the app deeply, report one valid bug
- Play CTFs as a team, weekly in our Discord
- **Done when:** your first accepted report or top-50% CTF finish.

## Stage 5: Red Team Operations
- Adversary emulation and MITRE ATT&CK
- Command & control concepts, OPSEC, phishing simulation (authorised only)
- Active Directory attacks in depth, cloud attack paths (AWS/Azure)
- Detection engineering: understand what the blue team sees

## Certifications (optional)
Skills first, certificates second. When you are ready: eJPT → PNPT or OSCP → CRTO / OSEP.
