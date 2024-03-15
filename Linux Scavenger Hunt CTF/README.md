# Linux Scavenger Hunt CTF

![portfolio4](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/3f13fc8f-0a98-4e10-8392-8d854c93a283)

## Table of Contents

  + [01. Overview](#Overview)
  + [02. Equipment and Tools](#Equipment-and-Tools)
  + [03. Activity Requirements](#Activity-Requirements)
  + [04. Capturing the Flags](#Capturing-the-Flags)

## Overview

- Worked in a team of six, competing against seven other teams.
- launched a headless virtual machine server and logged in.
- Found all eight flags, finishind second out of the eight total competing teams.

## Equipment and Tools

- Virtual Machine running Ubuntu OS
- [SSH Protocol](#https://www.ssh.com/academy/ssh/protocol)
- Bash Scripting

## Activity Requirements

- 8 flags in total. 7 flags from the system combine to make up the final flag.
  + When a flag is found, it is seen in this format - flag_1:97df27aec8c251503f5e3749eb2ddea2
- Timeline of 2.5 hours to get as many flags as possible, if not all of them.

**flag_1**:
Finding this flag is imperative to moving on quickly, as it contains the passwords from users before they were hacked. Luckily, it doesn't have a great hiding spot.

**flag_2**:
A famous hacker had created a user on the system a year ago. Find this user, crack his password, and login to his account.

**flag_3**:
Find a ‘log’ file and a zip file related to the hacker's name.

**flag_4**:
Find a directory with a list of hackers. Look for a file that has read permissions for the owner, no permissions for groups and executable only for everyone else.

**flag_5**:
This user is writing a bash script, except it isn't quite working yet. Find it, debug it, and run it.

**flag_6**:
Inspect this user's custom aliases and run the suspicious one for the proper flag.

**flag_7**:
Find an exploit to gain a root shell. Login as the root user.

**flag_8**:
Gather each of the 7 flags into a file and format it as if each flag was a username and password.
Crack these passwords for the final flag.
Every flag should be exactly the same length of characters. Be sure to remove any backslashes that you find!

## Capturing the Flags

<add here>

Flag 1.                                                                                                          
![flag 1](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/ea60720d-5f65-4451-beb9-8ecb9da28250)

Flag 2.                                                                                                          
![flag 2](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/66349b55-5073-4d8c-8bcc-a50207aa82f3)

Flag 3.                                                                                                              
![flag 3](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/6f587098-6104-4d51-9591-b28c76b17eac)

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
