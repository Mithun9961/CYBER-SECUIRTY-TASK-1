Network Scanning & Traffic Analysis – Task Summary

This repository contains all artifacts used to complete the network scanning and traffic-analysis task, including Nmap scan results, packet-capture files, and supporting documentation.

1. Objective

The objective of this task was to perform:

A network discovery scan on the local subnet (192.168.1.0/24).

Service enumeration of active hosts.

Traffic analysis using Wireshark to identify any notable patterns or security-relevant activity.

Consolidate results and provide evidence (logs, datasets, screenshots) with explanations.

2. Tools Used

Nmap 7.95 – Network scanning and service enumeration.

Wireshark – Packet capture and protocol analysis.

Kali Linux (Live Boot) – Execution environment for scanning and monitoring.

3. Files Included

scan_results.xml – Raw Nmap scan output for 192.168.1.0/24 

scan_results

wireshark_scan.pcapng – Packet capture taken during scanning and traffic inspection.

Screenshots (if added) – Evidence of commands executed and results observed.

README.md – Explanation of methodology and findings.

4. What I Did
4.1 Nmap Scan

Executed a SYN scan against the entire /24 subnet to identify live hosts and open services:

nmap -sS 192.168.1.0/24 -oX scan_results.xml

Findings:

Two hosts were discovered:

192.168.1.1

Open ports: 21 (FTP), 53 (DNS), 80 (HTTP), 443 (HTTPS)

Ports 22 (SSH) and 23 (Telnet) appeared filtered.

192.168.1.11

No open TCP ports detected.

Interpretation:

192.168.1.1 is likely the router or gateway, running common management services.

Exposed FTP and HTTP services indicate potential areas for further security review.

Host 192.168.1.11 is alive but not exposing TCP services, possibly due to firewalling.

4.2 Wireshark Traffic Analysis

Review of the .pcapng file focused on:

ARP broadcasts to discover local hosts.

TCP SYN packets from the Nmap scan.

DNS queries and responses.

Any anomalies (e.g., repeated retransmissions, suspicious traffic).

Observations:

Packet flow matches expected behaviour for a network discovery and port scan.

No evidence of malicious outbound or inbound traffic during the capture.

5. Conclusion

The task successfully demonstrated basic network enumeration and traffic analysis.
The included files provide raw evidence of the scanning process, device responses, and overall network behavior.
