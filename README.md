# Building a Home Lab.

## Objective


My goal is to build a personal cybersecurity homelab that simulates real-world environments to practice security hardening, network defense, and incident response. This lab will give me the opportunity to strengthen my hands-on skills with industry tools and technologies while expanding my technical knowledge. By documenting my progress and projects, I can showcase my problem-solving abilities and technical expertise to potential employers.

### Skills Learned

- Virtaulization 
- Advanced understanding of SIEM concepts and practical application.
- Ability to generate and recognize attack signatures and patterns.
- Enhanced knowledge of network protocols and security vulnerabilities.
- Development of critical thinking and problem-solving skills in cybersecurity.

### Tools Used


- VirtualBox
- Windows 11 iso image
- Kali Linux
- Splunk
- Windows Sysmon


## Steps

Part 1 - Setting Up The Virtual Enviornment

- 1. Install VirtualBox:

  Install Virtual Box along with all necessary dependencies to include python core and win-32-api for full functionality.


  <img src="https://github.com/user-attachments/assets/95ad53f0-2b62-4d82-a817-8358f676238f" width="600">

- 2. Install Windows 11 into VirtualBox:

  Download the Windows 11 iso image from a secure source. Configure Windows 11 inside of VirtualBox by paying attention to the available resources of your host system and the requirements of the iso image. 

  
    <img src="https://github.com/user-attachments/assets/13012569-4e51-4bab-a657-5db89ea590a7" width="600">

- 3. Install Kali Linux:

  Download the pre-built Kali Linux virtual machine from the Kali Linux website. Extract the downloaded file using 7-zip. Log-in to Kali Linux.

  <img src="https://github.com/user-attachments/assets/dc4716a7-8e0e-46a9-bcb5-2b2701b46c87" width="600">

- 4. Install Splunk

  Splunk will act as the secuirty informantion and event management (SIEM) tool. This tool will allow me to simulate an enterpirse environment by managing log files for analysis, detect possible secuirty threats, track performance metrics, and generate dashboards/reports for data insights.

  <img src="https://github.com/user-attachments/assets/711f36e1-e849-4771-9130-7bdbca2703c0" width="600">

Part 2 - Simulating an Basic Attack utilizing Kali Linux:

- 1. Network Security:

Ensure that the Kali Linux and Windows virtual machines are in their own internal network and statically assign each IP address. This ensures that each virtual machine has connectivity to each other, but not to the internet; keeping the network as a whole safe from malware.

  <img src="https://github.com/user-attachments/assets/eecd058c-af1e-4219-ad81-3265d4407c67" width="600">

  <img src="https://github.com/user-attachments/assets/3f2013ba-b76e-4218-874e-7900e5efec91" width="600">


- 2. Perform a Target Scan:

  Use "nmap -A 'target-IP' -Pn" to perform a comprehensive assessment of the target system. In this scenario, conducting this scan will detect any open ports on the target device.

   <img src="https://github.com/user-attachments/assets/a1b4a9e0-8148-4137-aae9-370c91066c0d" width="600">

- 3. Build the Malware:

  The malware will be constructed using a meterpreter (Metasploit) reverse shell as the payload within the TCP packet communication. This allows for real-time control over the target , bypassing firewalls and antivirus software by running in memory. It enables the attacker to dump credentials, move laterally, exfiltrate data, and maintain persistence without triggering obvious alerts. Use "msfvenom -l payloads" to see all available payloads.

<img src="https://github.com/user-attachments/assets/aa73d9b2-9663-4ab9-baa8-28c75213aa41" width="600">

   -Build the malware using the name of the payload chosen, the IP address of the attacking machine, the file format, and name of the file you want to create. The file will generate the malware that is instructed to connect back to the attacking system. 
                                                                                                                                                               
<img src="https://github.com/user-attachments/assets/9e7132e5-ace2-49d0-898d-9e08f3b0ddce" width="600">
















    
