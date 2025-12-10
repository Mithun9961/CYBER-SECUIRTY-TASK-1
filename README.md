# Network Scanning & Traffic Analysis Project

## Project Description
This project documents a basic network reconnaissance and traffic analysis task performed on a local network. The goal was to identify active hosts, enumerate open services, and analyze network traffic to understand normal scan behavior using standard cybersecurity tools.

---

## Objectives
- Perform host discovery on a local subnet
- Identify open, closed, and filtered TCP ports
- Analyze network traffic generated during scanning
- Document findings with scan outputs and packet captures

---

## Tools & Environment
- **Nmap 7.95** – Network scanning and service enumeration
- **Wireshark** – Packet capture and protocol analysis
- **Kali Linux (Live Boot)** – Testing environment
- **Target Network:** 192.168.1.0/24 (Local LAN)

---

## Files Included
- `scan_results.xml`  
  Nmap SYN scan results in XML format containing host discovery and port states.

- `wireshark_scan.pcapng`  
  Packet capture file recorded during the scan for traffic analysis.

- `README.md`  
  Documentation explaining the task, methodology, and results.

---

## Methodology

### Step 1: Network Scanning
A TCP SYN scan was performed on the local subnet to identify live systems and exposed services.

Command used:
nmap -sS 192.168.1.0/24 -oX scan_results.xml

---


---

### Step 2: Scan Findings

#### Host: 192.168.1.1
- Status: Online
- Open Ports:
  - 21 – FTP
  - 53 – DNS
  - 80 – HTTP
  - 443 – HTTPS
- Filtered Ports:
  - 22 – SSH
  - 23 – Telnet

This host appears to be the network gateway or router providing core services.

#### Host: 192.168.1.11
- Status: Online
- Open Ports: None detected

This host is reachable but does not expose TCP services, likely due to firewall restrictions.

---

### Step 3: Traffic Analysis
The packet capture file was analyzed using Wireshark to observe:
- ARP broadcasts for host discovery
- TCP SYN and SYN-ACK packets generated during scanning
- Normal DNS query/response activity
- Standard HTTP/HTTPS traffic

No abnormal or malicious traffic patterns were observed during analysis.

---

## Results & Observations
- Two live hosts were detected in the subnet
- Critical services such as HTTP, HTTPS, DNS, and FTP were identified on the gateway
- Network behavior matched expected patterns for a SYN-based scan
- Traffic analysis confirmed normal and controlled scan activity

---

## Conclusion
This project successfully demonstrates fundamental skills in network enumeration and traffic analysis. The collected artifacts provide clear evidence of scan execution and network behavior, making the project suitable for educational and cybersecurity practice purposes.

---

## Disclaimer
All scanning and analysis activities were conducted on a controlled network with proper authorization. This project is intended strictly for educational and defensive security use.
