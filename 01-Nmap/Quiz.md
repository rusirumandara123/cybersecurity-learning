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

## Quiz

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

---

1. What does NSE stand for?
2. Which language is used to write NSE scripts?
3. What does -sC do?
4. What is the difference between -sV and -sC?
5. Where are NSE scripts stored in Linux?

---

# NSE Categories Quiz

## Multiple Choice

### 1. Which category is executed by `-sC`?

A. safe

B. vuln

C. default

D. brute

**Answer:** C

---

### 2. Which category detects known vulnerabilities?

A. auth

B. safe

C. vuln

D. exploit

**Answer:** C

---

### 3. Which category performs password brute-force attacks?

A. auth

B. brute

C. discovery

D. safe

**Answer:** B

---

### 4. Which category is generally safe for information gathering?

A. brute

B. dos

C. safe

D. exploit

**Answer:** C

---

### 5. Which category may affect service availability?

A. safe

B. default

C. dos

D. discovery

**Answer:** C

---

## Short Questions

1. What is the purpose of NSE Categories?

2. What is the difference between auth and brute?

3. Does the vuln category exploit the target?

4. Why should DoS scripts be used carefully?

5. Which category is executed by `-sC`?
