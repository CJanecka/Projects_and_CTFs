# iOS Digital Forensics

![portfolio7](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/f051e5f1-4ff3-43b6-8ada-90a37b0488a7)

## Table of Contents

  + [01. Overview](#Overview)
  + [02. Executive Summary](#Executive-Summary)
  + [03. Equipment and Tools](#Equipment-and-Tools)
  + [04. Details of Tracy's iPhone](Details-of-Tracy's-iPhone)
  + [05. Evidence Establishing Personas](#Evidence-Establishing-Personas)
  + [06. Evidence pertaining to the Theft of Valuable Stamps](#Evidence-Pertaining-to-the-Theft-of-Valuable-Stamps)
  + [07. Evidence pertaining to the Defacement of Museum Art](#Evidence-pertaining-to-the-Defacement-of-Museum-Art)
  + [08. Plot Timeline](#Plot-Timeline)
  + [09. Conclusion](#Conclusion)
  + [10. Appendix A: Correspondence Evidence](#Appendix-A-Correspondence-Evidence)
  + [11. Appendix B: WiFi and GPS Location Information](#Appendix-B-WiFi-and-GPS-Location-Information)

## Overview

This project centered on leveraging the Autopsy tool (www.autopsy.com) to conduct a forensic analysis on an Apple iPhone image. The complete case report is provided as a PDF in this GitHub repository titled [Case Report National Gallery DC](https://github.com/CJanecka/Projects_and_CTFs/files/13734026/iOS_Forensics_Report_Collin_Janecka.pdf). This README file encapsulates the details of our involvement. Operating in the capacity of investigators under the guise of 'Digitech, Inc.' we were tasked to investigate a conspiracy aimed at stealing valuable collectible stamps from Washington, DC's National Gallery. A forensic image extracted from an iPhone was provided; from this image, evidence was gathered to support the criminal investigation.

## Executive Summary

On January 21, 2016, Digitech Inc. was called in to assist the National Gallery, Washington D.C. (NGDC) case involving the conspiracy associated with the theft of valuable stamps and defacing of museums are at the NGDC. 

  + Tracy is a suspect in the aforementioned conspiracy. 
  + As part of the investigation, Tracy’s iPhone was taken into custody. 
  + Digitech, Inc. was tasked with investigating evidence relevant to the aforementioned conspiracy.

Described in further detail with-in the report, the following findings were made: 

  + Evidence shows that Tracy and her brother, Pat, colluded with an unidentified third-party using the alias 'King kthings' and email 'throne1966@hotmail.com' in a plot to steal collectible stamps from the National Gallery.

## Equipment and Tools

I utilized the open-source forensic tool Autopsy, operating on a Kali Linux host, to examinine an image sourced from Tracy's iPhone. This analysis extracted pertinent details and specifications regarding Tracy's mobile device, along with the content of her messages and emails, complete with sender and recipient contacts. Furthermore, my examination uncovered latitude and longitude coordinates, indicative of the precise geographic locations to which Tracy's phone had communicated during the relevant timeframe.

To verify Tracy's presence at the museum during the heist, I cross-referenced the coordinates using an online resource and tool, specifically [Google Maps](https://www.google.com/maps). This process allowed for the precise determination of Tracy's location, providing compelling evidence that she was indeed situated at the museum during the time of the incident.

## Details of Tracy's iPhone

The following details have been extracted from Tracy's iPhone image, providing insights into the device's specifications and data:

![iPhone Details](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/05555a4d-c171-4321-86a4-f1c382f056b5)

## Evidence Establishing Personas

This data serves as a foundational element for identifying the primary individuals connected to the case, their contact information, and their affiliations with the defendant, Tracy. These data points play a central role in facilitating a more comprehensive investigation and deeper understanding of the case.

  + Tracy:
    - Phone Number:	(703) 340-9961
    - Email:			tracysumtwelve@gmail.com
    - Work Email:		tracy.sumtwelve@nationalgallerydc.org
    - Relationship:		Accused

  + Pat:
    - Phone Number: 	(571) 308-3236	
    - Email:			perrypatsum@yahoo.com & patsumtwelve@gmail.com
    - Relationship: 		Tracy’s Brother

  + Terry:
    - Phone Number:	(703) 829-6071
    - Email:			Unknown
    - Relationship:		Tracy & Joe’s Daughter

  + Joe:
    - Phone Number:	Unknown
    - Email:			joe.sum.twelve@gmail.com
    - Relationship:		Tracy's Ex-Husband

  + Carry:
    - Phone Number:	(202) 725-2124
    - Email:			carrysum2012@yahoo.com
    - Relationship:		Tracy's Accomplice & Friend

*Figure 0: Visual representation of personas under investigation*

![image](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/285210fe-6aee-4d7a-bd52-bba900ed2498)

## Evidence pertaining to the Theft of Valuable Stamps

This sub-section provides details regarding the evidence found as it relates to the theft of valuable stamps. 

Emails and SMS messages were exchanged between Tracy, Pat, Carry, and an unidentified co-conspirator known as “King (Kart)” with the email address “throne1966@hotmail.com” (referenced in Appendix A).

Within an email from 'King,' an attachment was included containing a list detailing the items required for the theft.

*Figure 1: Email attachment 'needs.txt' from "King kthings"*

![image](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/5ef73025-24e2-4cf5-9724-50732d42f00a)

An additional piece of evidence includes an attached MP3 audio file labeled as "Crazydave1.mp3". This audio file contains instructions on how to install the VirtualBox Machine (VM) on a host computer with intended use in this crime.

An SMS message was discovered, notifying Tracy of her receipt of a $1000 Target Giftcard. The message included instructions directing her to visit a deceptively named website, specifically “www.target.com.trdt.biz”. On this website, Tracy was prompted to input a numerical code followed by an inquiry regarding the shipping destination. The domain “trdt.biz” is unregistered and lacks any official ownership. Furthermore, the website in question employs the subdomain “www.target.com” in an attempt to obscure its true affiliation, although it is not affiliated with the legitimate Target corporation.

Three (3) PDF email attachments were identified, each of which contained Memoranda of Insurance pertaining to valuable stamps. Additionally, photographic documentation of these stamps was found within the camera storage location, as indicated below. Furthermore, the phone contained photographic representations of each stamp listed in the insurance documents.

*Figure 2: “Stamp insurance 1.pdf” email attachment*

![image](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/203affc5-f42c-4259-b1e6-348721097a31)

  + /vol5/mobile/Media/DCIM/100APPLE/IMG_0056.JPG
  + /vol5/mobile/Media/DCIM/100APPLE/IMG_0051.JPG
  + /vol5/mobile/Media/DCIM/100APPLE/IMG_0057.JPG

*Figure 3: The three (3) stamps mentioned above (Figure 2)*

![image](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/b2daff13-29a1-4c73-8b13-ec95c76004ae)

*Figure 4: “Stamp Insurance 2.pdf” email attachment*

![image](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/fc90aac5-2528-410d-88f3-1990beecef64)

  + /vol5/mobile/Media/DCIM/100APPLE/IMG_0067.JPG
  + /vol5/mobile/Media/DCIM/100APPLE/IMG_0055.JPG
  + /vol5/mobile/Media/DCIM/100APPLE/IMG_0050.JPG

*Figure 5: The three (3) stamps mentioned above (Figure 4)*

![image](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/e7cd2bba-0ca7-4344-82e5-0253c47c1c22)

*Figure 6: “Stamp insurance 3.pdf” email attachment*

![image](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/9fcee37b-8893-49ad-bf71-65e7fd858a4d)

  + /vol5/mobile/Media/DCIM/100APPLE/IMG_0054.JPG
  + /vol5/mobile/Media/DCIM/100APPLE/IMG_0065.JPG
  + /vol5/mobile/Media/DCIM/100APPLE/IMG_0071.JPG

## Evidence pertaining to the Defacement of Museum Art

This sub-section provides details regarding the evidence found as it relates to the defacement of museum art. 

Correspondence between Tracy and Carry, preserved within the email and SMS databases, substantiates Tracy's willingness to assist Carry in surreptitiously introducing a tablet into the museum and circumventing its security measures. Furthermore, these messages provide conclusive evidence that a flash mob was strategically employed as a diversionary tactic to divert the attention of the museum's security personnel during the commission of the heist.

*Figure 8: Email from Carry to Tracy, inquiring about bringing the tablet into the museum. The flash mob was also discussed.*

![image](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/14745afc-701d-4878-8f25-1b93cabc3ec6)

*Figure 9: Texts from Tracy to Carry, saying she will bring the tablet in and a follow-up on the status of the flash mob*

![image](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/ddfb2232-684a-424c-82a9-c7cf4ea2eb81)

## Plot Timeline

For detailed information, refer to Appendix A, found below, and the section labeled 'Evidence pertaining to the Theft of Valuable Stamps' provided above.

  + On Tuesday, June 19, 2012, at 2:38 PM, Pat (perrypatsum@yahoo.com) sent an email to Tracy (coralbluetwo@hotmail.com) with an MP3 audio recording attachment. This attachment contained synthesized voice instructions on the procedure for installing a VirtualBox Virtual Machine (VM) on her computer, purportedly for future use.

  + On Thursday, July 5, 2012, at 6:18:23 PM, Tracy and Carry reached an agreement via SMS to meet at Bubba's Grill.

  + On Friday, July 6, 2012, at 11:49:31 AM, Pat arranged via email, using the subject line "can't pass up", a "proposition" involving an individual identified as "King" (throne1966@hotmail.com) and Tracy.

  + On Friday, July 6, 2012, at 4:27:16 PM, Tracy and Carry confirmed their meeting at Bubba's Grill through SMS communication.

  + On Saturday, July 7, 2012, at 7:36:35 PM, Tracy received an SMS from an unknown number informing her that she had won a Target Gift Card worth $1000. The message instructed her to enter "703" at www.target.com.trdt.biz to specify the shipping destination. It's important to note that the URL appears to mimic Target Corp but is a subdomain of trdt.biz, which is currently unregistered. While it is presumed that this payment was received from Alex, there is no concrete evidence to support this claim.

  + On Monday, July 9, 2012, at 10:44:11 AM,
    
    + Tracy sent herself an email detailing which stamps to steal and their respective insurance values.
      
    + Pat and "King" coordinated via email with a list of things that King would need to accomplish for the job.

  + On Tuesday, July 10, 2012, at 11:24 AM, Pat forwarded the item list to Tracy.

  + On Wednesday, July 11, 2012, at 12:49:08 PM, Carry and Tracy communicated through SMS for Tracy to pick up a tablet from Carry.

  + On Thursday, July 12, 2012, at 5:06:45 PM, Tracy texted Carry to inquire about the progress of the flashmob.

## Conclusion

Evidence found on Tracy’s iPhone indicated the following: 

  + Tracy and Pat engaged in a conspiracy utilizing email account aliases. Specifically, Pat utilized the email alias 'patsumtwelve@gmail.com', whereas Tracy employed the email alias 'coralbluetwo@hotmail.com'. It is pertinent to note that Pat's customary email address is 'perrypatsum@yahoo.com', and Tracy's typical email address is 'tracysumtwelve@gmail.com'.

  + Pat collaborated with an individual known as 'King,' whose email address is 'throne1966@hotmail.com', in a scheme to pilfer valuable stamps. Pat possesses a connection to King's parole officer, affording him the means to exert influence over King's actions in this regard.

  + Tracy coordinated with Carry to facilitate the delivery of a tablet containing information related to a planned flashmob, which Carry intends to organize. The objective of this flashmob is to serve as a distraction for the museum's security personnel while King carries out the theft.

  + Tracy transmit, to her own email account, documentation concerning the stamps; including details regarding their respective insurance valuations.

  + Tracy received a notification regarding the establishment of a 'Gift Card' valued at $1000, which appears to be a form of payment either originating from Carry via Alex or potentially directly from Alex. It's worth noting that the website URL in question has been intentionally designed to resemble an official communication from Target, although it is situated within the trdt.biz domain. As of now, no substantial information is accessible regarding this particular URL.

  + There exist three (3) distinct sets of WIFI and cellular location data; however, the significance of these clusters remains unclear. To establish a meaningful correlation between the location data, its timing, and the email and SMS exchanges, a more comprehensive analysis is warranted.

## Appendix A: Correspondence Evidence

This subsection will provide a breakdown of the email and SMS correspondence evidence found on the iPhone image. 

![TL-01](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/fc88f8ef-28f3-4d4d-8025-87072d63ac31)
![TL-02](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/3638810a-226d-4aac-adc3-0b4ea99c3659)
![TL-03](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/1e8ce655-b3fb-45ce-a249-d9e333ba4cfb)
![TL-04](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/500405c2-852f-477a-9e1b-dda1baf85954)
![TL-05](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/548cbfa3-4476-4f0f-b2b6-7dc2d36a2885)
![TL-06](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/8b7760c6-de3c-4bcb-b711-a3b07a903fd9)
![TL-07](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/3da0bbfa-f5ec-450b-a6ee-5191ad6f5178)

## Appendix B: WiFi and GPS Location Information

WiFi locations gathered from /vol5/root/Library/Caches/locationd/consolidated.db and plotted using "maps.google.com".

*Figure 9: Map of Art Gallery vs iPhone GPS coordinate clusters*

![image](https://github.com/CJanecka/Projects_and_CTFs/assets/131223318/71de5cb1-58ee-43fd-b6e5-56dd7b6a42bb)
