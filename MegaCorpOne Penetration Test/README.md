# MegaCorpOne Penetration Test

![portfolio3](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/dee4c490-0fb5-4151-8556-5b4f990f849d)

## Table of Contents

  + [01. Overview](#Overview)
  + [02. Project Requirements](#Project-Requirements)
  + [03. Equipment and Tools](#Equipment-and-Tools)
  + [04. Executive Summary](#Executive-Summary)
  + [05. Vulnerability Findings](#Vulnerabilty-Findings)
  + [06. Mitigations](#Mitigations)

## Overview

On behalf of IronCurtain Testing, LLC, I undertook a solo penetration test with a focus on scrutinizing the web application, Linux hosts, and Windows hosts of the fictional entity, *MegaCorpOne*. This assessment brought to light notable security vulnerabilities within these systems. Here, I present an outline of my findings, emphasizing key vulnerabilities identified during the evaluation. The complete pen-test report is provided as a PDF, in this GitHub repository, titled [MegaCorpOne - Penetration Test Report](https://github.com/CJanecka/Projects_and_CTFs/files/14173862/MegaCorpOne.-.Penetration.Test.Report_Collin.Janecka.pdf). This document encapsulates my assessment findings, including all of the identified vulnerabilities and suggested ways to address each concern.

## Project Requirements

The project requirements included:

  + Providing an analysis of security flaws present in MegaCorpOne’s web applications, networks, and systems.

  + Utilizing the MITRE framework to discover vulnerabilities in the organization’s Linux and Windows hosts.

  + Documenting my findings and recommended mitigations in a penetration testing summary report.

## Equipment and Tools

***Technologies Used:*** Penetration testing methodology, OSINT (Google dorking, Shodan, certificate transparency), MITRE matrix, Nmap (with NSE scripts), Metasploit, Privilege Escalation, John the Ripper, Lateral Movement, Mimikatz, msfvenom, Meterpreter, Windows and Linux OS, DC replication, DCSync attack, Persistence, Reporting.

  + Conducted a penetration test on a simulated organization using the Penetration Testing Execution Standard (PTES) methodology and the MITRE Adversarial Tactics, Techniques, and Common Knowledge (ATT&CK) framework.

  + Found and successfully exploited vulnerabilities in the organization's web application, Linux, and Windows hosts.

  + Summarized the results and suggested ways to address the identified issues in a detailed penetration testing report.

## Executive Summary

I conducted a solo penetration test, focusing on a simulated organization called *MegaCorpOne*. My assessment honed in on the organization's web application, Linux, and Windows hosts, revealing vulnerabilities and security weaknesses. The conclusion of this effort led to the creation of a detailed penetration testing report. In this report, I outline the findings, highlighting identified vulnerabilities across the assessed domains. Furthermore, I present a set of recommendations aimed at mitigating the discovered security concerns.

## Vulnerability Findings

I found seven vulnerabilities throughout MegaCorpOne's network. Included here are two of those vulnerabilities deemed critical. See the report, linked above, for additional information on the vulnerabilities found.

  1. **Weak Password(s) on Public Web Application**

     By browsing MegaCorpOne's public web page, I obtained the credentials of five employees through process of deduction. The compromised users included: Tom Hudson (Web Designer), Tanya Rivera (Senior Developer), Matt Smith (Marketing Director), Mike Carlow (VP of Legal), and Alan Grofield (IT & Security Director).

     *Figure 01 - Portion of the webpage that discloses Executive Employee information.*                                          
     ![Executive Team](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/93901eb0-a930-417c-8b68-31cc10a6baa7)

     *Figure 02 - Portion of the webpage that discloses other employee information.*                                              
     ![Other Staff](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/b6a5c337-278c-4160-8e58-219d2a3f3ddd)

     From the list of employee emails, I discovered that MegaCorpOne uses the same characters before the "@" sign for some of their employee usernames. Specifically:

       + Tom Hudson: thudson
    
       + Tanya Rivera: trivera
    
       + Matt Smith: msmith
    
       + Mike Carlow: mcarlow
    
       + Alan Grofield: agrofield
    
     I was able to get the passwords, for each of these users, by guessing. These users had very simple passwords, Specifically:

       + Tom Hudson: thudson *(same as the username)*
    
       + Tanya Rivera: Spring2021
    
       + Matt Smith: Passw0rd
    
       + Mike Carlow: Pa55word
    
       + Alan Grofield: agrofield1
    
     With this information, I was able to log in and access MegaCorpOne's Index page. On this page was a shell script called *vpn.sh*, which was designed to enable direct employee access to "www.megacorpone.com".
