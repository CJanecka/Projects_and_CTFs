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
- [John the Ripper](https://www.openwall.com/john/)
- [Ubuntu OS](https://ubuntu.com/desktop)
- [Apache Guacamole](https://guacamole.apache.org/)

## Activity Requirements

- A 2.5-hour timeframe to obtain as many flags as possible.
- There are a total of 8 flags. Seven flags are obtained from the system, which are then combined to form the final flag. 
- Every team member must participate and work at least one task.
- Before accessing the challenge, all participants must install the provided scavenger hunt script. Once installed, participants can connect via ssh by running:
  + ssh student@192.168.200.105
  + Password: Goodluck!

## Flag Hints

These hints were provided for guidance in uncovering the flags within this challenge. When a flag is found, it is seen in this format - flag_#:97df27aec8c251503f5e3749eb2ddea2

  01. **Flag 1**: Finding this flag is imperative to moving on quickly, as it contains the passwords from users before they were hacked. Luckily, it doesn't have a great hiding spot.

  02. **Flag 2**: A famous hacker had created a user on the system a year ago. Find this user, crack his password, and login to his account.

  03. **Flag 3**: Find a ‘log’ file and a zip file related to the hacker's name.
       - Use a compound command to figure out the unique count of IP Addresses in this log file. That number is a password for the zip file.

  04. **Flag 4**: Find a directory with a list of hackers. Look for a file that has read permissions for the owner, no permissions for groups and executable only for everyone else.

  05. **Flag 5**: This user is writing a bash script, except it isn't quite working yet. Find it, debug it, and run it.

  06. **Flag 6**: Inspect this user's custom aliases and run the suspicious one for the proper flag.

  07. **Flag 7**: Find an exploit to gain a root shell. Login as the root user.

  08. **Flag 8**: Gather each of the 7 flags into a file and format it as if each flag was a username and password.
       - Crack these passwords for the final flag.
       - Every flag should be exactly the same length of characters. Be sure to remove any backslashes that you find!
  
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

The hint mentions that a famous hacker created a user on the system a year ago. We followed this clue by navigating to the "/etc/shadow" file, where encrypted passwords and other security-related information for user accounts are stored. Here, we identified the user *mitnik*, believed to represent Kevin Mitnick, a renowned computer hacker and cybersecurity consultant that gained notoriety in the 1980s and 1990s. 

Furthermore, we discovered a hashed password for the *student* user. Given the hint's emphasis on a famous hacker, we focused our attention on *mitnik* as the primary target. Returning to the desktop directory, we utilized John the Ripper to crack the hashed passwords found. The command used for this is as follows:

  + john --wordlist=.pass_list.txt ../Documents/my-files/shadow

When this command is executed, John the Ripper will systematically compare the hashed passwords stored in the "/etc/shadow" file with the entries in the provided wordlist. It will attempt various combinations and permutations of words from the wordlist to find matches for the hashed passwords. If a match is found, John the Ripper will reveal the corresponding plaintext password, thus successfully cracking the hashed password.

*Illustration of executing John the Ripper.*                                                                      
![john1](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/cd1f1eb4-d7ef-4527-870a-770835d87a73)

  +  The "--show" option can be used to display the cracked passwords reliably.

*Illustration of the "--show" option being utilized.*                                                                                        
![john2](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/18c207c7-1af4-48c7-a244-167f108f05f8)

John the Ripper was successful and provided the following passwords:

  + User: student | Password: letmein
  + User: mitnik | Password: trustno1

*Flag 2 - Found by logging in to the user mitnik.*                                                                                   
![flag 2](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/1fa1be45-5f66-42a4-a0ad-9ff50320d096)

### Flag 3             <revise this section is a rough draft>

While logged in as the user *mitnik*, we conducted a search for a log and zip file by recursively listing the directories starting from the home directory.

*Illustration of listing mitnik's directories.*                                                                          
![chrome_nMXOheqDR6](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/b07c56de-0644-4ce9-9e6a-e8119e2bb958)

  + A hidden zip file, *.secret.zip*, was found in the Documents directory.

The log file is located in: */var/log/mitnik.log*

*Illustration of mitnik's log folder contents.*                                                                    
![mitnik logs](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/310cd646-f3d0-4af6-b110-75ec9de177db)

Next we inspect the file, *mitnik.log*, to identify and analyze patterns within its contents, particularly focusing on the IP addresses present.

*Illustration of the contents of mitnik.log.*                                                                              
![mitnik log contents](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/bbc957a5-2e96-402a-8189-be09370967f6)

  + The file shows that the IP addresses are only at the beginning of each line. Followed by additional information; such as, the request method, HTTP status code, referrer URL, and user agent.

By recognizing that the IP addresses consistently appear at the beginning of each line, we can leverage this pattern to extract the unique count of IP Addresses in this log file. To do this, create a compound command that counts the number of unique lines. The command my team used:

  + cat /var/log/mitnik.log | sort | uniq | wc -l

To break this command down:

  + The command "**cat /var/log/mitnik.log**" utilizes the *cat* utility to display the contents of the *mitnik.log* file, outputting the entire log file contents to the standard output. 

  + The "**| sort**" component uses a pipe (|) symbol to redirect the output from *cat* to the *sort* command, arranging the lines of text alphabetically, grouping identical lines together for subsequent processing.

  + "**| uniq**" filters consecutive duplicate lines from the sorted input, retaining only unique lines while discarding duplicates.

  + The "**| wc -l**" component directs the output to the word count (wc) command with the *-l* option, which tallies the number of lines in the input and prints the total line count to the standard output.

*Illustration of compund command.*                                                                                              
![mitnik compound command](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/76c33f66-26b6-49c7-8f16-cf252130c1f6)

  + The password for the *.secret.zip* is: *102*

*Illustration of unzipping the secret file.*                                                                        
![mitnik unzip](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/c814dd0e-a8c4-4a32-b53e-57d38ce9af89)

  + The password for the *babbage* user is: *freedom*

Login as babbage and found flag 3.

*Successfully logged into babbage.*                                                                                                              
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
