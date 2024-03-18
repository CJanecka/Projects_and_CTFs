# Linux Scavenger Hunt CTF

![portfolio4](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/3f13fc8f-0a98-4e10-8392-8d854c93a283)

## Table of Contents

  + [01. Overview](#Overview)
  + [02. Equipment and Tools](#Equipment-and-Tools)
  + [03. Activity Requirements](#Activity-Requirements)
  + [04. Flag Hints](#Flag-Hints)
  + [05. Capturing the Flags](#Capturing-the-Flags)

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

- 8 flags in total. 7 flags from the system combine to make up the final flag.
  + When a flag is found, it is seen in this format - flag_1:97df27aec8c251503f5e3749eb2ddea2
- Timeline of 2.5 hours to get as many flags as possible, if not all of them.
- Every team member must participate and work at least one task

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

<add here>

Flag 1.                                                                                                                          
![flag 1](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/8ec21f67-b8e3-4cf1-957f-2c0e4c753216)

Flag 2.                                                                                                          
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
