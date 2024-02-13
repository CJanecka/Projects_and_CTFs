# Defensive Security

![portfolio8](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/0e681c7c-ca7b-4725-a35a-e84601eb8858)

## Table of Contents

  + [01. Overview](#Overview)
  + [02. Equipment and Tools](#Equipment-and-Tools)
  + [03. Project Requirements](#Project-Requirements)
  + [04. Baselines and Thresholds](#Baselines-and-Thresholds)
  + [05. Post-Attack Modifications](#Post-Attack-Modifications)
  + [06. Future Mitigations](#Future-Mitigations)

## Overview

In this project I played the role of a Security Operations Center *(SOC)* analyst for a small company, called Virtual Space Industries *(VSI)*. Tasked with monitoring an Apache web server, that hosts the administrative webpage; and a Windows operating system, which runs many of VSI’s back-end operations. Working in a small group, we employed Splunk to craft a monitoring environment, developing tailored reports, alerts, dashboards, and an add-on app to fortify the security of this fictitional organization. A pivotal element of this project entailed simulating an attack to gauge the efficacy of our monitoring solutions. Following the simulated attack, we conducted an analysis of the system's performance in detecting and mitigating the threat(s). The culmination of this effort was later presented to our cybersecurity bootcamp class, to offer insights for enhancing cybersecurity within a broader organizational context. <add docs here>

## Equipment and Tools

The technologies used in this project include:

  + Splunk
    - Reporting
    - Alerting
    - Dashboards
  + Windows Server Logs
    - This server houses the intellectual property of VSI's cutting-edge virtual reality programs for the next generation.
  + Apache Server Logs
    - This server is dedicated to hosting VSI's primary public-facing website, *vsi-company.com*.
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

## Baselines and Thresholds

This section outlines my group analysis conducted on the activity within VSI's operations. We first established a baseline for *normal* behavior by studying the log data and patterns. Once esablished, an alert threshold was designed, strategically positioned outside this baseline, to prevent false positives. The intent was to ensure that generated alerts truly indicate anomalous or potentially suspicious activities, bolstering the efficiency and accuracy of the monitoring system.

To establish a baseline and better understanding of how the organization operates normally, we uploaded and analyzed the two provided Windows security logs.

*Figure 01 - Splunk report of Signatures and their respective ID's.*                                                                        
![image](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/e555cd76-45ea-4c32-a6b6-49cb05b1a587)

