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
    - [g. GitHub Example](#GitHub-Example)
  + [06. Social Engineering Toolkit](#Social-Engineering-Toolkit)
  + [07. Countermeasures](#Countermeasures)
  + [08. Project Improvements](#Project-Improvements)

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

## Project Requirements

The project requirements included:

  + Demonstrating a security tool or security attack.
  + Analyzing the findings and providing recommendations for mitigations.
  + Presenting our findings to the class with a live presentation.

## What is Social Engineering?

Social engineering is a manipulative technique employed by individuals, or groups, to exploit human psychology. The goal is to gain unauthorized access to sensitive information, systems, or physical spaces.  This method entails deceiving or influencing people, leading them to disclose confidential information, perform specific actions, or make decisions that are not in their best interest. The overarching objective is to capitalize on human trust, curiosity, fear, or other emotions as a means to circumvent established security measures.

### Key Components

Key elements of social engineering include:

  + **Psychological Manipulation:** Where attackers use emotions and cognitive biases to influence people. This involves tactics like building trust, exploiting feelings, creating urgency, or appealing to the desire to help.
   
  + **Impersonation:** The act of pretending to be someone else, in order to gain trust and deceive individuals. Attackers may impersonate trusted figures, such as coworkers, IT support, or company executives. Exploiting this false identity to manipulate targets. This tactic can occur in various forms; including, in-person, phone calls, or electronic communication.
     
  + **Phishing:** Employing deceptive emails, messages, or websites to trick individuals into revealing sensitive information. Attackers use various tactics; including, creating fake login pages or posing as trustworthy entities, to lure victims into providing usernames, passwords, or financial details. This tactic plays on human trust and curiosity, exploiting individuals' willingness to interact with a seemingly legitimate communication.
   
  + **Pretexting:** Involves the creation of fabricated scenarios to trick individuals into disclosing information or performing actions. Pretexting emphasizes the manipulation of trust through storytelling, and exploits the target's willingness to assist or provide information.
      
  + **Baiting:** Exploits human curiosity and desire; by enticing individuals, with false promises or tempting offers, leading them into a trap. This tactic can occur both physically and online.
      + ***Physically:*** Strategically placed, malware-infected, flash drives in visible locations. When the flash drive is inserted into a computer, regardless of location, malware is automatically installed on the system.
      + ***Online:*** Through tempting ads directing users to malicious sites or encouraging them to download malware-infected apps.
     
  + **Quid Pro Quo:** Involves the exchange of a service, or benefit, in return for information or access. Social engineers may pose as helpful entities, offering assistance or rewards, such as IT support fixing a non-existent issue. The victim is required to perform a specific action, like providing login credentials, to receive the promised benefit. This tactic leverages the reciprocity principle, exploiting the target's willingness to give in exchange for perceived value. 
     
  + **Reverse Social Engineering:** Victims are manipulated into initiating contact with the attacker. Instead of the attacker reaching out, the victim is deceived into believing they need assistance or protection, establishing a high level of trust. This method exploits the victim's perception that they are the ones seeking help or information, allowing the attacker to subtly influence their decisions or actions.
   
  + **Physical Social Engineering:** Involves manipulating people, in person, to gain access to physical spaces, confidential information, or valuable assets. Unlike online interactions, this tactic relies on face-to-face engagement and exploits human tendencies and behaviors. Social engineers may impersonate authority figures, engage in tailgating, or use baiting techniques physically to deceive and gain trust.
   
### Potential Targets

Social engineering attacks can target individuals, organizations, or even entire systems by manipulating people into divulging sensitive information, performing specific actions, or making decisions that benefit the attacker. 

  + **Individuals:**
    - Often targeted due to the wealth of personal information they possess. Attackers aim to gain access to passwords, social security numbers, and financial details. Identity theft is a common objective, allowing perpetrators to engage in various fraudulent activities, using the stolen personal information.
     
  + **Employees:**
    - Targeted to gain access to sensitive corporate information, trade secrets, or intellectual property. By manipulating individuals into providing network access or acquiring their login credentials, attackers can compromise organizational systems. Employees are often the gateway to valuable corporate assets.
     
  + **Organizations:**
    -  Targeted for financial gain, including extortion, fraud, or direct theft of funds. Additionally, attackers may seek to obtain confidential data for resale or to cause reputational damage. Directly impacting an organization's financial and operational integrity.
     
  + **Government Entities:**
    - Often targeted with espionage objectives, where attackers aim to gather classified information or disrupt government operations. Some attacks on government entities are politically motivated, intending to influence decision-making or public perception. This has the potential to directly impact national security and governance.
     
### Potential Motives

The motives behind social engineering attacks vary, and attackers may choose their targets based on different objectives.

  + **Financial Gain:**
    - Serves as a primary motive; where attackers aim to exploit individuals, employees, organizations, or government entities for monetary benefit(s). This may involve tactics like phishing for banking credentials, engaging in identity theft, orchestrating ransomware attacks, or defrauding individuals and government entities. 
      
  + **Espionage:**
    - Adversaries may foucs on individuals, employees, organizations, or government entities; to acquire classified or proprietary data for economic, political, or military advantage. This is frequently driven by nation-state and corporate actors; where attackers aim to gain a competitive edge, or influence geopolitical landscapes, through covert information gathering.
      
  + **Information Manipulation:**
    - The intentional distortion or dissemination of false information to influence *- public opinion, specific outcomes, or perceptions*. This is accomplished by; spreading fake news, creating misleading narratives, or conducting disinformation campaigns. Allowing social engineers to shape narratives and control discourse; or achieve political, social, and economic objectives.
      
  + **Disruption and Sabotage:**
    - The objective is to induce chaos, impede operations, or damage critical infrastructure. Attackers aim to compromise systems, networks, or organizational functions using deceptive tactics, with the goal of disrupting normal operations. This involves intentionally creating instability, sowing discord, or inflicting harm; on individuals, organizations, and even entire sectors.
      
  + **Reputational Damage:**
    - The goal is to tarnish the image or credibility of individuals, organizations, or government entities. Attackers use deceptive tactics to spread false information, expose confidential data, and engage in activities that harm the targeted entity's reputation. The intention is to erode trust, credibility, and public perception, potentially leading to long-lasting and impactful consequences.
      
  + **Political or Ideological:**
    - Attackers aim to advance specific political agendas or promote particular ideologies. Through deceptive tactics, such as spreading propaganda, influencing public opinion, or engaging in cyber operations. Social engineering becomes a means of achieving broader sociopolitical goals through the manipulation of individuals, organizations, or even entire communities.
   
## Social Engineering Campaign

This is what a typical social engineering campaign looks like.

![Slide 4 v2](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/99c23393-5803-4d90-9306-1742701349c6)

### *Step 1 -* Attack Formulation

  + **Goal Identification:** Clearly define the goals of the social engineering campaign; whether it be, obtaining sensitive information, gaining unauthorized access, or influencing specific behaviors. Clearly identified goals serve as a guiding force, directing the subsequent steps of the campaign.
   
  + **Target Identification:** Once the goals are established, the focus shifts to identifying the targets – individuals, systems, or entities that possess the information or access needed to fulfill the predefined objectives. Effectively identifying targets streamlines the campaign's efforts, enabling a more precise and strategic execution.

### *Step 2 -* Information Gathering

  + **Identify Potential Sources**: Involves research of publicly available information related to the platform. This may include exploring GitHub repositories, tracking open-source projects, and examining user profiles. Clearly identified goals serve as a guiding force, directing the subsequent steps of the campaign and ensuring a focused and purposeful approach.
    
  + **Gather Info from Sources**: By scrutinizing commit histories, analyzing code contributions, and exploring public discussions within the platform. Information gathered from linked accounts or repositories provides insight into the broader digital footprint of the targets.
    
  + **Assess Gathered Information**: Analyze the targets/data to identify potential weaknesses or areas prone to errors. This is critical in determining the most effective approach.

### *Step 3 -* Preparation

  + **Combination & Analysis of Gathered Info**: Pooling togehter and synthesizing insights from different sources. This step aids in creating a profile of the target(s), highlighting their strengths, weaknesses, and potential points of vulnerability. Understanding a GitHub user's coding practices, the nature of their projects, and the dynamics of their interactions within the platform allows allows for a more refined approach.
    
  + **Developing an Attack Vector**: Entails crafting a tailored approach that aligns with the predefined goals of the social engineering attack. For GitHub users, the attack vector could involve creating deceptive communications related to specific projects, leveraging known collaborators, or exploiting trust within contributor networks.

  + **Goal Satisfaction**: By leveraging the obtained information, reassess and redefine the campaign's goals, ensuring a clear understanding of its purpose. The success of the attack hinges on how effectively these goals are met.

### *Step 4 -* Develop Relationship

  + **Establish Communication**: Initial contact to establish a connection with the target, that goes beyond a mere transaction. The key is to create a non-intrusive and seemingly benign channel through which the relationship can be cultivated. This communication could take various forms, such as direct messages, comments on repositories, or engagement in project-related discussions.
    
  + **Rapport Building**: The attacker strategically engages with the target, demonstrating genuine interest in their activities, projects, or coding contributions. By offering positive feedback, asking relevant questions, and showcasing a shared interest in the GitHub community, the attacker aims to create a connection that feels authentic to the target.

### *Step 5 -* Exploit Relationship
### *Step 6 -* Debrief
### GitHub Example
