# Nmap Notes

This file contains the concepts I learned while studying Nmap.

The notes are organized by topic instead of lesson number, making them easier to review and update as I continue learning.

---

# Contents

- Introduction to Nmap
- Hosts, Ports & Services
- Default Scan
- Host Discovery
- Target Selection
- Port Scanning
- Service Version Detection
- Operating System Detection
- Aggressive Scan
- TCP Connect Scan
- SYN Scan

---

# Introduction to Nmap

## What is Nmap?

Nmap (Network Mapper) is an open-source tool used for network discovery and security auditing.

It helps identify:

- Live hosts
- Open ports
- Running services
- Service versions
- Operating systems

Nmap is widely used by system administrators, security professionals, and penetration testers to understand how devices are exposed on a network.

---

## Why Learn Nmap?

Nmap is one of the first tools used during network reconnaissance.

Learning Nmap helps build a strong understanding of:

- Networking fundamentals
- Port scanning
- Service enumeration
- Target identification

Many other security tools rely on the information gathered by Nmap.

---

# Hosts, Ports & Services

## Host

A host is any device connected to a network.

Examples:

- Laptop
- Desktop
- Server
- Router
- Virtual Machine

Each host usually has its own IP address.

---

## Port

A port is a communication endpoint used by applications.

A single device can run many services, and each service listens on a different port.

Some common ports include:

| Port | Service |
|------|---------|
| 22 | SSH |
| 80 | HTTP |
| 443 | HTTPS |

A useful way to think about it:

- IP Address → identifies the device.
- Port → identifies the service running on that device.

---

## Service

A service is a program waiting for network connections.

For example:

- SSH service listens on Port 22.
- HTTP service listens on Port 80.
- HTTPS service listens on Port 443.

When Nmap finds an open port, it usually tries to identify the service running on that port.

---

# Default Scan

The default Nmap scan checks the most common TCP ports on a target.

It provides a quick overview of:

- Whether the host is online
- Which common ports are open
- The service associated with each open port

The default scan is usually the first step before performing more detailed scans.

---

# Host Discovery

Host Discovery is used to identify which devices are currently online.

Instead of scanning every possible IP address and port, Nmap first checks which hosts respond.

This helps reduce unnecessary scanning and saves time, especially on larger networks.

Host Discovery only determines whether a host is reachable. It does not identify open ports.

---

# Target Selection

Nmap allows different ways to specify scan targets.

Examples include:

- A single IP address
- Multiple IP addresses
- A network range
- A domain name
- A list of targets stored in a file

Choosing the correct target method depends on the size of the environment being scanned.

---

# Port Scanning

Port scanning is used to discover which services are accessible on a target.

Instead of scanning every port every time, specific ports or port ranges can be selected depending on the objective.

Port scanning is one of the most common activities during reconnaissance because it reveals which network services are available.

---

# Service Version Detection

Finding an open port is useful, but identifying the software behind that port provides much more information.

Service Version Detection attempts to determine:

- Service name
- Product name
- Software version

Knowing the software version helps identify outdated software that may contain known vulnerabilities.

---

# Operating System Detection

Operating System Detection attempts to identify the operating system running on a target.

Instead of reading system information directly, Nmap analyzes how the target responds to specially crafted network packets.

The detected operating system is displayed as a best guess rather than a guaranteed result.

---

# Aggressive Scan

Aggressive Scan combines several Nmap features into a single scan.

It performs:

- Operating System Detection
- Service Version Detection
- Default NSE Scripts
- Traceroute

This scan provides much more information than a default scan but also generates more network traffic and usually takes longer to complete.

---

# TCP Connect Scan

TCP Connect Scan performs the complete TCP Three-Way Handshake before closing the connection.

This scan works without special privileges but is generally easier to detect because the full connection is established.

---

# SYN Scan

SYN Scan sends only the initial SYN packet and does not complete the TCP connection.

Because the connection is not fully established, this scan is often referred to as a Stealth Scan.

On Linux systems, SYN Scan usually requires root privileges because it uses raw packets.

Although it is more stealthy than a TCP Connect Scan, modern security devices can still detect it.

---

# Summary

After completing these topics, I should understand:

- What Nmap is used for
- The difference between hosts, ports, and services
- How Host Discovery works
- Different ways to specify scan targets
- Why port scanning is important
- Why service versions matter
- How operating system detection works
- The difference between TCP Connect Scan and SYN Scan

Additional topics will be added as the module grows.
