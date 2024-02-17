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
  + [08. Monitoring and Analyzing Attacks](#Monitoring-and-Analyzing-Attacks)
  + [09. Visualizations and Dashboards](#Visualizations-and-Dashboards)
  + [10. Future Mitigations](#Future-Mitigations)

## Overview

I played the role of a Security Operations Center *(SOC)* analyst for a company, called Virtual Space Industries *(VSI)*. Tasked with monitoring an Apache web server, that hosts the administrative webpage; and a Windows operating system, which runs many of VSI’s back-end operations. Working in a small group, we employed Splunk to craft a monitoring environment, creating tailored reports, alerts, dashboards, and an add-on application to fortify the security of this fictitional organization. A key element of this project entailed analyzing a simulated attack to gauge the efficiency of our monitoring solutions. The culmination of this effort was later presented to our cybersecurity bootcamp class, to offer insights for enhancing cybersecurity within a broader organizational context. <add docs here>

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

In order to gain a better understanding of the organization's normal operations, we uploaded and analyzed the provided security logs for the Windows OS. To refine our search, the following Splunk fields were examined:

  + signature_id
  + signature
  + user
  + status
  + severity

### Signature ID's

Using the fields listed above, we crafted a report which showcased the ID number associated with each specific signature for Windows activity.

*Figure 01 - Search ran to generate the Signatures and ID's report.*                                                                                            
![windows server signature and ID search](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/a55dabe9-364a-4f02-a0e6-3eb16a3ef08e)

*Figure 02 - Signatures, and their respective ID's, for activity on the Windows OS.*                                                                              
![windows server signature and ID report](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/599971ce-1703-4657-9c69-eac27d79a5ff)

  + This allowed us to easily associate each signature with its corresponding ID.

*Figure 03 - Supplemental report showing the count for each signature.*
![win server - total signature counts](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/0ef7d5e6-e3a3-41f3-9943-0eb818142dc1)

  + This reveals how many times each signature occured.

### Severity Levels

An additional report was made that displays the severity levels, along with the count and percentage of each.

*Figure 04 - Search ran to generate the Severity level reoprt.*                                                                                          
![windows server severity level search](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/3dd32c5a-05dd-4a38-a445-a3d93780160f)

*Figure 05 - Severity Levels, their count, and percentages, on the Windows server.*                                                                  
![windows server severity with percentage](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/7ad34196-fe3b-4327-9241-5ebab017810e)

  + This provides insight into the distribution of severity levels, allowing us to assess the overall impact and significance of events recorded.

### Successful vs Failed Activity

Then we generated a report which provides a comparison of the successful and failed Windows events.

*Figure 06 - Comparison between the Success and Failure of Windows activities.*                                                                                
![windows server succ-fail report](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/39c9f315-cdaa-4005-8cc3-388be5a824e7)

  + This shows us if there was a suspicious level of failed activities on the system.

The ratio between success (9712) and failure (296) counts idicates a predominantly successful operational environment. This shows that the majority of Windows activities are completing successfully. The 296 failures represent a relatively small proportion, and may indicate potential issues, especially if the failure counts deviate significantly from historical norms. In the case of this project, this data was treated as *normal* since it was from the, provided, Windows log of normal activty.

## Windows Alerts

My group was tasked with designing alerts that notify VSI of suspicious activity on the Windows server. The specific alerts requested:

  + Suspicious hourly level of failed Windows activity.
  + Suspicious hourly count of the signature *“an account was successfully logged on”*.
  + Suspicious hourly count of the signature *“a user account was deleted"*.

Whenever activity surpasses the defined threshold, these alerts will promptly trigger an email to SOC@VSI-company.com.

### Hourly level of failed Windows activity

We began by establishing a baseline and threshold for the hourly level.

*Figure 07 - Search ran to view Failed Windows activity.*                                                                          
![win server failed activity search](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/02557ffe-fdbc-434f-a7fd-46f7b16f978a)

*Figure 08 - Hourly Failed Windows activity during normal operations.*                                                                            
![win server Failed Activities](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/0299b35f-55e0-4b2e-8e1a-8a8f97f444c0)

The failures shown, in Figure 8, reveal that VSI could typically expect to see 10-20 failed activities during any given hour on the Windows server. By hovering over the bar chart, we were able to pull additional information from each hour and determine:

  + Our basline is fifteen (15) failed events occurring, normally, on the Windows sever.
  + Our alert threshold is twenty (20) failed events, to notify VSI when suspicious activity is occuring.

*Figure 09 - Alert enabled for suspicious level of failed activity.*                                                              
![win Alert - Failed Activity](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/8be36de5-86d8-486e-b251-b7bb86004b3c)

### Hourly count of Successful Logins

We began by establishing a baseline and threshold for the hourly count of successful logins.

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

### Hourly count of Deleted Users

We began by establishing a baseline and threshold for the hourly count of deleted user accounts.

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

### HTTP Method Activity

*Figure 17 - Report displaying a table of HTTP methods being utilized.*                                                                            
![apache server - http methods table](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/84ef7489-9a08-4bd0-b380-9a98e0e5d674)

  + This gave us insight into the types of HTTP activity requested against the web server.

These are the general functions of the HTTP methods we found:

  + **GET**: Used to request data from a specified resource.
  + **POST**: Used to submit data to be processed to a specified resource.
  + **HEAD**: Similar to *GET* but retrieves only the headers of the response, not the actual content.
  + **OPTIONS**: Allows the client to determine the options and/or requirements associated with a resource, or the capabilities of a server, without initiating a resource retrieval.

## Top Referring Domains

Referrers are external domains or websites that direct traffic to another website. These referrers are other websites or domains that have links pointing to VSI's website, contributing to the incoming traffic.

*Figure 18 - Report highlighting the top 10 domains referring to VSI's website.*                                                                    
![apache  server - top 10 domains](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/6f5fe8db-daac-4f5f-8a4f-cb76f74707a1)

  + This helped us to identify suspicious referrers.

### HTTP Response Codes

HTTP response codes are standardized three-digit numerical codes that are sent by a web server to a client's browser as part of the HTTP (Hypertext Transfer Protocol) response. These codes provide information about the status of a requested HTTP transaction and help both servers and clients understand how to handle the communication

*Figure 19 - Report showing the count of each HTTP response code.*
![apache server -  top http responses](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/8a575834-96a1-47bf-a85c-0a58019c1ade)

  + This provided insights into potential suspicious levels of HTTP responses.

Here is what each of the shown response codes mean:

  + **200** *- OK:*
    - This indicates that the request was successful. The server processed the request and provided the requested resource.
      
  + **304** *- Not Modified:*
    - This is used in conditional requests. It indicates that the requested resource has not been modified since the last specified time, and there is no need to send the full content again.
      
  + **404** *- Not Found:*
    - This is given when the server cannot find the requested resource. It indicates that the URL or file path specified in the request does not exist on the server.
      
  + **301** *- Moved Permanently:*
    - This indicates that the requested resource has been permanently moved to a new location. The client is usually redirected to the new location specified in the "Location" header.
      
  + **206** *- Partial Content:*
    - This indicates that the server is delivering only a portion of the requested resource, often in response to a "Range" header in the request.
      
  + **500** *- Internal Server Error:*
    - This indicates a generic server error. The server encountered an unexpected condition that prevented it from fulfilling the request. It's a catch-all response for server-side errors.
      
  + **416** *- Range Not Satisfiable:*
    - This is returned when the server cannot satisfy the requested range conditions indicated by the "Range" header in the request.
      
  + **403** *- Forbidden:*
    - This indicates that the server understood the request, but it refuses to authorize it. The client does not have the necessary permissions to access the requested resource.
      
## Apache Alerts

My group was tasked with designing alerts that notify VSI of suspicious activity on the Apache server. The specific alerts requested:

  + Suspicious hourly activity from any country, aside from the United States.
  + Suspicious hourly count of the HTTP **Post** method.

Whenever activity surpasses the defined threshold, on the administrative webpage, these alerts will promptly trigger an email to SOC@VSI-company.com.

### Hourly Non-US Activity

*Figure 20 - Search ran to filter events and exlcude the United States.*                                                  
![apache server non US activity search](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/0cca8551-bf25-4d18-8e04-6d34892053f1)

*Figure 21 - Timeline of Non-US Activity on the web server.*                                                
![apache server non US activity](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/40570795-460d-4ff9-aca5-346cb5d51008)

The activity levels from outside the United States displayed a varied range of counts, typically fluctuating between 100 and 170 connections, with occasional counts dropping below 100. From this, we determined:

  + Our baseline is eighty (80) connections, occuring from any region outside of the United States, to the web server.
  + Our alert threshold is 170 connections, to notify VSI when suspicious activity is occuring.

*Figure 22 - Alert enabled for suspicious activity, from outside of the United States.*                                                                                  
![apache alert non US activity](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/a404b858-7e72-4d17-bd9b-f002a5b76a40)

### Hourly POST Method Count

*Figure 23 - Hourly count for the HTTP POST method on the administrative webpage.*                                                                      
![apache server - hourly http post method count](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/a763194c-fe56-45aa-9ac1-fa55c1a8e2f5)

The data depicted in Figure 23 reveals that the webpage typically registers 2-6 instances of the **POST** method, occasionally exhibiting spikes with counts exceeding 6. With this information, we dertermined:

  + Our baseline is two (2) instances of the **POST** method being registered on the administrative webpage.
  + Our alert threshold is seven (7) **POST** method occurances, to notify VSI when suspicious activity is occuring.

*Figure 24 - Enabled alert for suspicious hourly POST method count.*                                                                      
![apache alert http post](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/c665dbde-0020-4003-8967-aca60ca47de1)

## Monitoring and Analyzing Attacks

We had been notified that VSI recently experienced several cyberattacks; unfortunately, this attack took down several of VSI’s systems. This targeted several systems, specifically, the Windows and Apache servers, which we were fortunately monitoring. Management provided us with additional logs from those same servers. These new logs cover the time period during which the attack occurred.

Our goal was to analyze these *attack logs* with our monitoring solution; assessing its effectiveness in identifying, mitigating, and responding to the cyberattack on the Windows OS and Apache server that were being monitored. We uploaded the server *attack logs*, to Splunk, to review the updated results .

### Report Analysis for Severity

*Figure 25 - Windows Attack Log Severity Report.*
![win att log - severity report](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/2d259c1a-c184-4f53-b6c4-7222674be414)

By comparing the data, from Figures 5 and 25, we addressed the following inquiry raised by VSI:

  + Did we detect any suspicious changes in severity?
    - Yes; these findings indicate the presence of suspicious changes in severity within the Windows OS.
      + **Informational**: There has been a decrease of 13% in informational severity, declining from 93% to 80%.
      + **High**: Conversely, high severity cases have seen an increase of 13%, rising from 7% to 20%.

### Report Analysis for Failed Activities

By comparing the data found on the Windows attack log, to Figure 6, we addressed the following inquiry raised by VSI:

  + Did we detect any suspicious changes in failed activities?
    - There were no significant shifts or suspicious changes in failed activities during the analyzed period.
      + **Success Rate**: The success rate exhibited a marginal increase, transitioning from 97% to 98%, reflecting a modest 1% improvement.
      + **Failure Rate**: Conversely, the failure rate saw a slight decrease, moving from 3% to 2%, indicating a 1% reduction.

### Alert Analysis for Failed Windows Activity

*Figure 26 - Timeline of Failed Activities in the Attack Log.*                                                
![win att log - failed activity](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/49143bc3-4d9a-4e99-a9c9-c86406ceb6a0)

Using this, we addressed the following inquiry raised by VSI:

  + Did we detect a suspicious volume of failed Windows activity?
    - Yes, there was a suspicious volume of failed activity detected.
    
  + If so, what was the count of events in the hour(s) it occurred?
    - During a single hour, there were seventy (70) events logged.
    
  + When did it occur?
    - This occurred from 8:00 AM to 9:00 AM, Wednesday, March 25th, 2020.
    
  + Would our alert be triggered for this activity?
    - Yes; the alert would be triggered as the threshold, we set, is at twenty (20) failed events.
    
  + After reviewing, would we change our threshold from what was previously selected?
    - No; changing the threshold is unnecessary in this instance, as our alert should trigger without issue.

### Alert Analysis for Successful Logins

