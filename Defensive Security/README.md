# Defensive Security

![portfolio8](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/0e681c7c-ca7b-4725-a35a-e84601eb8858)

## Table of Contents

  + [01. Overview](#Overview)
  + [02. Equipment and Tools](#Equipment-and-Tools)
  + [03. Project Requirements](#Project-Requirements)
  + [04. Windows Reports](#Windows-Reports)
  + [05. Windows Alerts](#Windows-Alerts)
  + [06. Apache Reports](#Apache-Reports)
  + [07. Apache Alerts](#Apache-Alerts)
  + [08. Post-Attack Modifications](#Post-Attack-Modifications)
  + [09. Future Mitigations](#Future-Mitigations)

## Overview

In this project I played the role of a Security Operations Center *(SOC)* analyst for a small company, called Virtual Space Industries *(VSI)*. Tasked with monitoring an Apache web server, that hosts the administrative webpage; and a Windows operating system, which runs many of VSI’s back-end operations. Working in a small group, we employed Splunk to craft a monitoring environment, developing tailored reports, alerts, dashboards, and an add-on app to fortify the security of this fictitional organization. A pivotal element of this project entailed simulating an attack to gauge the efficacy of our monitoring solutions. Following the simulated attack, we conducted an analysis of the system's performance in detecting and mitigating the threat(s). The culmination of this effort was later presented to our cybersecurity bootcamp class, to offer insights for enhancing cybersecurity within a broader organizational context. <add docs here>

## Equipment and Tools

The technologies used in this project include:

  + Splunk
    - Reporting
    - Alerting
    - Dashboards
  + Windows Server Logs
  + Apache Server Logs
  + Ubuntu OS
  + Apache Guacamole

## Project Requirements

The project requirements included:

  + Loading Windows and Apache logs into a Splunk environment to centralize and streamline log management.
  + Analyzing the log files to establish baselines and thresholds, enabling the detection of anomalies and potential security threats.
  + Designing and implementing reports, alerts, and dashboards; within Splunk, each tailored to specific criteria. Providing real-time visibility into the health and security of system(s).
  + Loading Apache and Windows logs, containing a simulated attack, into the Splunk environment.
  + Assessing the effectiveness, and response, of the security measures implemented on both servers.
  + Showcasing our monitoring environment, attack analysis, and future mitigation recommendations to the class.

## Windows Reports

In order to gain a better understanding of the organization's normal operations, we uploaded and analyzed the provided security logs for the Windows server. To refine our search, the following Splunk fields were specifically examined:

  + signature_id
  + signature
  + user
  + status
  + severity

Using these fields, we crafted a report which showed the ID number associated with each specific signature for Windows activity.

*Figure 01 - Search ran to generate the Signatures and ID's report.*                                                                                            
![windows server signature and ID search](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/a55dabe9-364a-4f02-a0e6-3eb16a3ef08e)

*Figure 02 - Signatures, and their respective ID's, for activity on the Windows server.*                                                                              
![windows server signature and ID report](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/599971ce-1703-4657-9c69-eac27d79a5ff)

From here, an additional report was generated that displays the severity levels, along with the count and percentage of each.

*Figure 03 - Search ran to generate the Severity level reoprt.*                                                                                          
![windows server severity level search](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/3dd32c5a-05dd-4a38-a445-a3d93780160f)

*Figure 04 - Severity Levels, their count, and percentages, on the Windows server.*                                                                  
![windows server severity with percentage](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/7ad34196-fe3b-4327-9241-5ebab017810e)

Then we generated a report which provides a comparison between the success and failure of Windows activities.

*Figure 05 - Comparison between the success and failure of Windows activities.*                                                                                
![windows server succ-fail report](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/39c9f315-cdaa-4005-8cc3-388be5a824e7)

## Windows Alerts

My group was also tasked with designing alerts that notify VSI of suspicious activity. To accomplish this, we needed to establish a baseline and threshold for the hourly rate of failed Windows activity.

*Figure 06 - Search ran to view Failed Windows activity.*                                                                          
![win server failed activity search](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/02557ffe-fdbc-434f-a7fd-46f7b16f978a)

*Figure 07 - Hourly Failed Windows activity during normal operations.*                                                                            
![win server Failed Activities](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/0299b35f-55e0-4b2e-8e1a-8a8f97f444c0)

The failures shown, in figure 7, reveal that VSI could expect to see ten to twenty failed activities during any given hour on the Windows server. By hovering over the bar chart, we were able to pull additional information during each hour and determine:

  + Our basline is fifteen (15) failed events occurring, normally, on the Windows sever.
  + Our alert threshold will be twenty (20) failed events, to notify VSI when suspicious activity is occuring.
