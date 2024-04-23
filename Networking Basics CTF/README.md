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
    - [e. Layer 3 *- Network*](#Layer-3---Network)
    - [f. Layer 2 *- Data Link*](#Layer-2---Data-Link)
    - [g. Layer 1 *- Physical*](#Layer-1---Physical)
    - [h. Flow of Data](#Flow-of-Data)
  
## Overview

<base points to change>

  + a networking Capture the Flag competition.
  + Total of 64 questions *(flags)*, 
  + eight teams of four, two teams of 5 competed.
  + provided with a spreadsheet of various networking questions and activities, that are separated into different networking categories.
  + separated into eight different networking categories, one of which is a bonus, three required inspecting packets in Wireshark.
  + <cont here>
  + Completed spreadsheet provided separately.

## Equipment and Tools

  + [Networking CTF (Unanswered Form).xlsx](https://github.com/CJanecka/Projects_and_CTFs/files/14968538/Networking_CTF.xlsx)
  + [Wireshark](https://www.wireshark.org/about.html)
  + [The OSI Model](#Appendix---OSI-Model)
  + Open-source intelligence
  + <cont here>

## Activity Requirements

<base points to change>

  + There are a total of 64 questions and activites, four of which are bonus.
    - The answers for these are the flags to collect.
  + Each flag has a different numeric point value, with a max possible score of 600 points.
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

My team had to analyze the [Inspector Packet pcap file](https://github.com/CJanecka/Projects_and_CTFs/tree/main/Networking%20Basics%20CTF/Resources) using Wireshark in order to complete this section of the CTF (Capture The Flag).

![CTF2 - Packet Insp](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/e964bdcc-9f9f-4b7e-aa99-4f3d41cca863)

**Question 12** ***— How many total packets are in the pcap file?***

  + Answer — There are **50** total packets in the pcap file.
    - The Wireshark application shows the amount of packets, within the file, on the bottom bar of the application window.

![Inspector Packet - total packets](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/a579a0f0-a4db-4fcf-8de4-0d6d13eeee02)

**Question 13** ***— How many total ARP packets are in the pcap file?***

  + Answer — There are **19** address resolution protocol (ARP) packets in the pcap file.
    - We used Wireshark to filter the file contents and display only the ARP packets. The bottom of the application window shows the total.

![Inspector Packet - ARP packets](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/d8906128-05bd-4d07-b00a-8118040f5593)

**Question 14** ***— What domain did the user first try to access?***

  + Answer — The user first attempted to access '**thesimpsons.com**'.
    - By filtering for domain name system (DNS) packets; we identied the earliest DNS query, which represents the first attempt by the user to access a domain.

![Inspector Packet - first domain](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/fe26eb90-11b5-413d-a9f9-6b61d47aa834)

**Question 15** ***— What initial HTTP response code did the user get?***

  + Answer — The user received an HTTP response code of **301**, which indicates that the resource has been permanently moved to a new location.
    - By filtering for HTTP responses, we identified the initial response given to the user.

![Inspector Packet - http response](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/deee5aeb-6985-4287-a9da-89212a3acc2f)

**Question 16** ***— What primary domain was the website directed to?***

  + Answer — The website was directed to the primary domain '**fox.com**'.
    - By inspecting the file contents of the HTTP packet, from Question 15, we were able to identify the primary domain that 'thesimpsons.com' is being directed to.

![Inspector Packet - http response - site redirection - close view](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/29c9d33d-c694-4cd4-8301-bfb6e558401d)

**Question 17** ***— What is the status code of packet number 36?***

  + Answer — The status code of packet number 36 is **200**, which indicates a successful response from the server.
    - By examining the Hypertext Transfer Protocol of packet 36, we were able to determine its response status.

![status code of packet 36](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/89bfd580-b7ab-4ad2-983e-f0c59b4253f4)

**Question 18** ***— What is the source port of the original HTTP request?***

  + Answer — The source port of the original HTTP request is **50568**.
    - This falls within the dynamic or ephemeral port range (49152–65535); which typically means it was assigned by the operating system, to facilitate outgoing network communication.

![original HTTP request source port](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/b5a1f31d-decb-4fb4-906d-7e7c0324c573)

**Question 19** ***— What is the primary Name Server (NS) of the website being requested?***

  + Answer — The primary Name Server (NS) of the website being requested is '**ns01.foxinc.com**'.
    - The DNS response, for packet 20, provides us with the authoritative namerservers.

![primary Name Server](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/bc70c283-4d00-4a38-b40d-89ff8585f4f2)

**Question 20** ***— What is the TTL of the A record of the original website requested?***

  + Answer — The time-to-live (TTL) value of the A record of the original website is **600** seconds or 10 minutes.
    - By inspecting packet 19, the response reveals how long the DNS information can be cached by DNS resolvers before it expires.

![TTL of the A record](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/465140d7-1593-4aa9-9dff-9f05042a484e)

**Question 21** ***— In the one SYN/ACK packet, what is the time between this and the previous SYN packet in seconds?***

  + Answer — The time between the SYN/ACK packet (Packet 26) and the previous SYN packet (Packet 25) is **0.026018** seconds.
    - Packet 26 is a SYN/ACK packet, with a timestamp of 0.026018000 seconds.
    - Packet 25 is a SYN packet, with a timestamp of 0.000000000 seconds.
      
*Packet 26 (SYN/ACK)*                                                                                                                                                                                                       
![Packet 26 timestamp - Copy](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/e6b4b8a9-d11d-4c70-97e9-6279bc86be11)

*Packet 25 (SYN)*                                                                                                                                                                                                          
![Packet 25 timestamp - Copy](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/4575d6c7-0a67-4d33-97fa-21c03343eb98)

**Question 22** ***— What is Homer Simpson’s phone number?***

  + Answer — 856.238.2349

**Question 23** ***— Where does Homer want Marge to meet him?***

  + Answer — moes

**Question 24** ***— What is the vendor name of Homer’s NIC?***

  + Answer — intel

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

![OSI Model - detailed](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/52c8b521-e9df-48a3-8763-76b48607975c)                                                                                                
*Image sourced from [FS Community](https://community.fs.com/article/tcpip-vs-osi-whats-the-difference-between-the-two-models.html).*

While today's Internet utilizes the [TCP/IP Model](https://www.geeksforgeeks.org/tcp-ip-model/), the OSI Model can be valuable for troubleshooting network issues. Whether a single user cannot connect their laptop to the Internet, or a website is down for thousands of users, the OSI model helps break down the problem and isolate its source. By pinpointing the specific layer where the issue arises, unnecessary work can be minimized.

### Layer 7 *- Application*

![image](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/b4dcc207-b5ad-4bd9-b7e6-f7abca2829b1)                                                                                                              
*Image sourced from [Cloudflare](https://www.cloudflare.com/learning/ddos/glossary/open-systems-interconnection-model-osi/).*

Also known as the "End User layer", and the only layer that directly interacts with data from the user. It supports software applications; such as web browsers and email clients, in establishing communications and delivering meaningful data to the user. The software applications themselves are not part of the OSI model; they operate within the *end-user environment*, and use the application layer to interact with network resources and services. This layer acts as a gateway for application services to connect to the network and present received information to the user.

#### Functions

  + *Network Virtual Terminal* — allows a user to log into a remote host, and interact with it, as if they were directly connected to it.
  + *File Transfer Access and Management (FTAM)* — allows users to access files stored on a remote host, retrieve files from a remote host, and manage or control files remotely.
  + *Mail Services* — provides email services, enabling users to send and receive email messages across networks.
  + *Directory Services* — provides a distributed database for managing and accessing information about various objects and services in a network.

#### Protocol or Device Use

*Application layer protocols include:*

[TELetype NETwork](https://www.geeksforgeeks.org/introduction-to-telnet/) (TELNET) | [File Transfer Protocol](https://www.geeksforgeeks.org/file-transfer-protocol-ftp-in-application-layer/) (FTP) | [Network File System](https://www.geeksforgeeks.org/network-file-system-nfs/) (NFS) | [Simple Mail Transfer Protocol](https://www.geeksforgeeks.org/simple-mail-transfer-protocol-smtp/) (SMTP) | [Simple Network Management Protocol](https://www.geeksforgeeks.org/simple-network-management-protocol-snmp/) (SNMP) | [Domain Name System](https://www.geeksforgeeks.org/domain-name-system-dns-in-application-layer/) (DNS) | [Dynamic Host Configuration Protocol](https://www.geeksforgeeks.org/dynamic-host-configuration-protocol-dhcp/) (DHCP) | [Hypertext Transfer Protocol / Secured](https://www.geeksforgeeks.org/http-full-form/) (HTTP/HTTPS) | [Internet Relay Chat](https://www.geeksforgeeks.org/internet-relay-chat-irc/) (IRC) | [Post Office Protocol](https://www.geeksforgeeks.org/pop-full-form/) (POP) | [Multipurpose Internet Mail Extension](https://www.geeksforgeeks.org/multipurpose-internet-mail-extension-mime-protocol/) (MIME) | [Secure Shell](https://www.cloudflare.com/learning/access-management/what-is-ssh/#:~:text=(SSH's%20exact%20OSI%20layer%20is,7%2Fapplication%20layer%20protocol.)) (SSH)

### Layer 6 *- Presentation*

![image](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/eead6d60-d268-4bae-bfb8-ff076319c3ff)                                                                                                                
*Image sourced from [Cloudflare](https://www.cloudflare.com/learning/ddos/glossary/open-systems-interconnection-model-osi/).*

Also known as the "Translation layer", the layer that handles data translation, encryption, and compression. It ensures data is formatted properly for applications to use, accommodating different encoding methods between communicating devices. Since devices might be using different encoding methods, layer 6 translates incoming data into a syntax that the receiving device's application layer can understand. 

When communication is encrypted; this layer adds encryption at the sender's end, and decrypts data at the receiver's end to present unencrypted readable information to the application layer. It also compresses data received from the application layer, before passing it to layer 5, reducing the data transfer size and enhancing the speed and efficiency of communication.

#### Functions 

  + *Translation* — performs data translation, ensuring that data formats match the requirements of the receiving application.
    - This can include converting character sets *(e.g., [ASCII](https://www.geeksforgeeks.org/ascii-table/) to [EBCDIC](https://www.ibm.com/docs/en/zos-basic-skills?topic=mainframe-ebcdic-character-set))* or data serialization formats *(e.g., [JSON](https://www.json.org/json-en.html) to [XML](https://support.microsoft.com/en-us/office/xml-for-the-uninitiated-a87d234d-4c2e-4409-9cbc-45e4eb857d44))*.
  + *Encryption and Decryption* — converts plain text data into encrypted ciphertext for transmission. Upon receipt, the layer decrypts the ciphertext back into plain text, making the data readable and usable by the application.
  + *Compression* — reduces the size of data and bandwith usage, minimizing the number of bits that need to be transmitted over the network. Upon receipt, data is decompressed to its original form for use by the application.

#### Protocol or File Format Use

*Presentation layer protocols and file formats include:*

[Joint Photographic Experts Group](https://www.adobe.com/creativecloud/file-types/image/raster/jpeg-file.html) (JPEG) | [Moving Picture Experts Group](https://www.pcmag.com/encyclopedia/term/mpeg) (MPEG) | [Graphics Interchange Format](https://www.adobe.com/creativecloud/file-types/image/raster/gif-file.html) (GIF) | [Hyper Text Markup Language](https://www.freecodecamp.org/news/what-is-html-definition-and-meaning/) (HTML) | [Document file](https://www.pcmag.com/encyclopedia/term/doc-file) (DOC) | [MPEG Audio Layer 3](https://computer.howstuffworks.com/mp3.htm) (MP3) | [Audio Video Interleave](https://cloudinary.com/guides/video-formats/avi-format-should-you-still-use-avi) (AVI) | [Musical Instrument Digital Interface](https://blog.landr.com/what-is-midi/) (MIDI) | [Transport Driver Interface](https://www.komodia.com/tdi) (TDI) | [Transport Layer Security](https://www.cloudflare.com/learning/ssl/transport-layer-security-tls/#:~:text=Transport%20Layer%20Security%2C%20or%20TLS,web%20browsers%20loading%20a%20website.) (TLS) | [Extended Detection and Response](https://www.trendmicro.com/en_in/what-is/xdr.html) (XDR)

### Layer 5 *- Session*

![image](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/f5d54303-8e2b-40be-a5b4-e36cda743589)                                                                                                              
*Image sourced from [Cloudflare](https://www.cloudflare.com/learning/ddos/glossary/open-systems-interconnection-model-osi/).*

The session layer is responsible for establishing, managing, and terminating sessions between applications on different devices. A [session](https://d3fend.mitre.org/dao/artifact/d3f:NetworkSession/) is a dialogue or connection between two communicating systems that allows for data exchange over a network. Layer 5 software is also responsible for authentication and authorization, verifying the identity and permissions of the communicating parties. Additionally, it confirms that the data is delivered.

#### Functions

  + *Session Establishment* — initiates and sets up connections between applications on different devices. It negotiates the rules for communication, such as the duration and synchronization points, and establishes the session context.
  + *Session Maintenance* — manages the communication between applications. This includes controlling data flow, sequencing data packets, and handling interruptions or reconnections.
  + *Session Termination* — terminates sessions, in an orderly manner, when they are no longer needed; by gracefully closing connections, cleaning up allocated resources, and notifying parties of the session's end.
  + *Synchronization* — synchronizes data exchange by setting checkpoints within the data stream; allowing for recovery and retransmission of data, in case of disruptions or errors during transmission.
  + *Dialog Controller* — controls the communication dialogue between applications by determining whether the communication is full-duplex *(both devices can transmit simultaneously)* or half-duplex *(devices take turns transmitting)*.

#### Protocol or Device Use

*Session layer protocols include:*

[AppleTalk Data Stream Protocol](https://developer.apple.com/library/archive/documentation/mac/pdf/Networking/ADSP.pdf) (ADSP) | [AppleTalk Session Protocol](https://developer.apple.com/library/archive/documentation/mac/pdf/Networking/ASP.pdf) (ASP) | [Network Basic Input Output System](https://www.professormesser.com/security-plus/sy0-401/netbios/) (NetBIOS) | [Point-to-Point Tunneling Protocol](https://www.geeksforgeeks.org/pptp-full-form/) (PPTP) | [Real-time Transport Control Protocol](https://www.crazyegg.com/blog/rtp-protocol/) (RTCP) | [Password Authentication Protocol](https://www.geeksforgeeks.org/password-authentication-protocol-pap/) (PAP) | [Internet Storage Name Service](https://docs.netapp.com/us-en/ontap/san-admin/isns-concept.html#what-an-isns-server-does) (iSNS) | [Layer 2 Forwarding Protocol](https://www.geeksforgeeks.org/l2f-fullform/) (L2F) | [Layer 2 Tunnel Protocol](https://www.cisco.com/c/en/us/td/docs/net_mgmt/prime/network/3-8/reference/guide/l2tp.pdf) (L2TP) | [Zone Information Protocol](https://developer.apple.com/library/archive/documentation/mac/pdf/Networking/ZIP.pdf) (ZIP) | [Sockets Direct Protocol](https://network.nvidia.com/pdf/whitepapers/SDPCluster2006.pdf) (SDP) | [Session Control Protocol](https://www.w3.org/Protocols/HTTP-NG/http-ng-scp.html#:~:text=SCP%20is%20a%20simple%20protocol,and%20is%20modelled%20after%20TCP.) (SCP) | [Short Message Peer-to-Peer](https://smpp.org/) (SMPP)

### Layer 4 *- Transport*

![image](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/a69c39c8-3c48-4b6a-a241-f1c8acc8e325)                                                                                                               
*Image sourced from [Cloudflare](https://www.cloudflare.com/learning/ddos/glossary/open-systems-interconnection-model-osi/).*

The transport layer serves as a bridge between the upper layers *(Application, Presentation, and Session)* responsible for user applications, and the lower layers *(Network, Data Link, and Physical)* that handle the actual transmission of data across the network. Its primary function is to ensure reliable, efficient, and orderly delivery of data between end systems. Mechanisms are implemented; such as acknowledgments, sequence numbers, and retransmissions - ensuring that data reaches the destination accurately and in the correct order.

#### Functions

  + *Segmentation and Reassembly* — breaks down data from the upper layers into smaller units called segments for efficient transmission across the network. Upon receipt, it reassembles these segments into the original data.
  + *Service Point Addressing* — accurately delivers messages to the appropriate process by incorporating a type of address known as the service point address or port address within its header.
  + *Flow Control* — mechanisms manage the rate of data transmission between sender and receiver, preventing data overflow and congestion. The flow of data is regulated to match the receiver's processing capabilities.
  + *Multiplexing and Demultiplexing* — multiplexing allows multiple communication streams to be transmitted over a single network connection, while demultiplexing ensures that each stream reaches its intended destination.

#### Protocol or Device Use

*Transport layer protocols include:*

[Transmission Control Protocol](https://www.fortinet.com/resources/cyberglossary/tcp-ip) (TCP) | [User Datagram Protocol](https://www.cloudflare.com/learning/ddos/glossary/user-datagram-protocol-udp/#:~:text=What%20is%20the%20User%20Datagram%20Protocol%20(UDP%2FIP)%3F,connection%20before%20data%20is%20transferred.) (UDP) | [AppleTalk Transaction Protocol]() (ATP) | [Stream Control Transmission Protocol](https://www.ibm.com/docs/en/aix/7.1?topic=protocol-stream-control-transmission) (SCTP) | [Secure Sockets Layer](https://www.ibm.com/docs/en/ibm-http-server/9.0.5?topic=communications-secure-sockets-layer-ssl-protocol) (SSL) | [Transport Layer Security](https://www.cloudflare.com/learning/ssl/transport-layer-security-tls/#:~:text=Transport%20Layer%20Security%2C%20or%20TLS,web%20browsers%20loading%20a%20website.) (TLS)

### Layer 3 *- Network*

![image](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/ac1ac274-3aba-45a9-9487-8e6b407d1f6a)                                                                                                              
*Image sourced from [Cloudflare](https://www.cloudflare.com/learning/ddos/glossary/open-systems-interconnection-model-osi/).*

The network layer facilitates data transfer between different networks. However, when the communicating devices are on the same network, this layer is unnecessary and the data link layer is used instead. The network layer partitions segments, from the transport layer, into smaller units known as [packets](https://www.cloudflare.com/learning/network-layer/what-is-a-packet/) on the sender's device and reassembles them on the receiving end. Additionally, the network layer determines the optimal physical path for data to reach its destination, a process referred to as [routing](https://www.cloudflare.com/learning/network-layer/what-is-routing/).

#### Functions

  + *Routing* — determines the best path for data packets to travel from the source to the destination across interconnected networks. Routing algorithms calculate optimal routes based on factors like network topology, traffic congestion, and quality of service requirements.
  + *Logical Addressing* — assigns logical addresses, such as IP addresses, to devices on the network. These addresses uniquely identify devices and enable routing decisions to be made based on destination addresses.
  + *Fragmentation and Reassembly* — fragment data packets into smaller units for transmission over networks with different maximum transmission unit (MTU) sizes. At the receiving end, these fragments are reassembled into the original data packets.

#### Protocol or Device Use

*Network layer protocols include:*

[Internet Control Message Protocol](https://www.cloudflare.com/learning/ddos/glossary/internet-control-message-protocol-icmp/) (ICMP) | [Internet Group Management Protocol](https://www.geeksforgeeks.org/what-is-igmpinternet-group-management-protocol/) (IGMP) | [Internet Protocol Security](https://www.geeksforgeeks.org/ip-security-ipsec/) (IPsec) | [Distance Vector Multicast Routing Protocol](https://www.ietf.org/proceedings/43/I-D/draft-ietf-idmr-dvmrp-v3-07.txt) (DVMRP) | [Internetwork Packet Exchange](https://www.geeksforgeeks.org/what-is-ipxinternetwork-packet-exchange/) (IPX) | [Routing Information Protocol](https://www.geeksforgeeks.org/routing-information-protocol-rip/) (RIP)

### Layer 2 *- Data Link*

![image](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/c91a2acb-7cc5-4488-bfcc-0894835d0f2a)                                                                                                              
*Image sourced from [Cloudflare](https://www.cloudflare.com/learning/ddos/glossary/open-systems-interconnection-model-osi/).*

The data link layer facilitates data transfer between neighboring network nodes within a [wide area network](https://www.fortinet.com/resources/cyberglossary/wan) (WAN) or on the same [local area network](https://www.cloudflare.com/learning/network-layer/what-is-a-lan/) (LAN) segment. It receives packets from the network layer and divides them into smaller units called [frames](https://www.tutorialspoint.com/the-data-link-layer-frame-and-frame-fields). These data-link frames remain within the boundaries of a local network, as higher-layer functions handle inter-network routing and global addressing. With a focus on delivery, addressing, and media arbitration, the data link layer manages flow control and error handling in [intra-network](https://www.geeksforgeeks.org/difference-between-internet-and-intranet/) communication.

The data link layer is broken into [two distinct sublayers](https://www.tutorialspoint.com/what-are-logical-link-control-llc-and-medium-access-control-mac) - the media access control (MAC) layer and the logical link control (LLC) layer. The MAC layer governs how devices within a network obtain access to the media and authorization to transmit data. The LLC layer is tasked with identifying and encapsulating network layer protocols, while also managing error checking and frame synchronization.

#### Functions

  + *Framing* — divides the stream of data received, from the network layer, into manageable units that can be individually transmitted and acknowledged. 
  + *Physical Addressing* — adds source and destination addresses to the data frames, allowing devices to identify the intended recipients and route data packets to the correct destination.
  + *Error Control* — involves the detection and retransmission of damaged or lost frames; by incorporating, error detection codes, such as [cyclic redundancy checks](https://csrc.nist.gov/glossary/term/cyclic_redundancy_check) (CRC), within the frame trailer.
  + *Flow Control* — mechanisms regulate the flow of data between devices to prevent data loss or congestion; by coordinating the amount of data, that can be sent, before receiving an acknowledgment.
  + *Access Control* — manages access to the physical network medium, ensuring that multiple devices can share the same channel without interfering with each other's transmissions. 

#### Protocol or Device Use

*Data Link layer protocol and device use include:*

[Point-to-Point Protocol](https://www.tutorialspoint.com/point-to-point-protocol-ppp) (PPP) | [wireless LAN](https://standards.ieee.org/beyond-standards/the-evolution-of-wi-fi-technology-and-standards/) (IEEE 802.11) | [Ethernet](https://www.geeksforgeeks.org/what-is-ethernet/) (IEEE 802.3) | [Fiber Distributed Data Interface](https://www.tutorialspoint.com/fiber-distributed-data-interface-fddi) (FDDI) | [Address Resolution Protocol](https://www.fortinet.com/resources/cyberglossary/what-is-arp#:~:text=Address%20Resolution%20Protocol%20(ARP)%20is,%2Darea%20network%20(LAN).) (ARP) | [High-level Data Link Control](https://www.tutorialspoint.com/high-level-data-link-control-hdlc) (HDLC)

### Layer 1 *- Physical*

![image](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/7433bec7-f0b0-4876-9d85-a1e275755e14)                                                                                                               
*Image sourced from [Cloudflare](https://www.cloudflare.com/learning/ddos/glossary/open-systems-interconnection-model-osi/).*

The physical layer is responsible for the actual physical connection between the devices, andserves as a representation of the electrical and physical characteristics of the system. Such as, pin layouts for connectors, operational voltages of electrical cables, specifications for optical fiber cables, and frequencies for wireless devices. The physical layer sends data bits from one device to another, and is responsible for the communication of the unstructured raw data streams over a physical medium.

#### Functions

  + *Bit Synchronization* — also known as clock synchronization or bit-level synchronization, is a process within the physical layer that ensures that the receiver's clock is synchronized with the incoming bit stream from the transmitter, allowing for accurate and reliable data recovery.
  + *Bit Rate Control* — involves regulating the rate at which digital data is transmitted over a communication channel, adjusting the data transmission rate based on channel conditions and network requirements.
  + *Physical Topology* — defines how devices are connected to each other and to the communication medium. [Physical topologies](https://www.geeksforgeeks.org/types-of-network-topology/) range from simple star and bus topologies, to complex mesh and hybrid configurations. The choice of physical topology depends on factors such as scalability, cost, performance, and fault tolerance, with each topology offering unique advantages and trade-offs.

#### Protocol or Device Use

*Physical layer protocol and device use include:*

[Bluetooth Low Energy](https://developerhelp.microchip.com/xwiki/bin/view/applications/ble/introduction/bluetooth-architecture/bluetooth-controller-layer/physical/#:~:text=The%20Bluetooth%C2%AE%20Low%20Energy,services%20to%20the%20link%20layer.) (BLE) | [Digital Subscriber Line](https://www.geeksforgeeks.org/digital-subscriber-line-dsl/) (DSL) | [Repeaters](https://www.tutorialspoint.com/what-are-repeaters-in-computer-network) | [Network Hubs](https://www.geeksforgeeks.org/what-is-network-hub-and-how-it-works/) | [Universal Serial Bus](https://www.geeksforgeeks.org/universal-serial-bus-usb/) (USB) | [Server Message Block](https://learn.microsoft.com/en-us/previous-versions/windows/it-pro/windows-server-2012-r2-and-2012/hh831795(v=ws.11)) (SMB)

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
    - *Step 7* — The frames are transmitted as electrical, optical, or radio signals over a network medium *(e.g., Ethernet cable, fiber optics, or Wi-Fi)* from Harry's device to Hermione's device. **(Layer 1 — Physical)**

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
