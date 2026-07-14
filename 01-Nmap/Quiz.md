# Nmap Quiz

## Multiple Choice

### 1. Which command performs Host Discovery?

A. nmap -sV target

B. nmap -sn target

C. nmap -O target

D. nmap -A target

Answer: B

---

### 2. Which command detects service versions?

A. -sn

B. -O

C. -sV

D. -A

Answer: C

---

### 3. Which command scans all TCP ports?

A. -p-

B. -sn

C. -O

D. -A

Answer: A

---

### 4. Which scan completes the TCP Three-Way Handshake?

A. SYN Scan

B. TCP Connect Scan

Answer: TCP Connect Scan

---

### 5. Which scan is generally more stealthy?

A. TCP Connect Scan

B. SYN Scan

Answer: SYN Scan

---

## Short Answer

1. What is the purpose of Nmap?

2. Explain the difference between a host and a port.

3. Why is Service Version Detection useful?

4. Why does SYN Scan usually require root privileges?

5. When would you use Aggressive Scan?

---

## Practical Questions

Write the command to:

- Scan a target using the default scan.
- Scan only port 443.
- Detect service versions.
- Detect the operating system.
- Perform an Aggressive Scan.
- Perform a SYN Scan.

---

## Day 10 Quiz

### 1. Which option performs a UDP scan?

A. -sS

B. -sT

C. -sU

D. -sV

Answer: C

---

### 2. Which UDP port is used by DNS?

Answer: 53

---

### 3. Which UDP port is used by NTP?

Answer: 123

---

### 4. What does open|filtered indicate?

Answer:

Nmap cannot determine whether the port is open or filtered.

---

### 5. Why are UDP scans generally slower than TCP scans?

Answer:

Because many UDP services do not respond, forcing Nmap to wait for timeouts.
