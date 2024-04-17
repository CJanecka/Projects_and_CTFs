# Networking Basics CTF

![portfolio5](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/562b0a28-7c3d-42bf-8c1d-77fcb02c7c2c)

## Table of Contents

  + [01. Overview](#Overview)
  + [02. Equipment and Tools](#Equipment-and-Tools)
  + [03. Activity Requirements](#Activity-Requirements)
  + [04. Networking Capture the Flag *- Cartoon Edition*](#Networking-Capture-the-Flag---Cartoon-Edition)
    - [a. Sponge Bob Square Ports](#Sponge-Bob-Square-Ports)
    - [b. Inspector Packet](#Inspector-Packet)
    - [c. Where Waldo's Address?](#Where-Waldos-Address)
    - [d. Dragons Layers](#Dragons-Layers)
    - [e. The Ping Panther](#The-Ping-Panther)
    - [f. The Grinch Stole my wifi Password](#The-Grinch-Stole-my-wifi-Password)
    - [g. Ronald MACdonald](#Ronald-MACdonald)
    - [h. SUPER Mario Hackers! *- Bonus*](#SUPER-Mario-Hackers---Bonus)
  + [05. Appendix - OSI Model](#Appendix---OSI-Model)
    - [a. Layer 7 *- Application*](#Layer-7---Application)
    - [b. Layer 6 *- Presentation*](#Layer-6---Presentation)
    - [c. Layer 5 *- Session*](#Layer-5---Session)
    - [d. Layer 4 *- Transport*](#Layer-4---Transport)
    - [e. Layer 3 *- Network*](##Layer-3---Network)
    - [f. Layer 2 *- Data Link*](##Layer-2---Data-Link)
    - [g. Layer 1 *- Physical*](##Layer-1---Physical)
    - [h. Flow of Data](#Flow-of-Data)
  
## Overview

<base points to change>

  + a networking Capture the Flag competition.
  + Total of 64 questions *(flags)*, 
  + eight teams of four, two teams of 5 competed.
  + provided a spreadsheet of various networking questions and activities that are separated into different networking categories.
  + separated into eight different networking categories, one of which is a bonus, three required inspecting packets in Wireshark.
  + <cont here>
  + Completed spreadsheet provided separately.

## Equipment and Tools

  + [Networking CTF (Unanswered Form).xlsx](https://github.com/CJanecka/Projects_and_CTFs/files/14968538/Networking_CTF.xlsx)
  + Wireshark
  + Open-source intelligence

## Activity Requirements

<base points to change>

  + There are a total of 64 questions and activites, four of which are bonus.
    - The answers for these are the flags to collect.
  + Each flag has a different numeric point value. Max possible score of 600 points.
    - The higher the point value, the more challenging the question/activity.
  + 2.5-hour alotted timeframe.
  + The team that completes all the flags correctly first, or who has the most points by the end of the alotted time, wins the CTF.

## Networking Capture the Flag *- Cartoon Edition*

<add intro content>

![CTF0 - Header](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/bbd020d9-e8a1-4176-b769-e2eb65733ffb)

<base points to change>

<cont here>

### Sponge Bob Square Ports

This section explores various network ports and their roles in facilitating a range of internet services. *Including -* online gaming, web browsing, remote access, email delivery, and more.

![CTF1 - S Bob](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/3c037525-0326-4021-ab7d-9824b75e4ec0)

**Question 01** ***— What is the port of HTTPS?***

  + Answer — HTTPS occurs on **port 443** by default.
    - HTTPS stands for Hypertext Transfer Protocol Secure. It occurs on the *Application layer* of the [OSI model](https://www.geeksforgeeks.org/open-systems-interconnection-model-osi/), as an extension of HTTP, and encrypts the data being transferred between a web server and a client *(web browser or application)*. Commonly used for online banking, secure logins, and e-commerce transactions.

**Question 02** ***— What is the port of SSH?***

  + Answer — SSH occurs on **port 22** by default.
    - SSH stands for Secure Shell. It occurs on the *Application layer* of the OSI model, and is a protocol that allows secure remote access and control of servers and systems. This is widely used for remote login and command execution over encrypted channels, making it a popular choice for server administrators.

**Question 03** ***— What is the port of SMTP?***

  + Answer — SMTP occurs on **port 25** by default.
    - SMTP stands for Simple Mail Transfer Protocol. It occurs on the *Application layer* of the OSI model; and is used to facilitate communication, between the sending and receiving servers, when delivering an email message to a recipient.

**Question 04** ***— What is port 53 used for?***

  + Answer — Port 53 is the default used for Domain Name System (**DNS**) queries and responses.
    - DNS translates domain names (like, google.com) into IP addresses. It occurs on the *Application layer* of the OSI model, enabling web browsers and other applications to locate servers based on their domain names.

**Question 05** ***— What is port 123 used for?***

  + Answer — Port 123 is the default used for Network Time Protocol (**NTP**).
    -  This protocol works over the *Application layer* of the OSI model, and facilitates accurate timekeeping across different systems, by synchronizing the clocks of networked devices.

**Question 06** ***— What is the port of BGMP?***

  + Answer — The default port number for BGMP is **264**.
    - BGMP stands for Border Gateway Multicast Protocol. It operates on the *Transport layer* of the OSI model, and is a protocol used in networking to manage the distribution of multicast traffic across the internet.

**Question 07** ***— What is the port of Tomcat Remote Shutdown?***

  + Answer — Tomcat uses TCP port **8005** as a dedicated port for accepting shutdown requests.
    - This operates at the *Application layer* of the OSI model, and allows for administrative control over the Tomcat server, specifically for shutting down the server remotely.

**Question 08** ***— What is the port of Bitcoin?***

  + Answer — By default, Bitcoin nodes communicate with one another using port **8333**.
    - This port is used for sharing and receiving data blocks and transaction information across the Bitcoin network.

**Question 09** ***— What is the total amount of TCP and UDP ports?***

  + Answer — There are **131,070** total TCP and UDP ports.
    - TCP and UDP are two of the major *Transport layer* protocols in the [internet protocol suite](https://docs.oracle.com/cd/E19455-01/806-0916/6ja85398m/index.html). Both have a range of available ports from 0 to 65,535.
      + 0 to 1,023 — Well-known or System ports
      + 1,024 to 49,451 — Registered ports
      + 49,512 to 65,535 — Dynamic and/or Private ports
    - The total number of ports, when combining TCP and UDP is: 65,535 (TCP) + 65,535 (UDP) = 131,070. 

**Question 10** ***— Well-known ports are from zero to what?***

  + Answer — Well-known ports are from 0 to **1,023**.
    - Well-known ports are defined by the [Internet Assigned Numbers Authority](https://www.iana.org/assignments/service-names-port-numbers/service-names-port-numbers.xhtml) (IANA), with the range from 0 to 1,023. These ports are reserved for standard protocols and services (such as: HTTP, FTP, and SMTP).

**Question 11** ***— What TCP port does Call of Duty: Ghosts use on the Xbox 360?***

  + Answer — *Call of Duty: Ghosts* uses port **3074** for online multiplayer on the 360.
    - It is a standard port for several online gaming platforms and consoles. This port allows for game servers and clients to communicate for matchmaking and gameplay purposes. It is used to establish connections with game servers, allowing players to join multiplayer matches, communicate with other players, and synchronize game data.

***Sponge Bob Square Ports*** *— Successfully Completed*                                                                              
![CTF1 - S Bob - complete](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/2d44117d-c518-4f51-a133-e56f126f186f)

### Inspector Packet

<base points to change>

![CTF2 - Packet Insp](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/e964bdcc-9f9f-4b7e-aa99-4f3d41cca863)

<cont here>

***Inspector Packet*** *— Successfully Completed*                                                                                    
![CTF2 - Packet Insp - complete](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/0ea05fe9-4241-4fc3-82fc-82ba46acc39c)

### Where Waldo's Address?

<base points to change>

![CTF3 - Waldo Address](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/99dac332-e279-4fd1-91e0-f536adedf21f)

<cont here>

***Where Waldo's Address?*** *— Successfully Completed*                                                                                
![CTF3 - Waldo Address - complete](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/8e803f8f-52c4-46dc-a046-675b47bfef35)

### Dragons Layers

<base points to change>

![CTF4 - Dragon Layers](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/fe958147-0686-4ccf-871f-5acae55b1c94)

<cont here>

***Dragons Layers*** *— Successfully Completed*                                                                                        
![CTF4 - Dragon Layers - complete](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/5acdb7db-f561-4f2d-9606-196612a4e124)

### The Ping Panther

<base points to change>

![CTF5 - Ping Panther](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/6ef243a8-8acb-4d16-91ba-64f74e327d64)

<cont here>

***The Ping Panther*** *— Successfully Completed*                                                                                      
![CTF5 - Ping Panther - complete](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/504e4128-385a-40f3-b60a-2454ceac00f8)

### The Grinch Stole my wifi Password

<base points to change>

![CTF6 - Grinch](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/f6eeb8a5-cf18-4cb5-aa8c-a94c537398ed)

<cont here>

***The Grinch Stole my wifi Password*** *— Successfully Completed*                                                                
![CTF6 - Grinch - complete](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/9d170575-7cfe-4b05-a944-ba1becd50c04)

### Ronald MACdonald

<base points to change>

![CTF7 - MACdonald](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/d0f2799f-c583-428e-942c-b674721c1b30)

<cont here>

***Ronald MACdonald*** *— Successfully Completed*                                                                                  
![CTF7 - MACdonald - complete](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/e233f907-9a14-4865-85d5-74a2e0a69baf)

### SUPER Mario Hackers! *- Bonus*

<base points to change>

![CTF8 - Mario](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/247649be-461f-4056-9009-0055a133ba4b)

<cont here>

***SUPER Mario Hackers!*** *— Bonus Successfully Completed*                                                                      
![CTF8 - Mario - complete](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/020c90cd-107f-45da-b427-4043c6cc2007)

## Appendix - OSI Model

The Open Systems Interconnection (OSI) model is a reference framework that allows different computer systems to communicate with each other. Developed by the International Organization for Standardization (ISO), the OSI model facilitates interoperability between diverse communication systems through standard [network protocols](https://www.comptia.org/content/guides/what-is-a-network-protocol). This model organizes a communication system into seven conceptual layers, each building upon the one below it.

<add main image here>

While today's Internet utilizes the [TCP/IP Model](https://www.geeksforgeeks.org/tcp-ip-model/), the OSI Model can be valuable for troubleshooting network issues. Whether a single user cannot connect their laptop to the Internet, or a website is down for thousands of users, the OSI model helps break down the problem and isolate its source. By pinpointing the specific layer where the issue arises, unnecessary work can be minimized.

### Layer 7 *- Application*

<add Application layer image here>

Also known as the *"End User Layer"*, and the only layer that directly interacts with data from the user. It supports software applications; such as web browsers and email clients, in establishing communications and delivering meaningful data to the user. The software applications themselves are not part of the OSI model; they operate within the *end-user environment*, and use the Application layer to interact with network resources and services. This layer acts as a gateway for application services to connect to the network and present received information to the user.

#### Functions

The Application Layer, being topmost layer in OSI model, serves as the interface between network services and end-user applications, providing the necessary protocols and services to facilitate communication, data exchange, and resource management across networks.

  + *Network Virtual Terminal* — allows a user to log into a remote host, and interact with it, as if they were directly connected to it.
  + *File Transfer Access and Management (FTAM)* — allows users to access files stored on a remote host, retrieve files from a remote host, and manage or control files remotely.
  + *Mail Services* — provides email services, enabling users to send and receive email messages across networks.
  + *Directory Services* — provides a distributed database for managing and accessing information about various objects and services in a network.

#### Protocols

*Application layer protocols include:*

[TELetype NETwork](https://www.geeksforgeeks.org/introduction-to-telnet/) (TELNET) | [File Transfer Protocol](https://www.geeksforgeeks.org/file-transfer-protocol-ftp-in-application-layer/) (FTP) | [Network File System](https://www.geeksforgeeks.org/network-file-system-nfs/) (NFS) | [Simple Mail Transfer Protocol](https://www.geeksforgeeks.org/simple-mail-transfer-protocol-smtp/) (SMTP) | [Simple Network Management Protocol](https://www.geeksforgeeks.org/simple-network-management-protocol-snmp/) (SNMP) | [Domain Name System](https://www.geeksforgeeks.org/domain-name-system-dns-in-application-layer/) (DNS) | [Dynamic Host Configuration Protocol](https://www.geeksforgeeks.org/dynamic-host-configuration-protocol-dhcp/) (DHCP) | [Hypertext Transfer Protocol / Secured](https://www.geeksforgeeks.org/http-full-form/) (HTTP/HTTPS) | [Internet Relay Chat](https://www.geeksforgeeks.org/internet-relay-chat-irc/) (IRC) | [Post Office Protocol](https://www.geeksforgeeks.org/pop-full-form/) (POP) | [Multipurpose Internet Mail Extension](https://www.geeksforgeeks.org/multipurpose-internet-mail-extension-mime-protocol/) (MIME) | [Secure Shell](https://www.cloudflare.com/learning/access-management/what-is-ssh/#:~:text=(SSH's%20exact%20OSI%20layer%20is,7%2Fapplication%20layer%20protocol.)) (SSH)

### Layer 6 *- Presentation*

<add Presentation layer image here>

#### Functions

#### Protocols

*Presentation layer protocols include:*

### Layer 5 *- Session*

<add Session layer image here>

#### Functions

#### Protocols

*Session layer protocols include:*

### Layer 4 *- Transport*

<add Transport layer image here>

#### Functions

#### Protocols

*Transport layer protocols include:*

### Layer 3 *- Network*

<add Network layer image here>

#### Functions

#### Protocols

*Network layer protocols include:*

### Layer 2 *- Data Link*

<add Data Link layer image here>

#### Functions

#### Protocols

*Data Link layer protocols include:*

### Layer 1 *- Physical*

<add Physical layer image here>

#### Functions

#### Protocols

*Physical layer protocols include:*

### Flow of Data

When transferring information from one device to another, the data passes through all seven layers of the OSI model. Initially, on the sender's side, data moves **down** through the seven layers; then ascends back **up** the seven layers, on the recipient's side. The following is an example of this:

*Scenario* — Harry sends an email with an attachment to Hermione.

  + **Sender's Side**:
    - *Step 1* — Harry uses an email application, such as Outlook/Yahoo/Gmail, to compose an email and attach a file he wants to send to Hermione. **(Layer 7 — Application)**
    - *Step 2* — The mail application encrypts and formats the email, and attachment, for transmission. **(Layer 6 — Presentation)**
    - *Step 3* — A connection is established between Harry's device and Hermione's device for the email to be sent. **(Layer 5 — Session)**
    - *Step 4* — The email and attachment are broken down into smaller data segments. Adding sequence numbers and error-checking information, to maintain data reliability. **(Layer 4 — Transport)**
    - *Step 5* — The email segments are addressed using IP addresses to find the best route from Harry's device to Hermione's device. **(Layer 3 — Network)**
    - *Step 6* — Data packets are encapsulated into frames, and MAC addresses are added for local devices. Error detection and correction are also performed. **(Layer 2 — Data Link)**
    - *Step 7* — The frames are transmitted as electrical, optical, or radio signals over the network medium (e.g., Ethernet cable, fiber optics, or Wi-Fi) from Harry's device to Hermione's device. **(Layer 1 — Physical)**

The data then travels up the OSI model layers in reverse order on Hermione's device.

  + **Recipient's Side**:
    - *Step 1* — The received signals are converted back into digital data at Hermione's device. **(Layer 1 — Physical)**
    - *Step 2* — The frames are reassembled into packets and checked for errors. **(Layer 2 — Data Link)**
    - *Step 3* — The packets are routed to the appropriate higher layer for processing. **(Layer 3 — Network)**
    - *Step 4* — The segments are reassembled into the complete email and attachment, then checked for any errors. **(Layer 4 — Transport)**
    - *Step 5* — A connection is established between Harry's device and Hermione's device for the email to be received. **(Layer 5 — Session)**
    - *Step 6* — The data is decrypted back into the original email and attachment. **(Layer 6 — Presentation)**
    - *Step 7* — The email and attachment are delivered to Hermione's email application. **(Layer 7 — Application)**

*Visual Representation:*                                                                                          
![OSI Model](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/3a4af882-05f2-417f-9312-eafed4a6bc8d)
