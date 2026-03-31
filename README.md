# Wireshark Threat Analysis Lab 

## Objective 

This project simulates a real-world network investigation using Wireshark to identify a compromised host, analyze malicious traffic, determine that type of malware involved. 

## Objectives 
- Identify infected hosts within network traffic
- Analyze suspicious network behavior
- Extract and validate malicious payloads
- Determine malware classification using threat intelligence

## Tools Used 
- WIreshark
- VirusTotal
- PCAP Analysis

## Environment 
- Internal network range: 10.0.0.0/24
- Windows endpoints observed
- Traffic captured via PCAP file

## Investigation Summary 
Affected Users 
- Alyssa Fitzgerald (initial target)
- Elmer O'Brien (infected systems)

## Infected Host 
- IP Address: 10.0.0.167

## Key Indicators of Compromise (IOCs) 
- Unusual outbound connections
- Dowmloads from untrusted domains
- Suspicious SMB activity (ports 445 and 139)
- Evidence of payload execution

Analysis Breakdown 
1. Host Identification
Traffic analysis revealed abnormal behavior from 10.0.0.167, including:
- Repeated outbound connections
- Suspicious file transfer activiy
- Indicates potential compromise
2. User Attribution
  Usernmaes were identified through: 
- SMB authentication traffic
- File-sharing activity
Ports observed:
- TCP 445 (SMB)
- TCP 139 (NetBIOS)
3. Malware Analysis
The suspicious file was extracted and analyzed using VirusTotal
Findings
- Malware Type: Trojan / Backdoor
- Detection Name: Trojan.Generic, Backdoor..Win32
- Indicators: 
- Obfuscated script in attachment
- Command-and-Control (C2) beaconing

## Screenshots 
<img width="519" height="274" alt="Screenshot 2026-03-31 at 4 00 38 PM" src="https://github.com/user-attachments/assets/faeff0a1-8511-4dee-9cd3-7b929b2161d0" />

Screenshot 1 (Usernames + SMB traffic) 
- Screenshot 1: SMB authentication traffic revealing associated user accounts
Network traffic over ports 445 and 139 was analyzed to idetify user activity. This helped attribute the affected systems to Alyssa Fitzgerald and Elmer O'Brien through observed authnetication and file-sharing behavior.

<img width="594" height="379" alt="Screenshot 2026-03-31 at 4 04 10 PM" src="https://github.com/user-attachments/assets/e494735e-0dfc-4b02-9b00-18e770ab345a" />

 Screenshot 2 ( Wireshark packet view / suspicious traffic)
- Screenshot 2: Suspicious network traffic from infected hosts (10.0.0.167)
Packet analysis shows abnormal outbound connections and potential file transfer activity from the infected host, indicating compromise and possible malware communication.

<img width="680" height="456" alt="Screenshot 2026-03-31 at 4 06 59 PM" src="https://github.com/user-attachments/assets/cf33fed0-b538-416e-b62a-9fcfe94a3ceb" />

Screenshot 3 (VirusTotal results) 
- Screenshot 3: VirusTotal analysis confirming Trojan malware classification
The extracted file was analyzed using VirusTotal, where multiple security vendors flagged the file as a Trojan/Backdoor variant, confirming malicious intent and supporting the compromise findings.



Screenshot 4 (Conclusion / evidence summary screen) 
- Screenshot 4: Correlation of investigation findings indetifying attack vectors and infected host.
Combined analysis confirms that host 10.0.0.167 was infected via a malicious email attachment, resulting in Trojan-based comromise and command-and-control (C2) activity. 

## Attack Timeline 
1. User receives malicious email attchment
2. Attachment executed on host 10.0.0.167
3. Malware establishes outbound connection (C2)
4. Suspicious traffic detected in Wireshark
5. Payload extracted and analyzed via VirusTotal 


### Key Takeaways 
- Learned how to identify compromised hosts using network traffic
- Gained experience analyzing SMB and outbound connections
- Improved ability to corrolate traffic with malware behavior 

## Steps 

https://docs.google.com/document/d/19E7zlmnU5pXBIOjmRT2LkzYz-cDMC1QpilqKPOo65nU/edit
