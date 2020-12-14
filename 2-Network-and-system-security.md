# Network and system security

Your application will run on servers.
A system hardening of you all your remote hosts is needed

## Operating system hardening OWASP 6

### Lynis

[Lynis](https://cisofy.com/lynis/) is a battle-tested security tool for systems running Linux, macOS, or Unix-based operating system. It performs an extensive health scan of your systems to support system hardening and compliance testing.

### Remove unused software

```zsh
dpkg --list
dpkg --info packageName
apt-get remove packageName
```

### Keep Linux Kernel and software up to date: OWASP 9

```zsh
apt-get update && apt-get upgrade
```

### Firewall

`ufw`: https://help.ubuntu.com/community/UFW
`iptables`: https://doc.ubuntu-fr.org/iptables

### Find all activated and running services

```zsh
systemctl --type=service --state=active
systemctl --type=service --state=running
```

### find all running processes

```zsh
ps aux
pstree
ps axjf
```

### Find listening network ports

from local:

```zsh
netstat -tulpn
```

from remote (listening ports on localhost are not reachable from remote):

```zsh
sudo nmap -v -sV -sT -p0-65535 -A -O --osscan-guess IpOrUrl -T5
```

### Don't use a X11 graphical user interface

```zsh
sudo apt purge 'x11-*'
sudo apt autoremove
```

### Use ssh for remote connection

https://doc.ubuntu-fr.org/ssh

### Use SSL certificate for web server OWASP 3

https://letsencrypt.org/

### Logging & Monitoring: OWASP 10

#### journalctl

Most Linux distros have `systemd` to manage services. Systemd catches the output of these services and writes them to the journal. The journal is written in a binary format, so you’ll use `journalctl` to explore it.
The journal storage defaults to being in-memory. You can change the default to be persistent by opening `/etc/systemd/journald.conf` and changing the `Storage=` line from `auto` to `persistent` and restart the `journald` service with:

```zsh
sudo systemctl restart systemd-journald
```

https://www.loggly.com/ultimate-guide/using-journalctl/  
https://sematext.com/blog/linux-logs/

#### Application logs

All logs are stored by default in `/var/log/` directory.

- **Nginx**: `/var/log/nginx/access.log` , `/var/log/nginx/error.log`
- **Postfix**: `/var/log/maillog`, `/var/log/mail`
- **PostgreSQL**: `/var/log/postgresql/postgresql-11-main.log`

#### System monitoring

monit: https://mmonit.com/monit/

#### Security monitoring

IDS: Intrusion and Detection System
IPS: Intrusion and Prevention System
Snort: https://www.snort.org/

## Vulnerability scanning

OS, Services and web vulnerabilities scanning with [Nessus](https://fr.tenable.com/products/nessus?tns_redirect=true)
