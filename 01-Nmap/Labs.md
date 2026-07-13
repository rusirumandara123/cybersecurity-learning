# Nmap Labs

This file contains the practical exercises completed while learning Nmap.

Each lab includes the objective, command used, observations, and key takeaways.

---

# Lab 01 - Default Scan

## Objective

Run a basic Nmap scan to identify common open TCP ports.

### Command

```bash
nmap scanme.nmap.org
```

### Observation

- Host was reachable.
- Nmap identified several open TCP ports.
- Default scan completed quickly.

### Key Takeaway

The default scan is a good starting point when scanning a new target.

---

# Lab 02 - Host Discovery

## Objective

Identify whether the target is online without performing a port scan.

### Command

```bash
nmap -sn scanme.nmap.org
```

### Observation

- The host responded successfully.
- No port information was displayed.

### Key Takeaway

Host Discovery only confirms whether a host is online.

---

# Lab 03 - Network Host Discovery

## Objective

Discover active devices within a local network.

### Command

```bash
nmap -sn 192.168.1.0/24
```

### Observation

- Active hosts were identified.
- Offline devices were ignored.

### Key Takeaway

Scanning only live hosts saves time before performing detailed scans.

---

# Lab 04 - Scan a Specific Port

## Objective

Check whether HTTPS is available on the target.

### Command

```bash
nmap -p 443 scanme.nmap.org
```

### Observation

- Only port 443 was scanned.
- The scan completed much faster than a full scan.

### Key Takeaway

Scanning specific ports is useful when checking a known service.

---

# Lab 05 - Scan All TCP Ports

## Objective

Identify every open TCP port on the target.

### Command

```bash
nmap -p- scanme.nmap.org
```

### Observation

- The scan checked all TCP ports.
- The process took noticeably longer than the default scan.

### Key Takeaway

A full port scan provides more complete results but requires more time.

---

# Lab 06 - Target List Scan

## Objective

Scan multiple targets using a file.

### Command

```bash
nmap -iL targets.txt
```

### Observation

- Every target in the file was scanned.
- This method simplified scanning multiple hosts.

### Key Takeaway

Using a target list is more efficient than entering multiple IP addresses manually.

---

# Lab 07 - Service Version Detection

## Objective

Identify service versions running on open ports.

### Command

```bash
nmap -sV scanme.nmap.org
```

### Observation

Example results included:

- OpenSSH 6.6.1p1
- Apache httpd 2.4.7

### Key Takeaway

Service version detection provides valuable information for vulnerability research.

---

# Lab 08 - Operating System Detection

## Objective

Identify the target operating system.

### Command

```bash
sudo nmap -O scanme.nmap.org
```

### Observation

Nmap displayed several possible operating systems with confidence percentages.

Example:

- Linux 4.19–5.15 (98%)
- Linux 4.15 (94%)
- Linux 5.4 (92%)

### Key Takeaway

Operating system detection provides an estimate rather than a guaranteed result.

---

# Lab 09 - Aggressive Scan

## Objective

Collect multiple types of information using a single scan.

### Command

```bash
sudo nmap -A scanme.nmap.org
```

### Observation

The scan included:

- Open ports
- Service versions
- Operating system guesses
- NSE script results
- Traceroute information

### Key Takeaway

Aggressive Scan combines several useful detection techniques into one command.

---

# Lab 10 - TCP Connect Scan

## Objective

Perform a complete TCP connection.

### Command

```bash
nmap -sT scanme.nmap.org
```

### Observation

- The scan completed the TCP Three-Way Handshake.
- Results were similar to a SYN scan.

### Key Takeaway

TCP Connect Scan is reliable but easier to detect because it establishes a full connection.

---

# Lab 11 - SYN Scan

## Objective

Perform a Half-Open Scan.

### Command

```bash
sudo nmap -sS scanme.nmap.org
```

### Observation

- The scan returned similar port results to TCP Connect Scan.
- The TCP connection was not completed.

### Key Takeaway

SYN Scan is generally faster and more stealthy than TCP Connect Scan, but modern security devices can still detect it.

---

# Overall Learning

After completing these labs, I can:

- Discover live hosts
- Scan individual or multiple targets
- Scan specific or all TCP ports
- Detect service versions
- Estimate operating systems
- Perform Aggressive Scans
- Understand the difference between TCP Connect Scan and SYN Scan
