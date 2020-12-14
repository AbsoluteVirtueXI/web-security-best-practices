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

### Vulnerability identification: Common Vulnerabilities and Exposures ID

All vulnerabilities are identified by a `CVE` id.
https://cve.mitre.org references all known CVE.  
https://nvd.nist.gov can give additional information about a CVE.  
(CVE-2020-28037)[https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2020-28037] is the CVE-ID of a wordpress vulnerability which might allow an attacker to perform a new installation, leading to remote code execution (as well as a denial of service for the old installation).

### Vulnerability score:

CVSS: [Common Vulnerability Scoring System](https://www.first.org/cvss/v3.1/specification-document)

> The Common Vulnerability Scoring System (CVSS) is a free and open industry standard for assessing the severity of computer system security vulnerabilities. CVSS attempts to assign severity scores to vulnerabilities, allowing responders to prioritize responses and resources according to threat. Scores are calculated based on a formula that depends on several metrics that approximate ease of exploit and the impact of exploit. Scores range from 0 to 10, with 10 being the most severe.
>
> [_Wikipedia: Common Vulnerability Scoring System_](https://en.wikipedia.org/wiki/Common_Vulnerability_Scoring_System)</cite>

**None/Information**: 0.0  
**Low**: 0.1 - 3.9  
**Medium**: 4.0 - 6.9  
**High**: 7.0 - 8.9  
**Critical**: 9.0 - 10.0

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
For example a buffer overflow on a service can permit to execute code and gain a higher privilege on the remote host.

### Web app vulnerabilities

OWASP: [The Open Web Application Security Project](https://owasp.org/)
Each year a [TOP 10 of most critical security risks](https://owasp.org/www-project-top-ten/) to web applications is released by the OWASP foundation.

## Finding vulnerabilities

### Secure code review

An automated or manual code review for finding vulnerabilities in source code.
It should not be performed by the code's author.

- Check best practices
- For web app: search for OWASP TOP 10
- Check dependency versions and vulnerabilities
- Check Identity and Authentification code
- Check for Authorization code
- Check for User credentials management code
- Check for Error handling code
- Check for logging code
- Check for session management code: cookies, session id
- Check for input validation: input fields, upload,...

The scope of a secure code review is all the source code of the application.

### Audits / Vulnerability assessments

An automated or manual scanning for finding vulnerabilities on running applications, web sites or servers.
A mix of tools and applications have to be used to maximize findings. A list available tools can be found [here](https://owasp.org/www-community/Vulnerability_Scanning_Tools).

The scope of a vulnerability assessment can be a range of ip addresses or the url of an application.  
Vulnerability scanning check vulnerabilities on client and server side.  
Often a vulnerability scanning is performed automatically and periodically.

### Penetration testing

Penetration testing is a manual process.  
The objective is not to find all known vulnerabilities in an information system, but to find a way to break into the system.  
While vulnerability assessments find security threats and report these flaws, penetration testings exploit these flaws for gaining access.  
Vulnerability exploitations can be made with the [Metasploit framework](https://www.metasploit.com/) or by exploit code found for example on (ExploitDB)[https://www.exploit-db.com]

#### White-box penetration testing

Penetration testers are given full access to source code, architecture documentation and so forth. The main challenge with white-box testing is sifting through the massive amount of data available to identify potential points of weakness, making it the most time-consuming type of penetration testing.  
White-box penetration testers are able to perform code analysis.

#### Black-box penetration testing

The penetration tester is placed in the role of the average hacker, with no internal knowledge of the target system. Testers are not provided with any architecture diagrams or source code that is not publicly available. A black-box penetration test determines the vulnerabilities in a system that are exploitable from outside the network.

#### Process

- information gathering / Open source intelligence gathering
- Social engineering: Phone, email, malicious website, social media
- scanning & network/services discovery
- exploitation
- escalation privilege
- clearing tracks and maintaining control: R.A.T. & backdoor

#### Reports

After a vulnerability assessment or a penetration test a report is written.
It should contain:

- vulnerabilities found
- severity score of these vulnerabilities
- exploitation path if it is a penetration test
- recommendation, remediation and how to fix issues

example of a penetration test report [here](https://static1.squarespace.com/static/589316f3cd0f68e6bd715655/t/5d7ce2ed69433d1c3e3f7021/1568465657128/SAMPLE+Security+Testing+Findings.pdf)

## Patching and fixing issues

This is the process of installing updates and patches for fixing issues.  
If the vulnerable code or application come from a third party or is open-source, an upgrade to the latest secured version is needed.  
If the issues come from your code, you will have to fix this manually by yourself.

## Vulnerabilities and Exploits databases

Known vulnerabilities and exploits are referenced on online databases

### CVE: common vulnerabilities and exposures

https://cve.mitre.org/cve/search_cve_list.html

### NVD: National Vulnerability Database from NIST

https://nvd.nist.gov/vuln/search

### ExploitDB

https://www.exploit-db.com/

### Rapid7

https://www.rapid7.com/db/?type=nexpose

### Cxsecurity

https://cxsecurity.com/exploit/

### Packet Storm

https://packetstormsecurity.com/files/tags/exploit/

### 0day.today

https://en.0day.today/

## tools

A list of available tools classified by security field: https://tools.kali.org/tools-listing
They are all installed on Kali Linux: [Official website](https://www.kali.org/)
Kali Linux is an operating system based on Debian containing a lot, maybe too many, security tools.
