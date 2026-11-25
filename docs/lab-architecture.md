# Lab Architecture

## Overview

The lab uses two virtual machines and a Windows host system to generate, capture, and analyse controlled network traffic.

## Components

### Windows 11 VM — Traffic Generator
- Generates HTTP requests using PowerShell and curl.
- Performs DNS lookups using nslookup.
- Initiates client-side network connections.

### Ubuntu Server VM — Network Service and Capture
- Hosts a Python HTTP server.
- Runs dnsmasq for controlled DNS resolution.
- Captures packets using TCPDump.
- Stores PCAP files for later investigation.

### Windows Host — Analysis Workstation
- Runs Wireshark.
- Opens and analyses PCAP files copied from Ubuntu.
- Maintains the GitHub project repository.

## Network Configuration

The virtual machines communicate through a VirtualBox host-only network.

| System | IP Address |
|---|---|
| Windows host | 192.168.56.1 |
| Ubuntu Server | 192.168.56.112 |
| Windows 11 VM | 192.168.56.113 |

## Traffic Flow

1. Windows 11 generates controlled network traffic.
2. Traffic reaches the Ubuntu server over the host-only network.
3. TCPDump captures the packets on the Ubuntu host-only interface.
4. PCAP files are copied to the Windows host.
5. Wireshark is used to inspect and investigate the captured traffic.

## Security Scope

All exercises use benign, controlled traffic. No external target systems are involved in the intended simulations.