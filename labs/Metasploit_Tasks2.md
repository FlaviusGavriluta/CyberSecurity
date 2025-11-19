# ✅ ANSWER THE QUESTIONS BELOW:


## 🧠 PART 1 — Scan open ports

### How many ports are open on the target system?


### ✔ What you did

You scanned the target using Nmap (or another scanner provided by the lab).
The scan showed 5 open ports.

### ✔ What this means

An open port = a service on the target that listens for connections.
Examples: SMB, SSH, HTTP, FTP.

Each open port is a possible entry point for enumeration or exploitation.

### ✔ Command in Kali / bash

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
