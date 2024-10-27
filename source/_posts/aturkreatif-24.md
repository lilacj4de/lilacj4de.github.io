---
title: Aturkreatif'24 CTF Writeup
date: 2024-10-27
description: Fun and simple writeup for the Aturkreatif'24 CTF, focusing on Boot2Root challenges for beginners
tags:
  - CTF
  - Boot2Root
  - Writeup
---
## Another round of internal CTF!

I joined Aturkreatif'24 CTF and pushed myself to tackle as many Boot2Root (B2R) challenges as possible to see how far I’ve come. Managed to crack two during the competition, and figured out the third one afterward (brain was fried during the CTF itself). All in all, pretty cool challenges – shoutout to Amirul for making these fun!

---

## Silent Access
- Room Link: [Silent Access on TryHackMe](https://tryhackme.com/r/room/aturkreatif2024ctf)

**Walkthrough:**
1. Started with the basics – scanning ports and directories. To save time, I used [AutoRecon](https://github.com/Tib3rius/AutoRecon) by Tib3rius, which runs Nmap, directory busting, etc., all at once. 
2. Found an open FTP port and listed files. Jackpot – a `.txt` file had the first flag.

- **Flag:** `4turkr34tif24{20nra7s_7h15_15_70ur_fl@g}`

---

## Episode 2
- Room Link: [Episode 2 on TryHackMe](https://tryhackme.com/r/room/episode2)

**Walkthrough:**
1. More recon with AutoRecon. It found an open FTP port and a hint about “vstpd.”
2. Googled vstpd vulnerabilities and found a backdoor exploit for `vsftpd 2.3.4`.
3. Used a public Python script to get in (credit to the GitHub owner).
4. After getting access, found the flag hidden in the Ubuntu directory under Desktop.

- **Flag:** `4turkr34tif{M374spl0IT}`

---

## Bashed
- Room Link: [Bashed Boot2Root on TryHackMe](https://tryhackme.com/r/room/bashedboot2root)

**Walkthrough:**
1. Created a folder for organizing recon files (trust me, this helps a lot).
2. Ran AutoRecon and gave it time to run a full scan.
3. Dug into the results folder and found a potential directory to explore.
4. Generated a reverse shell script using [revshells](https://revshells.com/), filled in `RHOST` with the IP from TryHackMe, and set my preferred port.
5. Started a listener on the chosen port, ran the script, and got a shell!
6. Checked `sudo -l` to see if I could escalate privileges.
7. Used `sudo sh` to get root and `cat` to reveal the final flag.

- **Flag:** `4turkr34tif24{qs@1345Huyajs*&*ak34fQS}`

---

## Final Thoughts
These B2R challenges were awesome for beginners to get into the basics of enumeration, backdoor exploits, and reverse shells. Perfect if you’re looking to level up your CTF game. Happy hacking, and see you in the next one!
```