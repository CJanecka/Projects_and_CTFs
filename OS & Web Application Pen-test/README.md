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

During this three-day, Capture-the-Flag style, penetration test, I acted as a representative for *Ultimate Pentesting, LLC*. Hired by the ficticious organization *Rekall Corportion* to test their network. Both individual and collaborative efforts within a small team were utilized. The assessment focused on targeting the organization's web application, as well as its Linux and Windows hosts, systematically identifying vulnerabilities and potential security risks. The complete pen-test report is provided as a PDF in this GitHub repository titled [Rekall Corporation - Penetration Test Report](https://github.com/CJanecka/Projects_and_CTFs/files/14016819/Rekall.Corporation.-.Penetration.Test.Report._.Collin.Janecka.pdf). This detailed document provides a thorough analysis of my findings, including the identification of vulnerabilities, accompanied by a set of recommendations aimed at effectively mitigating the identified security concerns.

## Project Requirements

The project requirements included:

  + Examination of the organization's web application, leading to the discovery of vulnerabilities embedded in their website. Leveraging Burp Suite, identified and documented these vulnerabilities, aiming to fortify the organization's online security.

  + Employing the MITRE framework to systematically scrutinize the security of the organization's Linux and Windows hosts. Allowing vulnerabilities and potential threat vectors within the infrastructure to be uncovered.

  + Compiled findings and recommended mitigations into a comprehensive penetration testing report. This serves as a valuable resource for the organization, providing a clear roadmap for addressing vulnerabilities and enhancing their overall security posture.

## Equipment and Tools

***Technologies Used:*** Penetration testing methodology, MITRE framework, OSINT tools, Metasploit/Meterpreter, vulnerability scanning with Nmap and Nessus, Burp Suite.

  + Performed a penetration test on a simulated organization in accordance with the Penetration Testing Execution Standard (PTES) methodology and the MITRE Adversarial Tactics, Techniques, and Common Knowledge (ATT&CK) framework.
    
  + Identified and successfully exploited vulnerabilities within the organization's web application, as well as on Linux and Windows hosts.

  + Documented the findings and proposed mitigation strategies within a comprehensive penetration testing summary report.

## Executive Summary

I executed a thorough three-phase penetration test for Rekall Corporation's network, successfully meeting all predefined objectives. Each phase centered on scrutinizing web applications, Linux, and Windows system hosts, uncovering twenty-four vulnerabilities spanning from low to critical severity.

In Phase 1, my web application assessment identified pressing security issues, encompassing Cross-Site Scripting (XSS), Local File Inclusion (LFI), sensitive data leakage, and more. The report provides a detailed breakdown of specific vulnerabilities with corresponding flags, underscoring the necessity for swift attention.

Moving to Phase 2, the assessment of Linux systems unveiled critical vulnerabilities, including open-source data exposure, Apache Tomcat Remote Code Execution (RCE), Shellshock, and susceptibility in the Drupal service. My report emphasizes the urgency of addressing unauthorized privilege escalation promptly.

Transitioning to Phase 3, which focused on Windows systems, vulnerabilities related to GitHub credentials, anonymous FTP login, SLMail service exploitation, and NTLM exploits were revealed. My full report underscores the potential harm to Total Rekall's network and data, emphasizing the immediate need for mitigation.

The *Vulnerability Findings* section, of the report, provides a comprehensive breakdown, detailing potential risks to Rekall Corporation's network, data, and reputation. Here I have presented a diverse range of remediation recommendations for each idententified vulnerability, urging urgent attention to critical issues and prioritization based on severity. The suggested strategies offer a tailorable approach to enhance Rekall Corporation's security measures.

## Web Application Vulnerabilities

I found twelve vulnerabilities on the Web Application. Included here are three of those vulnerablilities deemed critical. See the report, linked above, for the other nine vulnerabilities found.

  1. Cross Site Scripting (XSS) *– Reflected & Stored*

     The ability to inject these scripts poses a significant security risk, as it could potentially enable an attacker to redirect your customers to fraudulent web pages, install keyloggers, or capture user cookies. This, 
     in turn, would allow malicious actors to pilfer customer data and exploit it for unauthorized access to your system, potentially launching further damaging attacks.

     I submitted the following script which successfully reflected on Rekall Corporation's home page, revealing Flag 1:

     + <script>alert(Document.cookie)</script>

     ![image](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/526f02a1-e0cb-4237-9518-609c44f5d363)

