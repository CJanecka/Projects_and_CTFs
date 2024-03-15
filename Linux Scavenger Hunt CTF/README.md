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
