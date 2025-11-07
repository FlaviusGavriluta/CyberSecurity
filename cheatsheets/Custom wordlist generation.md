# Crack the Hash — *dogs* wordlist exercise

## Task (goal)
We know the target password is **about dogs** (dog **breeds**, not races).  
The goal is to build a focused wordlist of dog-breed words, generate sensible mutations, and use that wordlist to crack a password hash.

> **English note:** use **"dog breeds"** instead of “dog races”.

---

## Steps

### 1. Download a dog-breeds wordlist
If you have `wordlistctl` installed, you can fetch a prepared wordlist (example):

```bash
~ $ cd ~/CyberSecurity/wordlists/misc 
misc $ ls -la
total 0
drwxr-xr-x  2 flavius.gavriluta  staff   64 Nov  4 13:54 .
drwxr-xr-x  9 flavius.gavriluta  staff  288 Nov  7 08:19 ..
misc $ curl -k -L "https://download.weakpass.com/wordlists/355/dogs.txt.gz" -o ~/CyberSecurity/wordlists/misc/dogs.txt.gz

  % Total    % Received % Xferd  Average Speed   Time    Time     Time  Current
                                 Dload  Upload   Total   Spent    Left  Speed
  0     0    0     0    0     0      0      0 --:--:-- --:--:-- --:  0     0    0     0    0     0      0      0 --:--:-- --:--:-- --:100  1149  100  1149    0     0   3164      0 --:--:-- --:--:-- --:--:--  3165
misc $ ls
dogs.txt.gz
misc $ gunzip -f ~/CyberSecurity/wordlists/misc/dogs.txt.gz
misc $ ls
dogs.txt

```

---
