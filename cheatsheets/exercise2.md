# Exercise

**Objective**  
Crack the following  hash:

$2y$12$Dwt1BZj6pcyc3Dy1FWZ5ieeUznr71EeNkJkUlypTsgbX1H68wsRom

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
copy-paste $2y$12$Dwt1BZj6pcyc3Dy1FWZ5ieeUznr71EeNkJkUlypTsgbX1H68wsRom

2. Find the Hash's Algorithm and Hash-type https://hashcat.net/wiki/doku.php?id=example_hashes

bcrypt - 3200

3. Run Hashcat:
```bash
cheatsheets $ hashcat -m 3200 hash /usr/share/wordlists/rockyou.txt
```

4. Show the password:
```bash
cheatsheets $ hashcat -m 3200 hash /usr/share/wordlists/rockyou.txt --show
2y$12$Dwt1BZj6pcyc3Dy1FWZ5ieeUznr71EeNkJkUlypTsgbX1H68wsRom:bleh
```
