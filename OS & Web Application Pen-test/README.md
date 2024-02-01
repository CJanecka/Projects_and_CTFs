# OS and Web Application Pen-test

![portfolio6](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/c270a7bf-30ee-4a68-8e82-f9eda9a1991e)

## Table of Contents

  + [01. Overview](#Overview)
  + [02. Project Requirements](#Project-Requirements)
  + [03. Equipment and Tools](#Equipment-and-Tools)
  + [04. Executive Summary](#Executive-Summary)
  + [05. Web Application Vulnerabilities](#Web-Application-Vulnerabilities)
  + [06. Linux Host Vulnerabilities](#Linux-Host-Vulnerabilities)
  + [07. Windows Host Vulnerabilities](#Windows-Host-Vulnerabilities)
  + [08. Mitigations](#Mitigations)

## Overview

During this three-day, Capture-the-Flag style, penetration test, I acted as a representative for *Ultimate Pentesting, LLC*. Hired by the ficticious organization *Rekall Corportion* to test their network. Both individual and collaborative efforts within a small team were utilized. The assessment focused on targeting the organization's web application, as well as its Linux and Windows hosts, systematically identifying vulnerabilities and potential security risks. The complete pen-test report is provided as a PDF in this GitHub repository titled [Rekall Corporation - Penetration Test Report](https://github.com/CJanecka/Projects_and_CTFs/files/14118993/Rekall.Corporation.-.Penetration.Test.Report._.Collin.Janecka.docx.pdf). This detailed document provides a thorough analysis of my findings, including the identification of vulnerabilities, accompanied by a set of recommendations aimed at effectively mitigating the identified security concerns.

## Project Requirements

The project requirements included:

  + Examination of the organization's web application, leading to the discovery of vulnerabilities embedded in their website. Leveraging Burp Suite, identified and documented these vulnerabilities, aiming to fortify the organization's online security.

  + Employing the MITRE framework to systematically scrutinize the security of the organization's Linux and Windows hosts. Allowing vulnerabilities and potential threat vectors within the infrastructure to be uncovered.

  + Compiled findings and recommended mitigations into a penetration testing report. This serves as a valuable resource for the organization, providing a clear roadmap for addressing vulnerabilities and enhancing their overall security posture.

## Equipment and Tools

***Technologies Used:*** Penetration testing methodology, MITRE framework, OSINT tools, Metasploit/Meterpreter, vulnerability scanning with Nmap and Nessus, Burp Suite.

  + Performed a penetration test on a simulated organization in accordance with the Penetration Testing Execution Standard (PTES) methodology and the MITRE Adversarial Tactics, Techniques, and Common Knowledge (ATT&CK) framework.
    
  + Identified and successfully exploited vulnerabilities within the organization's web application, as well as on Linux and Windows hosts.

  + Documented the findings and proposed mitigation strategies within a comprehensive penetration testing summary report.

## Executive Summary

I executed a thorough three-phase penetration test for Rekall Corporation's network, successfully meeting all predefined objectives. Each phase centered on scrutinizing web applications, Linux, and Windows system hosts, uncovering twenty-four vulnerabilities spanning from low to critical severity.

In Phase 1, my web application assessment identified pressing security issues, encompassing Cross-Site Scripting (XSS), Insecure Direct Object Reference (IDOR), Local File Inclusion (LFI), sensitive data leakage, and more. The report provides a detailed breakdown of specific vulnerabilities with corresponding flags, underscoring the necessity for swift attention.

Moving to Phase 2, the assessment of Linux systems unveiled critical vulnerabilities, including open-source data exposure, Apache Tomcat Remote Code Execution (RCE), Shellshock, and susceptibility in the Drupal service. My report emphasizes the urgency of addressing unauthorized privilege escalation promptly.

Transitioning to Phase 3, which focused on Windows systems, vulnerabilities related to GitHub credentials, anonymous FTP login, SLMail service exploitation, and NTLM exploits were revealed. My full report underscores the potential harm to Total Rekall's network and data, emphasizing the immediate need for mitigation.

The *Vulnerability Findings* section, of the report, provides a comprehensive breakdown, detailing potential risks to Rekall Corporation's network, data, and reputation. Here I have presented a diverse range of remediation recommendations for each idententified vulnerability, urging urgent attention to critical issues and prioritization based on severity. The suggested strategies offer a tailorable approach to enhance Rekall Corporation's security measures.

## Web Application Vulnerabilities

I found twelve vulnerabilities on the Web Application. Included here are two of those vulnerablilities deemed critical. See the report, linked above, for the other ten vulnerabilities found.

  1. **Cross Site Scripting (XSS)** *– Reflected & Stored*

     The ability to inject these scripts poses a significant security risk, as it could potentially enable an attacker to redirect your customers to fraudulent web pages, install keyloggers, or capture user cookies.            This, in turn, would allow malicious actors to pilfer customer data and exploit it for unauthorized access to your system, potentially leading to further damaging attacks.

     On Rekall Corporation's *Home page*, I submitted the following script within the input field designated as "Begin by entering your name below!". 

      + <script>alert(Document.cookie)</script>

      This script is intended to display a pop-up alert containing the value of the "*Document.cookie*" property.

     *Figure 01 - Shows the script successfully reflected revealing Flag 1.*
     
     ![image](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/526f02a1-e0cb-4237-9518-609c44f5d363)

     I then accessed the *Memory Planner page*, and submitted the following script within the input field "Who do you want to be?".

     + <script>alert("You have been hacked")</script>

     This script is designed to display a pop-up alert with the message "You have been hacked" when it executed.

     *Figure 02 - Shows the script successfully reflected, by displaying the pop-up alert.*

     ![image](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/4e0fc79b-4ba9-4082-b8a7-4037c1d487c7)

     *Figure 03 - Upon closing the pop-up, Flag 2 was revealed.*

     ![image](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/8d50438b-be1d-40cd-aa1d-a5b7239bec03)

     From here I navigated to the *Comments page*, and submitted the following script within the *Comment input field.*

     + <script>alert(“Hope this works!”)</script>

     This script is designed to display a pop-up alert with the message "Hope this works!" when it executed.

     *Figure 04 - Shows the script successfully reflected, by revealing Flag 3.*

     ![image](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/b6ff98fd-8122-4302-8676-e5c5f35d11dc)

  2. **Insecure Direct Object Reference (IDOR)**
