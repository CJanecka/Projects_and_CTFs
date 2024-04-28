# MegaCorpOne Penetration Test

![portfolio3](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/dee4c490-0fb5-4151-8556-5b4f990f849d)

## Table of Contents

  + [01. Overview](#Overview)
  + [02. Equipment and Tools](#Equipment-and-Tools)
  + [03. Project Requirements](#Project-Requirements)
  + [04. Executive Summary](#Executive-Summary)
  + [05. Vulnerability Findings](#Vulnerabilty-Findings)
    - [a. Weak Passwords on Public Web Application](#Weak-Passwords-on-Public-Web-Application)
    - [b. Files with Administrative Credentials in Plain Text](#Files-with-Administrative-Credentials-in-Plain-Text)
  + [06. Mitigations](#Mitigations)

## Overview

On behalf of IronCurtain Testing, LLC, I undertook a solo penetration test with a focus on scrutinizing the web application, Linux hosts, and Windows hosts of the fictional entity, *MegaCorpOne*. This assessment brought to light notable security vulnerabilities within these systems. Here, I present an outline of my findings, emphasizing key vulnerabilities identified during the evaluation. The complete pen-test report is provided as a PDF, in this GitHub repository, titled [MegaCorpOne - Penetration Test Report](https://github.com/CJanecka/Projects_and_CTFs/files/14173862/MegaCorpOne.-.Penetration.Test.Report_Collin.Janecka.pdf). This document encapsulates my findings, including all of the identified vulnerabilities and suggested ways to address each concern.

## Equipment and Tools

The technologies used in this project include:

  + Penetration Testing Execution Standard [(PTES)](https://www.geeksforgeeks.org/penetration-testing-execution-standard-ptes/) methodology
  + Open Source Intelligence (OSINT) tools
    - [Google Dorking](https://www.geeksforgeeks.org/what-is-google-dorking/)
    - [Shodan.io](https://www.shodan.io/)
    - [Certificate Transparency](https://www.geeksforgeeks.org/ct-exposer-uncover-hidden-subdomains-and-reveal-internal-server-information/)
  + MITRE Adversarial Tactics, Techniques, and Common Knowledge [*(ATT&CK)* matrix](https://attack.mitre.org/)
  + Network Mapper *(Nmap)* scanning with NSE scripts
  + [Metasploit](https://www.metasploit.com/)
    - [Meterpreter](https://docs.metasploit.com/docs/using-metasploit/advanced/meterpreter/meterpreter.html)
    - [Mimikatz](https://www.offsec.com/metasploit-unleashed/mimikatz/#:~:text=Mimikatz%20is%20an%20attempt%20to,disk%20of%20the%20compromised%20host.)
    - [MSFvenom](https://docs.metasploit.com/docs/using-metasploit/basics/how-to-use-msfvenom.html)
  + [Privilege Escalation](https://www.geeksforgeeks.org/how-to-prevent-privilege-escalation/)
  + [John the Ripper](https://www.openwall.com/john/)
  + [Lateral Movement](https://www.crowdstrike.com/cybersecurity-101/lateral-movement/)
  + Windows and Linux OS
  + Reporting

## Project Requirements

The project requirements included:

  + Providing an analysis of security flaws present in MegaCorpOne’s web applications, networks, and systems.

  + Utilizing the MITRE framework to discover vulnerabilities in the organization’s Linux and Windows hosts.

  + Documenting my findings and recommended mitigations in a penetration testing summary report.

## Executive Summary

I have successfully completed a thorough security assessment aligned with the specified scope for this engagement. The evaluation focused on identifying vulnerabilities within Megacorpone's network infrastructure, encompassing reconnaissance and implementation/exploitation phases.

In the Reconnaissance phase, I utilized Google Dorking techniques to gather information, revealing security vulnerabilities and potential exposure of confidential data. Further enumeration of Megacorpone's domain using tools like Shodan.io and Nmap unveiled accessible ports and Common Vulnerabilities and Exposures (CVEs).

Moving to the Implementation/Exploitation phase, I deduced usernames and passwords, which gave me access to the webpage through a script. By exploiting a Python file found on the webpage, administrator-level credentials were acquired, leading to root level access. This escalated privilege provided me with control over files, commands, and system settings. Overly simple passwords were being used, and additional security risks were introduced, including a hidden access point and a novel administrative user.

The report linked above emphasizes the need for Megacorpone to promptly address these vulnerabilities to safeguard its network infrastructure and sensitive data. The "Vulnerability Findings" section provides detailed remediation strategies for a tailored security enhancement strategy. 

## Vulnerability Findings

I discovered seven vulnerabilities within MegaCorpOne's network. Below is a summary of these: 

![MCO-vuln list](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/37d38253-176e-4b0f-8744-83618cc37b48)

Included here are two of those vulnerabilities deemed critical. For further details; on all vulnerabilities identified and the grading methodology, used to assess the severity of each finding, please refer to the report linked above.

### Weak Passwords on Public Web Application

By browsing MegaCorpOne's public web page, I obtained the credentials of five employees through process of deduction. The compromised users included: Tom Hudson (Web Designer), Tanya Rivera (Senior Developer), Matt Smith (Marketing Director), Mike Carlow (VP of Legal), and Alan Grofield (IT & Security Director).

*Figure 01 - Portion of the webpage that discloses Executive Employee information.*                                          
![Executive Team](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/93901eb0-a930-417c-8b68-31cc10a6baa7)

*Figure 02 - Portion of the webpage that discloses other employee information.*                                              
![Other Staff](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/b6a5c337-278c-4160-8e58-219d2a3f3ddd)

From the list of employee emails, I discovered that MegaCorpOne uses the same characters before the "@" sign for some of their employee usernames. Specifically:

  + Tom Hudson: **thudson**
    
  + Tanya Rivera: **trivera**
    
  + Matt Smith: **msmith**
    
  + Mike Carlow: **mcarlow**
    
  + Alan Grofield: **agrofield**
    
I was able to get the passwords, for each of these users, by guessing. These users had very simple passwords, Specifically:

  + Tom Hudson: **thudson** *(same as the username)*
    
  + Tanya Rivera: **Spring2021**
    
  + Matt Smith: **Passw0rd**
    
  + Mike Carlow: **Pa55word**
    
  + Alan Grofield: **agrofield1**
    
Using this information, I logged into the employee portal and accessed MegaCorpOne's Index page. On this page, there was a downloadable shell script named *vpn.sh* intended to facilitate direct employee access to the webpage. I successfully adjusted the script, using the nano text editor, to incorporate the compromised credentials. This modification allowed me to utilize the VPN script and access MegaCorpOne's webpage without being prompted to log in.

*Figure 03 - VPN script location.*                                                                          
![script location](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/7869cfa9-df4f-44ce-9156-4412bea61f1d)

*Figure 04 - Modified script contents using "nano".*                                                                                
![modified script contents](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/9a7057c8-4d58-4747-9129-0b80fd8e7448)

The adjusted script ran successfully, granting me access to MegaCorpOne's Domain Controller. Through this connection, unauthorized individuals with malicious intent, are provided with the opportunity to exploit the network further, as shown in my full report.

### Files with Administrative Credentials in Plain Text

While operating through a reverse shell in Metasploit, I discovered a plaintext document addressed to *Jim*. This document contained administrator-level credentials, which I utilized to compromise MegaCorpOne's Linux machine.

*Figure 05 - Location and contents of the plaintext document.*                                                                          
![plaintext document](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/b42dd20b-2d10-4da1-94a5-ebfb7ea171cc)

I then opened a new terminal to test if the credentials were valid.

*Figure 06 - Administrator credentials shown working.*                                                                                      
![admin credentials working](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/64f5af79-5c13-4191-8b69-e3f04dad7f9f)

With the credentials working, I've effectively accessed the Linux machine as an administrative-level user. In my full report, you'll see how this can be leveraged for privilege escalation and persistence, posing a greater threat to the security of MegaCorpOne's network.

## Mitigations

My full report, accessible through the provided link above, includes a range of suggested strategies corresponding to each identified vulnerability and its respective host. These recommended mitigations aim to enable a customized approach in addressing the vulnerabilities.

The following shows how this is displayed in the attached report:

![MCO-vuln](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/d17c8218-c02c-4ef5-80bc-f93b90396d01)
