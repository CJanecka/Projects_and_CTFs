# Linux Scavenger Hunt CTF

![portfolio4](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/3f13fc8f-0a98-4e10-8392-8d854c93a283)

## Table of Contents

  + [01. Overview](#Overview)
  + [02. Equipment and Tools](#Equipment-and-Tools)
  + [03. Activity Requirements](#Activity-Requirements)
  + [04. Flag Hints](#Flag-Hints)
  + [05. Capturing the Flags](#Capturing-the-Flags)
    - [a. Flag 1](#Flag-1)
    - [b. Flag 2](#Flag-2)
    - [c. Flag 3](#Flag-3)
    - [d. Flag 4](#Flag-4)
    - [e. Flag 5](#Flag-5)
    - [f. Flag 6](#Flag-6)
    - [g. Flag 7](#Flag-7)
    - [h. Flag 8](#Flag-8)
  + [06. Mitigations](#Mitigations) <placeholder- might remove or change>

## Overview

- 2.5 hour capture the flag challenge.
- Worked in a team of six, competing against seven other teams.
- launched a headless virtual machine server and logged in.
- Found all eight flags, finishind second out of the eight total competing teams.
- I personally found three of the eight flags.

## Equipment and Tools

- [SSH Protocol](https://www.ssh.com/academy/ssh/protocol)
- [Bash Scripting](https://www.geeksforgeeks.org/bash-scripting-introduction-to-bash-and-bash-scripting/)
- [John the Ripper](https://www.openwall.com/john/)
- [Headless Computer](https://nordvpn.com/cybersecurity/glossary/headless-system/#:~:text=A%20headless%20system%20is%20a,through%20other%20devices%20or%20interfaces.)
- [Ubuntu OS](https://ubuntu.com/desktop)
- [Apache Guacamole](https://guacamole.apache.org/)

## Activity Requirements

- A 2.5-hour timeframe to obtain as many flags as possible.
- There are a total of eight (8) flags.
  + Seven (7) flags are obtained from the system, which are then combined to form the final flag. 
- Every team member must participate and work at least one task.
- Before accessing the challenge, all participants must install a scavenger hunt script *(not provided here)*. Once installed, participants can connect via ssh by running:
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

  + This revealed two (2) hidden files on the student's desktop:
    - A file named "flag_1", the contents on which are shown below.
    - A text file called ".pass_list.txt", which contains a list of likely passwords, organized line by line. This includes; common words, dictionary terms, commonly used phrases, and other character combinations that are frequently chosen by users as passwords.

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

### Flag 3

While logged in as the user *mitnik*, we conducted a search for a log and zip file by recursively listing the directories starting from the home directory.

*Illustration of listing mitnik's directories.*                                                                          
![chrome_nMXOheqDR6](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/b07c56de-0644-4ce9-9e6a-e8119e2bb958)

  + A hidden zip file, *.secret.zip*, was found in the Documents directory.

The zip file is password-protected. As per the hint provided, we need to figure out the unique count of IP Addresses in the log file, that number is a password for the zip file. This log file is located within the 'var' directory, specifically within the 'log' subdirectory.

*Illustration of mitnik's log folder contents.*                                                                    
![mitnik logs](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/310cd646-f3d0-4af6-b110-75ec9de177db)

Inspect the file, *mitnik.log*, to identify and analyze patterns within its contents, particularly focusing on the IP addresses present.

*Illustration of the contents of mitnik.log.*                                                                              
![mitnik log contents](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/bbc957a5-2e96-402a-8189-be09370967f6)

  + The file shows that the IP addresses are only at the beginning of each line. Followed by additional information; such as, the request method, HTTP status code, referrer URL, and user agent.

By recognizing that the IP addresses consistently appear at the beginning of each line, we can leverage this pattern to extract the unique count of IP Addresses in this log file. To do this, create a compound command that counts the number of unique lines. The command my team used:

  + cat /var/log/mitnik.log | sort | uniq | wc -l

To break this down:

  + The command "**cat /var/log/mitnik.log**" utilizes the *cat* utility to display the contents of the *mitnik.log* file, outputting the entire log file contents to the standard output. 

  + The "**| sort**" component uses a pipe (|) symbol to redirect the output from *cat* to the *sort* command, arranging the lines of text alphabetically, grouping identical lines together for subsequent processing.

  + "**| uniq**" filters consecutive duplicate lines from the sorted input, retaining only unique lines while discarding duplicates.

  + The "**| wc -l**" component directs the output to the word count (wc) command with the *-l* option, which tallies the number of lines in the input and prints the total line count to the standard output.

*Illustration of the compound command.*                                                                           
![mitnik compound command](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/76c33f66-26b6-49c7-8f16-cf252130c1f6)

  + The password for *.secret.zip* is: *102*

We can now access the the zip file. Upon entering the correct password, the file "babbage" is extracted from the zip archive. The contents of the extracted file are displayed using the cat command.

*Illustration of unzipping the secret file.*                                                                        
![mitnik unzip](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/c814dd0e-a8c4-4a32-b53e-57d38ce9af89)

  + The output reveals that the password for the user *babbage* is: *freedom*

By logging in as *babbage*, we were prompted with flag 3.

*Successfully logged into babbage.*                                                                                      
![flag_3-transformed](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/0cd3320b-b904-4cb8-affb-8b6cb643312b)

### Flag 4

While logged in as *babbage*, from the provided hint, we need to find a directory with a list of hackers. The desired file has read permissions for the owner, no permissions for groups, and executable only for everyone else. 

In operating systems such as Linux, [file permissions](https://www.redhat.com/sysadmin/linux-file-permissions-explained#:~:text=All%20Linux%20files%20belong%20to,write%2C%20and%20x%20for%20execute.) can be seen as a string which is actually an expression of three different sets of permissions: **Owner**, **Group**, and **Others**

*Linux File Permissions Overview.*                                                                                      
![chrome_PZHQmcWnqt](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/b2c1dec3-3eb5-490b-adc4-6c4c738a0c7c)

Each file and directory is associated with an "owner" (user), a Unix group, and a set of permission flags; defining separate read, write, and execute privileges for the three permission sets. "Group" permissions extend to all users that are part of the group associated with the file. "Other", also referred to as "world" permissions, encompasses all users with login access to the system. 

Running a recursive search, on the headless machine, allows us to explore the contents of babbage's directories.

*Illustration listing the hacker files located in the Documents directory.*                                                 
![babbage listing files](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/b8fc310d-34e4-49d5-8e89-d859467310a9)

Change directories to *Documents* and list the permissions for those files.

*Illustrastion of listed file permissions.*                                                                                
![chrome_T8ZYlWvjbD](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/d2215d0f-f1f4-42b2-888f-54628bf96eaa)

From left to right, the fields above represent:

  + **Ten Character String**: Set of ten characters representing the file's permissions.
  + **Number of Hard Links**: The number of hard links to a file indicating how many directory entries (filenames) point to the same inode.
  + **Owner**: Specifies the user who owns the file.
  + **Associated Group**: Specifies the group associated with the file.
  + **Size**: Indicates the size of the file in bytes.
  + **Date of Last Modification**: Displays the date and time when the file was last modified. 
  + **Name of File**: The name of the file or directory being listed.

The sought after permissions "read for the owner, no permissions for groups, and executable only for everyone else" are represented as: **-r-------x**. From the listed files and permissions, there are four (4) files with these:

*Illustration of the Four Files.*                                                                                      
![chrome_ksyR0lfMGk](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/bd343d4c-2d82-4431-957a-a86fe9cdfecc)

Among the files shown, only the "stallman" file contains data. When we use the *cat* command to examine its contents, we find that it contains the word "computer".

*Illustration of the stallman file contents.*                                                                            
![chrome_rVmrwuAFuh](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/65d01451-ac53-4aaf-ad03-55c46a991211)

This is the password used to log into the *stallman* user. After logging in, we obtained flag 4.

*Successfully logged in as "stallman".*                                                                                 
![flag 4](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/74771b20-32eb-4f46-928c-0922326c5111)

### Flag 5

Flag 5.                                                                                                        
![flag 5](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/ae6814d4-711d-4a89-be89-f9bf61326b46)

### Flag 6

Flag 6.                                                                                                        
![flag 6](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/489f6888-f7af-41ae-a2ef-099f99e8bef9)

### Flag 7

Flag 7.                                                                                                        
![flag 7](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/9299b52f-b2f9-4651-9e22-0e8105471226)

### Flag 8

Flag 8.
Hashed Password List:                                                                                                     
![hashed password list](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/05f96b23-c353-4a5d-8d4d-6372e2bb1194)

Cracked Password List:                                                                                            
![Cracked password list](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/d154dc1e-e981-49a1-ba11-b5a2ce7b0f7f)

## Mitigations

Mitigations for the methods used to capture the flags in this project.

### Flag 1 <rename to specific topic>
