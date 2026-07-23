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

---

## UDP Scan

```bash
sudo nmap -sU target
```

Scan common UDP ports.

---

## Scan UDP Port 53

```bash
sudo nmap -sU -p 53 target
```

Scan DNS service.

---

## Fast UDP Scan

```bash
sudo nmap -sU -F target
```

Scan common UDP ports quickly.

---

## Multiple UDP Ports

```bash
sudo nmap -sU -p 53,123,161 target
```

Scan DNS, NTP and SNMP.
---

nmap -sC target
Run default NSE scripts.

nmap --script=http-title target
Run HTTP title script.

nmap --script=http-title,http-headers target
Run multiple scripts.

ls /usr/share/nmap/scripts/ | grep http
List HTTP-related NSE scripts.

sudo nmap --script-updatedb
Update NSE database.

-sC                    -> Default category
--script safe          -> Safe scripts
--script vuln          -> Vulnerability detection
--script discovery     -> Discovery scripts
--script brute         -> Brute-force scripts
--script dos           -> DoS scripts
