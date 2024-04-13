# Linux Scavenger Hunt CTF

![portfolio4](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/3f13fc8f-0a98-4e10-8392-8d854c93a283)

## Table of Contents

  + [01. Overview](#Overview)
  + [02. Equipment and Tools](#Equipment-and-Tools)
  + [03. Activity Requirements](#Activity-Requirements)
  + [04. Flag Hints](#Flag-Hints)
  + [05. Capturing the Flags](#Capturing-the-Flags)
    - [Flag 1](#Flag-1)
    - [Flag 2](#Flag-2)
    - [Flag 3](#Flag-3)
    - [Flag 4](#Flag-4)
    - [Flag 5](#Flag-5)
    - [Flag 6](#Flag-6)
    - [Flag 7](#Flag-7)
    - [Flag 8](#Flag-8)
  + [06. Appendix *- Key Figures*](#Appendix---Key-Figures)
    - [Ancheta](#Ancheta)
    - [Anonymous](#Anonymous)
    - [Assange](#Assange)
    - [Astra](#Astra)
    - [Babbage](#Babbage)
    - [Berners-Lee](#Berners-Lee)
    - [Bevan](#Bevan)
    - [Calce](#Calce)
    - [Gates](#Gates)
    - [Gonzalez](#Gonzalez)
    - [Gosling](#Gosling)
    - [Hopper](#Hopper)
    - [James](#James)
    - [Kernighan](#Kernighan)
    - [Knuth](#Knuth)
    - [Lamo](#Lamo)
    - [Lovelace](#Lovelace)
    - [Mitnik](#Mitnik)
    - [Poulsen](#Poulsen)
    - [Pryce](#Pryce)
    - [Ritchie](#Ritchie)
    - [Rossum](#Rossum)
    - [Stallman](#Stallman)
    - [Stroustrup](#Stroustrup)
    - [Thompson](#Thompson)
    - [Torvalds](#Torvalds)
    - [Wirth](#Wirth)
    - [Woz](#Woz)

## Overview

In this 2.5-hour Capture the Flag *(CTF)* challenge, my team of six competed against seven other teams of 5-6 members each. Using the [provided hints](#Flag-Hints); we launched a headless virtual machine server and logged in, to search for a total of eight flags. The challenge followed a linear structure, with each flag being discovered in successive order.

***Flag 1*** was discovered by conducting a recursive file search from the initial login point. This search revealed two hidden files on the student's desktop —  a file containing the first flag and a wordlist of potential passwords.

***Flag 2*** was found by examining the [shadow file](https://linuxize.com/post/etc-shadow-file/). Here the user *mitnik* was targeted. John the Ripper and the wordlist, from flag 1, were utilized to successfully crack the passwords found. Once logged into *mitnik*, my team was prompted with the second flag.

***Flag 3*** involved locating a hidden, password-protected, zip file while logged in as *mitnik*. Then analyzing a log file, to derive the password needed to unzip the file. My team unzipped the file and found the password "freedom" for the user "babbage". Once logged into *babbage*, we obtained the third flag.

***Flag 4*** was obtained while logged in as *babbage* and running a recursive search, from the documents directory, for a file with specific permissions. Four files matched the specified permissions, but only one file contained data. Examining its contents revealed a password, "computer", for the user "stallman". Once logged into this user, the fourth flag was displayed.

***Flag 5*** required examining a malfunctioning bash script found in the documents directory, while logged in as *stallman*. This script specifies the target file's name and location, which could be directly accessed without fixing the script. Viewing the contents of the file revealed the "sysadmin" password, "passw0rd", and the fifth flag.

***Flag 6*** was found by inspecting a shell configuration file on the *sysadmin* user. In the file, an alias named "flag" was set to execute the *echo* command. This alias displayed a message containing the sixth flag when invoked.

***Flag 7*** required obtaining *root* shell access. By examining the *sudo* permissions for the *sysadmin* user, my team identified that the *less* command is able to be used with elevated privileges. Using these privileges, we opened a new bash shell, acquired root access, and changed the *root* user password. Upon exiting the shell, and re-entering with the new *root* password, we were prompted with the seventh flag.

***Flag 8*** was found by compiling the first seven flags into a single text file, and formatted for use with John the Ripper. Cracking the passwords with the wordlist, found with flag 1, revealed the eighth flag.

My team finished this CTF challenge in second place — successfully locating all eight flags, fifteen minutes after the first place team finished. I contributed by finding three flags — 2, 4, and 8. The [flag capturing](#Capturing-the-Flags) section, included below, expands on the steps my team took to acquire these flags.

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
       - Every flag should be exactly the same length of characters.
  
## Capturing the Flags

*Before proceeding, it's worth mentioning that some of the images presented are illustrative examples, rather than exact representations of the command dashboard. They've been included to offer improved guidance on this project.*

We received login credentials for the scavenger hunt's server with the username "student", and the password "Goodluck!", for the IP address "192.168.200.105". Using these credentials, my team connected to the server and began our search for the first flag.

### Flag 1

The provided hint suggests that the flag is not well-hidden. Therefore, we decided to list all files and directories recursively from the initial login point. This was done using the following command:

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

In operating systems such as Linux, [file permissions](https://www.redhat.com/sysadmin/linux-file-permissions-explained#:~:text=All%20Linux%20files%20belong%20to,write%2C%20and%20x%20for%20execute.) can be seen as a string which is actually an expression of three different sets of permissions: **Owner**, **Group**, and **Others**. Each file and directory is associated with an "owner" (user), a Unix group, and a set of permission flags; defining separate read, write, and execute privileges for the three permission sets. "Group" permissions extend to all users that are part of the group associated with the file. "Other", also referred to as "world" permissions, encompasses all users with login access to the system. 

Running a recursive search, on the headless machine, allows us to explore the contents of babbage's directories.

*Illustration listing the files located in the Documents directory.*                                                 
![babbage listing files](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/b8fc310d-34e4-49d5-8e89-d859467310a9)

  + See [Appendix *- Key Figures*](#Appendix---Key-Figures) below for additional information on who these files represent.

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

The sought after permissions "read for the owner, no permissions for groups, and executable only for everyone else" are represented as: **-r-------x**. From the listed files and permissions, there are four (4) files that match:

*Illustration of the Four Files.*                                                                                      
![chrome_ksyR0lfMGk](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/bd343d4c-2d82-4431-957a-a86fe9cdfecc)

Among the files shown, only the "stallman" file contains data. When we use the *cat* command to examine its contents, we find that it contains the word "computer".

*Illustration of the stallman file contents.*                                                                            
![chrome_rVmrwuAFuh](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/65d01451-ac53-4aaf-ad03-55c46a991211)

This is the password used to log into the *stallman* user. After logging in, we obtained flag 4.

*Successfully logged in as "stallman".*                                                                                 
![flag 4](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/74771b20-32eb-4f46-928c-0922326c5111)

### Flag 5

With access to the *stallman* user, we conducted a recursive search to locate the malfunctioning bash script. 

*Illustration of the Recursive Search results.*                                                                          
![chrome_6T3ZYZVMup](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/9a93ce14-2ae4-431a-9b97-ece5cc75a22e)

The search revealed a script file located in the *Documents* directory. This script was not intially executable. To remedy this and make the flag 5 script file executable, run the following command:
  + chmod +x Documents/flag5.sh

*Enabling and Executing the Script.*                                                                                                                                                                            
![flag 5 - script execute](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/a23f6f4e-3a0c-4fc2-9b57-245512bab0a9)

When trying to execute the script, an error occurs, indicating a syntax issue on line 4. This error prevents the interpreter from parsing the script correctly. To address this issue, we utilized the [VIM text editor](https://www.geeksforgeeks.org/getting-started-with-vim-editor-in-linux/) to review the script's contents and rectify the error on line 4, along with any other errors present within the script.

*Contents of the Flag5 Script.*                                                                                          
![01 initial script](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/ac1b175e-99ca-4da8-be9a-2e3fe43d45ab)

The errors found within the shell script:

  + Line 4 - the *for* loop has an extra *do*.
  + Line 13 - the *if* statement is missing the *then* declaration after Line 13.

*Contents of the Corrected Flag5 Script.*                                                                                  
![01 corrected script](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/fda4ab15-9649-4594-b078-6c812b205b91)

This script is designed to read a file, calculate its size and owner, and then display its contents with formatting if necessary. Line 18 specifies that the input will be read from **/var/tmp/5galf**. *5galf* can be accessed, directly, without correcting the script. When doing so, we are prompted with flag 5.

*Flag 5 and Sysadmin Password found.*                                                                                                  
![flag 5 - found flag in directory](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/751fc346-dc74-4a20-af6b-e65ca9c10f7c)

The flag and *Sysadmin* password can also be found by running the corrected shell script.

*Illustration of executing the script.*                                                                                  
![chrome_sjmNOshRxu](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/0f3504ee-b893-439b-90ce-e2ffc24d64cf)

### Flag 6

Using the *Sysadmin* credentials we logged in and examined the *.bashrc* file for aliases, which are custom shortcuts configured on the system. 

*Illustration of Accessing the Bashrc file.*                                                                          
![flag 6 - login](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/c599de5f-4645-4660-9403-7db8d927a056)

Within the *Alias definitions* section of the *bashrc* file, the alias "flag" has been defined. This alias has been set up to echo a message indicating the discovery of a flag.

*Flag 6 provided from Alias.*                                                                                                        
![flag 6](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/9a86caab-7b5c-4bc2-89ee-4e301508aefc)

### Flag 7

To find an exploit and gain root shell access, we began by looking at the *sudo* permissions for *sysadmin*.

*Illustration of Sudo Permissions.*                                                                                                        
![flag 7 - sysadmin default settings](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/580b4c76-4979-4455-885d-36e3e3c15dd7)

This specifies the commands that the *sysadmin* user is permitted to run with *sudo* privileges on the system. We are able to utilize *sudo* and run *less* - a [pager](https://www.geeksforgeeks.org/paging-in-operating-system/) allowing us to interactively view file contents page by page, with elevated privileges. This was the method we used to launch a shell with root privileges.

*The Command Utilized:*                                                                                                    
![Flag 7 - less command](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/c6663f4c-bd7d-4f71-8748-51206ff9690d)

Open the command mode with "**:**", then launch a bash shell with "**!bash**". This was successful, and we were able to change the password for the *root* user.

*Illustration of Changing the Password.*                                                                                        
![flag 7 - root pass reset](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/a54e622e-b665-4170-8ab2-0832985b1a37)

After changing the *root* password, we exited the *root shell*, and then re-entered the *root* account using the new password. This successful login gave us access to flag 7.

*Successful login revealed Flag 7.*                                                                                                        
![flag 7](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/9299b52f-b2f9-4651-9e22-0e8105471226)

### Flag 8

With *root* privileges, we can search the entire system for flags and consolidate them into a single file. We began by running a case-insensitive and recursive search for all flags within non-*root* users' directories. This search allowed us to locate files containing the term *'flag'*. The command we used:

  + grep -ir 'flag' /home/

*Illustration pulling the Non-Root user Flags.*                                                                                          
![Flag 8 - non root flags](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/b0758d15-c0ce-4877-895c-e3d391bf2f35)

This revealed five out of the seven flags. We need to add the missing flags, 5 and 7, separately. The following commands were used to compile all the flags into a text file:

  + grep -ir 'flag' /home/ > flags
  + cat /var/tmp/5galf >> flags
  + grep -r 'flag' /root/.bashrc >> flags

*Illustration of the Text File Contents.*                                                                                          
![flag 8 - txt file contents](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/6e4dded0-5e6e-4a67-af7a-8931cdfc32ca)

The flags file needs to be in a *username:hashed-password* format, in order to be cracked by [John the Ripper](https://www.openwall.com/john/). We used the [nano text editor](https://www.nano-editor.org/dist/latest/faq.html), to get rid of the unnecessary content. 

*Illustration of the Appended Content.*                                                                                                
![flag 8 - initial txt file append](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/662a0339-ff4e-45c5-b26c-f495207ae0d2)

Flag 6 has three backslashes that need to be removed.

*Final Text File Contents:*                                                                                                    
![hashed password list](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/05f96b23-c353-4a5d-8d4d-6372e2bb1194)

The text file can now be run through *john*, using the word list found with Flag 1.

*Cracked Passwords for Flag 8.*                                                                                            
![Cracked password list](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/b0f036f0-7cd4-464b-b2fb-e1a230517124)

The final flag, 8, was the statement *- "Congratulations you have completed this cyber challenge."*

## Appendix *- Key Figures*

During this capture the flag challenge, I saw the names of influential figures in the fields of computing, technology, and cybersecurity. While some of these figures were familiar to me, others were not. In this section; I expand on the background, contributions, and significance of these individuals, and their impact on the digital landscape.

### Ancheta
Full Name: [Jeanson James Ancheta](https://www.justice.gov/archive/criminal/cybercrime/press-releases/2005/anchetaArrest.htm)
  + Also known as "ir Resilient" or "Zombie King", is a hacker who gained infamy for orchestrating a large-scale botnet operation. He utilized the [RXBot computer worm](https://scholarworks.sjsu.edu/cgi/viewcontent.cgi?referer=&httpsredir=1&article=4669&context=etd_theses), to infect hundreds of thousands of computers worldwide.
  + He used these compromised computers to launch distributed denial-of-service (DDoS) attacks, steal sensitive information, and install malicious software, among other nefarious activities.
  + In 2005, Ancheta was apprehended by law enforcement authorities as a result of a joint investigation involving the FBI, the U.S. Department of Defense, and other agencies. He was charged with multiple counts of cybercrime, including conspiracy, fraud, and unauthorized access to computers.

### Anonymous
Referring to: [The Hacker Group](https://www.anonymoushackers.net/anonymous-history/)
  + A decentralized collective of online and offline activists known for engaging in direct action, hacktivism, and other subversive activities.
  + Founded on 4chan in 2003, the group lacks formal leadership or membership structures, operating instead as a network of individuals with shared interests.
  + They advocate for internet freedom, challenge censorship, and have been involved in various high-profile operations, often using the iconic Guy Fawkes masks as a symbol.
     
### Assange
Full Name: [Julian Paul Assange](https://www.justice.gov/opa/press-release/file/1153486/dl)
  + An Australian computer programmer, editor, publisher, and activist known for founding [WikiLeaks](https://wikileaks.org/What-is-WikiLeaks.html), a website that publishes classified and confidential information provided by anonymous sources.
  + Assange gained international attention for his involvement in releasing classified documents related to war, diplomacy, and surveillance.
  
### Astra
Full Name: [Real Name Withheld](https://www.scmagazine.com/news/hacker-arrested-in-greece-for-stealing-selling-weapons-data) 
  + A 58-year-old Greek mathematician who hacked into the computer systems of France's Dassault Group over a five-year period.
  + Astra stole weapons technology data and 3D modeling software, which they subsequently sold to at least 250 individuals across various countries, including Brazil, France, Germany, Italy, South Africa, and the Middle East. Dassault initiated a global manhunt, ultimately tracing ASTRA to an apartment in Athens in January 2008.

### Babbage
Full Name: [Charles Babbage](https://cse.umn.edu/cbi/who-was-charles-babbage)
  + An English polymath renowned for his contributions across various fields including mathematics, philosophy, invention, and mechanical engineering. He is commonly hailed as the "father of the computer".
  + He is best known for his pioneering work in developing early mechanical computers. He conceptualized [the Difference Engine](https://ed-thelen.org/bab/DoronSwadeIEEE.pdf) in 1821 and [the Analytical Engine](https://web.archive.org/web/20160304081812id_/http://profs.scienze.univr.it/~manca/storia-informatica/babbage.pdf) in 1837.
  + The Difference Engine was designed to automate complex mathematical calculations. Its primary purpose was to produce accurate tables of mathematical functions. The design was based on the [Finite Difference Method](https://www.ljll.fr/frey/cours/UdC/ma691/ma691_ch6.pdf), a mathematical technique for approximating values of functions by examining the differences between successive values. Additionally, it had the ability to compute values to a high degree of precision, exceeding the capabilities of [human calculators](https://en.wikipedia.org/wiki/Mental_calculator).
  + The Analytical Engine is a mechanical computing device designed to perform a wide range of calculations and operations. It was intended to be a universal computing machine, capable of executing any sequence of instructions and had a [Central Processing Unit](https://www.geeksforgeeks.org/central-processing-unit-cpu/) (CPU), which could execute instructions stored on [punch cards](https://en.wikipedia.org/wiki/Punched_card). Additionally, it included memory storage, allowing it to store and manipulate data throughout computations. Unfortunately, Babbage was never able to construct a working model of the Analytical Engine during his lifetime.

### Berners-Lee
Full Name: [Sir Timothy John Berners-Lee](https://webfoundation.org/about/sir-tim-berners-lee/)
  + Commonly known as Tim Berners-Lee, a British computer scientist, best known for inventing the World Wide Web.
  + In 1989, while working at CERN (the European Organization for Nuclear Research) in Switzerland, Berners-Lee proposed the concept of a distributed hypertext system to facilitate communication and collaboration among researchers. He developed the [first web browser](https://digital-archaeology.org/the-nexus-browser/), called WorldWideWeb (later renamed Nexus).
  + Berners-Lee's groundbreaking work laid the foundation for the modern internet and revolutionized the way people access, share, and interact with information online.
  + In 1991, Berners-Lee made the World Wide Web freely available to the public, releasing the source code for the first web browser and web server software. This decision to make the web an open and accessible platform for all users was instrumental in its rapid growth and adoption.

### Bevan
Full Name: [Mathew Bevan](https://irp.fas.org/congress/1996_hr/s960605b.htm)
  + Also known by his hacker alias "Kuji", gained notoriety in 1996 for his involvement in hacking into secure US government networks, particularly the files of the Griffiss Air Force Base Research Laboratory in New York.
  + Born in Cardiff, Wales, Bevan was just 21 years old when arrested. He was part of a hacking duo that included Richard Pryce, also known as "Datastream Cowboy".
  + His motive was to prove a UFO conspiracy theory, a goal he pursued using his hacking skills and a Commodore Amiga computer loaded with a blueboxing program called Roxbox.
       
### Calce
Full Name: [Michael Calce](https://www.blackhatethicalhacking.com/articles/hacking-stories/mafiaboy-the-hacker-who-took-down-the-internet/)
  + Also known as "MafiaBoy", is a security expert and former computer hacker from Île Bizard, Quebec.
  + In February 2000, he initiated a sequence of widely publicized denial-of-service attacks targeting major commercial websites such as Yahoo, Fifa, Amazon, Dell, eBay, and CNN.
  + In September 2001, he pleaded guilty to 55 counts of illegal access to computer systems and was sentenced to eight months of open custody, restricted use of the internet, and a small fine.
  
### Gates
Full Name: [Bill Gates](https://www.britannica.com/biography/Bill-Gates)
  + A computer programmer, businessman, and philanthropist from Seattle, Washington.
  + Widely recognized as a co-founder of Microsoft Corporation, which he established alongside [Paul Allen](https://www.britannica.com/biography/Paul-Allen) in 1975.
  + While Microsoft had early success with programming languages and applications, it was the release of [Windows 1.0](https://microsoft.fandom.com/wiki/Windows_1.0) in 1985 that propelled the company to new heights. Providing a user-friendly graphical interface for personal computers, making them more accessible to the general public and leading to widespread adoption.
  
### Gonzalez
Full Name: [Albert Gonzalez](https://www.blackhatethicalhacking.com/articles/albert-gonzalez-the-get-rich-or-die-trying-crew-who-stole-130-million-credit-card-numbers/)
  + Also known as "SoupNazi", this infamous hacker gained notoriety for orchestrating the largest combined credit card theft and subsequent reselling operation in history.
  + From 2005 to 2007, he masterminded the theft and distribution of over 170 million card and ATM numbers.
  + In 2008, Gonzalez was [apprehended by the U.S. Secret Service](https://www.justice.gov/opa/pr/leader-hacking-ring-sentenced-massive-identity-thefts-payment-processor-and-us-retail) as part of "Operation Get Rich or Die Tryin'". This targeted individuals involved in cybercrimes, specifically those responsible for the TJX and Heartland breaches.
  
### Gosling
Full Name: [James Gosling](https://www.sis.pitt.edu/mbsclass/hall_of_fame/gosling.html)
  + A Canadian computer scientist, renowned for creating the [Java programming language](https://www.java.com/en/download/help/whatis_java.html#:~:text=Java%20is%20a%20programming%20language,services%20and%20applications%20are%20built.).
  + Java, unveiled by Sun Microsystems in 1995, was designed to be platform-independent, robust, secure, and easy to use.
  + It became the foundation for countless web-based applications and services, powering everything from websites to enterprise systems. 
  
### Hopper
Full Name: [Grace Hopper](https://obamawhitehouse.archives.gov/blog/2014/12/22/honoring-grace-hopper)
  + Known affectionately as "Amazing Grace" and "Grandma COBOL". She was a computer scientist, mathematician, and United States Navy Rear Admiral.
  + She created the first compiler, [the A-0 System](https://www.computinghistory.org.uk/det/5487/Grace-Hopper-completes-the-A-0-Compiler/), in 1951. Which allowed programmers to write code in a more human-readable form rather than in machine code.
  + In 1959 she developed and standardized the [Common Business-Oriented Language (COBOL)](https://www.geeksforgeeks.org/what-is-cobolcommon-business-oriented-language/) programming language.
  + Throughout her career, she actively promoted diversity and encouraged more women to pursue careers in STEM fields.
  
### James
Full Name: [Jonathan Joseph James](https://www.blackhatethicalhacking.com/articles/jonathan-james-the-teenager-who-hacked-nasa-for-fun/)
  + An American hacker, known by the alias "C0mrade". In 2000, he was the first juvenile incarcerated for cybercrime in the United States.
  + By age fifteen (15), he hacked into several high-profile organizations, including the Department of Defense (DoD) and NASA. In 1999, he managed to access NASA's network and download software worth approximately $1.7 million. Claiming that he did this to prove that he could, rather than for malicious purposes.
  + In 2007 Jonathan James was linked to the [TJX data breach](https://www.ftc.gov/sites/default/files/documents/cases/2008/03/080327complaint_0.pdf), through an unknown pseudonym “JJ”. However, he denied any involvement and the agents could not find anything to connect him with the ongoing crimes.
  + In May 2008, at the age of 24, his life ended by suicide at his home in Pinecrest, Florida.
  
### Kernighan
Full Name: [Brian Kernighan](https://www.cs.princeton.edu/people/profile/bwk)
  + A Canadian computer scientist name became widely known through co-authorship of the first book on the C programming, [The C Programming Language](https://github.com/CJanecka/Projects_and_CTFs/files/14781948/The_C_Programming_Language_.2nd_Edition_Ritchie_Kernighan.pdf), with Dennis Ritchie.
  + This book played a significant role in the development of the C programming language and Unix operating system.
  + In a 2003 [interview with the Linux Journal](https://www.linuxjournal.com/article/7035), Kernighan emphasized that he played no role in the design of the C language, stating - *"it's entirely Dennis Ritchie's work"*.
        
### Knuth
Full Name: [Donald Ervin Knuth](https://www.britannica.com/biography/Donald-Knuth)
  + An American computer scientist and mathematician that has been referred to as the "father of the analysis of algorithms".
  + Known for his contributions to the analysis of algorithms and the creation of the [TeX typesetting system](https://ctan.org/tex?lang=en) and the associated [METAFONT](https://ctan.org/pkg/metafont?lang=en) font definition language.
  + Knuth's most famous work is his multivolume series [The Art of Computer Programming](https://www-cs-faculty.stanford.edu/~knuth/taocp.html). Initiated in 1962, this undertaking aims to represent the core of computer programming for sequential machines.
  
### Lamo
Full Name: [Adrian Lamo](https://www.blackhatethicalhacking.com/articles/hacking-stories/andrian-lamo-homeless-hacker/)
  + An American hacker, dubbed "The Homeless Hacker", and a controversial figure within the cybersecurity and hacking communities.
  + In the early 2000s, he gained notoriety through a series of attacks against major corporations, which were largely benign in nature. His goal was to demonstrate point - If someone like him, who relied on borrowed internet access from a local Kinko’s, could easily breach companies such as AOL, Yahoo, Microsoft, and The New York Times; then, anyone could exploit them.
  + In 2010, [Chelsea Manning](https://www.britannica.com/biography/Chelsea-Manning) (then known as Bradley Manning) - an American activist, whistleblower, and former U.S. Army intelligence analyst who leaked classified documents to WikiLeaks, including diplomatic cables and military logs; made contact with Adrian Lamo via online chat, confiding in him about the leaks and expressing personal struggles. Lamo ultimately chose to disclose their exchanges to authorities, ultimately leading to Manning's arrest.
  
### Lovelace
Full Name: [Augusta Ada Byron, Countess of Lovelace](https://www.sdsc.edu/ScienceWomen/lovelace.html)
  + An English mathematician and writer, known for her work on Charles Babbage's proposed mechanical general-purpose computer, the [Analytical Engine](https://www.britannica.com/technology/Analytical-Engine).
  + Ada translated an article about the Analytical Engine, by the Italian mathematician Luigi Federico Menabrea, from French to English. In this translation, she included extensive notes and annotations, three times the length of the original article. Expanding on the capabilities of the Analytical Engine, foreseeing its potential beyond mere number-crunching. She suggested algorithms for the Engine to compute [Bernoulli numbers](https://www.whitman.edu/documents/academics/majors/mathematics/2019/Larson-Balof.pdf), which are considered the first published algorithms specifically tailored for implementation on a computer.
  + Despite her groundbreaking work, Lovelace's contributions were not widely recognized during her lifetime, partly due to the prevailing gender biases of the time. However, her work gained renewed attention in the mid-20th century, with computer scientists and historians acknowledging her as a pioneer in the field of computing.
  + She is now widely considered the world's first computer programmer.
  
### Mitnik
Full Name: [Kevin Mitnick](https://www.mitnicksecurity.com/about-kevin-mitnick-mitnick-security)
  + An American computer security consultant, author, and the most notorious hacker of all time. He led a remarkable journey as he transitioned from his origins as a black-hat hacker, to emerge as a prominent figure in cybersecurity consulting.
  + He gained notoriety during the 1980s and 1990s by engaging in a series of unauthorized intrusions into the computer networks of 40 industry giants. Among his targets were IBM, Nokia, and Motorola; where he managed to gain unauthorized access to sensitive information, including proprietary data and source code. His ability to penetrate supposedly secure systems earned him a reputation as one of the most skilled hackers to date.
  + In 1995, Mitnick was [apprehended by the FBI](https://www.justice.gov/archive/opa/pr/Pre_96/February95/89.txt.html) after a highly publicized pursuit that involved extensive media coverage. His arrest marked the culmination of a years-long cat-and-mouse game between him and law enforcement agencies. He faced a series of legal proceedings and was ultimately convicted of multiple charges related to computer and wire fraud, as well as unauthorized access to computer systems.
  + Upon release from prison, Mitnick redirected his talents toward constructive endeavors, leveraging his intimate understanding of hacking techniques for the greater good. Drawing on his firsthand experiences, he emerged as a trusted advisor, guiding organizations through the intricacies of cybersecurity.
  
### Poulsen
Full Name: [Kevin Lee Poulsen](https://www.blackhatethicalhacking.com/articles/hacking-stories/kevin-poulsen-dark-dante-and-his-hacking-activities-on-arpanets-networks/)
  + Also known by the moniker "Dark Dante", a former black-hat hacker who transitioned into a career as a journalist and cybersecurity expert.
  + He gained notoriety through a KIIS-FM phone hack in 1990; during which, Poulsen commandeered all telephone lines for the Los Angeles radio station KIIS-FM, ensuring that he would be the 102nd caller and secure the prize of a Porsche 944 S2.
  + In 1983, Poulsen hacked into [ARPANET](https://www.techtarget.com/searchnetworking/definition/ARPANET#:~:text=The%20U.S.%20Advanced%20Research%20Projects,for%20academic%20and%20research%20purposes.), the Pentagon’s computer network. Despite being swiftly apprehended, the government opted to give Poulsen, who was a minor at the time, a warning.
  + In 1991, he was arrested and charged with multiple counts of computer fraud, wire fraud, and conspiracy. Following his arrest, Poulsen made legal history as the first American to be released from prison with a court-imposed prohibition against using computers and the internet after serving his sentence.
  
### Pryce
Full Name: [Richard Pryce](https://www.soldierx.com/hdb/Datastream-Cowboy)
  + A British hacker, also known as "Datastream Cowboy", and part of a hacking duo with Matthew Bevan (Kuji) which gained notoriety in 1996 by hacking into numerous military networks; including, the [Griffiss Air Force Base and the Korea Atomic Energy Research Institute (KAERI)](https://irp.fas.org/congress/1996_hr/s960605b.htm).
  + At 16 years old, Pryce hacked into the KAERI facility, extracting and transferring the institute's database contents into the United States Air Force (USAF) computer system. The data's origins being unknown raised concerns; if North Korea discovered this, they could have interpreted the data theft as an intrusion by the USAF, potentially sparking retaliatory actions due to perceived espionage, it was later determined that the data belonged to South Korea.
  + As per Supervisory Special Agent Jim Christy of the Air Force Office of Special Investigations, Pryce was one of two hackers whose actions nearly incited a third world war.
  
### Ritchie
Full Name: [Dennis MacAlistair Ritchie](https://www.sis.pitt.edu/mbsclass/hall_of_fame/ritchie.html)
  + An American computer scientist who developed the [C programming language](https://www.geeksforgeeks.org/c-programming-language/) and [Unix operating system](https://www.geeksforgeeks.org/introduction-to-unix-system/), at Bell Labs from the 1960s to 1970s.
  + Unix was co-developed with Ken Thompson and introduced several concepts, such as a hierarchical file system, multi-user support, and a shell for command-line interaction, which have since become standard features in many operating systems.
  + C is a flexible, efficient, and portable programming language for the Unix OS. Released in 1972, it's simplicity and power made it immensely popular among programmers. Many modern programming languages; such as, [C++](https://www.geeksforgeeks.org/c-plus-plus/), [Java](https://www.ibm.com/topics/java), and [Python](https://www.geeksforgeeks.org/what-is-python/), have been influenced by or built upon C's syntax and concepts.
  
### Rossum
Full Name: [Guido van Rossum](https://gvanrossum.github.io/)
  + A Dutch programmer that created and released the [Python programming language](https://www.python.org/) in 1991.
  + The language was named after the British comedy group Monty Python, and designed with a concise syntax that emphasizes readability; combined with its extensive standard library, versatility, community, and open-source nature, which has made it a popular and widely used programming language.
  
### Stallman
Full Name: [Richard Matthew Stallman](https://www.sis.pitt.edu/mbsclass/hall_of_fame/stallman.html)
  + An American programmer and free software movement activist known for founding the [GNU project](https://www.gnu.org/gnu/thegnuproject.en.html), the FSF [(Free Software Foundation)](https://www.fsf.org/about/), and the LPF [(League for Programming Freedom)](https://groups.csail.mit.edu/mac/projects/lpf/).
  + In 1983, Stallman launched the GNU Project, an initiative aimed at developing a complete Unix-like operating system composed entirely of free software. The project's name, "GNU", is a recursive acronym that stands for *GNU's Not Unix*.
  + The FSF was established in 1985, and stands to promote the rights of users *- to run, study, distribute, and modify computer software*. This is encapsulated in the FSF's seminal work; the GPL [(GNU General Public License)](https://www.gnu.org/licenses/gpl-3.0.en.html), which embodies the concept of [copyleft](https://www.gnu.org/licenses/copyleft.en.html#:~:text=Copyleft%20is%20a%20general%20method,in%20the%20public%20domain%2C%20uncopyrighted.) and ensures that software remains free for all users.
  + In 1989, he co-founded the LPF, which advocates for the rights of computer programmers and the preservation of software freedom. Their goal is to defend the principles of freedom in software development by opposing legislation and corporate policies that hinder programmers' ability to create and distribute software freely.
  
### Stroustrup
Full Name: [Bjarne Stroustrup](https://www.stroustrup.com/)
  + A Danish computer scientist known for creating the [C++ programming language](https://www.geeksforgeeks.org/c-plus-plus/) at Bell Labs in 1985.
  + C++ is an extension of the [C programming language](https://www.geeksforgeeks.org/c-plus-plus/), envisioned as a language that combines the efficiency and low-level control of C with high-level features such as classes, inheritance, and polymorphism. This led to the introduction of OOP [(Object-oriented programming)](https://www.geeksforgeeks.org/introduction-of-object-oriented-programming/) to the C language.
  
### Thompson
Full Name: [Kenneth Lane Thompson](https://www.britannica.com/biography/Kenneth-Lane-Thompson)
  + An American computer scientist who worked at [Bell Labs](https://en.wikipedia.org/wiki/Bell_Labs); and is known for, co-creating the Unix OS *(alongside Dennis Ritchie)*, inventing the [B programming language](https://www.bell-labs.com/usr/dmr/www/btut.pdf), being one of the early developers of the [Plan 9 operating system](https://9p.io/plan9/about.html).
  + The *B language* was developed in 1969, and intended for writing computer programs that could repeat tasks, handle data that isn't just numbers, and work on different types of computers. B is a [typeless language](https://wiki.c2.com/?TypelessVsDynamic) that uses the basic memory format of the computer it is running on. Essentially all data is treated as just a bunch of numbers. Depending on what the program is doing, these numbers could be treated either as regular whole numbers *(integers)* or as memory addresses, which point to locations in the computer's memory where data is stored.
  + In 2003 Bell Labs released the Plan 9 OS, a distributed operating system that allows users and programs to access resources from any machine on the network. It incorporates network transparency into its design, meaning that network communications are abstracted away from the applications using them. This allows programs to communicate with each other and access remote resources without needing to be aware of the underlying network details.
  + In 2009, Thompson was one of the co-developers at Google for the [Go programming language](https://go.dev/doc/). Referred to as *Golang*, this open-source programming language was designed to be simple, efficient, and easy to learn. Its user-friendly nature made it a popular choice for building scalable network services, web applications, and command-line tools.
  
### Torvalds
Full Name: [Linus Benedict Torvalds](https://www.britannica.com/biography/Linus-Torvalds)
  + A Finnish-American software engineer, is known for his creation and development of the [Linux kernel](https://www.redhat.com/en/topics/linux/what-is-the-linux-kernel), alongside the establishment of one of the most used distributed version control systems [Git](https://www.geeksforgeeks.org/what-is-a-git-repository/).
  + In 1991 Linus developed the Linux Kernel; a foundational component of the Linux operating system, that serves as the bridge between the hardware and the software layers, managing system resources, facilitating communication between hardware devices, and providing essential services to higher-level software applications.
  + Git is a [distributed version control system](https://www.geeksforgeeks.org/centralized-vs-distributed-version-control-which-one-should-we-choose/) (DVCS) created by Torvalds in 2005, designed to track versions of files and store them in a dedicated location known as a repository. Within these repositories, users can perform a multitude of operations to create different versions of a project. *This includes - [commiting changes](https://www.git-tower.com/learn/git/commands/git-commit), [branching](https://www.git-tower.com/learn/git/commands/git-branch#:~:text=The%20Tower%20Git%20client%20allows,be%20more%20productive%20with%20Git!), [merging](https://www.git-tower.com/help/guides/branches-and-tags/merge-rebase/windows), [reverting changes](https://www.git-tower.com/help/guides/commit-history/undo-commits/windows#:~:text=The%20%22revert%22%20feature%20solves%20a,the%20effect%20of%20those%20changes.), [reviewing history](https://www.git-tower.com/blog/investigating-git-history/), and [collaborabtion](https://vickysteeves.gitlab.io/collaborating-with-git/collaborating-with-git.html).*
  
### Wirth
Full Name: [Niklaus Emil Wirth](https://www.britannica.com/biography/Niklaus-Emil-Wirth)
  + A Swiss computer scientist and recipient of the [A.M. Turing Award in 1984](https://amturing.acm.org/award_winners/wirth_1025774.cfm). He designed a series of pioneering programming languages; including, Pascal, Modula, and Oberon. Which significantly influenced the development of programming languages and software engineering.
  + The [Pascal language](https://www.studysmarter.co.uk/explanations/computer-science/computer-programming/pascal-programming-language/) was completed in 1970 and named after the French mathematician and physicist [Blaise Pascal](https://plato.stanford.edu/entries/pascal/#PasWor). It emphasized on structured programming, strong typing, modularization, and was suitable for both educational and professional use. Earlier languages like [Fortran](https://www.ibm.com/history/fortran) and [BASIC](https://interestingengineering.com/innovation/basic-the-first-computer-language-for-the-masses) notoriously used [*spaghetti code*](https://craftofcoding.wordpress.com/wp-content/uploads/2013/10/lore_spaghetti.pdf) *- A programming style characterized by its lack of structure and organization, making it challenging to work with*.
  + *Modula* is a descendant of Pascal [published in 1976](https://typeset.io/pdf/modula-a-language-for-modular-multiprogramming-470x3ovyzt.pdf). Modula-1 introduced the concept of modules, which were used to group related data and procedures into [program units](https://www.ibm.com/docs/en/openxl-fortran-aix/17.1.0?topic=procedures-program-units-subprograms). Building on this; Wirth released [Modula-2](https://en.wikipedia.org/wiki/Modula-2) in 1978, by introducing stronger typing, an improved module system, and support for system programming. 
  + In 1987, Wirth introduced [Oberon](https://people.inf.ethz.ch/wirth/Oberon/Oberon.Report.pdf) as a successor to Modula-2, naming it after the moon of Uranus. Oberon was designed to be a minimalist language, offering features such as strong typing, modular programming, and a lightweight runtime system.

### Woz
Full Name: [Steve Wozniak](https://www.britannica.com/biography/Stephen-Gary-Wozniak)
  + An American electrical engineer and computer programmer who co-founded [Apple Computer](https://guides.loc.gov/this-month-in-business-history/april/apple-computer-founded) with [Steve Jobs](https://www.britannica.com/biography/Steve-Jobs) in 1976. The duo started the company in the Jobs family garage, with Wozniak handling the technical side and Jobs managing the business aspects. Wozniak's most notable contributions include the design of the Apple I and Apple II computers.
  + The [Apple I](https://americanhistory.si.edu/collections/nmah_1692121) was Apple's inaugural product, and one of the first personal computers to feature a single-board design, making it easier to assemble and operate. This simplified construction made the computer more affordable and easier to assemble, as it required fewer components and connections. It was initially offered as a DIY kit priced at $666.66, and included the circuit board, pre-assembled components, and a manual with schematics and assembly instructions. There are less than 100 Apple I computers known to exist, making them a sought-after [collector's item](https://en.wikipedia.org/wiki/Apple_I#:~:text=Apple%20I%20computers%20with%20original,auctioned%20in%202022%20for%20%24677%2C196.).
  + In 1977 the [Apple II](https://americanhistory.si.edu/collections/nmah_334638) was released and positioned as a fully assembled, ready-to-use personal computer targeted at a broader consumer market. It revolutionized personal computing with its integrated keyboard, color graphics, expandable architecture featuring seven expansion slots, built-in BASIC interpreter for programming, audio support, and versatile peripheral connectivity, all packaged in a user-friendly design.
