# Building a Home Lab.

## Objective


My goal is to build a personal cybersecurity homelab that simulates real-world environments to practice virtualization.This lab will give me the opportunity to strengthen my hands-on skills with industry tools and technologies while expanding my technical knowledge. By documenting my progress and projects, I can showcase my problem-solving abilities and technical expertise to potential employers. In this case, I will be trying to generate telemetry within the Windows 10 VM to review with Splunk and Sysmon; simulating incident detection.

### Skills Learned

- Virtaulization 
- Advanced understanding of SIEM concepts and practical application.
- Ability to generate and recognize attack signatures and patterns.
- Development of critical thinking and problem-solving skills in cybersecurity.

### Tools Used


- VirtualBox
- Windows 10 iso image
- Kali Linux
- Splunk
- Windows Sysmon


## Steps

Part 1 - Setting Up The Virtual Enviornment

- 1. Install VirtualBox:

  Install Virtual Box along with all necessary dependencies to include python core and win-32-api for full functionality.


  <img src="https://github.com/user-attachments/assets/9e22eed4-6d52-4827-bb1b-b533734b8966" width="600">

- 2. Install Windows 10 into VirtualBox:

  Download the Windows 10 iso image from a secure source. Configure Windows 11 inside of VirtualBox by paying attention to the available resources of your host system and the requirements of the iso image. 

    <img src="https://github.com/user-attachments/assets/64d1e0c4-e7c8-45c7-b8a6-ee0842b012e2" width="600">

- 3. Install Kali Linux:

  Download the pre-built Kali Linux virtual machine from the Kali Linux website. Extract the downloaded file using 7-zip. Log-in to Kali Linux.

  <img src="https://github.com/user-attachments/assets/dc4716a7-8e0e-46a9-bcb5-2b2701b46c87" width="600">

- 4. Install Splunk

  Splunk will act as the secuirty informantion and event management (SIEM) tool. This tool will allow me to simulate an enterpirse environment by managing log files for analysis, detect possible secuirty threats, track performance metrics, and generate dashboards/reports for data insights.

  <img src="https://github.com/user-attachments/assets/d4a58124-c78e-4363-ae65-131655c05785" width="600">

Part 2 - Simulating an Basic Attack utilizing Kali Linux:

- 1. Network Security:

Ensure that the Kali Linux and Windows virtual machines are in their own internal network and statically assign each IP address. This ensures that each virtual machine has connectivity to each other, but not to the internet; keeping the network as a whole safe from malware.


  <img src="https://github.com/user-attachments/assets/2831b50b-d7f7-4fdb-ae0a-5066d6583823" width="600">

  <img src="https://github.com/user-attachments/assets/3f2013ba-b76e-4218-874e-7900e5efec91" width="600">


- 2. Perform a Target Scan:

  Use "nmap -A 'target-IP' -Pn" to perform a comprehensive assessment of the target system. In this scenario, conducting this scan will detect any open ports on the target device.

   <img src="https://github.com/user-attachments/assets/d1c92de2-0452-41ab-9ddf-ac750b1f4d0e" width="600">

- 3. Build the Malware:

  The malware will be constructed using a meterpreter (Metasploit) reverse shell as the payload within the TCP packet communication. This allows for real-time control over the target , bypassing firewalls and antivirus software by running in memory. It enables the attacker to dump credentials, move laterally, exfiltrate data, and maintain persistence without triggering obvious alerts. Use "msfvenom -l payloads" to see all available payloads.

<img src="https://github.com/user-attachments/assets/aa73d9b2-9663-4ab9-baa8-28c75213aa41" width="600">

- 4. Build the malware using the name of the payload chosen, the IP address of the attacking machine, the file format, and name of the file you want to create. The file will generate the malware that is instructed to connect back to the attacking system. 
                                                                                                                                                               
<img src="https://github.com/user-attachments/assets/9e7132e5-ace2-49d0-898d-9e08f3b0ddce" width="600">

- 5. Open Metasploit: 

Use the "msfconsole" command.

<img src="https://github.com/user-attachments/assets/1d1f7c79-84fe-4cc7-ba86-c9c9d91b68f2" width="600">

- 6. Configure the proper payload and IP address for the lhost(attacking machine) and enable the handler so that it can wait for the target to respond.


<img src="https://github.com/user-attachments/assets/d3058024-0b3a-44ca-9372-a865478d6908" width="600">

- 7. Create an HTTP Server:

Set up an HTTP Server using python. The target (Windows VM) is going to access and download the malware through its browser. The allows for a connection back to the attacking machine(Kali Linux).

<img src="https://github.com/user-attachments/assets/61c3c1e1-be10-40d0-8b7d-371b05c853e6" width="600">

Part 3 - Access the Malware from the Target:

- 1. Go the web browser within the Windows VM:

Click and download the malware file previously created to entice the target (Payrollinfo.pdf).
     
<img src="https://github.com/user-attachments/assets/d7f8049c-12d9-4ed5-9c85-c3661b441b1d" width="600">

- 2. Verify Connectivity in Kali Linux:

<img src="https://github.com/user-attachments/assets/a2b2b82f-321e-48dc-b9f6-af1f672bd6f6" width="600">

- 3. Review Splunk:

  Review and analyze the telemetry given within the Windows 10 VM from downloading the malware.


<img src="https://github.com/user-attachments/assets/0365bb7a-d1b5-4e75-9320-0f43ca539b1b" width="600">







    
