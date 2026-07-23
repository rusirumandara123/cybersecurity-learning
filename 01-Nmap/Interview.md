# Nmap Interview Questions

## Basic Questions

### 1. What is Nmap?

Nmap is an open-source network scanning and security auditing tool used to discover hosts, ports, services, and operating systems.

---

### 2. Why is Nmap used?

It is used for:

- Host discovery
- Port scanning
- Service detection
- Operating system detection
- Network reconnaissance

---

### 3. What is the difference between a Host and a Port?

A host is a device connected to a network.

A port is a communication endpoint used by a service.

---

### 4. What is the purpose of Host Discovery?

To identify whether a target is online before performing a port scan.

---

### 5. Why is Service Version Detection important?

It identifies software versions that may contain known vulnerabilities.

---

### 6. What is Operating System Detection?

It attempts to identify the target operating system by analyzing network responses.

---

### 7. What does Aggressive Scan include?

- OS Detection
- Service Version Detection
- NSE Scripts
- Traceroute

---

### 8. What is TCP Connect Scan?

A scan that completes the full TCP Three-Way Handshake.

---

### 9. What is SYN Scan?

A Half-Open Scan that does not complete the TCP connection.

---

### 10. Why does SYN Scan usually require sudo?

Because it sends raw packets, which require elevated privileges.

---

## What is UDP?

UDP (User Datagram Protocol) is a connectionless transport layer protocol designed for fast communication.

---

## Why is UDP scanning slower than TCP scanning?

UDP services often do not respond, so Nmap waits for timeouts before determining the port state.

---

## What does open|filtered mean?

Nmap cannot determine whether the port is open or filtered because no response was received.

---

## Why does UDP scanning usually require sudo?

UDP scanning uses raw packets, which require root privileges on Linux systems.

---

## Name four common UDP services.

- DNS (53)
- DHCP (67/68)
- NTP (123)
- SNMP (161)

---

Q: What is NSE?
A: Nmap Scripting Engine used for enumeration and information gathering.

Q: What does -sC do?
A: Runs the default NSE scripts.

Q: What is the difference between -sV and -sC?
A: -sV detects service versions, while -sC executes default NSE scripts.

---

# NSE Categories

## Q1. What are NSE Categories?

**Answer:**

NSE Categories are groups of NSE scripts organized by their purpose, making it easier to run the correct scripts during a scan.

---

## Q2. What is the purpose of the safe category?

**Answer:**

The safe category performs information gathering and enumeration without harming the target.

---

## Q3. What does the vuln category do?

**Answer:**

The vuln category checks for known vulnerabilities but does not exploit the target.

---

## Q4. What is the difference between default and safe?

**Answer:**

- **default** runs the commonly used default NSE scripts.
- **safe** runs scripts that are considered non-intrusive and safe for information gathering.

---

## Q5. Why should DoS scripts be used carefully?

**Answer:**

Because they may interrupt or crash services if executed against a target.

---

## Q6. What is the purpose of the brute category?

**Answer:**

The brute category attempts to discover valid credentials using multiple username and password combinations.

---

## Interview Tips

- `-sC` = Default Scripts
- `vuln` = Detect Only (No Exploitation)
- `auth` = Authentication Checks
- `brute` = Password Guessing
