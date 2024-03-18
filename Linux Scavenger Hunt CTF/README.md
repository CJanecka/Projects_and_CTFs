# Linux Scavenger Hunt CTF

![portfolio4](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/3f13fc8f-0a98-4e10-8392-8d854c93a283)

## Table of Contents

  + [01. Overview](#Overview)
  + [02. Equipment and Tools](#Equipment-and-Tools)
  + [03. Activity Requirements](#Activity-Requirements)
  + [04. Flag Hints](#Flag-Hints)
  + [05. Capturing the Flags](#Capturing-the-Flags)
  + [06. Mitigations](#Mitigations) <placeholder- might remove or change>

## Overview

- 2.5 hour capture the flag challenge.
- Worked in a team of six, competing against seven other teams.
- launched a headless virtual machine server and logged in.
- Found all eight flags, finishind second out of the eight total competing teams.
- I personally found three of the eight flags.

## Equipment and Tools

- [SSH Protocol](https://www.ssh.com/academy/ssh/protocol)
- Bash Scripting
- [Apache Guacamole](https://guacamole.apache.org/)
- [Ubuntu OS](https://ubuntu.com/desktop)

## Activity Requirements

- A 2.5-hour timeframe to obtain as many flags as possible.
- There are a total of 8 flags. Seven flags are obtained from the system, which are then combined to form the final flag. 
  + When a flag is found, it is seen in this format - flag_#:97df27aec8c251503f5e3749eb2ddea2
- Every team member must participate and work at least one task.
- Before accessing the challenge, all participants must install the provided scavenger hunt script. Once installed, participants can connect via ssh by running:
  + ssh student@192.168.200.105
  + Password: Goodluck!

## Flag Hints

These hints were provided for guidance in uncovering the flags within this challenge.

**Flag 1**:
  + Finding this flag is imperative to moving on quickly, as it contains the passwords from users before they were hacked. Luckily, it doesn't have a great hiding spot.

**Flag 2**:
  + A famous hacker had created a user on the system a year ago. Find this user, crack his password, and login to his account.

**Flag 3**:
  + Find a ‘log’ file and a zip file related to the hacker's name.

**Flag 4**:
  + Find a directory with a list of hackers. Look for a file that has read permissions for the owner, no permissions for groups and executable only for everyone else.

**Flag 5**:
  + This user is writing a bash script, except it isn't quite working yet. Find it, debug it, and run it.

**Flag 6**:
  + Inspect this user's custom aliases and run the suspicious one for the proper flag.

**Flag 7**:
  + Find an exploit to gain a root shell. Login as the root user.

**Flag 8**:
  + Gather each of the 7 flags into a file and format it as if each flag was a username and password.
    - Every flag should be exactly the same length of characters. Be sure to remove any backslashes that you find!
  + Crack these passwords for the final flag.
  
## Capturing the Flags

*Before proceeding, it's worth mentioning that some of the images presented are illustrative examples, rather than exact representations of the command dashboard. They've been included to offer improved guidance on this project.*

### Flag 1

After successfully connecting using the command "ssh student@192.168.200.105" as specified in the preceding requirements, we can initiate our search for the first flag. The provided hint suggests that the flag is not well-hidden. Therefore, I decided to list all files and directories recursively from the initial login point. This was done using the following command:

  + ls -Ra
    - The *-R* option instructs *ls* to list directories recursively, meaning it will display the contents of subdirectories as well.
    - The *-a* option tells *ls* to show all files and directories, including those whose names start with a dot (.), which are typically hidden.

Combining these options provides a view of the entire directory structure, including all files and directories, both visible and hidden.

*Illustration of *ls -Ra* command results.*                                                                        
![displaying](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/ab648d71-5c1e-41e4-881e-d70072719e14)

  + This reveals two (2) files in the student's desktop:
    - A file titled Flag 1.
    - A password list contained in a text file.

*Flag 1 - File Contents.*                                                                                    
![flag 1](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/8ec21f67-b8e3-4cf1-957f-2c0e4c753216)

### Flag 2

The hint says a famous hacker had created a user on the system a year ago. We navigated to the "/etc/shadow" file which stores encrypted passwords and other security-related information for user accounts. Here we found the user *mitnik* which represents Kevin Mitnick; a prominent computer hacker and cybersecurity consultant that gained notoriety in the 1980s and 1990s.

Ran John the Ripper to crack the hashed password for the user *mitnik*.

*Illustration of executing John the Ripper.*                                                                      
![john the ripper - mitnik](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/7af7c6fd-5c6f-4d63-9da2-eb01b73e0cfe)

Flag 2 - sample text here.                                                                                   
![flag 2](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/1fa1be45-5f66-42a4-a0ad-9ff50320d096)

Flag 3.                                                                                                              
![flag_3-transformed](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/0cd3320b-b904-4cb8-affb-8b6cb643312b)

Flag 4.                                                                                                        
![flag 4](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/74771b20-32eb-4f46-928c-0922326c5111)

Flag 5.                                                                                                        
![flag 5](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/ae6814d4-711d-4a89-be89-f9bf61326b46)

Flag 6.                                                                                                        
![flag 6](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/489f6888-f7af-41ae-a2ef-099f99e8bef9)

Flag 7.                                                                                                        
![flag 7](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/9299b52f-b2f9-4651-9e22-0e8105471226)

Flag 8.
Hashed Password List:                                                                                                        
![hashed password list](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/05f96b23-c353-4a5d-8d4d-6372e2bb1194)

Cracked Password List:                                                                                                          
![Cracked password list](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/d154dc1e-e981-49a1-ba11-b5a2ce7b0f7f)

## Mitigations

Mitigations for the methods used to capture the flags in this project.

### Flag 1 <rename to specific topic>