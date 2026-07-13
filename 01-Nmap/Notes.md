# Nmap Notes

This file contains the concepts learned while studying Nmap.

The notes are organized by topic so they can be updated easily as new lessons are completed.

---

# Contents

- Introduction to Nmap
- Hosts, Ports and Services
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

## Overview

Nmap (Network Mapper) is an open-source tool used for network discovery and security auditing.

It helps identify devices connected to a network and provides information about the services running on those devices.

Nmap is one of the most commonly used tools during the reconnaissance phase of penetration testing.

---

## Why Learn Nmap?

Learning Nmap helps build a strong foundation in networking and reconnaissance.

It can be used to:

- Discover live hosts
- Find open ports
- Identify running services
- Detect software versions
- Guess the target operating system

Many penetration testing tools depend on the information collected by Nmap.

---

## Things Worth Remembering

- Nmap is mainly a reconnaissance tool.
- It does not exploit vulnerabilities.
- Information collected by Nmap is often used by other security tools.

---

## Common Mistake

Many beginners think Nmap is an exploitation tool.

Its primary purpose is information gathering.

---

# Hosts, Ports and Services

## Host

A host is any device connected to a network.

Examples include:

- Laptop
- Desktop
- Server
- Router
- Virtual Machine

Every host usually has its own IP address.

---

## Port

A port is a logical communication endpoint used by network applications.

One device can run multiple services, and each service normally listens on a different port.

Common ports:

| Port | Service |
|------|----------|
| 22 | SSH |
| 80 | HTTP |
| 443 | HTTPS |

Think of it like this:

- IP Address → House
- Port → Door
- Service → Person inside the room

---

## Service

A service is a program waiting for incoming network connections.

Examples:

SSH Service → Port 22

HTTP Service → Port 80

HTTPS Service → Port 443

When an open port is found, Nmap attempts to identify the service running behind it.

---

## Things Worth Remembering

Host ≠ Port

Port ≠ Service

All three work together.

---

## Common Mistake

Confusing ports with services.

Port 80 is not HTTP itself.

Port 80 is where the HTTP service usually listens.

---

# Default Scan

## Overview

Running Nmap without additional scan options performs a default TCP scan.

This scan checks the most common TCP ports on the target.

It quickly answers questions such as:

- Is the host online?
- Which common ports are open?
- Which common services are available?

---

## Why It Matters

The default scan is usually the first step before running more detailed scans.

It provides a quick overview without generating too much traffic.

---

## Things Worth Remembering

Default scan ≠ Scan every port.

It scans the default top TCP ports.

---

## Common Mistake

Assuming the default scan checks all 65,535 ports.

It does not.

---

# Host Discovery

## Overview

Host Discovery checks whether a target device is online before performing a port scan.

Instead of scanning every possible address, Nmap first identifies active hosts.

---

## Why It Matters

Finding active hosts first:

- Saves time
- Reduces unnecessary traffic
- Makes larger network scans more efficient

---

## Things Worth Remembering

Host Discovery only answers one question:

"Is this host online?"

It does NOT identify open ports.

---

## Common Mistake

Thinking Host Discovery performs a port scan.

It does not.

---

# Quick Review

✔ Nmap is used for reconnaissance.

✔ Hosts are devices.

✔ Ports are communication endpoints.

✔ Services are applications listening on ports.

✔ Default Scan checks common TCP ports.

✔ Host Discovery only identifies active hosts.

---

# Target Selection

## Overview

Before starting a scan, Nmap needs to know which target should be scanned.

A target can be:

- A single IP address
- Multiple IP addresses
- A network range
- A domain name
- A list of targets stored in a file

Choosing the correct target method depends on the environment and the purpose of the scan.

---

## Why It Matters

Different situations require different target selection methods.

Examples:

- One server → Single IP
- Small network → Network range
- Many hosts → Target list file

Using the correct target method makes scanning more organized and efficient.

---

## Things Worth Remembering

- Nmap supports IP addresses and domain names.
- Large environments are easier to manage using a target list file.
- Always verify the target before starting a scan.

---

## Common Mistake

Scanning the wrong network because the target was entered incorrectly.

Always double-check the IP address or domain before scanning.

---

# Port Scanning

## Overview

Port scanning is used to discover which network services are accessible on a target.

Each open port usually represents a service waiting for incoming connections.

Knowing which ports are open helps build a picture of the target system.

---

## Why It Matters

Open ports reveal available services.

These services may:

- Provide useful information
- Require further investigation
- Contain outdated software

Port scanning is one of the most important steps during reconnaissance.

---

## Things Worth Remembering

Open port ≠ Vulnerable service.

Further enumeration is always required.

---

## Common Mistake

Assuming every open port contains a vulnerability.

An open port only tells us a service is available.

---

# Service Version Detection

## Overview

After identifying open ports, the next step is determining what software is running.

Service Version Detection attempts to identify:

- Service name
- Product name
- Software version

---

## Why It Matters

Many known vulnerabilities affect specific software versions.

Knowing the version helps during vulnerability research.

---

## Things Worth Remembering

- Version detection provides more information than a normal port scan.
- Results are best-effort and may not always be exact.

---

## Common Mistake

Assuming every detected version is 100% accurate.

Some services intentionally hide version information.

---

# Operating System Detection

## Overview

Operating System Detection attempts to identify the operating system running on the target.

Instead of reading system files, Nmap analyzes how the target responds to specially crafted packets.

The result is displayed as the most likely operating system.

---

## Why It Matters

Knowing the operating system helps choose the correct tools and techniques for further assessment.

---

## Things Worth Remembering

Operating System Detection provides an estimate, not a guarantee.

---

## Common Mistake

Treating the detected operating system as absolute truth.

Always verify important findings using additional methods.

---

# Aggressive Scan

## Overview

Aggressive Scan combines several Nmap features into one scan.

It performs:

- Service Version Detection
- Operating System Detection
- Default NSE Scripts
- Traceroute

This provides much more information than a standard scan.

---

## Why It Matters

Aggressive Scan saves time by collecting multiple types of information in a single scan.

---

## Things Worth Remembering

- Produces more network traffic.
- Usually takes longer than a default scan.
- Suitable for detailed reconnaissance.

---

## Common Mistake

Running Aggressive Scan on every target without considering the additional time and traffic it generates.

---

# TCP Connect Scan

## Overview

TCP Connect Scan completes the full TCP Three-Way Handshake before closing the connection.

Because a complete connection is established, this scan is reliable and does not require raw packet privileges.

---

## Why It Matters

Useful when SYN Scan cannot be performed due to permission restrictions.

---

## Things Worth Remembering

- Completes the TCP connection.
- Easier to detect in logs.
- Does not normally require administrator/root privileges.

---

## Common Mistake

Assuming TCP Connect Scan is stealthy.

The completed connection makes it more visible than SYN Scan.

---

# SYN Scan

## Overview

SYN Scan sends a SYN packet but does not complete the TCP Three-Way Handshake.

For this reason it is commonly called a Half-Open Scan or Stealth Scan.

---

## Why It Matters

SYN Scan is faster and generally less noisy than TCP Connect Scan.

It is one of the most commonly used scan types during reconnaissance.

---

## Things Worth Remembering

- Uses raw packets.
- Usually requires root/administrator privileges.
- Modern firewalls and IDS solutions can still detect it.

---

## Common Mistake

Thinking SYN Scan is invisible.

It is more stealthy than TCP Connect Scan, but it is not undetectable.

---

# Summary

After completing these topics, the following concepts should be familiar:

- Purpose of Nmap
- Hosts, Ports and Services
- Default Scan
- Host Discovery
- Target Selection
- Port Scanning
- Service Version Detection
- Operating System Detection
- Aggressive Scan
- TCP Connect Scan
- SYN Scan

These concepts form the foundation for more advanced Nmap topics such as UDP Scanning, NSE Scripts, Firewall Evasion, Timing Templates, and Output Formats.
