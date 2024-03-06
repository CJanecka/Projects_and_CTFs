# BootCon: Social Engineering with SET

![portfolio9](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/9b60b3fa-bdd4-4b9f-92ea-e61c57b6868d)

## Table of Contents

  + [01. Overview](#Overview)
  + [02. Equipment and Tools](#Equipment-and-Tools)
  + [03. Project Requirements](#Project-Requirements)
  + [04. What is Social Engineering?](#What-is-Social-Engineering?)
    - [a. Key Components](#Key-Components)
    - [b. Potential Targets](#Potential-Targets)
    - [c. Potential Motives](#Potential-Motives)
  + [05. Social Engineering Campaign](#Social-Engineering-Campaign)
    - [a. *Step 1 -* Attack Formulation](#Step-1---Attack-Formulation)
    - [b. *Step 2 -* Information Gathering](#Step-2---Information-Gathering)
    - [c. *Step 3 -* Preparation](#Step-3---Preparation)
    - [d. *Step 4 -* Develop Relationship](#Step-4---Develop-Relationship)
    - [e. *Step 5 -* Exploit Relationship](#Step-5---Exploit-Relationship)
    - [f. *Step 6 -* Debrief](#Step-6---Debrief)
  + [06. The Social Engineering Toolkit](#The-Social-Engineering-Toolkit)
    - [a. Pros and Cons of SET](#Pros-and-Cons-of-SET)
    - [b. Initial Setup](#Initial-Setup)
    - [c. Website Cloning and Credential Harvesting](#Website-Cloning-and-Credential-Harvesting)
    - [d. Phishing Attacks](#Phishing-Attacks)
    - [e. Video Demonstration](#Video-Demonstration)
    - [f. QR Code Attack](#QR-Code-Attack)
  + [07. Mitigations](#Mitigations)

## Overview

<add here>

## Equipment and Tools

The technologies used in this project include:

  + [The Social Engineering Toolkit *(SET)*](https://github.com/trustedsec/social-engineer-toolkit/blob/master/README.md)
  + [Kali Linux](https://github.com/trustedsec/social-engineer-toolkit/blob/master/README.md)
  + [Oracle VirtualBox](https://www.virtualbox.org/)
  + Google Mail *(Gmail)*
  + Open-Source Intelligence *(OSINT)*
  + [Social Engineering Methodology](https://www.ibm.com/topics/social-engineering#How+and+why+social+engineering+works)
  + [OpenAI - ChatGPT](https://openai.com/)
  + [ElevenLabs - Generative Voice AI](https://elevenlabs.io/)
  + [PlayHT - Generative Voice AI](https://play.ht/)

## Project Requirements

The project requirements included:

  + Demonstrating a security tool or security attack.
  + Analyzing the findings and providing recommendations for mitigations.
  + Presenting our findings to the class with a live presentation.

## What is Social Engineering?

Social engineering is a manipulative technique employed by individuals, or groups, to exploit human psychology. The goal is to gain unauthorized access to sensitive information, systems, or physical spaces.  This method entails deceiving or influencing people, leading them to disclose confidential information, perform specific actions, or make decisions that are not in their best interest. The overarching objective is to capitalize on human trust, curiosity, fear, or other emotions as a means to circumvent established security measures.

### Key Components

Key elements of social engineering include:

  + **Psychological Manipulation:** Emotions and cognitive biases and used to influence people. This involves tactics like building trust, exploiting feelings, creating urgency, or appealing to the desire to help, or take actions that are not in their best interests.
   
  + **Impersonation:** The act of pretending to be someone else, in order to gain trust and deceive individuals. Malicious users may impersonate trusted figures, such as coworkers, IT support, or company executives. Exploiting this false identity to manipulate targets. This tactic can occur in various forms; including, in-person, phone calls, or electronic communication.
     
  + **Phishing:** Deceptive digital or voice messages aimed at coercing recipients into divulging sensitive information, downloading malicious software, transferring funds or assets to unintended recipients, or engaging in other detrimental actions. Scammers construct these phishing messages to mimic the appearance or voice of a trusted and credible entity, even individual(s) known personally to the recipient.

    - As AI technology advances, distinguishing these attempts will become increasingly challenging. In under ten (10) minutes, I created the following vishing examples using ChatGPT and a text-to-speech synthesizer:

https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/4603c33f-22f4-490a-86a8-201caf712b92

https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/4cdb4468-1c61-498e-b0bb-e758804aa90a

  + **Pretexting:** Involves a threat actor crafting a deceptive scenario and pretending to be the person who can solve the issue. Ironically, scammers often claim the victim is affected by a security breach, offering to help in exchange for vital account details or control over the victim's device. Almost every social engineering attack includes some form of pretexting.
      
  + **Baiting:** Involves enticing individuals to willingly, or unwittingly, disclose sensitive information or download malicious code; by presenting them with attractive offers or valuable objects.

    - The [Nigerian Prince scam](https://nordvpn.com/blog/nigerian-prince-scam/#:~:text=The%20Nigerian%20Prince%20scam%20is%20a%20phishing%20attack%20when%20swindlers,details%20to%20get%20their%20reward.) stands out as a widely recognized use of this technique. More modern examples utilize seemingly free, but malware-infected; offerings such as games, music, or software downloads. However, some forms of baiting lack subtlety. An example of this involves threat actors strategically placing malware-infected USB drives in locations where unsuspecting individuals discover, pick up, and utilize them simply because they are perceived as "free USB drives".
     
  + **Quid Pro Quo:** Hackers present an enticing good or service, seeking the victim's sensitive information in return. Examples of such schemes include fake contest winnings or seemingly benign loyalty rewards, where individuals are enticed with statements like, "As a token of gratitude for your payment, please accept this special gift".
   
  + **Physical Social Engineering:** Involves manipulating people, in person, to gain access to physical spaces, confidential information, or valuable assets. Unlike online interactions, this tactic relies on face-to-face engagement and exploiting tendencies and behaviors. Social engineers may impersonate authority figures, engage in tailgating, or use baiting techniques physically to deceive and gain trust.
   
### Potential Targets

Social engineering attacks can target individuals, organizations, or even entire systems by manipulating people into divulging sensitive information, performing specific actions, or making decisions that benefit the attacker. 

  + **Individuals:** Often targeted due to the wealth of personal information they possess. Attackers aim to gain access to passwords, social security numbers, and financial details. Identity theft is a common objective, allowing perpetrators to engage in various fraudulent activities, using the stolen personal information.
     
  + **Employees:** Targeted to gain access to sensitive corporate information, trade secrets, or intellectual property. By manipulating individuals into providing network access or acquiring their login credentials, attackers can compromise organizational systems. Employees are often the gateway to valuable corporate assets.
     
  + **Organizations:** Targeted for financial gain, including extortion, fraud, or direct theft of funds. Additionally, attackers may seek to obtain confidential data for resale or to cause reputational damage. Directly impacting an organization's financial and operational integrity.
     
  + **Government Entities:** Often targeted with espionage objectives, where attackers aim to gather classified information or disrupt government operations. Some attacks on government entities are politically motivated, intending to influence decision-making or public perception. This has the potential to directly impact national security and governance.
     
### Potential Motives

The motives behind social engineering attacks vary, and attackers may choose their targets based on different objectives.

  + **Financial Gain:** Serves as a primary motive; where attackers aim to exploit individuals, employees, organizations, or government entities for monetary benefit(s). This may involve tactics like phishing for banking credentials, engaging in identity theft, orchestrating ransomware attacks, or defrauding individuals and government entities. 
      
  + **Espionage:** Adversaries may foucs on individuals, employees, organizations, or government entities; to acquire classified or proprietary data for economic, political, or military advantage. This is frequently driven by nation-state and corporate actors; where attackers aim to gain a competitive edge, or influence geopolitical landscapes, through covert information gathering.
      
  + **Information Manipulation:** The intentional distortion or dissemination of false information to influence *- public opinion, specific outcomes, or perceptions*. This is accomplished by; spreading fake news, creating misleading narratives, or conducting disinformation campaigns. Allowing social engineers to shape narratives and control discourse; or achieve political, social, and economic objectives.
      
  + **Disruption and Sabotage:** The objective is to induce chaos, impede operations, or damage critical infrastructure. Attackers aim to compromise systems, networks, or organizational functions using deceptive tactics, with the goal of disrupting normal operations. This involves intentionally creating instability, sowing discord, or inflicting harm; on individuals, organizations, and even entire sectors.
      
  + **Reputational Damage:** The goal is to tarnish the image or credibility of individuals, organizations, or government entities. Attackers use deceptive tactics to spread false information, expose confidential data, and engage in activities that harm the targeted entity's reputation. The intention is to erode trust, credibility, and public perception, potentially leading to long-lasting and impactful consequences.
      
  + **Political or Ideological:** Attackers aim to advance specific political agendas or promote particular ideologies. Through deceptive tactics, such as spreading propaganda, influencing public opinion, or engaging in cyber operations. Social engineering becomes a means of achieving broader sociopolitical goals through the manipulation of individuals, organizations, or even entire communities.
   
## Social Engineering Campaign

This is what a typical social engineering campaign looks like:

![Slide 4 v2](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/99c23393-5803-4d90-9306-1742701349c6)

### *Step 1 -* Attack Formulation

  + **Goal Identification:** Clearly define the goals of the social engineering campaign; whether it be, obtaining sensitive information, gaining unauthorized access, or influencing specific behaviors. Clearly identified goals serve as a guiding force, directing the subsequent steps of the campaign.
   
  + **Target Identification:** Once the goals are established, the focus shifts to identifying the target(s) – individuals, systems, or entities that possess the information or access needed to fulfill the predefined objectives. Effectively identifying targets streamlines the campaign's efforts, enabling a more precise and strategic execution.

### *Step 2 -* Information Gathering

  + **Identify Potential Sources**: Take note of sources that could provide valuable insights or vulnerabilities related to the campaign's goals. This may include exploring online platforms, databases, or other sources to compile a list of targets or resources that could be leveraged in the subsequent stages of the campaign.
    
  + **Gather Info from Sources**: With potential sources identified, the next objective is to collect information from these sources. The purpose is to build profiles of the targets, understanding their behaviors, preferences, and potential weaknesses. Information gathered may include personal details, digital footprints, or patterns of behavior.
    
  + **Assess Gathered Information**: Extract actionable insights that can inform the development of a targeted and effective social engineering strategy. This includes identifying potential attack vectors, understanding the operational environment, and evaluating the strengths and weaknesses of the target(s).

### *Step 3 -* Preparation

  + **Combination & Analysis of Gathered Info**: Combine and analyze the information gathered in the previous stages. The purpose is to formulate a better understanding of the target(s), their vulnerabilities, and the operational environment. By combining data from various sources, we gain insights that guide the subsequent steps of the campaign.
    
  + **Developing an Attack Vector**: Create a strategic approach that aligns with the predefined goals. This involves choosing the most effective methods, communication channels, and psychological tactics based on the analyzed information. This serves as the blueprint for the actual execution of the campaign.

  + **Goal Satisfaction**: Establish what would signify success for the campaign. Specify the outcomes that align with the campaign's goals, such as gaining unauthorized access or extracting sensitive information.

### *Step 4 -* Develop Relationship

  + **Establish Communication**: Initial contact to establish a connection with the target, that goes beyond a mere transaction. The key is to create a non-intrusive and seemingly benign channel through which the relationship can be cultivated. This could take various forms; such as, direct messages,  making phone calls, or using other communication channels.
    
  + **Rapport Building**: Once communication is established; build a connection that aids in garnering the trust of the target, rendering them more susceptible to manipulation. This could involve engaging in friendly conversations, finding common interests, and creating a sense of familiarity.

### *Step 5 -* Exploit Relationship

  + **Prime the Target**:  Utilize the established relationship to subtly shape the target's thoughts, perceptions, or behavior. This includes strategically planting seeds or cues designed to make the target more receptive to the upcoming request; preparing them for a desired response without arousing suspicion.
      
  + **Citation**: Reference specific details or information gathered during the *Relationship Building* phase to convince the target that you have genuine knowledge and authority. This can include recalling names, events, or preferences discussed previously. This capitalizes on the trust established, increasing the likelihood of compliance.

### *Step 6 -* Debrief

  + **Maintenance**: Sustain the manipulated relationship over an extended period by keeping the target engaged and the rapport intact. This can involve periodic check-ins, updates, or casual conversations to reinforce the connection. 
    
  + **Transition**: Conclude the engagement without raising suspicion or leaving traces. It's crucial to exit the relationship strategically, ensuring minimal risk of discovery.

## The Social Engineer Toolkit

The [Social-Engineer Toolkit (SET)](https://github.com/trustedsec/social-engineer-toolkit) is an open-source penetration testing framework crafted for social engineering purposes. It comes preinstalled by default on Kali Linux, and was developed by TrustedSec, LLC - an information security consulting firm based in Cleveland, Ohio. SET includes multiple custom attack vectors, providing the capability to swiftly craft and launch believable attacks. This software is exclusively designed for testing and is permissible only in instances where explicit consent has been granted.

*The SET Welcome Dashboard on Kali Linux.*                                                                                            
![00_main_page](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/668539cc-8ab0-40c4-a3c3-9315afa2b3ff)

*Social Engineering Attack Options.*                                                                                                      
![01_Social_Engineering_Attack_options](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/a1fd66c3-92f7-4238-81aa-a3db368d10b6)

*Penetration Testing Attack Options.*                                                                                                                  
![02_Penetration_Testing_Fast_Track_Attack_options](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/01f3dd3f-14a1-4714-a810-f3190909ea98)

### Pros and Cons of SET

  + ***Pros***:
    - **Versatility**: A diverse selection of specialized tools is available, & designed to address specific needs.
    - **User-Friendly Interface**: Provides a menu-driven, user-friendly interface making it widely accessible.
    - **Community Support**: With 2+ million downloads, SET has a strong user-base & community support.
    - **Educational Value**: Can be used for educational purposes, helping to better understand social engineering tactics & their mitigations.
    - **Open Source**: SET is freely available, and its code can be inspected & modified by users, contributing to transparency & trust.
   
  + ***Cons***:
    - **Legal & Ethical Concerns**: Using SET for malicious purposes is unethical, unauthorized use can result in criminal charges. 
    - **Risk of Data Misuse**: Harvested data can be used for further malicious activities.
    - **Bugs**: Often froze or got stuck on processes, requiring application relaunch for the toolkit to properly function.
    - **Prior Knowledge Needed**: A good understanding of social engineering, networking, & cybersecurity principles are necessary in order to use this application effectively.
    - **Platform Specific**: Primarily designed for Linux distributions. A less straightforward set-up is needed for macOS configurations.

Balancing the benefits with these considerations is crucial for ethical, and effective, utilization of the Social Engineer Toolkit.

### Initial Setup

To establish a secure testing environment and mitigate any potential adverse effects on our personal systems, my team employed [Oracle VirtualBox](https://www.virtualbox.org/wiki/Downloads). This virtualization tool offers the flexibility to run various operating systems, and for this project we chose [Kali Linux](https://www.kali.org/). The Social Engineer Toolkit is integrated into Kali, being among the pre-installed tools on this operating system. For a better understanding of Virtual Machines (VMs), and guidance on the setup of different operating systems, I recommend watching [NetworkChuck's YouTube video](https://youtu.be/wX75Z-4MEoM?si=eU4TRx4yWV-k9sDN) on the subject.

Prior to using the Social Engineer Toolkit, we need to give ourselves root-level privileges, if this configuration was not established during the Kali installation process. This can be accomplished easily, by doing the following, in a new command line terminal:

![enable root user on kali - disabled by default](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/e4a3db5e-1c9e-4577-81dc-386b84ec2f14)

Using root privileges:

  + Check the package lists for upgrades and new package installations.
  + Upgrade all installed packages to their latest versions. If new packages are required to satisfy dependencies, of upgraded packages, they will be installed.

Keeping the system up-to-date from the start is essential for establishing a secure, stable, and efficient computing environment. This approach minimizes the risk of security vulnerabilities, and guarantees access to the most recent features and enhancements. To do this, open a new command terminal and run the following:

  + sudo apt update && sudo apt upgrade -y

The "-y" option will automatically answer *yes* to the confirmation prompts during the upgrade process, making it more suitable for unattended or scripted updates where user interaction is not desired. While this option is convenient for automated updates; it should be used judiciously. Specifically avoiding critical systems, production environments, systems with custom configurations, and situations where careful consideration, testing, and security measures are essential. 

After updating the system, proceed to the SET configuration file and enable the Apache server. This enhances attack speed and automatically preserves any captured credentials, even when the utility is closed. While optional, it serves as a means to streamline data collection and run a continuous attack. If disabled, SET will still operate as intended; however, the application must be running, any acquired data will be temporary and overwritten after each use of a SET utility.

*Apache Server Config File - Enabled.*
![Enable Apache Server01](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/ba76a730-689d-4be3-9473-a7745fa89a03)

*Aknowledgment prompt to Enable the Listener.*                                                                          
![Enable Apache Server02](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/2c28aa2f-e29a-46c0-932a-2cd9b994cf75)

While there are additional configurations available within the Social Engineer Toolkit, those were not employed in this instance. The alterations made were sufficient for the objectives of this project.

### Website Cloning and Credential Harvesting

Cloning a webpage serves as a deceptive technique, creating a replica of a legitimate website, with the intention of tricking users into interacting with it. The goal is to harvest sensitive information such as usernames and passwords. By going into *Social-Engineering Attacks* from the main menu, and selecting the *Credential Harvester Attack Method*, we are able to clone a range of websites successfully. 

The *Credential Harvester Attack Method* presents three (3) options:

![cred harvester options](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/220ddda4-2445-4552-8d8d-dc8429ca9813)

The *Templates* option comes with a set of default pages, but these tend to be outdated. The *Cloner* feature mirrors a site and searches for form fields to rewrite. However, if the POST fields deviate from the usual methods for posting forms, this method may fail. In such cases, save the HTML of the targeted webpage, modify the forms into standard format(s), and then use the *Import* feature for successful replication. 

When utilizing an external IP address, input the external IP rather than the NAT address.  It's crucial to establish port forwarding from the external IP to the NAT IP because browsers cannot directly communicate with private IP addresses. Therefore, specifying an external IP is essential for external access. This is a networking requirement, not an issue specific to *SET*. For the purposes of this project, this step was unnecessary. My team utilized the *Cloner* method to illustrate the ease with which popular websites can be cloned and exploited for harvesting credentials. This method will capture all POST activity from the designated page. 

For optimal credential harvesting, utilize websites that have both the username and password fields available on the same page. The following are examples of this:

*GitHub Login Page | Real vs Clone.*                                                                                                      
![GitHub-login_clone_and_actual_page](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/a3fffecf-42e8-48cf-85c9-5f9518cd0715)

*Chick-fil-A Login Page | Real vs Clone.*
![Chickfila-login03](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/a2c6f144-89dd-4e63-b9d8-d95039a94078)

Differentiating between these is quite straightforward when inspecting the webpages. This intentional design choice serves to emphasize the key differences, and assist in the identification of genuine and malicious links. With some effort and configuration, the cloned website could be enhanced to appear more convincing, increasing the likelihood of deceiving someone into providing their credentials. Even these evident fakes could trick some less intuitive, or tech-savvy, individuals into disclosing their information.

*Captured Data from the Fake GitHub Login.*                                                                                            
![Github-login_txt_file_contents](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/c114754a-6137-4ab6-9995-72875e6d526a)

The credential harvester is now prepared for further use; the choice of attack method depends on the desired target. For the purposes of this project, we continued using GitHub as an example.

### Phishing Attacks

To enhance the effectiveness of a phishing attempt, it's beneficial to have a well-crafted deceptive pretext ready. For example, a pretext for a GitHub email targeting credentials might look like:

![GitHub Pretext](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/71e51b58-ea17-4a5a-8f6b-df8fae718cfd)

A fake link has been strategically embedded among real ones; specifically within the login link, to seem more authentic and increase the likelihood of the recipient clicking on it. The Social Engineer Toolkit leverages its website cloning and credential harvesting capabilities to launch phishing email attacks, through the Spear-Phishing and Mass Mailer menu options.

*Spear-Phishing Menu.*                                                                                                              
![01a_SE_Spearphishing_options](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/36d27d14-3917-4d99-8c3a-d47e6798ac1e)

*Spear-Phishing Payload Options.*                                                                                                    
![mass email attack payloads](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/6f473b83-5f85-423d-9ba6-b71c2921975e)

*Mass Mailer Menu.*                                                                                                                        
![01e_SE_Mass_Mailer_Attack_options](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/0196b44e-a7f0-4990-bd51-c532dad29652)

*Single Email Attack Fields.*                                                                                                            
![mass mailer - single email target](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/cbc88473-bd6a-4589-a241-f4da999df530)

*Mass Email Attack Format Info.*                                                                                                          
![mass mailer - text file of emails](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/d00ae929-b40f-4daf-be86-7e7e4b4c8e39)

The same fields from the *single email attack* are used after uploading the text file containing the target usernames.

### Video Demonstration



### QR Code Attack


## Mitigations

<temp bullet points - placeholder to revise>

  + **Check the URL**: Examine the website's URL carefully. Phishing sites often have misspelled or slightly changed domain names. Watch out for variations, extra words, or different top-level domains *(.com, .net, etc..)*.

  + **Look for HTTPS**: Legitimate websites typically use HTTPS for secure communication. Check for the padlock symbol and "https://" in the URL.

  + **Check the Site/Page Design**: Examine the website's design; legitimate websites have a consistent and professional layout, fonts, and graphics. Check for brand consistency, proper color schemes, and responsive design.

  + **Examine the Email Source and Content**: Check the sender's email address, spoofed emails often have slight variations in the sender's address. Look for grammatical errors, urgent language, or requests for sensitive information. Legitimate organizations usually communicate professionally.

  + **Beware of Unexpected Attachments or Links**: Avoid clicking on unexpected attachments or links. Verify the legitimacy by contacting the sender through official channels.

  + **Examine the Security Certificate**: Check the website's security certificate by clicking on the padlock icon in the address bar. A mismatch or untrusted certificate may indicate a phishing site.

  + **Use Security Software**: Employ reliable antivirus and anti-phishing software to provide an additional layer of protection.

  + **Use Multi-Factor Authentication (MFA)**: Even if a user's password is compromised through phishing or other means, an additional factor (such as a temporary code from a mobile app or a fingerprint) is needed for access.

