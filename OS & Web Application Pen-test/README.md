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

During this three-day, Capture-the-Flag style, penetration test, I acted as a representative for *Ultimate Pentesting, LLC*. Hired by the ficticious organization *Rekall Corportion* to test their network. Both individual and collaborative efforts within a small team were utilized. The assessment focused on targeting the organization's web application, as well as its Linux and Windows hosts, systematically identifying vulnerabilities and potential security risks. The complete pen-test report is provided as a PDF, in this GitHub repository, titled [Rekall Corporation - Penetration Test Report](https://github.com/CJanecka/Projects_and_CTFs/files/14118993/Rekall.Corporation.-.Penetration.Test.Report._.Collin.Janecka.docx.pdf). This detailed document provides a thorough analysis of my findings, including the identification of vulnerabilities, accompanied by a set of recommendations aimed at effectively mitigating the identified security concerns.

## Project Requirements

The project requirements included:

  + Examination of the organization's web application and leveraging Burp Suite, identifying and documenting these vulnerabilities, aiming to fortify the organization's online security.

  + Employing the MITRE framework to systematically scrutinize the security of the organization's Linux and Windows hosts. Allowing vulnerabilities and potential threat vectors within the infrastructure to be uncovered.

  + Compiled findings and recommended mitigations into a penetration testing report. Providing a clear roadmap for addressing vulnerabilities and enhancing the organization's overall security posture.

## Equipment and Tools

The technologies used in this project include:

  + Penetration Testing Execution Standard *(PTES)* methodology
  + MITRE Adversarial Tactics, Techniques, and Common Knowledge *(ATT&CK)* framework
  + Open Source Intelligence *(OSINT)* tools
  + Metasploit and Meterpreter
  + Vulnerability scanning with Nmap and Nessus
  + Burp Suite
  + Report writing

## Executive Summary

I executed a thorough three-phase penetration test for Rekall Corporation's network, successfully meeting all predefined objectives. Each phase centered on scrutinizing web applications, Linux, and Windows system hosts, uncovering twenty-four vulnerabilities spanning from low to critical severity.

In Phase 1, my web application assessment identified pressing security issues, encompassing Cross-Site Scripting (XSS), Insecure Direct Object Reference (IDOR), Local File Inclusion (LFI), sensitive data leakage, and more. The report provides a detailed breakdown of specific vulnerabilities with corresponding flags, underscoring the necessity for swift attention.

Moving to Phase 2, the assessment of Linux systems unveiled critical vulnerabilities, including open-source data exposure, Apache Tomcat Remote Code Execution (RCE), Shellshock, and susceptibility in the Drupal service. My report emphasizes the urgency of addressing unauthorized privilege escalation promptly.

Transitioning to Phase 3, which focused on Windows systems, vulnerabilities related to GitHub credentials, anonymous FTP login, SLMail service exploitation, and NTLM exploits were revealed. My full report underscores the potential harm to Total Rekall's network and data, emphasizing the immediate need for mitigation.

The *Vulnerability Findings* section, of the report, provides a comprehensive breakdown, detailing potential risks to Rekall Corporation's network, data, and reputation. Here I have presented a diverse range of remediation recommendations for each idententified vulnerability, urging urgent attention to critical issues and prioritization based on severity. The suggested strategies offer a tailorable approach to enhance Rekall Corporation's security measures.

## Web Application Vulnerabilities

I found twelve vulnerabilities on the Web Application. Included here are two of those vulnerablilities deemed critical. See the report, linked above, for additional information on the vulnerabilities found.

  1. **Cross Site Scripting (XSS)** *– Reflected & Stored*

     On Rekall Corporation's *Home page*, I submitted the following script within the input field designated as "Begin by entering your name below!". 

      + <script>alert(Document.cookies)</script>

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

     *Figure 04 - Shows the script successfully reflected and stored, by revealing Flag 3.*
     ![image](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/b6ff98fd-8122-4302-8676-e5c5f35d11dc)

     The ability to inject these scripts poses a significant security risk, as it could potentially enable an attacker to redirect users to fraudulent web pages, install keyloggers, or capture user cookies.                     This, in turn, would allow malicious actors to pilfer customer data and exploit it for unauthorized access to your system, potentially leading to further damaging attacks.

  2. **Insecure Direct Object Reference (IDOR).**

     In an IDOR vulnerability, an attacker can access or manipulate objects (such as files, directories, database records, or URLs) directly by changing parameters in the URL, without proper authentication or   authorization.

     On the web application, I found an associated Docker container by executing the "*docker ps*" command within a Kali Linux environment.

     *Figure 05 - Docker Container ID found.*
     ![image](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/502f5da8-7f67-4b0b-8c5a-f03102e23995)

     I subsequently exploited this docker container using the following command:

     + docker exec -it bd68ca4426b1 /bin/bash

     *Figure 06 - Docker exploit successfully deployed.*
     ![image](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/c2051ef6-c7fa-4ae4-8958-1e1be0cf1d04)

     Upon gaining access to the docker container, I discovered the file "*Login.php.old2*" within the directory: "*/var/www/html*".

     *Figure 07 - “Login.php.old2” file found within the html directory.*
     ![image](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/9bd1ca19-7d14-4b5e-b704-68b85fe296ad)

     From here I adjusted the web URL to "*192.168.14.35/Login.php.old2*". This gave me access to the targeted web page, without the use of valid credentials.

     *Figure 08 - Successfully accessed the targeted web page, revealing Flag 7.*
     ![image](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/44bf70d8-b8b6-4380-b6fa-3d51b23996c2)

## Linux Host Vulnerabilities

I found six vulnerabilities on the Linux host systems. Included here are two of those vulnerablilities deemed critical. See the report, linked above, for additional information on the vulnerabilities found.

  1. **Apache Tomcat Remote Code Execution (CVE-2017-12617)**

     I utilized MSFconsole to identify vulnerabilities linked to Tomcat and JSP components. The following command was used to generate possible exploits:

     + search RCE JSP

     *Figure 09 - MSFconsole results.*                                                                
     ![image](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/4ba25654-89e7-4033-bee6-f3b133a117be)

     I then used the following exploit to bypass restrictions on JSP (JavaServer Pages) file uploads in Tomcat:

     + multi/http/tomcat_jsp_upload_bypass
    
     *Figure 10 - Exploit is successfully running.*                                    
     ![image](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/710869ad-8973-4528-b5de-fa5452fa2c7a)

     From here I gained access to the command line and utilized the following *find* command to search for a hidden flag:

     + find / -type f -iname “*flag *.txt”

     *Figure 11 - Command line search revealing Flag 7 within the "root" directory.*                                  
     ![image](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/3f287c97-4850-4f0b-bc56-0fd772887c8a)

     This poses a grave risk as it grants unauthorized access to the target system through the exploitation of a known Apache Tomcat vulnerability (CVE-2017-12617). An attacker could potentially execute malicious code remotely, compromising the integrity, confidentiality, and availability of the affected system. This could result in unauthorized data access, data manipulation, and even full system compromise, leading to severe consequences for the organization.

  2. **Apache Struts (CVE-2017-5638) Remote Code Execution (RCE)**

     I conducted a network vulnerability assessments by using Nmap and Nessus scans. These scans revealed a critical Apache Struts RCE vulnerability.

     *Figure 12 - Nessus scan results targeting the Linux Host IP address.*
     ![image](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/d7857e88-bcaf-4114-9c0d-09ffedd9384a)

     *Figure 13 - CVE Reference Information.*                                                                          
     ![image](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/0f7d4831-a815-4d5e-89bc-218430b9087c)

     I then leveraged the following RCE script within Metasploit to exploit a vulnerability in Apache Struts 2 related to content type validation and the OGNL (Object-Graph Navigation Language) expression language:

     + multi/http/struts2_content_type_ognl

     *Figure 14 - Exploit successfully ran, granting unauthorized access, and revealing the location of Flag 10.*                          
     ![image](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/c85a0f6a-84f6-4699-96a5-73e8f97ac4c0)

     From here I copied the compressed 7z file from the host to my Kali Linux machine, to be able to view its contents.

     *Figure 15 - 7z file contents, revealed Flag 10.*                                              
     ![image](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/64093800-960f-44bd-a309-cad0a5d95597)

     RCE exploits of this nature have the potential to grant malicious actors the capability to execute unauthorized programs, access confidential source code, and exfiltrate sensitive data.

## Windows Host Vulnerabilities

I found six vulnerabilities on the Windows Host(s). Included here are two of those vulnerablilities deemed critical/high. See the report, linked above, for additional information on the vulnerabilities found.

  1. **SLMail Service (POP3)**

     I conducted a network assessment using Nmap scanning; which revealed the presence of an SLMail service running on SMTP port 25, and port 110 for POP3 on the target system. I used the following command to generate these results:

     + nmap -A 172.22.117.0/24

     *Figure 16 - Nmap scan results.*                                                                
     ![image](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/e91377ba-99da-4990-8d57-798323a70cd0)

     From here I employed the following *searchsploit* command, within Metasploit, to identify an exploit module compatible with the SLMail service found in the nmap scan:

     + searchsploit slmail

     *Figure 17 - SLMail results from Searchsploit.*                                              
     ![image](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/17b076b2-b000-4119-9fed-c6ec617d1289)

     With the vulnerability found I then utilized Metasploit to execute the following exploit which provided unauthorized access, through port 110, on the Windows 10 machine:

     + windows/pop3/seattlelab_pass

     *Figure 18 - Successfully ran exploit on the target “172.22.117.20”, port 110.*                                              
     ![image](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/a7a830a3-0bdc-4c37-8179-8416cb536e87)

     This gave me unauthorized access to the target system, and allowed me to view any data stored in the system. In this case I was able to locate Flag 4, using the "*ls*" command.

     *Figure 19 - Flag 4 found by listing the directory files.*                      
     ![image](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/736ff41b-f619-448f-b371-f87330eb1091)

     As shown with the proceeding vunlnerability; this can be taken futher, depending on the intent of the actor, and runs the potential risk of unauthorized access, data theft, malware deployment, system manipulation, privilege escalation, and propagation.

2. **Exposed User/System Hashes (Kiwi)**

     I was granted system-level privileges, following the successful compromise of the SLMail service. I then leveraged the Metasploit tool "*Kiwi*" to further exploit the system.

     *Figure 20 - Successfully launched "Kiwi" on the target system.*                                                                  
     ![image](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/ad39f12f-d2de-441b-a5b0-fe5f6e17bada)

     I dumped the hashed passwords stored, in the compromised system, using the following command:

     + run post/windows/gather/hashdump

     Among the hashes dumped, I found, one corresponded to Flag 6. I copied this into a new text file, on a separate system, for later use.

     *Figure 21 - System dump of hashed passwords, revealing the location of Flag 6.*                                                    
     ![image](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/d9628c37-9a08-4676-be93-23541ec84d54)

     From here I utilized the tool, *John the Ripper*, to crack the password associated with Flag 6. The following command was used:

     + john hash.txt --format=NT

     *Figure 22 - Successfully cracked stolen hash for Flag 6, showing the password was "Computer!".*                                        
     ![image](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/a176bb57-51de-4ef1-961b-d12ea7703227)

     From the same Meterpreter (Kiwi) session, I dumped the cached credentials using the following command:

     + kiwi_cmd lsadump::cache
     
     *Figure 23 - Successfully dumped cached credentials.*                                                          
     ![image](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/4b15732e-31f6-483e-98fb-662637d3ce8e)

     This provided me with an administrative level user "ADMBob", and their respective hashed NTML. I used the following command with *John the Ripper* to crack the hashed NTML:

     + john hash.txt --format=mscash2

     *Figure 24 - Cracked hash reveals password for "ADMBob" is "Changeme!".*                              
     ![image](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/6552525e-9182-4348-a36b-f78639396984)

     With these acquired credentials I accessed the Windows 2019 Server, by employing the following *psexec* exploit:

     + windows/smb/psexec

     *Figure 25 - psexec exploit successfully deployed.*                                                          
     ![image](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/360266a3-51e2-41d3-839a-4272afdd698d)
     ![image](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/ec69c572-6423-488f-9972-8a75410ff2a5)

     After gaining access to the Windows Server; I ran the following command to display the listed users:

     + \>net users

     *Figure 26 - Flag 8 found on the Windows 2019 Server.*                                                          
     ![image](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/e55938d2-3196-49ed-a678-38b5bf7416de)

     With no other exploits discovered on the Windows server, I returned to the Meterpreter session and proceeded to use the following exploit:

     + dcsync_ntlm administrator

     My goal was to leverage the "Directory Replication Service Remote Protocol" and request password data for user accounts from the domain controller. I impersonated the domain controller and retrieved password hashes of user accounts, with specifically the *administrator account* targeted.

     *Figure 27 - DCsync exploit successfully deployed, providing the NTLM hash for the administrator account.*                        
     ![image](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/92e66fbb-e723-4441-a2cc-37ce644c4a5b)

     These credentials could be cracked and further used to compromise the network.

## Mitigations

The complete report, accessible through the provided link above, includes a diverse set of suggested mitigation strategies corresponding to each identified vulnerability and its respective impacted host. I have presented a broad spectrum of mitigation measures to empower Rekall Corporation in formulating a customized approach to address all identified vulnerabilities effectively.
