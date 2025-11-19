# ✅ ANSWER THE QUESTIONS BELOW:


## 🧠 PART 1 — Scan open ports (answer: 5)

### How many ports are open on the target system?


### ✔ What you did

You scanned the target using Nmap (or another scanner provided by the lab).
The scan showed 5 open ports.

### ✔ What this means

An open port = a service on the target that listens for connections.
Examples: SMB, SSH, HTTP, FTP.

Each open port is a possible entry point for enumeration or exploitation.

### ✔ Command in Kali / bash

### Run a Fast & stealthy port scan:
```bash
msf6 > nmap -sS 190.161.214.185
[*] exec: nmap -sS 190.161.214.185


Starting Nmap 7.60 ( https://nmap.org ) at 2021-08-20 03:54 BST
Nmap scan report for ip-190-161-214-185.eu-west-1.compute.internal (190.161.214.185)
Host is up (0.0011s latency).
Not shown: 992 closed ports
PORT      STATE SERVICE
135/tcp   open  msrpc
139/tcp   open  netbios-ssn
445/tcp   open  microsoft-ds
3389/tcp  open  ms-wbt-server
49152/tcp open  unknown
MAC Address: 12:DB:T5:2S:E8:3W (Unknown)

Nmap done: 1 IP address (1 host up) scanned in 64.19 seconds
```
### If you see something interesting (445, 22, 80, 139…) run -sC -sV to get deeper information:
### ✔ What this means
	•	-sC → runs safe default scripts
	•	-sV → detects service versions
	•	-p- → scans all 65535 ports
	•	-oN → saves output to a file

```bash
msf6 > nmap -sC -sV -p- 190.161.214.185 -oN full_scan.txt
[*] exec: nmap -sC -sV -p- 190.161.214.185 -oN full_scan.txt

Starting Nmap 7.80 ( https://nmap.org ) at 2025-11-19 05:18 GMT
mass_dns: warning: Unable to open /etc/resolv.conf. Try using --system-dns or specify valid servers with --dns-servers
mass_dns: warning: Unable to determine any DNS servers. Reverse DNS is disabled. Try using --system-dns or specify valid servers with --dns-servers
Stats: 0:02:01 elapsed; 0 hosts completed (1 up), 1 undergoing SYN Stealth Scan
SYN Stealth Scan Timing: About 35.47% done; ETC: 05:23 (0:03:38 remaining)
Stats: 0:02:02 elapsed; 0 hosts completed (1 up), 1 undergoing SYN Stealth Scan
SYN Stealth Scan Timing: About 35.62% done; ETC: 05:23 (0:03:37 remaining)
Stats: 0:02:02 elapsed; 0 hosts completed (1 up), 1 undergoing SYN Stealth Scan
SYN Stealth Scan Timing: About 35.64% done; ETC: 05:23 (0:03:38 remaining)
Stats: 0:02:05 elapsed; 0 hosts completed (1 up), 1 undergoing SYN Stealth Scan
SYN Stealth Scan Timing: About 36.61% done; ETC: 05:23 (0:03:35 remaining)
Nmap scan report for 190.161.214.185
Host is up (0.00055s latency).
Not shown: 65526 closed ports
PORT      STATE SERVICE            VERSION
135/tcp   open  msrpc              Microsoft Windows RPC
139/tcp   open  netbios-ssn        Microsoft Windows netbios-ssn
445/tcp   open  microsoft-ds       Windows 7 Professional 7601 Service Pack 1 microsoft-ds (workgroup: WORKGROUP)
3389/tcp  open  ssl/ms-wbt-server?
|_ssl-date: 2025-11-19T05:22:52+00:00; -1m55s from scanner time.
49152/tcp open  msrpc              Microsoft Windows RPC
Service Info: Host: JON-PC; OS: Windows; CPE: cpe:/o:microsoft:windows

Host script results:
|_clock-skew: mean: 1h28m05s, deviation: 3h00m00s, median: -1m55s
|_nbstat: NetBIOS name: JON-PC, NetBIOS user: <unknown>, NetBIOS MAC: 12:DB:T5:2S:E8:3W (unknown)
| smb-os-discovery: 
|   OS: Windows 7 Professional 7601 Service Pack 1 (Windows 7 Professional 6.1)
|   OS CPE: cpe:/o:microsoft:windows_7::sp1:professional
|   Computer name: Jon-PC
|   NetBIOS computer name: JON-PC\x00
|   Workgroup: WORKGROUP\x00
|_  System time: 2025-11-18T23:22:47-06:00
| smb-security-mode: 
|   account_used: guest
|   authentication_level: user
|   challenge_response: supported
|_  message_signing: disabled (dangerous, but default)
| smb2-security-mode: 
|   2.02: 
|_    Message signing enabled but not required
| smb2-time: 
|   date: 2025-11-19T05:22:47
|_  start_date: 2025-11-19T05:13:42

Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
Nmap done: 1 IP address (1 host up) scanned in 464.20 seconds
```

