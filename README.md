# Network Traffic Analysis & Threat Investigation Lab

## Project Overview

A hands-on network security lab focused on generating, capturing, and analysing network traffic to understand how suspicious communication patterns can be identified during a SOC investigation.

The project uses controlled traffic generation and packet-level analysis to investigate HTTP communication, DNS activity, unusual DNS queries, and periodic HTTP beacon-like behaviour.

The objective is to develop practical skills in network traffic analysis, threat detection, packet investigation, and evidence-based incident reporting.

## Lab Environment

| Component | Technology |
|---|---|
| Traffic generation | Windows 11 VM |
| Network sensor / server | Ubuntu Server |
| Packet capture | TCPDump |
| Packet analysis | Wireshark |
| DNS service | dnsmasq |
| HTTP service | Python HTTP server |
| Virtualisation | Oracle VirtualBox |
| Network | Host-only network |

### Lab Network

| System | IP Address | Role |
|---|---|---|
| Windows 11 VM | 192.168.56.113 | Traffic generator |
| Ubuntu Server | 192.168.56.112 | HTTP/DNS server and packet capture |
| Windows host | 192.168.56.1 | Wireshark analysis workstation |

*Addresses reflect the lab configuration during the recorded exercises.*

## Project Objectives

- Understand normal HTTP and DNS communication.
- Capture network traffic using TCPDump.
- Analyse packet flows using Wireshark.
- Identify repeated DNS queries and unusual subdomain patterns.
- Investigate periodic HTTP communication resembling beaconing.
- Interpret network indicators without relying on a single suspicious characteristic.
- Produce investigation reports supported by packet-capture evidence.

## Investigations

| No. | Investigation | Focus |
|---|---|---|
| 01 | Network baseline | HTTP requests, responses and TCP communication |
| 02 | DNS baseline | DNS queries, record types and responses |
| 03 | Repeated DNS queries | Repeated requests and timing patterns |
| 04 | Unusual DNS subdomains | Unique subdomains and DNS tunnelling indicators |
| 05 | HTTP beaconing | Periodic HTTP communication and TCP connections |

Detailed findings are available in the `investigations/` directory.

## Repository Structure

```text
network-traffic-analysis-lab/
├── README.md
├── docs/
│   ├── lab-architecture.md
│   └── investigation-methodology.md
├── pcaps/
├── investigations/
├── scripts/
└── evidence/
    └── screenshots/
```

## Tools and Skills

**Tools:** Wireshark, TCPDump, dnsmasq, Python HTTP server, PowerShell, VirtualBox.

**Skills developed:**
- Packet capture and protocol analysis
- TCP handshake and connection analysis
- HTTP request and response inspection
- DNS query and response analysis
- Beaconing pattern identification
- Network investigation and evidence documentation

## Important Investigation Notes

The traffic in this project was generated in a controlled lab environment.

The DNS exercises reproduce indicators such as repeated queries and unique subdomains. They do not implement a functional DNS tunnel.

The HTTP beaconing exercise reproduces periodic communication using benign HTTP requests. It does not involve malware or a real command-and-control server.

Suspicious indicators are treated as investigation leads, not proof of malicious activity. Conclusions are based on the available evidence and documented limitations.

## Future Work

- Controlled cleartext HTTP credential-exposure investigation.
- Additional traffic-generation scripts.
- More advanced protocol analysis and independent PCAP investigations.
- Improved evidence collection and detection logic.

## Disclaimer

This project is intended for educational and defensive cybersecurity training only. All traffic-generation activities are performed in an isolated, controlled lab environment.