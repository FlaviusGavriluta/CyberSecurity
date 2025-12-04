# Hidden Note Discovery – McSkidy Task

## Location
Path: `/home/mcskidy/Documents/`

## Steps Taken

```bash
cd /home/mcskidy/Documents/
ls -la
```

Output:

```
total 12
drwxr-xr-x  2 mcskidy mcskidy 4096 Oct 29 20:48 .
drwxr-x--- 21 mcskidy mcskidy 4096 Nov 13 17:10 ..
-rw-rw-r--  1 mcskidy mcskidy 1078 Oct 29 20:48 read-me-please.txt
```

## Content of the Hidden Note

```bash
cat read-me-please.txt
```

Content:

```
From: mcskidy
To: whoever finds this

I had a short second when no one was watching. I used it.

I've managed to plant a few clues around the account.
If you can get into the user below and look carefully,
those three little "easter eggs" will combine into a passcode
that unlocks a further message that I encrypted in the
/home/eddi_knapp/Documents/ directory.
I didn't want the wrong eyes to see it.

Access the user account:
username: eddi_knapp
password: S0mething1Sc0ming

There are three hidden easter eggs.
They combine to form the passcode to open my encrypted vault.
```

### Clues for the Easter Eggs

1. **"I ride with your session, not your chest of files.  
   Open the little bag your shell carries when you arrive."**  
   → This suggests checking shell startup files (`.bashrc`, `.bash_profile`, `.bash_logout`, etc.).

2. **"The tree shows today; the rings remember yesterday.  
   Read the ledger’s older pages."**  
   → Refers to filesystem history: log files, rotated logs, old history, archived logs.

3. **"When pixels sleep, their tails sometimes whisper plain words.  
   Listen to the tail."**  
   → Suggests checking log tails (e.g., `/var/log`, tailing files).

---

## Summary

- Hidden note located successfully.  
- Reveals credentials for user `eddi_knapp`.  
- Three clues point to hidden “easter eggs” needed to decrypt an encrypted message located in `/home/eddi_knapp/Documents/`.
