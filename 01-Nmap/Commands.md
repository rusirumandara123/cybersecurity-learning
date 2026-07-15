# Nmap Commands

This file contains the Nmap commands practiced during each topic. The commands are grouped by purpose to make revision easier.

---

# Basic Scan

### Command

```bash
nmap scanme.nmap.org
```

**Purpose**

Runs the default TCP scan against the target.

**When to Use**

- First scan on a new target
- Quick overview of common open ports

**Notes**

- Scans the default top TCP ports.
- Good starting point before running advanced scans.

---

# Host Discovery

### Command

```bash
nmap -sn scanme.nmap.org
```

**Purpose**

Checks whether the target is online without scanning ports.

**When to Use**

- Before port scanning
- Large network discovery

**Notes**

- No port scan is performed.
- Only identifies live hosts.

---

# Host Discovery (Network)

### Command

```bash
nmap -sn 192.168.1.0/24
```

**Purpose**

Discovers active hosts in a network.

**When to Use**

- Local network reconnaissance

**Notes**

Useful before scanning multiple devices.

---

# Scan a Specific Port

### Command

```bash
nmap -p 443 scanme.nmap.org
```

**Purpose**

Scans only the specified port.

**When to Use**

Checking whether a specific service is available.

**Notes**

Reduces scan time.

---

# Scan All TCP Ports

### Command

```bash
nmap -p- scanme.nmap.org
```

**Purpose**

Scans every TCP port.

**When to Use**

Detailed reconnaissance.

**Notes**

- Checks ports 1–65535.
- Takes longer than the default scan.

---

# Scan Multiple Ports

### Command

```bash
nmap -p 21,22,80,443 scanme.nmap.org
```

**Purpose**

Scans only selected ports.

**When to Use**

Interested in specific services.

---

# Scan Port Range

### Command

```bash
nmap -p 20-100 scanme.nmap.org
```

**Purpose**

Scans a range of ports.

---

# Target List

### Command

```bash
nmap -iL targets.txt
```

**Purpose**

Scans every target listed in a file.

**When to Use**

Large environments.

**Notes**

One target per line.

---

# Service Version Detection

### Command

```bash
nmap -sV scanme.nmap.org
```

**Purpose**

Detects the service name and software version.

**When to Use**

After identifying open ports.

**Notes**

Helpful for vulnerability research.

---

# Operating System Detection

### Command

```bash
sudo nmap -O scanme.nmap.org
```

**Purpose**

Attempts to identify the target operating system.

**When to Use**

Operating system enumeration.

**Notes**

Usually requires root/administrator privileges.

---

# Aggressive Scan

### Command

```bash
sudo nmap -A scanme.nmap.org
```

**Purpose**

Runs multiple detection techniques in one scan.

Includes:

- OS Detection
- Version Detection
- Default NSE Scripts
- Traceroute

**Notes**

Produces more traffic and takes longer.

---

# TCP Connect Scan

### Command

```bash
nmap -sT scanme.nmap.org
```

**Purpose**

Performs a complete TCP Three-Way Handshake.

**When to Use**

When raw packet privileges are unavailable.

---

# SYN Scan

### Command

```bash
sudo nmap -sS scanme.nmap.org
```

**Purpose**

Performs a Half-Open (Stealth) Scan.

**When to Use**

General reconnaissance.

**Notes**

- Faster than TCP Connect Scan.
- Usually requires root privileges.

---

# Quick Command Summary

| Task | Command |
|------|---------|
| Default Scan | `nmap scanme.nmap.org` |
| Host Discovery | `nmap -sn scanme.nmap.org` |
| Network Discovery | `nmap -sn 192.168.1.0/24` |
| Scan Specific Port | `nmap -p 443 scanme.nmap.org` |
| Scan All Ports | `nmap -p- scanme.nmap.org` |
| Scan Multiple Ports | `nmap -p 21,22,80,443 scanme.nmap.org` |
| Scan Port Range | `nmap -p 20-100 scanme.nmap.org` |
| Target List | `nmap -iL targets.txt` |
| Version Detection | `nmap -sV scanme.nmap.org` |
| OS Detection | `sudo nmap -O scanme.nmap.org` |
| Aggressive Scan | `sudo nmap -A scanme.nmap.org` |
| TCP Connect Scan | `nmap -sT scanme.nmap.org` |
| SYN Scan | `sudo nmap -sS scanme.nmap.org` |

---

# UDP Scan

## Scan Common UDP Ports

```bash
sudo nmap -sU scanme.nmap.org
```

**Purpose**

Scans common UDP ports on the target.

---

## Scan a Specific UDP Port

```bash
sudo nmap -sU -p 53 scanme.nmap.org
```

**Purpose**

Scans only UDP Port 53.

---

## Fast UDP Scan

```bash
sudo nmap -sU -F scanme.nmap.org
```

**Purpose**

Scans only the most common UDP ports.

---

## Scan Multiple UDP Ports

```bash
sudo nmap -sU -p 53,123,161 scanme.nmap.org
```

**Purpose**

Scans multiple UDP services in one command.

---

# Run Default NSE Scripts

nmap -sC scanme.nmap.org

Purpose:
Run the default NSE scripts.

---

# Run a Single Script

nmap --script=http-title scanme.nmap.org

Purpose:
Display the website title.

---

# Run Multiple Scripts

nmap --script=http-title,http-headers scanme.nmap.org

Purpose:
Run multiple NSE scripts.

---

# Search HTTP Scripts

ls /usr/share/nmap/scripts/ | grep http

Purpose:
List available HTTP-related NSE scripts.

---

# Update Script Database

sudo nmap --script-updatedb

Purpose:
Update the NSE script database.
