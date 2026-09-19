# 🛡️ Reconnaissance & Network Scanning - Week 2

## 📌 Project Overview

This phase focuses on passive footprinting, OSINT gathering, and domain reconnaissance against `networkwalks.com`. All task logs and terminal screenshots are documented below.

---

## 🛠️ Tools & Technologies Used

* **WHOIS (`whois`):** Enumerated domain registration metadata and GoDaddy name servers.
* **WhatWeb (`whatweb`):** Identified web server technologies, CMS components, and server headers.
* **NSLookup (`nslookup`):** Resolved the target domain to its public IP address mapping.
* **cURL (`curl`):** Inspected raw HTTP response headers, caching layers, and server signatures.
* **wafw00f (`wafw00f`):** Detected active Web Application Firewall protection (**ModSecurity / SpiderLabs**).
* **DNSRecon (`dnsrecon`):** Enumerated DNS record types (A, NS, MX, SOA).

---

## 📊 Key Security Findings

* **Domain Registrar & Hosting:** Registered through GoDaddy with DNS managed via GoDaddy name servers (`NS01.DOMAINCONTROL.COM` / `NS02.DOMAINCONTROL.COM`).
* **Web Architecture:** Running on GoDaddy hosted web servers with standard HTTP/HTTPS redirection configured.
* **WAF Protection:** Actively protected by **ModSecurity (SpiderLabs)** Web Application Firewall, configured to filter malicious payloads and block unauthorized scanning signatures.
* **DNS Configuration:** Valid MX records, SOA records, and A record mappings identified without unauthorized subdomain exposures during passive enumeration.

---

## ✅ Deliverables Checklist

- [x] Executed passive footprinting using CLI reconnaissance tools.
- [x] Redirected output streams to non-empty text log files (`*.txt`).
- [x] Saved high-resolution terminal screenshots to the `images/` directory.
- [x] Verified file integrity and size via `ls -lh *.txt`.
- [x] Structured repository documentation with formatted Markdown and inline media embeds.

---

## 🛡️ Purpose of the Lab

This laboratory provides a secure, self-contained workspace dedicated to practical cybersecurity training and authorized vulnerability testing.

Key capabilities and practice areas include:

- Domain footprinting and passive reconnaissance
- DNS record analysis and enumeration
- Web application fingerprinting and header analysis
- WAF detection and identification
- Log file redirection and command-line execution documentation


## 🔍 Task 1: WHOIS Domain Lookup

Performs domain registration lookup to gather registrar, creation date, name servers, and ownership details.

**Command Executed:**

```bash
whois networkwalks.com > whois-output.txt
```

![Kali Linux running](images/whois-output.png)

---

## 🛠️ Task 2: WhatWeb Technology Detection

Identifies underlying web server technologies, CMS platforms, IP addresses, and frontend frameworks.

**Command Executed:**

whatweb networkwalks.com > whatweb-output.txt

![Kali Linux running](images/whatweb-output.png)

---

## 🌐 Task 3: NSLookup Query

Queries Domain Name System (DNS) servers to reveal the target domain's primary IP address mapping.

**Command Executed:**
nslookup networkwalks.com > nslookup-output.txt


![Kali Linux running](images/nslookup-output.png)


---

## 📑 Task 4: cURL HTTP Header Inspection

Fetches HTTP response headers to analyze server signatures, caching protocols, and set-cookie policies.

**Command Executed:**
curl -I [https://networkwalks.com](https://networkwalks.com) > curl-output.txt


![Kali Linux running](images/curl-output.png)

---

## 🛡️ Task 5: WAF Detection (wafw00f)
Fingerprints the web application to determine if an active Web Application Firewall (WAF) protects the host.


**Command Executed:**
wafw00f [https://networkwalks.com](https://networkwalks.com) -o wafw00f-output.txt


![Kali Linux running](images/wafw00f-output.png)

---

## 🔎 Task 6: DNS Reconnaissance (dnsrecon)
Enumerates DNS records (A, NS, MX, SOA) and performs sub-domain enumeration.

**Command Executed:**
dnsrecon -d networkwalks.com &> dnsrecon-output.txt


![Kali Linux running](images/dnsrecon-output.png)


---

## 📂 Output Verification

Confirms that all output logs were captured and non-empty.

**Command Executed:**
ls -lh *.txt


![Kali Linux running](images/file-verification.png)


---

## 📂 Repository Structure

```text
.
├── images/                      # Week 1 project screenshots
│   ├── import-kali-linux.png    # VirtualBox Kali Linux import configuration
│   └── kali-linux-running.png   # Kali Linux virtual machine running
├── week-2/                      # Week 2 lab directory
│   ├── images/                  # Week 2 project screenshots
│   │   ├── .gitkeep             # Directory tracking file
│   │   ├── curl-output.png      # cURL execution screenshot
│   │   ├── dnsrecon-output.png  # DNSRecon output screenshot
│   │   ├── file-verification.png# Terminal log file verification screenshot
│   │   ├── nslookup-output.png  # NSLookup query screenshot
│   │   ├── wafw00f-output.png   # WAF detection screenshot
│   │   ├── whatweb-output.png   # WhatWeb technology scan screenshot
│   │   └── whois-output.png     # WHOIS query screenshot
│   ├── .gitkeep                 # Directory tracking file
│   ├── curl-output.txt          # HTTP headers scan log
│   ├── dnsrecon-output.txt      # DNS enumeration log
│   ├── nslookup-output.txt      # Domain IP resolution log
│   ├── wafw00f-output.txt       # WAF detection scan log
│   ├── whatweb-output.txt       # Web technology fingerprint log
│   ├── whois-output.txt         # Domain registration log
│   └── README.md                # Week 2 lab documentation
├── .gitignore                   # Excludes VirtualBox VM and system files
└── README.md                    # Main repository README file
```

---


