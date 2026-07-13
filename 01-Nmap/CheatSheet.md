# Nmap Cheat Sheet

## Basic Scan

```bash
nmap target
```

Default TCP scan.

---

## Host Discovery

```bash
nmap -sn target
```

Checks if the host is online.

---

## Scan Specific Port

```bash
nmap -p 443 target
```

Scans only the specified port.

---

## Scan Multiple Ports

```bash
nmap -p 21,22,80,443 target
```

Scans selected ports.

---

## Scan All TCP Ports

```bash
nmap -p- target
```

Scans ports 1–65535.

---

## Target List

```bash
nmap -iL targets.txt
```

Scans targets listed in a file.

---

## Service Version Detection

```bash
nmap -sV target
```

Detects service name and software version.

---

## Operating System Detection

```bash
sudo nmap -O target
```

Attempts to identify the operating system.

---

## Aggressive Scan

```bash
sudo nmap -A target
```

Includes:

- OS Detection
- Version Detection
- NSE Scripts
- Traceroute

---

## TCP Connect Scan

```bash
nmap -sT target
```

Performs the complete TCP Three-Way Handshake.

---

## SYN Scan

```bash
sudo nmap -sS target
```

Performs a Half-Open (Stealth) Scan.
