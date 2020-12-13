# 1 Security general knowledge

## Attack surface

### Operating systems

- Linux/BSD
- macOs
- Windows

### Services and applications

- Web server: Nginx, Apache, IIS
- Database server: SQL server, Oracle, MySQL, PostgreSQL, MongoDB
- Mail server: Postfix, Exchange
- Other services: sshd, DNS, FTP server,
- Server side scripting: node.js, python, php
- Framework & CMS: Express, WordPress, Django, Joomla, CakePHP

### Your code / libraries used

Your code application and the imported libraries can contain server side or client side vulnerabilities

- injection: SQL Injection, NOSQL Injection, LDAP Injection
- Access control bypass
- Cross-Site Scripting: XSS
- Cross-site request forgery: CSRF
- XML external entity injection: XXE
- Business logic vulnerabilities
- Authentification bypass
- Information/Data exposure

### Third parties

- api
- cloud services
- partners

### People

- employees with high privileges in the information system or in the hierarchy
- Vulnerable workstations
- Social engineering: Social media (Facebook, Instagram, Linkedin,), email, phone

## Security threats

### Vulnerability score:

CVSS: [Common Vulnerability Scoring System](https://www.first.org/cvss/v3.1/specification-document)

> The Common Vulnerability Scoring System (CVSS) is a free and open industry standard for assessing the severity of computer system security vulnerabilities. CVSS attempts to assign severity scores to vulnerabilities, allowing responders to prioritize responses and resources according to threat. Scores are calculated based on a formula that depends on several metrics that approximate ease of exploit and the impact of exploit. Scores range from 0 to 10, with 10 being the most severe.
>
> [_Wikipedia: Common Vulnerability Scoring System_](https://en.wikipedia.org/wiki/Common_Vulnerability_Scoring_System)</cite>

<span style="color:blue"><b>None/Information: 0.0 </b></span>  
<span style="color:green"><b>Low: 0.1 - 3.9 </b></span>  
<span style="color:orange"><b>Medium: 4.0 - 6.9 </b></span>  
<span style="color:#e77f00"><b>High: 7.0 - 8.9 </b></span>  
<span style="color:red"><b>Critical: 9.0 - 10.0 </b></span>

### Vulnerability type(s):

- DoS: Denial of service
- Code Execution
- Overflow
- Memory Corruption
- SQL Injection
- XSS
- CSRF
- Directory Traversal
- Http Response Splitting
- Bypass something
- Gain Information
- Gain privileges
- File Inclusion

Vulnerabilities types can be combined.  
For example a buffer overflow can permit to gain a higher privilege and execute malicious code by an attacker.

## Audits

### Security audits by third parties

### Reports

## Penetration testing

### White box penetration testing

Auditors have full access

### Blackbox penetration testing

Auditors have no

### Process

- information gathering
- scanning & network/service discovery
- exploitation
- escalation privilege
- clearing tracks and maintaining control: R.A.T. & backdoor

## Reverse engineering

### Finding flaw

### Patching / cracking

## Social engineering

### phone

### email

### website

## Code review

## Exploit database and notification

### TOP 10 OWASP

web app Top 10 flaws

### CVE: common vulnerabilities and exposures

### Criticité des vulnérabilités (CVSS)

### https://www.exploit-db.com/

## Exploits

### Zero day

### Opportunisme

## tools

### debugger/disassembler

### information gathering

### port scanner

### vulnerability scanner

### Metasploit

### R.A.T: Remote Access Trojan

### Kali Linux

Kali Linux: [Official website](https://www.kali.org/)
An operating system based on Debian containing a lot, maybe too many, security tools classified by theme.
