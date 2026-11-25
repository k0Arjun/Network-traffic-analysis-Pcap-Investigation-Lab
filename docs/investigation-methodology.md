# Network Investigation Methodology

The following workflow is used throughout the project.

## 1. Understand the Scenario
Identify the network behaviour being investigated and understand how it may appear in legitimate and malicious environments.

## 2. Generate Controlled Traffic
Use the Windows VM to generate repeatable network activity against the Ubuntu lab server.

## 3. Capture Network Traffic
Use TCPDump to capture packets on the VirtualBox host-only interface and save the output as a PCAP file.

## 4. Analyse with Wireshark
Inspect:
- Source and destination IP addresses
- Source and destination ports
- Protocols
- TCP connection establishment
- DNS queries and responses
- HTTP requests and responses
- Communication timing and frequency

## 5. Identify Indicators
Look for unusual or repeated patterns, including:
- Repeated DNS requests
- Unique or unusually long DNS subdomains
- Regular communication intervals
- Repeated connections to the same destination
- Unexpected HTTP behaviour

## 6. Correlate and Interpret
A single indicator is not sufficient to establish malicious activity. Consider legitimate explanations and identify what additional endpoint, process, DNS, or reputation evidence would be required.

## 7. Document Findings
Each investigation should record:
- Objective
- Lab environment
- Tools and filters
- Observations
- Analysis
- Conclusion
- Evidence and limitations

## Investigation Principle

Distinguish between an observed fact, a possible explanation, and a confirmed conclusion. Do not label simulated traffic as malware or confirmed command-and-control activity.