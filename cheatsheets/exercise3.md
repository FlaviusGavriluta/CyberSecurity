# Exercise

**Objective**  
Crack the following  hash:

$6$aReallyHardSalt$6WKUTqzq.UQQmrm0p/T7MPpMbGNnzXPMAXi4bJMl9be.cfi3/qxIf.hsGpS41BqMhSrHVXgMpdjS6xeKZAs02.

---

## Prerequisites
- `hashcat` installed and runnable from the command line.  

###  Wordlist:  

**Location (example):**  
`/usr/share/wordlists/rockyou.txt`

---

## Expected behavior

1. Create a Hash file:
```bash
nano hash
```
copy-paste $6$aReallyHardSalt$6WKUTqzq.UQQmrm0p/T7MPpMbGNnzXPMAXi4bJMl9be.cfi3/qxIf.hsGpS41BqMhSrHVXgMpdjS6xeKZAs02.

2. Find the Hash's Algorithm and Hash-type https://hashcat.net/wiki/doku.php?id=example_hashes

bcrypt - 1800

3. Run Hashcat:
```bash
cheatsheets $ hashcat -m 1800 hash /usr/share/wordlists/rockyou.txt
```

4. Show the password:
```bash
cheatsheets $ hashcat -m 1800 hash /usr/share/wordlists/rockyou.txt --show
$6$aReallyHardSalt$6WKUTqzq.UQQmrm0p/T7MPpMbGNnzXPMAXi4bJMl9be.cfi3/qxIf.hsGpS41BqMhSrHVXgMpdjS6xeKZAs02.:waka99
```
