# PENETRATION-TESTING-REPORT
# 🔐 Footprinting and Network Scanning

**Author:** Nithin K  
**Operating System:** Kali Linux & Windows  
**Tools Used:** WHOIS, NSLookup, DNSRecon, cURL, WAFW00F, WhatWeb, Nmap, Zenmap  
**Category:** Cybersecurity | Information Gathering | Network Reconnaissance

---

## 📌 Project Overview

This project documents a practical cybersecurity exercise focused on understanding the footprinting and network scanning phases of security assessment.

The exercise involved collecting publicly available domain information, examining DNS configurations, identifying web technologies, detecting Web Application Firewall (WAF) protection, and discovering active hosts within a local network.

Different reconnaissance utilities were used to understand how security professionals gather information before conducting a detailed security assessment.

**Note:** Domain reconnaissance should only be performed against authorized targets. Network discovery was conducted within the available lab network.

---

## 🎯 Objectives

- Understand the fundamentals of footprinting.
- Retrieve domain registration information.
- Investigate DNS records and domain resolution.
- Examine HTTP response headers.
- Identify web server technologies and application frameworks.
- Detect the presence of Web Application Firewall protection.
- Discover active devices within a local network.
- Understand the role of reconnaissance in security assessments.

---

## 🛠️ Tools and Technologies

| Tool | Purpose |
|---|---|
| WHOIS | Domain registration information |
| NSLookup | DNS queries and IP resolution |
| DNSRecon | DNS record enumeration |
| cURL | HTTP header inspection |
| WAFW00F | Web Application Firewall identification |
| WhatWeb | Website technology fingerprinting |
| Nmap | Network discovery and scanning |
| Zenmap | Graphical interface for Nmap |

---

# 🔍 Practical Implementation

## 1. WHOIS Lookup

**Objective:** Collect domain registration details.

**Command:**

```bash
whois networkwalks.com
```

**Observations:**

- Identified the domain registrar.
- Retrieved domain creation and expiration dates.
- Examined the registered nameservers.
- Observed domain status information.
- Reviewed available registration details.

**Result:** Domain registration information was successfully retrieved.
<img width="1600" height="900" alt="whois" src="https://github.com/user-attachments/assets/0289e537-de97-4855-838e-a04b21796b21" />


---

## 2. DNS Lookup Using NSLookup

**Objective:** Identify the IP address associated with the target domain.

**Command:**

```bash
nslookup networkwalks.com
```

**Observations:**

- DNS resolver: 1.1.1.1
- Resolved IPv4 address: 192.232.216.135
- Received a non-authoritative DNS response.

**Result:** The domain was successfully resolved to its associated IP address.
<img width="1600" height="900" alt="nslookup" src="https://github.com/user-attachments/assets/c907cd9e-44f9-435e-8551-7bbc4c6ed781" />



---

## 3. DNS Enumeration Using DNSRecon

**Objective:** Examine DNS records associated with the domain.

**Command:**

```bash
dnsrecon -d networkwalks.com
```

**Observations:**

The enumeration process identified several DNS record types, including:

- A Records
- NS Records
- SOA Records
- TXT Records
- SRV Records

The output also revealed nameserver information, mail-related DNS entries, and domain verification records.

**Result:** DNS enumeration completed successfully, with eight records reported by the tool.
<img width="1600" height="900" alt="dnsrecon" src="https://github.com/user-attachments/assets/3a38a62e-cc33-4219-b15c-70edff4383d1" />



---

## 4. HTTP Header Analysis Using cURL

**Objective:** Examine the HTTP response and identify server-related information.

**Command:**

```bash
curl -I https://networkwalks.com
```

**Observations:**

- HTTP response: 301 Moved Permanently
- Web server: Apache
- HTTPS communication was used.
- WordPress-related response information was observed.
- Cookie and security-related headers were identified.

**Result:** HTTP response headers were successfully retrieved and analyzed.
<img width="1600" height="900" alt="curl" src="https://github.com/user-attachments/assets/40b48cfa-d3d2-4e0d-bf80-c891537d9d40" />

---

## 5. Web Application Firewall Detection Using WAFW00F

**Objective:** Determine whether the website uses Web Application Firewall protection.

**Command:**

```bash
wafw00f https://networkwalks.com
```

**Observations:**

The tool identified ModSecurity (SpiderLabs) as the Web Application Firewall protecting the website.

The detection process completed using two requests.

**Result:** WAF protection was identified successfully.
<img width="1600" height="900" alt="wafwoof" src="https://github.com/user-attachments/assets/d0f3e1ce-6edc-4347-9770-e0cde12d72c0" />


---

## 6. Website Technology Identification Using WhatWeb

**Objective:** Discover the technologies and components used by the website.

**Command:**

```bash
whatweb networkwalks.com
```

**Observations:**

The scan identified several technologies and components, including:

- Apache Web Server
- WordPress CMS
- jQuery 3.7.1
- WordPress Download Manager
- Google Tag Manager
- HTML5
- HTTPS
- Cookie-related information

**Result:** Multiple website technologies and application components were identified.
<img width="1600" height="900" alt="whatweb" src="https://github.com/user-attachments/assets/05640631-dbf4-4fe8-8bba-3a7bbe32f35a" />


---

## 7. Network Discovery Using Nmap and Zenmap

**Objective:** Identify active hosts within the local network.

The Windows system's network configuration was inspected using:

```cmd
ipconfig
```

The local network range was identified as:

```text
10.182.236.0/24
```

**Nmap Command:**

```bash
nmap -sn 10.182.236.0/24
```

**Observations:**

- Total IP addresses scanned: 256
- Active hosts discovered: 2
- Host 1: 10.182.236.80
- Host 2: 10.182.236.74
- Scan duration: 9.65 seconds

Zenmap was also used to visualize the discovered hosts and examine the network topology.

**Result:** Two active hosts were identified within the scanned network range.
<img width="961" height="691" alt="nmap" src="https://github.com/user-attachments/assets/e0affd96-280d-4fe3-b20e-cdf68f55b457" />
<img width="1916" height="1018" alt="topology" src="https://github.com/user-attachments/assets/ffc76f8f-cf03-4e95-a693-e74b6a72ae0c" />



---

# 📊 Overall Findings

| Assessment Activity | Outcome |
|---|---|
| WHOIS Lookup | Domain registration details collected |
| DNS Lookup | IP address successfully resolved |
| DNSRecon | Eight DNS records reported |
| HTTP Analysis | HTTP response headers examined |
| WAF Detection | ModSecurity identified |
| WhatWeb | Website technologies identified |
| Network Discovery | Two active hosts discovered |
| Zenmap | Network topology visualized |

---

## 📚 Key Learnings

Through this practical exercise, I gained experience in:

1. Understanding different footprinting techniques.
2. Investigating domain and DNS information.
3. Examining web server response headers.
4. Identifying website technologies and security mechanisms.
5. Understanding the purpose of Web Application Firewalls.
6. Performing host discovery using Nmap.
7. Visualizing network information using Zenmap.

---

## ⚠️ Important Note

This repository is intended for educational and cybersecurity learning purposes.

All testing and scanning activities should be conducted only on systems, networks, and domains for which proper authorization has been obtained.

The observations documented here represent reconnaissance results and do not establish the presence of exploitable vulnerabilities.

---

## 👩‍💻 Author

**Nithin S**

Cybersecurity Student | Aspiring Security Professional

---

⭐ *Learning cybersecurity one practical exercise at a time!*

#CyberSecurity #Footprinting #NetworkScanning #KaliLinux #Nmap #DNSRecon #EthicalHacking #InformationSecurity
