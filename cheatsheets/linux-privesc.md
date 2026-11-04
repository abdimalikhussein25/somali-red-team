# Linux Privilege Escalation Cheat Sheet

> For CTFs, labs and authorised engagements.

## First look
```bash
id; hostname; uname -a; cat /etc/os-release
sudo -l                       # what can I run as root?
ls -la /home /root 2>/dev/null
```

## Misconfigurations
```bash
# SUID binaries: compare against GTFOBins
find / -perm -4000 -type f 2>/dev/null

# Capabilities
getcap -r / 2>/dev/null

# Writable files owned by root / in PATH
find / -writable -type f -not -path "/proc/*" 2>/dev/null | grep -v "^/sys"
echo $PATH

# Cron jobs and timers
cat /etc/crontab; ls -la /etc/cron.*; systemctl list-timers
```

## Credentials
```bash
grep -rniE "pass(word)?|secret|token" /var/www /opt /home 2>/dev/null | head
cat ~/.bash_history; ls -la ~/.ssh
find / -name "*.env" -o -name "config.php" -o -name "wp-config.php" 2>/dev/null
```

## Services
```bash
ss -tlnp                      # services only listening locally
ps aux | grep root
```

## Automate (after you understand the manual steps)
- `linpeas.sh`
- `pspy`: watch processes and cron without root

Reference: [GTFOBins](https://gtfobins.github.io)
