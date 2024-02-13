# Securing Cloud Applications

![portfolio1](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/c2e290f7-3cac-46ef-89d2-558df710fb84)

## Table of Contents

  + [01. Overview](#Overview)
  + [02. Equipment and Tools](#Equipment-and-Tools)
  + [03. Project Requirements](#Project-Requirements)
  + [04. Advantages of Azure's App Service](#Advantages-of-Azure's-App-Services)
  + [05. Security Issues](#Security-Issues)
  + [06. Addressing the Security Concerns](#Addressing-the-Security-Concerns)
  + [07. Azure's Front Door](#Azure's-Front-Door)
  + [08. Azure's Security Center](#Azure's-Security-Center)

## Overview

I developed a cyber-blog web application using Azure's Cloud services and Docker, prioritizing security measures throughout. SSL certificates were securely stored in Azure's Key Vault and seamlessly integrated for enhanced protection. To fortify the web application, I implemented Azure's Security features, including Front Door, WAF, and Security Center. This approach empowers a secure and reliable system against potential cyber threats. My project technical brief is provided as a PDF, in this GitHub repository, titled [Securing Cloud Applications - Technical Brief](https://github.com/CJanecka/Projects_and_CTFs/files/14234281/Securing.Cloud.Applications.-.Technical.Brief._.Collin.Janecka.pdf). This document offers a detailed overview of the project, providing insights and addressing the questions that were posed to me.

## Equipment and Tools

The technologies used in this project include:

  + Azure
    - Keyvaults
    - App Services
    - Front Door
    - Web Application Firewall *(WAF)*
  + Hypertext Preprocessor *(PHP)*
  + Hypertext Markup Language *(HTML)*
  + Open-Source Software Library *(OpenSSL)*
  + Docker

## Project Requirements

The project requirements included:

  + Utilizing Azure's Cloud Services to host the web application.
    
  + Creating the web application through Azure's App Service resource.
    
  + Opting for a domain, a choice between GoDaddy or Azure, I went with a GoDaddy domain.
    
  + Deploying a Docker container containing the framework for a blog webpage.
    
  + Customizing the webpage by SSHing into the container.
    
  + Generating a self-signed certificate using OpenSSL.

  + Storing the certificate in Azure's Key Vault.

  + Binding the certificate to the website, since I did not utilitze an Azure domain.

  + Addressing security concerns associated with the self-signed certificate by creating and binding a managed CA-approved certificate to the web application.

  + Implementing Azure's Front Door and configuring a WAF rule to restrict traffic from specific countries.

  + Conducting an analysis of Azure's Security Center recommendations and applying the recommended fixes.

## Advantages of Azure's App Service

The advantages of choosing Azure’s App Service resource, instead of creating a Virtual Machine from scratch:

  + By leveraging Azure App Service, the responsibility for managing features beyond the web application is transferred to the cloud service provider.

    - In essence, I was able to focus on the deployment and management of the web application along with its associated data.
   
  + The deployment of web applications becomes significantly faster as users are relieved from the intricacies of configuring their operating systems.

  + Users are unburdened from concerns related to OS and middleware maintenance, including the installation of software updates and patch management.

  + Azure App Services offer a cost-effective alternative to running Virtual Machines.

  + Azure App Services come equipped with an array of built-in features designed to secure and host web applications, including DNS management, Web Application Firewalls (WAF), domain procurement, and SSL certificate binding.

## Security Issues

A self-signed certificate is an unsigned certificate, meaning it has not received validation from a recognized certificate authority. Although creating such certificates is a straightforward and cost-effective process, it's imperative to note that most web browsers will issue a warning to users when they visit a webpage secured with a self-signed certificate. This warning notifies users that the webpage lacks verification from a certificate authority listed in the browser's root store, thus urging caution when proceeding.

## Addressing the Security Concerns

To address the challenge posed by the use of a self-signed certificate; I opted to generate, and link, a managed certificate supplied by Azure. This certificate holds the endorsement of a certificate authority (CA), ensuring its trustworthiness and wide recognition across most web browsers.

## Azure's Front Door

***What is Azure’s Security Center, and how did I apply its features?***

Azure's Front Door is a cloud resource, positioned ahead of my web application, serving as a defense mechanism. Operating at the Application Layer of the OSI Model (Layer 7), its central function revolves around load balancing. Moreover, it offers the capability to integrate a Web Application Firewall (WAF) to fortify defenses against vulnerabilities inherent to web attacks. In conjunction with the WAF, a custom rule was implemented to safeguard against web requests originating from regions not within the anticipated scope of visitors. This proactive measure plays a crucial role in protecting the system against potential threats in cases where unexpected visitors may pose a security risk.

*Figure 01 - Azure Front Door enabled.*                                                                        
![image](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/84fd63e5-1a8b-4848-8602-8550a251c37f)

*Figure 02 - Custom Web Application Firewall (WAF).*                                                    
![image](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/a6d6f7de-2862-415b-b744-778c73bb101b)

## Azure's Security Center

***What is Azure’s Security Center, and how did I apply its features?***

Azure Security Center serves as a management system, offering a repository of best practices and guidance to augment the security of cloud-based resources. During my evaluation, security recommendations were observed spanning a range of  criticality levels. One noteworthy recommendation suggests strengthening the security of data transmissions, by enforcing FTP access, to the web application through FTPS. FTPS refers to the encrypted version of File Transfer Protocol, providing a secure means of transferring data. This measure enhances the overall security posture of the system.
