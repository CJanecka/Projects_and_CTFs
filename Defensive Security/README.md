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
  + [08. Visualizations and Dashboards](#Visualizations-and-Dashboards)
  + [09. Future Mitigations](#Future-Mitigations)

## Overview

I played the role of a Security Operations Center *(SOC)* analyst for a company, called Virtual Space Industries *(VSI)*. Tasked with monitoring an Apache web server, that hosts the administrative webpage; and a Windows operating system, which runs many of VSI’s back-end operations. Working in a small group, we employed Splunk to craft a monitoring environment, creating tailored reports, alerts, dashboards, and an add-on application to fortify the security of this fictitional organization. A pivotal element of this project entailed simulating an attack to gauge the efficiency of our monitoring solutions. Following the simulated attack, we conducted an analysis of the system's performance in detecting the threat(s). The culmination of this effort was later presented to our cybersecurity bootcamp class, to offer insights for enhancing cybersecurity within a broader organizational context. <add docs here>

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
  + Analyzing the log files, of normal activity, to establish baselines and thresholds, enabling the detection of anomalies and potential security threats.
  + Designing and implementing reports, alerts, and dashboards; within Splunk, each tailored to specific criteria. Providing real-time visibility into the health and security of system(s).
  + Loading Apache and Windows logs, containing a simulated attack, into the Splunk environment.
  + Assessing the effectiveness, and response, of the security measures implemented on both servers.
  + Showcasing our monitoring environment, attack analysis, and future mitigation recommendations to the class.

## Windows Reports

In order to gain a better understanding of the organization's normal operations, we uploaded and analyzed the provided security logs for the Windows server. To refine our search, the following Splunk fields were examined:

  + signature_id
  + signature
  + user
  + status
  + severity

Using these fields, we crafted a report which showcased the ID number associated with each specific signature for Windows activity.

*Figure 01 - Search ran to generate the Signatures and ID's report.*                                                                                            
![windows server signature and ID search](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/a55dabe9-364a-4f02-a0e6-3eb16a3ef08e)

*Figure 02 - Signatures, and their respective ID's, for activity on the Windows server.*                                                                              
![windows server signature and ID report](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/599971ce-1703-4657-9c69-eac27d79a5ff)

*Figure 03 - Supplemental report showing the count for each signature.*
![win server - total signature counts](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/0ef7d5e6-e3a3-41f3-9943-0eb818142dc1)

An additional report was made that displays the severity levels, along with the count and percentage of each.

*Figure 04 - Search ran to generate the Severity level reoprt.*                                                                                          
![windows server severity level search](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/3dd32c5a-05dd-4a38-a445-a3d93780160f)

*Figure 05 - Severity Levels, their count, and percentages, on the Windows server.*                                                                  
![windows server severity with percentage](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/7ad34196-fe3b-4327-9241-5ebab017810e)

Then we generated a report which provides a comparison of the successful and failed Windows events.

*Figure 06 - Comparison between the success and failure of Windows activities.*                                                                                
![windows server succ-fail report](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/39c9f315-cdaa-4005-8cc3-388be5a824e7)

The ratio between success (9712) and failure (296) counts idicates a predominantly successful operational environment. This shows that the majority of Windows activities are completing successfully. The 296 failures represent a relatively small proportion, and may indicate potential issues, especially if the failure counts deviate significantly from historical norms. In the case of this project, this data was treated as normal since it was from the, provided, Windows log of normal activty.

## Windows Alerts

My group was also tasked with designing alerts that notify VSI of suspicious activity on the Windows server. The specific alerts requested:

  + Suspicious hourly level of failed Windows activity.
  + Suspicious hourly count of the signature *“an account was successfully logged on”*.
  + Suspicious hourly count of the signature *“a user account was deleted"*.

Whenever activity surpasses the defined threshold, these alerts will promptly trigger an email to SOC@VSI-company.com.

We began by establishing a baseline and threshold for the hourly rate of Failed Windows activity.

*Figure 07 - Search ran to view Failed Windows activity.*                                                                          
![win server failed activity search](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/02557ffe-fdbc-434f-a7fd-46f7b16f978a)

*Figure 08 - Hourly Failed Windows activity during normal operations.*                                                                            
![win server Failed Activities](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/0299b35f-55e0-4b2e-8e1a-8a8f97f444c0)

The failures shown, in Figure 8, reveal that VSI could typically expect to see 10-20 failed activities during any given hour on the Windows server. By hovering over the bar chart, we were able to pull additional information from each hour and determine:

  + Our basline is fifteen (15) failed events occurring, normally, on the Windows sever.
  + Our alert threshold is twenty (20) failed events, to notify VSI when suspicious activity is occuring.

*Figure 09 - Alert enabled for suspicious level of failed activity.*                                                              
![win Alert - Failed Activity](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/8be36de5-86d8-486e-b251-b7bb86004b3c)

With this alert deployed, my group's next step was to establish a baseline and threshold for the hourly signature count of, *"an account was successfully logged on"*.

*Figure 10 - Search ran to display an hourly count by signature.*                                                                                            
![win server hourly count by signature search](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/1bd7006a-e45e-4b15-bc54-5e73a33f60c8)

*Figure 11 - Hourly count for "an account was successfully logged on" highlighted.*
![win server hourly count by signature](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/4d9263ff-19c2-4676-a4f1-a7032ab05781)

The data highlighted in Figure 11, shows that VSI sees the signature, "an account was successfully logged on", an average of thirty-one (31) times per hour. With this, we determined:

  + Our basline is thirty-one (31) successful account logins ocurring, normally, on the Windows server.
  + Our alert threshold is fourty-five (45) successful logins, to notify VSI when suspicious activity is occuring.
  + It is best to design this alert with the corresponding signature ID, since signature names sometimes change. 
    - The ID needed for this alert is: **4624** *(see Figure 2)*

*Figure 12 - Alert enabled for suspicious signature count "an account was successfully logged on".*                                                            
![win alert - login success](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/ddf15d29-c5dc-4712-828e-845c4f4ac64c)

To craft the final Windows alert, requested by VSI, we proceeded to determine the baseline and threshold for the hourly signature count of, *"a user account was deleted"*.

*Figure 13 - Search ran to display the hourly count of user accounts being deleted.*                                                                    
![win server - deleted user acc search](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/db247094-ee54-4d09-a6d9-8c3c89346cd0)

*Figure 14 - Hourly user accounts being deleted, normally, on the Windows server.*                                                                                                                                          
![win server - user acc deleted](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/4306170d-098f-4543-bcca-3d3e3fec0180)

In Figure 14, the data reveals that VSI generally experiences the deletion of 20-30 user accounts in any given hour on the Windows server. However, my team observed a variance in event counts and hourly totals. Upon deeper investigation, we identified that this discrepancy was attributed to the multiple uploads of the Windows server log on my system. From this, we determined:

  + My Splunk report was the only one, in the group, with the log data uploaded multiple times.
  + We opted to use the team's data to design this alert.
  + Our baseline is ten (10) user accounts being deleted, normally, on the Windows server.
  + Our alert threshold is seventeen (17) user accounts being deleted, to notify VSI when suspicious activity is occuring.
  + The corresponding Signature ID is: **4726** *(see Figure 2)*

*Figure 15 - Alert enabled for suspicious signature count "a user account was deleted".*                                                        
![win Alert - User Deleted](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/dbf4c620-21fd-4a20-8e16-32d48cfefab4)

## Apache Reports

During this stage, my team uploaded and analyzed the Apache web server logs, representing regular activity for VSI. 

*Figure 16 - Splunk review page to verify upload settings.*                                                                                    
![splunk review](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/c19c46c7-009b-487a-a5d6-7aed4504cd3a)

In order to refine our search, we examined the following Splunk fields:

  + method
  + referer_domain
  + status
  + clientip
  + useragent

To assist in monitoring the Apache web server, we created the following reports:

*Figure 17 - Report displaying a table of HTTP methods being utilized.*                                                                            
![apache server - http methods table](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/84ef7489-9a08-4bd0-b380-9a98e0e5d674)

  + This gave us insight into the types of HTTP activity requested against the web server.

*Figure 18 - Report highlighting the top 10 domains referring to VSI's website.*                                                                    
![apache  server - top 10 domains](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/6f5fe8db-daac-4f5f-8a4f-cb76f74707a1)

  + This helped us to identify suspicious referrers.
  
*Figure 19 - Report showing the count of each HTTP response code.*
![apache server -  top http responses](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/8a575834-96a1-47bf-a85c-0a58019c1ade)

  + This provided insights into potential suspicious levels of HTTP responses.

## Apache Alerts

My group was tasked with designing alerts that notify VSI of suspicious activity on the Apache server. The specific alerts requested:

  + Suspicious hourly activity from any country, aside from the United States.
  + Suspicious hourly count of the HTTP **Post** method.

Whenever activity surpasses the defined threshold, these alerts will promptly trigger an email to SOC@VSI-company.com.

*Figure 20 - Search ran to filter events and exlcude the United States.*                                                  
![apache server non US activity search](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/0cca8551-bf25-4d18-8e04-6d34892053f1)

*Figure 21 - Timeline of Non-US Activity on the web server.*                                                
![apache server non US activity](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/40570795-460d-4ff9-aca5-346cb5d51008)

The activity levels from outside the United States displayed a varied range of counts, typically fluctuating between 100 and 170 connections, with occasional counts dropping below 100. From this, we determined:

  + Our baseline is eighty (80) connections, occuring from any region outside of the United States, to the web server.
  + Our threshold is 170 connections, to the administrative webpage, to notify VSI when suspicious activity is occuring.

*Figure 22 - Alert enabled for suspicious activity, from outside of the United States.*                                                                                  
![apache alert non US activity](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/a404b858-7e72-4d17-bd9b-f002a5b76a40)

With this alert deployed, my group's next step was to establish a baseline and threshold for the hourly count of the HTTP **POST** method.

*Figure 23 - Hourly count for the HTTP POST method on the administrative webpage.*                                                                      
![apache server - hourly http post method count](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/a763194c-fe56-45aa-9ac1-fa55c1a8e2f5)
