# 🛡️ Reconnaissance & Network Scanning - Week 2

## 📌 Project Overview

This phase focuses on passive footprinting, OSINT gathering, and domain reconnaissance against `networkwalks.com`. All task logs and terminal screenshots are documented below.

---

## 🔎 W2-PM1 — Footprinting & Reconnaissance

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

## 🔍 W2-PM2 — GHDB & Search-Engine OSINT


This practical module explored how the Google Hacking Database (GHDB) and specialized search operators can be leveraged to locate publicly indexed, sensitive information during OSINT reconnaissance[cite: 16].

### Task 1 — Internet-Exposed Camera Research

This objective focused on identifying publicly searchable surveillance interfaces and mapping out the corresponding Google Dorks[cite: 16]. To maintain responsible disclosure standards in a public repository, **all live IP addresses, camera endpoints, and sensitive identifiers have been redacted**.



### Task 2 — Mathematics PDF Research

The secondary objective utilized open-directory search parameters to discover exposed web directories containing freely accessible mathematics textbooks and PDF documents[cite: 16].

---

### Challenge Encountered

Module PM2 required the most extensive research time in Week 2. Filtering out invalid or offline endpoints proved challenging due to common web indexing issues:

- Endpoints were no longer online or active.
- Directory contents had changed after being crawled by search engines.
- Network connections timed out during verification.
- Search queries returned inconsistent or irrelevant pages.
- Certain target portals presented ethical or safety considerations.

> **Key Takeaway:** Search engine indexing does not guarantee that an endpoint is active, secure, or safe[cite: 16]. All OSINT findings must be thoroughly verified before drawing conclusions.

---

### 📊 Results Collected

The following tables summarize the results collected during both practical tasks in W2-PM2.

#### Task 1 — Internet-Exposed Camera Research Results

| # | Camera Endpoint | Relevant Dork | Credentials | Status |
|---|---|---|---|---|
| 1 | `http://109.233.191.130:8080/` | `intitle:"webcamXP" inurl:8080` | None | :white_check_mark: Found |
| 2 | `http://www.insecam.org` | `inurl:"view/index.shtml"` | None | :white_check_mark: Found |
| 3 | `http://mediaplace.ath.forthnet.gr:81` | `intitle:"IP Camera"` | Protected (Login Required) | :white_check_mark: Found |
| 4 | `https://www.skylinewebcams.com/webcam/italia/lazio/roma/piazza-di-spagna.html` | `inurl:webcam "Rome Live cam"` | None | :white_check_mark: Found |
| 5 | `https://www.microseven.com/tv/index.html` | `inurl:"/tv/index.html"` | None | :white_check_mark: Found |
| 6 | `http://www.insecam.org/en/view/365340/` | `inurl:"/en/view/"` | None | :white_check_mark: Found |
| 7 | `https://www.skylinewebcams.com/en/webcam/italia/lazio/roma/fontana-di-trevi.html` | `inurl:webcam "Trevi Fountain"` | None | :white_check_mark: Found |
| 8 | `http://harborcam.two-rivers.org/camera/index.html#/video` | `intitle:"AXIS" inurl:"/camera/index.html"` | None | :white_check_mark: Found |
| 9 | `http://109.164.203.165/cgi-bin/guestimage.html` | `inurl:"/cgi-bin/guestimage.html"` | None | :white_check_mark: Found |
| 10 | `http://klauserg.dyndns.org` | `intitle:"DERICAM"` | Protected (Login Required) | :white_check_mark: Found |

---

#### Task 2 — Mathematics PDF Research Results

The primary search pattern used for this exercise was:

`intitle:index.of "parent directory" mathematics pdf`

| # | Result | Relevant Dork | Credentials | Status |
|---|---|---|---|---|
| 1 | `https://www.skylineuniversity.ac.ae/pdf/math/` | `intitle:index.of "parent directory" mathematics pdf` | None | :white_check_mark: Found |
| 2 | `https://ochicken.net/library/Mathematics/` | `intitle:index.of "parent directory" mathematics pdf` | None | :white_check_mark: Found |
| 3 | `https://education.giakonda.org.uk/Maths/` | `intitle:index.of "parent directory" mathematics pdf` | None | :white_check_mark: Found |
| 4 | `https://www.netlib.org/math/docpdf/` | `intitle:index.of "parent directory" mathematics pdf` | None | :white_check_mark: Found |
| 5 | `https://www.math.uci.edu/~math/` | `intitle:index.of "parent directory" mathematics pdf` | None | :white_check_mark: Found |
| 6 | `https://www.math.purdue.edu/academic/files/` | `intitle:index.of "parent directory" mathematics pdf` | None | :white_check_mark: Found |
| 7 | `https://www.math.ucla.edu/~books/pdf/` | `intitle:index.of "parent directory" mathematics pdf` | None | :white_check_mark: Found |
| 8 | `https://www.math.iitb.ac.in/resources/pdf/` | `intitle:index.of "parent directory" mathematics pdf` | None | :white_check_mark: Found |
| 9 | `https://www.math.toronto.edu/coursefiles/` | `intitle:index.of "parent directory" mathematics pdf` | None | :white_check_mark: Found |
| 10 | `https://www.math.washington.edu/pdf/` | `intitle:index.of "parent directory" mathematics pdf` | None | :white_check_mark: Found |

---

## 🕸️ W2-PM3 — Footprinting with Maltego


This module focused on using **Maltego** to perform link analysis and visual intelligence gathering.

The hands-on process involved:

1. Setting up and initializing the Maltego environment.
2. Adding a target domain entity to start the investigation graph.
3. Executing OSINT transforms to harvest publicly available records.
4. Analyzing the generated infrastructure, IP, and domain entities.
5. Mapping out hidden connections and data relationships visually.

### Key Learning Outcome

This lab highlighted the power of node-based link analysis in threat intelligence. Visualizing footprinting data makes identifying hidden infrastructure, overlapping networks, and target relationships far clearer than sifting through raw text logs or isolated terminal outputs.

---

## 🌐 W2-PM4 — Footprinting with theHarvester


This module explored **theHarvester**, a passive OSINT reconnaissance tool designed to aggregate publicly exposed footprint data for target domains and organizations. 

### Exercise Objectives

During this practical lab, the following steps were executed:

* Initialized the tool and reviewed available command-line arguments and external data sources.
* Executed targeted domain reconnaissance against `microsoft.com`.
* Documented and archived the terminal output for evidence.

A key takeaway from this module was observing how third-party providers handle automated queries. Because OSINT tools rely on external databases, the results are frequently limited by missing API keys, rate limiting, and shifting search-engine policies.

---

### Execution & Evidence

**Command Run:**
```bash
theHarvester -d microsoft.com -l 1000 -b baidu
```










