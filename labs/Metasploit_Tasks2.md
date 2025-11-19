✅ ANSWER THE QUESTIONS BELOW:


🧠 PART 1 — Scan open ports

#1) “How many ports are open on the target system?” → 5


##✔ What you did

You scanned the target using Nmap (or another scanner provided by the lab).
The scan showed 5 open ports.

##✔ What this means

An open port = a service on the target that listens for connections.
Examples: SMB, SSH, HTTP, FTP.

Each open port is a possible entry point for enumeration or exploitation.

##✔ Command in Kali / bash

'''bash
nmap -sS 190.161.214.185 
'''
