# THM — Border mutation with 10k common passwords

**Objective:**  
Use the top **10,000** most used password list from [SecLists](https://github.com/danielmiessler/SecLists#install) (`/usr/share/seclists/Passwords/Common-Credentials/10k-most-common.txt`) and generate a *border mutation* by appending all 2 digits combinations (`00`–`99`) to each password. Then crack the SHA‑1 hash `2d5c517a4f7a14dcb38329d228a7d18a3b78ce83` using John the Ripper with a custom rule.

---

## Prerequisites
- `seclists` installed  
- `john` (John the Ripper) installed  
- Permissions to edit `john-local.conf` 

> **Note about John configuration locations**  
> Depending on your distribution, the John configuration may be located at `/etc/john/john.conf` and/or `/usr/share/john/john.conf`. To locate the JtR install directory run:
```bash
locate john.conf
```
---

## Add custom rule to john-local.conf
Edit `/../john-local.conf` and add:

```ini
[List.Rules:THM01]
$[0-9]$[0-9]
```

This rule appends two digits to each password candidate.

---

## Files
- Wordlist: `/../seclists/Passwords/Common-Credentials/10k-most-common.txt`  
- Hash file: `hash.txt`  
- John local rules: `/../john/john-local.conf`

---

## Commands

1. Verify John location:
```bash
/ $ which john
/opt/homebrew/bin/john
/ $ whereis john
john: /opt/homebrew/bin/john
```
2. Locating `john.conf` on macOS (Homebrew Install)

When using John the Ripper installed via Homebrew, the configuration file may not appear in the expected `/usr/share/john/` location.

To search for it:
```bash
~ $ find / -name "john.conf" 2>/dev/null
/System/Volumes/Data/opt/homebrew/Cellar/john-jumbo/1.9.0_1/share/john/john.conf
/opt/homebrew/Cellar/john-jumbo/1.9.0_1/share/john/john.conf
```

3. Verify wordlist exists:
```bash
ls -l /usr/share/seclists/Passwords/Common-Credentials/10k-most-common.txt
```

4. Append rule to john-local.conf:
```bash
sudo bash -c 'cat >> /usr/share/john/john-local.conf' <<'EOF'
[List.Rules:THM01]
$[0-9]$[0-9]
EOF
```

5. Create hash file:
```bash
printf '2d5c517a4f7a14dcb38329d228a7d18a3b78ce83\n' > hash.txt
```

6. Run John the Ripper:
```bash
john --wordlist=/usr/share/seclists/Passwords/Common-Credentials/10k-most-common.txt \
     --rules=THM01 \
     hash.txt
```

7. Show cracked results:
```bash
john --show hash.txt
```

---

## Task sentence
Now let's crack the hash `2d5c517a4f7a14dcb38329d228a7d18a3b78ce83`, we just have to write the hash in a text file and specify the hash type, the wordlist and our rule name.

---

## Expected behavior
John will generate candidates by appending `00`–`99` to each password from the 10k list. If the plaintext matches the SHA‑1 hash, `john --show` will display it.

---

## Troubleshooting
- If John complains about rule syntax, check your build/version.  
- Confirm the hash type: `raw-sha1` is for 40-character SHA‑1 hashes.  
- Use `john --help` for more options or verbosity
