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
