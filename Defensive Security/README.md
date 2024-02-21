# Defensive Security

![portfolio8](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/0e681c7c-ca7b-4725-a35a-e84601eb8858)

## Table of Contents

+ [01. Overview](#Overview)
+ [02. Equipment and Tools](#Equipment-and-Tools)
+ [03. Project Requirements](#Project-Requirements)
+ [04. Windows Reports](#Windows-Reports)
  - [a. Signature IDs](#Signature-IDs)
  - [b. Severity Levels](#Severity-Levels)
  - [c. Successful vs Failed Activity](#Successful-vs-Failed-Activity)
  - [d. User Account Locked Out](#User-Account-Locked-Out)
  - [e. Password Reset Attempts](#Password-Reset-Attempts)
+ [05. Windows Alerts](#Windows-Alerts)
  - [a. Hourly Level of Failed Windows Activity](#Hourly-Level-of-Failed-Windows-Activity)
  - [b. Hourly Count of Successful User Logins](#Hourly-Count-of-Successful-User-Logins)
  - [c. Hourly Count of Deleted Users](#Hourly-Count-of-Deleted-Users)
+ [06. Windows Server Monitoring](#Windows-Server-Monitoring)
  - [a. Signature Counts Timeline](#Signature-Counts-Timeline)
  - [b. User Activity Timeline](#User-Activity-Timeline)
  - [c. User Counts](#User-Counts)
+ [07. Apache Reports](#Apache-Reports)
  - [a. HTTP Method Activity](#HTTP-Method-Activity)
  - [b. Top Referring Domains](#Top-Referring-Domains)
  - [c. HTTP Response Codes](#HTTP-Response-Codes)
+ [08. Apache Alerts](#Apache-Alerts)
  - [a. Hourly Non-US Activity](#Hourly-Non-US-Activity)
  - [b. Hourly POST Method Count](#Hourly-POST-Method-Count)
+ [09. Apache Web Server Monitoring](#Apache-Web-Server-Monitoring)
  - [a. Geographical Mapping of Client IPs](#Geographical-Mapping-of-Client-IPs)
  - [b. Uniform Resource Identifiers](#Uniform-Resource-Identifiers)
  - [c. Top 10 Active Countries](#Top-10-Active-Countries)
  - [d. User Agent Counts](#User-Agent-Counts)
+ [10. Add-On Splunk Application](#Add-On-Splunk-Application)
+ [11. Monitoring and Analyzing Windows Attacks](#Monitoring-and-Analyzing-Windows-Attacks)
  - [a. Report Analysis for Severity](#Report-Analysis-for-Severity)
  - [b. Report Analysis for Failed Activities](#Report-Analysis-for-Failed-Activities)
  - [c. Alert Analysis for Failed Windows Activity](#Alert-Analysis-for-Failed-Windows-Activity)
  - [d. Alert Analysis for Successful Logins](#Alert-Analysis-for-Successful-Logins)
  - [e. Alert Analysis for Deleted Accounts](#Alert-Analysis-for-Deleted-Accounts)
+ [12. Windows Dashboard Analysis](#Windows-Dashboard-Analysis)
  - [a. Analysis for Time Chart of Signatures](#Analysis-for-Time-Chart-of-Signatures)
  - [b. Analysis for Users](#Analysis-for-Users)
  - [c. Analysis of Statistical Charts](#Analysis-of-Statistical-Charts)
+ [13. Monitoring and Analyzing Apache Attacks](#Monitoring-and-Analyzing-Apache-Attacks)
  - [a. Report Analysis for HTTP Methods](#Report-Analysis-for-HTTP-Methods)
  - [b. Report Analysis for Referrer Domains](#Report-Analysis-for-Referrer-Domains)
  - [c. Report Analysis for HTTP Response Codes](#Report-Analysis-for-HTTP-Response-Codes)
  - [d. Alert Analysis for International Activity](#Alert-Analysis-for-International-Activity)
  - [e. Alert Analysis for HTTP POST Activity](#Alert-Analysis-for-HTTP-POST-Activity)
+ [14. Apache Dashboard Analysis](#Apache-Dashboard-Analysis)

## Overview

I played the role of a Security Operations Center *(SOC)* analyst for a company, called Virtual Space Industries *(VSI)*. Tasked with monitoring an Apache web server, that hosts the administrative webpage; and a Windows operating system, which runs many of VSI’s back-end operations. Working in a small group, we employed Splunk to craft a monitoring environment, creating tailored reports, alerts, dashboards, and an add-on application to fortify the security of this fictitional organization. A key element of this project entailed analyzing a simulated attack to gauge the efficiency of our monitoring solutions. The culmination of this effort was later presented to our cybersecurity bootcamp class, to offer insights for enhancing cybersecurity within a broader organizational context. <add docs here>

## Equipment and Tools

The technologies used in this project include:

  + Splunk
    - Reporting
    - Alerting
    - Dashboards
    - Add-on Application: [Website Monitoring](https://splunkbase.splunk.com/app/1493)
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

### Signature IDs

Using the fields listed above, we crafted a report which showcased the ID number associated with each specific signature for Windows activity.

*Figure 01 - Search ran to generate the Signatures and ID's report.*                                                                                            
![windows server signature and ID search](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/a55dabe9-364a-4f02-a0e6-3eb16a3ef08e)

*Figure 02 - Signatures, and their respective ID's, for activity on the Windows OS.*                                                                              
![windows server signature and ID report](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/599971ce-1703-4657-9c69-eac27d79a5ff)

  + This allowed us to easily associate each signature with its corresponding ID.

*Figure 03 - Report showing the Count for each Signature.*
![win server - total signature counts](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/0ef7d5e6-e3a3-41f3-9943-0eb818142dc1)

  + This reveals how many times each signature occured.

### Severity Levels

A report that displays the severity levels, along with the count and percentage of each.

*Figure 04 - Search ran to generate the Severity Level Reoprt.*                                                                                          
![windows server severity level search](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/3dd32c5a-05dd-4a38-a445-a3d93780160f)

*Figure 05 - Severity Levels, their Count, and Percentages, on the Windows server.*                                                                  
![windows server severity with percentage](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/7ad34196-fe3b-4327-9241-5ebab017810e)

  + This provides insight into the distribution of severity levels, allowing us to assess the overall impact and significance of events recorded.

### Successful vs Failed Activity

A report which provides a comparison of the successful and failed Windows events.

*Figure 06 - Comparison of normal Successful and Failed Windows activities.*                                                                                
![windows server succ-fail report](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/39c9f315-cdaa-4005-8cc3-388be5a824e7)

  + This shows us if there was a suspicious level of failed activities on the system.

The ratio between success (9712) and failure (296) counts idicates a predominantly successful operational environment. This shows that the majority of Windows activities are completing successfully. The 296 failures represent a relatively small proportion, and may indicate potential issues, especially if the failure counts deviate significantly from historical norms. In the case of this project, this data was treated as *normal* since it was from the, provided, Windows log of normal activty.

### User Account Locked Out

A report that displays when user accounts were locked out on the Windows server.

*Figure 07 - Timeline of normal User Account Lockout Activity.*
![win server - Locked Out Accounts](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/5e4407af-13d0-4ea1-af1b-8ac8ea4afbd9)

  + This helps us to establish a baseline of activity for user accounts being locked out.

### Password Reset Attempts

*Figure 08 - Timeline of normal Attempts to Reset an Account Password.*                                                                          
![win server -  Password Reset Attempt](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/dcc706fc-a587-4bc3-ac44-7e9c844804ea)

  + This helps us to establish a baseline of activity for password reset attempts.

## Windows Alerts

My group was tasked with designing alerts that notify VSI of suspicious activity on the Windows server. The specific alerts requested:

  + Suspicious hourly level of failed Windows activity.
  + Suspicious hourly count of the signature *“an account was successfully logged on”*.
  + Suspicious hourly count of the signature *“a user account was deleted"*.

Whenever activity surpasses the defined threshold, these alerts will promptly trigger an email to SOC@VSI-company.com.

### Hourly Level of Failed Windows Activity

We began by establishing a baseline and threshold for the hourly level.

*Figure 09 - Search ran to view Failed Windows activity.*                                                                          
![win server failed activity search](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/02557ffe-fdbc-434f-a7fd-46f7b16f978a)

*Figure 10 - Hourly Failed Windows activity during normal operations.*                                                                            
![win server Failed Activities](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/0299b35f-55e0-4b2e-8e1a-8a8f97f444c0)

The failures shown, in Figure 10, reveal that VSI could typically expect to see 10-20 failed activities during any given hour on the Windows server. By hovering over the bar chart, we were able to pull additional information from each hour and determine:

  + Our basline is fifteen (15) failed events occurring, normally, on the Windows sever.
  + Our alert threshold is twenty (20) failed events, to notify VSI when suspicious activity is occuring.

*Figure 11 - Alert enabled for suspicious level of failed activity.*                                                              
![win Alert - Failed Activity](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/8be36de5-86d8-486e-b251-b7bb86004b3c)

### Hourly Count of Successful User Logins

We began by establishing a baseline and threshold for the hourly count of successful logins.

*Figure 12 - Search ran to display an hourly count by signature.*                                                                                            
![win server hourly count by signature search](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/1bd7006a-e45e-4b15-bc54-5e73a33f60c8)

*Figure 13 - Hourly count for "an account was successfully logged on" highlighted.*
![win server hourly count by signature](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/4d9263ff-19c2-4676-a4f1-a7032ab05781)

The data highlighted in Figure 13, shows that VSI sees the signature, "an account was successfully logged on", an average of thirty-one (31) times per hour. With this, we determined:

  + Our basline is thirty-one (31) successful account logins ocurring, normally, on the Windows server.
  + Our alert threshold is fourty-five (45) successful logins, to notify VSI when suspicious activity is occuring.
  + It is best to design this alert with the corresponding signature ID, since signature names sometimes change. 
    - The ID needed for this alert is: **4624** *(see Figure 2)*

*Figure 14 - Alert enabled for suspicious signature count "an account was successfully logged on".*                                                            
![win alert - login success](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/ddf15d29-c5dc-4712-828e-845c4f4ac64c)

### Hourly Count of Deleted Users

We began by establishing a baseline and threshold for the hourly count of deleted user accounts.

*Figure 15 - Search ran to display the hourly count of user accounts being deleted.*                                                                    
![win server - deleted user acc search](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/db247094-ee54-4d09-a6d9-8c3c89346cd0)

*Figure 16 - Hourly user accounts being deleted, normally, on the Windows server.*                                                                                                                                          
![win server - user acc deleted](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/4306170d-098f-4543-bcca-3d3e3fec0180)

In Figure 16, the data reveals that VSI generally experiences the deletion of 20-30 user accounts in any given hour on the Windows server. However, my team observed a variance in event counts and hourly totals. Upon deeper investigation, we identified that this discrepancy was attributed to the multiple uploads of the Windows server log on my system. From this, we determined:

  + My Splunk report was the only one, in the group, with the log data uploaded multiple times.
  + We opted to use the team's data to design this alert.
  + Our baseline is ten (10) user accounts being deleted, normally, on the Windows server.
  + Our alert threshold is seventeen (17) user accounts being deleted, to notify VSI when suspicious activity is occuring.
  + The corresponding Signature ID is: **4726** *(see Figure 2)*

*Figure 17 - Alert enabled for suspicious signature count "a user account was deleted".*                                                        
![win Alert - User Deleted](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/dbf4c620-21fd-4a20-8e16-32d48cfefab4)

## Windows Server Monitoring

My team leveraged Splunk's visualization capabilities to transform raw log data into meaningful insights, making it easier to monitor and understand the Windows server activity. This section includes the majority of the Windows dashboards that we created.

Splunk dashboards provide a centralized and user-friendly interface, facilitating interactive analysis of the data we acquired. 

### Signature Counts Timeline

*Dashboard 01 - Line Chart and Table of Signature Field Values Over Time.*                                                                                
![win serv monitoring -Signature Line Chart](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/ffbfa581-22fe-4741-b0b7-abc022220986)

  + This provides us with a clear and graphical representation, making it easier to identify patterns, trends, or anomalies in the data.

### User Activity Timeline

*Dashboard 02 - Line Chart of User Activity Over Time.*                                                  
![win serv monitoring - users over time](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/8ef1ef06-5487-46ac-8ad9-dc8ffcd55cce)

  + This provides insight into the patterns, trends, and changes in user activity within a specified timeframe.

### User Counts

*Dashboard 03 - Interactive Chart of total User Counts.*
![win serv monitoring - user count](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/3261c8ba-43d5-42f2-a338-3add7ef4e6c7)

  + By highlighting over the chart, within Splunk, my team was able to discern which user accounts had the highest count(s).

## Apache Reports

During this stage, my team uploaded and analyzed the Apache web server logs, representing regular activity for VSI. 

*Figure 18 - Splunk Review page to Verify Upload Settings.*                                                                                    
![splunk review](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/c19c46c7-009b-487a-a5d6-7aed4504cd3a)

In order to refine our search, we examined the following Splunk fields:

  + method
  + referer_domain
  + status
  + clientip
  + useragent

To assist in monitoring the Apache web server, we created the following reports:

### HTTP Method Activity

*Figure 19 - Report displaying a Table of HTTP Methods being Utilized.*                                                                            
![apache server - http methods table](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/84ef7489-9a08-4bd0-b380-9a98e0e5d674)

  + This gave us insight into the types of HTTP activity requested against the web server.

These are the general functions of the HTTP methods we found:

  + **GET**: Used to request data from a specified resource.
  + **POST**: Used to submit data to be processed to a specified resource.
  + **HEAD**: Similar to *GET* but retrieves only the headers of the response, not the actual content.
  + **OPTIONS**: Allows the client to determine the options and/or requirements associated with a resource, or the capabilities of a server, without initiating a resource retrieval.

### Top Referring Domains

Referrers are external domains or websites that direct traffic to another website. These referrers are other websites or domains that have links pointing to VSI's website, contributing to the incoming traffic.

*Figure 20 - Report highlighting the top 10 domains referring to VSI's website.*                                                                    
![apache  server - top 10 domains](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/6f5fe8db-daac-4f5f-8a4f-cb76f74707a1)

  + This helped us to identify suspicious referrers.

### HTTP Response Codes

HTTP response codes are standardized three-digit numerical codes that are sent by a web server to a client's browser as part of the HTTP (Hypertext Transfer Protocol) response. These codes provide information about the status of a requested HTTP transaction and help both servers and clients understand how to handle the communication

*Figure 21 - Report showing the count of each HTTP response code.*
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

*Figure 22 - Search ran to filter events and exlcude the United States.*                                                  
![apache server non US activity search](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/0cca8551-bf25-4d18-8e04-6d34892053f1)

*Figure 23 - Timeline of Non-US Activity on the web server.*                                                
![apache server non US activity](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/40570795-460d-4ff9-aca5-346cb5d51008)

The activity levels from outside the United States displayed a varied range of counts, typically fluctuating between 100 and 170 connections, with occasional counts dropping below 100. From this, we determined:

  + Our baseline is eighty (80) connections, occuring from any region outside of the United States, to the web server.
  + Our alert threshold is 170 connections, to notify VSI when suspicious activity is occuring.

*Figure 24 - Alert enabled for suspicious activity, from outside of the United States.*                                                                                  
![apache alert non US activity](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/a404b858-7e72-4d17-bd9b-f002a5b76a40)

### Hourly POST Method Count

*Figure 25 - Hourly count for the HTTP POST method on the administrative webpage.*                                                                      
![apache server - hourly http post method count](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/a763194c-fe56-45aa-9ac1-fa55c1a8e2f5)

The data depicted in Figure 25 reveals that the webpage typically registers 2-6 instances of the **POST** method, occasionally exhibiting spikes with counts exceeding 6. With this information, we dertermined:

  + Our baseline is two (2) instances of the **POST** method being registered on the administrative webpage.
  + Our alert threshold is seven (7) **POST** method occurances, to notify VSI when suspicious activity is occuring.

*Figure 26 - Alert enabled for suspicious hourly POST method count.*                                                                      
![apache alert http post](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/c665dbde-0020-4003-8967-aca60ca47de1)

## Apache Web Server Monitoring

My team leveraged Splunk's visualization capabilities to provide a centralized and user-friendly interface; facilitating interactive analysis of the, Apache web server, data we acquired. This section includes the majority of the Apache dashboards that we created.

### Geographical Mapping of Client IPs

*Dashboard 04 - Map and Table showing the location of the Client-side IP's.*                                                         
![apache serv monitoring - Clientip Cluster Map](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/44340332-995d-4a7c-8d46-5945a39d0b0f)

  + This provides us with a better understanding of the geographic distribution of users accessing the Administrative webpage.

### Uniform Resource Identifiers

URIs are strings of characters that identify a particular resource, typically on the internet. A URI can be categorized into two subtypes: **URLs** *(Uniform Resource Locators)* and **URNs** *(Uniform Resource Names)*.

  + URLs are a type of URI that specifies the means of accessing a resource and the protocol used to access said resource. Typical components include:
    - **https**: Protocol (in this case, Hypertext Transfer Protocol Secure)
    - **www.example.com**: Domain or host
    - **/index.html**: Path to the specific resource on the server
  + URNs are a type of URI that is used to identify resources by name in a particular namespace. Typical components include:
    - **urn**: Identifier type
    - **isbn**: Namespace identifier
    - **0451450523**: Unique identifier within the specified namespace

This dashboard focuses on the Uniform Resource Locators *(URLs)*.

*Dashboard 05 - Bar Chart and Table of Different URI Counts.*
![apache serv monitoring - URI counts](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/884b8ceb-a8d5-4602-be09-44771210228d)

  + This helped us monitor access to specific resources on the administrative webpage.

### Top 10 Active Countries

*Dashboard 06 - Bar Chart and Table of Top 10 Countries.*                                                                                        
![apache serv monitoring - Top 10 Countries](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/2978c8c6-cbf2-4928-9d13-07cfc28d208f)

  + This identifies countries with a high connection count, to the administrative webpage, and provides a baseline of activity.

### User Agent Counts

A User Agent refers to a string of information that is included in the HTTP header of a request made by a client (such as a web browser) to a web server. The User Agent string, includes browser, operating system, and device information, that provides context about the client's environment. Such as, identifying that a user is running Google Chrome 58 on Windows 10, macOS 10.15.7, or an iPhone running iOS 14.4.

*Dashboard 07 - Pie Chart and Table displaying the percentage of User Agent Counts.*                                                        
![apache serv monitoring - User Agents](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/430b87fc-26e1-44f5-9f48-de5354dbd683)

  + This helped us to establish a baseline of activty for the different User Agents, and understand the browsers, operating systems, and devices users are employing to connect to VSI's webpage.

## Add-On Splunk Application

My team chose the Splunk add-on app, [Website Monitoring](https://splunkbase.splunk.com/app/1493), to provide additional monitoring of VSI's systems. 

This application enables continuous monitoring of a designated website at predefined intervals. Providing insight into the average response time, historical response time data, maximum connection response time, and the count of previous website failures.

Additionally, this app allows VSI to monitor their website and react faster if they were to be attacked by Distributed Denial of Service *(DDoS)*. A type of cyberattack where multiple compromised computers or devices are used to flood a target system, service, or network with traffic, rendering it unavailable to its users.

Unfortunately due to how our systems were configured, for the Bootcamp, we were unable to get this add-on to connect during testing. The following is what you could expect to see when using the Website Monitoring application.

*Add-on Status Overview.*                                                                                                            
![addon tool - status overview](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/59ec283b-1ee1-4b4e-b42c-f72fe6c989b3)

*Add-on Connection Responses.*                                                                                                  
![addon tool - responses](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/3507e3b5-7efc-404a-b9e5-519a7d12ebb1)

## Monitoring and Analyzing Windows Attacks

We had been notified that VSI recently experienced several cyberattacks; unfortunately, this attack took down several of VSI’s systems. This targeted several systems, specifically, the Windows and Apache servers, which we were fortunately monitoring. Management provided us with additional logs from those same servers. These new logs cover the time period during which the attack occurred.

Our goal was to analyze these *attack logs* with our monitoring solution; assessing its effectiveness in identifying, mitigating, and responding to the cyberattack on the Windows Domain Controller that was being monitored. We uploaded the server *attack logs*, to Splunk, to review the updated results.

### Report Analysis for Severity

*Figure 27 - Windows Attack Log: Severity Report.*
![win att log - severity report](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/2d259c1a-c184-4f53-b6c4-7222674be414)

By comparing the data, from Figures 5 and 27, we addressed the following inquiry raised by VSI:

  + Did you detect any suspicious changes in severity?
    - Yes; these findings indicate the presence of suspicious changes in severity on the Windows server.
      + **Informational**: There has been a decrease of 13% in informational severity, declining from 93% to 80%.
      + **High**: Conversely, high severity cases have seen an increase of 13%, rising from 7% to 20%.

### Report Analysis for Failed Activities

*Figure 28 - Windows Attack Log: Successful vs Failed Activty.*                                                                          
![win att log - succ and failed activ](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/12b00aa5-e3b3-4e71-a142-294bf2994f26)

By comparing the data found, in Figures 6 and 28, we addressed the following inquiry raised by VSI:

  + Did you detect any suspicious changes in failed activities?
    - There were no significant shifts or suspicious changes in failed activities during the analyzed period.
      + **Success Rate**: The success rate exhibited a marginal increase, transitioning from 97% to 98%, reflecting a modest 1% improvement.
      + **Failure Rate**: Conversely, the failure rate saw a slight decrease, moving from 3% to 2%, indicating a 1% reduction.

### Alert Analysis for Failed Windows Activity

*Figure 29 - Timeline of Failed Activity in the Attack Log.*                                                
![win att log - failed activity](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/49143bc3-4d9a-4e99-a9c9-c86406ceb6a0)

By comparing the data found, in Figures 9 and 29, we addressed the following inquiries raised by VSI:

  + Did you detect a suspicious volume of failed Windows activity?
    - Yes, there was a suspicious volume of failed activity detected.
    
  + What was the count of events in the hour(s) it occurred?
    - During a single hour, there were seventy (70) events logged.
    
  + When did it occur?
    - This occurred from 8:00 AM to 9:00 AM, Wednesday, March 25th, 2020.
    
  + Would your alert be triggered for this activity?
    - Yes; the alert would be triggered as the threshold, we set, is at twenty (20) failed events. *(See Figure 11)*
    
  + After reviewing, would you change the threshold from what was previously selected?
    - No; changing the threshold is unnecessary in this instance, as our alert should trigger without issue.

### Alert Analysis for Successful Logins

*Figure 30 - Windows Attack Log: Successful Login Count Timeline.*                                                                        
![win att log - successful logins](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/33001990-31ec-44cc-b1dc-960be1c1fdff)

*Figure 31 - Timeline and the Count of each User Login during the Attack.*                                                                            
![win att log - user login timeline](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/4a0d4206-e485-41e0-b05d-ae399932d700)

By comparing the data found in the following figures Figure 3 and 30, and using the data in Figure 31. We addressed the following inquiries raised by VSI:

  + Did you detect a suspicious volume of successful logins?
    - Yes, there was a suspicious level of successful logins detected.

  + What was the count of events in the hour(s) it occurred? 
    - The successful login count was: 46 events at 10:00 AM, 392 events at 11:00AM, and 154 events at 12:00 PM. This led to a total of 592 events occurring during a three (3) hour window.
   
  + Who was the primary user logging in?
    - The primary user logging in during this timeframe was **user_j**. 
   
  + When did it occur?
    - The suspicious volume of logins occurred from 10:00 AM to 12:00 PM on Wednesday, March 25th 2020. 
   
  + Would your alert be triggered for this activity?
    - Yes, the alert would be triggered as the threshold is set at forty-five (45). *(See Figure 12)*

  + After reviewing, would you change the threshold from what was previously selected?
    - Yes, I would want to increase the alert threshold, slightly, from forty-five (45) to sixty (60). There were some data points that nearly reached our threshold, this would help to avoid any false positive alerts.
   
### Alert Analysis for Deleted Accounts

Referencing the Signature ID's, shown in Figure 2, we filtered our Splunk search to show the successful deletion of user accounts during the attack. This Signature's ID: **4726**

*Figure 31 - Timeline of Successful User Account Deletion.*                                                                              
![win att log - successful user deletion](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/5977e76d-f2c8-4eda-8a6f-970b71d869fa)

By comparing the data found; in Figures 14 and 31, we addressed the following inquiry raised by VSI:

  + Did you detect a suspicious volume of deleted accounts?
    - There were no signs of suspicious volumes of deleted accounts.
   
## Windows Dashboard Analysis

We accessed the Windows dashboards initially made; changing the source from the *original log* to the *attack log*. This adjustment enabled us to seamlessly view the new log data, while retaining the existing dashboard configurations. This section only covers part of my team's dashboard analysis.

### Analysis for Time Chart of Signatures

*Dashboard 08 - Line Chart of Signature Field Values during the Attack.*                                                                      
![Win Att Dash - signature timeline chart](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/d14f07cc-744e-454f-b39f-13a8ce45f285)

*Figure 32 - Bar Graph and Table of the Locked Out User Signature during the Attack.*                                                      
![Win Att - Locked Out Accounts](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/a4a8e07e-3346-4cea-bd11-ade8643459d5)

*Figure 33 - Line Chart and Table of Attempted Password Resets during the Attack.*                                                      
![Win Att - Password Reset Attempt](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/d37e5b26-a45e-40cb-8f16-d39a04820e3a)

By comparing data from:

  + Dashboard 1 and 8.
  + Figure 7 and 32.
  + Figure 8 and 33.

We addressed the following inquiries raised by VSI:

  + Does anything stand out as suspicious?
    - Yes, there were two (2) signatures displaying unusual spikes of activity.
   
  + What signatures stand out?
    - *A user account was locked out*. Signature ID:  **4740**
    - *An attempt was made to reset an accounts password*. Signature ID: **4724**
   
  + What time did the suspicious activity begin and stop for each signature?
    - Signature 4740 started at 12:00 AM on Wednesday, March 25th 2020 and stopped by 3:00 AM on Wednesday, March 25th 2020.
    - Signature 4724 started at 8:00 AM on Wednesday, March 25th and stopped at 11:00 AM on Wednesday, March 25th 2020.

  + What is the peak count of the different signatures?
    - Signature 4740 displayed a peak count of 1,792 account lockouts.
    - Signature 4724 displayed a peak count of 2,516 attempts to reset an account's password.

### Analysis for Users

*Dashboard 09 - Line Chart of User Activity during the Attack.*                                                                    
![Win Att Dash - User Activity](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/2d208deb-f6e4-4714-ac72-44a3694268fe)

*Dashboard 10 - Bar Graph of User Counts during the Attack.*                                                                        
![Win Att Dash - User Count](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/42f47ccb-f233-4ad8-b502-dc9de0590ee1)

By comparing data from:

  + Dashboard 2 and 9.
  + Dashboard 3 and 10.

We addressed the following inquiries raised by VSI:

  + Does anything stand out as suspicious?
    - Yes, there was suspicious activity detected.
   
  + Which users stand out?
    - “user_a” and “user_k”.
   
  + What time did it begin and stop for each user?
    - **User_a** started at 12:00 AM and stopped at 3:00 AM on Wednesday, March 25th 2020.
    - **User_k** started at 8:00 AM and stopped at 11:00 AM on Wednesday, March 25th 2020.
   
  + What is the peak count of the different users?
    - **User_a** showed a peak count of 1,968.
    - **User_k** showed a peak count of 2,512.

### Analysis of Statistical Charts

My team addressed the following inquiry made by VSI:

  + What are the advantages and disadvantages of using a statistical chart, compared to the other panels that you created?
    
    - **Advantages:**
      + Statistical charts provide a visual representation of data, making it easier to identify patterns, trends, and outliers.
      + Effective at displaying time-based data, enabling the observation of trends and fluctuations over time.
      + Many statistical charts in Splunk offer interactive features, such as zooming and panning, providing the ability to explore and interact with the data dynamically.
    
    - **Disadvantages:**
      + Charts may provide an overview but can lack the detailed information available in raw data tables, requiring reference to the underlying data for specific values.
      + In situations with a large volume of data, charts can become crowded, potentially leading to information overload and making it challenging to discern specific details.
      + Some users, particularly those with visual impairments, may face challenges with visual charts. Ensuring accessibility for all users may require additional considerations.
     
Statistical charts in Splunk offer valuable visual insights and are effective for certain types of analysis. However, considerations should be made based on the specific data, analytical goals, and the organization's preferences. Depending on the context, a combination of statistical charts and other panels may provide the most comprehensive and user-friendly approach to data analysis.

## Monitoring and Analyzing Apache Attacks

Our goal was to analyze the *attack logs* with our monitoring solution; assessing its effectiveness in identifying, mitigating, and responding to the cyberattack on the Apache web server that was being monitored. We uploaded the server *attack logs*, to Splunk, to review the updated results.

### Report Analysis for HTTP Methods

*Figure 34 - Graph and Table showing HTTP Method Count during the Attack.*                                                          
![apache attack - HTTP Methods](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/1d5a720f-8d44-42a9-8a9d-e1226bccc7a0)

By comparing the data found, in Figures 19 and 34, we addressed the following inquiries raised by VSI:

  + Did you detect any suspicious changes in HTTP methods? If so, which one?
    - Yes; there was a 29% decrease in **GET** activity, from 99% to 70%, and as well as a 29% increase in **POST** activity, from 1% to 29%.
   
  + What is that method used for?
    - **GET**: Used to request data from a specified resource.
      + The data is visible in the URL, making it suitable for non-sensitive information. However, there is a limitation on the amount of data that can be sent via URL.
    - **POST**: Used to submit data to be processed to a specified resource.
      + The data is not visible in the URL, providing a more secure way to transmit sensitive information.

### Report Analysis for Referrer Domains

*Figure 35 - Bar Graph and Table of the Top 10 Domains, referring to VSI's website, during the attack.*                                        
![apache attack - Referer Top 10 Domains](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/043b589a-8e7d-4a4e-8212-3bc81ee93b15)

By comparing the data found, in Figures 20 and 35, we addressed the following inquiry raised by VSI:

  + Did you detect any suspicious changes in referrer domains?
    - No; we did not detect any suspicious changes in referrer domain activity.
   
### Report Analysis for HTTP Response Codes

*Figure 36 - Bar Graph and Table of HTTP Responses during the attack.*                                                                
![apache attack - HTTP Responses](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/35c7e59a-2f98-417a-af62-3a48a7e4cb10)

By comparing the data found, in Figures 21 and 36, we addressed the following inquiry raised by VSI:

  + Did you detect any suspicious changes in HTTP response codes?
    - Yes; while numerous minor changes occured, the most suspicious was the change in *404* responses. It displayed an 11% increase, rising from 4% to 15%.

### Alert Analysis for International Activity

*Dashboard 11 - Map showing the location of the Client-side IP's during the attack.*                                                            
![apache attack - Clientip Cluster Map](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/773151cf-0b45-4bbd-bd74-3e980774a8a1)

By comparing the data found, in Dashboards 4 and 11, we addressed the following inquiries raised by VSI:

  + Did you detect a suspicious volume of international activity?
    - Yes; there was a suspicious level of activity in Kiev, Ukraine at 8:00 PM on March 25th 2020.
   
  + What was the count of the hour(s) it occurred in?
    - There was a total of 937 connections, to the administrative webpage from Kiev, during the 8:00 PM attack.
   
  + Would your alert be triggered for this activity?
    - Yes; the alert would be triggered, as our threshold is set at 170. *(See Figure 24)*
   
  + After reviewing, would you change the threshold that was previously selected?
    - Yes; I want to increase the threshold from 170 to 200, to help avoid any false positive alerts.

### Alert Analysis for HTTP POST Activity

*Dashboard 12 - Timeline of HTTP Method Activity during the attack.*                                                                        
![apache attack - http method activity](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/d51f7344-7de6-4c68-adc7-87456b129ae0)

*Figure 37 - Timeline of POST Method Activity during the attack.*                                                                     
![apache attack - HTTP POST Count](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/6cb93f09-46e3-4bd1-b363-f3de3ef3187c)

By comparing the data found; in Figures 25, 37, and Dashboard 12, we addressed the following inquiries raised by VSI:

  + Did you detect any suspicious volume of HTTP POST activity?
    - Yes, a suspicious and potentially concerning elevation in *POST* method activities was detected.
   
  + What was the count of the hour(s) it occurred in?
    - There was a total count of 1,296 for the *POST* method during the attack.
   
  + When did it occur?
    - The attack occurred at 8:00 PM, Wednesday, March 25th 2020.
   
  + After reviewing, would you change the threshold that you previously selected?
    - No, changing the threshold is unnecessary in this instance.

## Apache Dashboard Analysis

We accessed the Apache dashboards initially made; changing the source from the *original log* to the *attack log*, enabling us to view the new log data, while retaining the existing dashboard configurations. This section only covers part of my team's dashboard analysis.
