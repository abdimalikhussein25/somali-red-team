# Recon Cheat Sheet

> Only against targets you are authorised to test. See [ETHICS.md](../ETHICS.md).

## Subdomains
```bash
# Certificate transparency
curl -s "https://crt.sh/?q=%25.example.com&output=json" | jq -r '.[].name_value' | sort -u

# Passive enumeration
subfinder -d example.com -silent | tee subs.txt

# Which ones are alive?
cat subs.txt | httpx -silent -status-code -title -tech-detect
```

## DNS
```bash
dig example.com ANY +noall +answer
dig example.com MX +short
dig example.com TXT +short          # SPF, DMARC, verification tokens
dig axfr @ns1.example.com example.com   # zone transfer (should fail)
```

## Ports & services
```bash
nmap -sC -sV -oA initial target            # default scripts + versions
nmap -p- --min-rate 2000 -oA allports target
nmap -sU --top-ports 50 target             # common UDP
```

## Web content discovery
```bash
ffuf -u https://target/FUZZ -w /usr/share/seclists/Discovery/Web-Content/raft-medium-directories.txt -mc 200,301,302,403
ffuf -u https://target/FUZZ -w words.txt -e .php,.bak,.zip,.env
```

## Historical URLs & JS
```bash
waybackurls example.com | sort -u > urls.txt
cat urls.txt | grep -E "\.js$" | httpx -silent | tee js.txt
# Look inside JS for API routes, keys and hidden endpoints
```

## Quick wins to check
- `/.git/HEAD`, `/.env`, `/backup.zip`, `/server-status`
- `/robots.txt`, `/sitemap.xml`
- `/swagger`, `/api-docs`, `/graphql`
- Default credentials on admin panels
