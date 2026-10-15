# KAPALALA CORPORATION - Active Directory


## Project overview
A virtualized hands-on practical windows Server Active Directory , with centralized domain controller, managing users, groups, Organization Units (OUs),and client computers while ensuring security and Digital Forensic and Incident Response(DFIR)


## Objectives

- Use virtualization to create a Windows Server Active Directory environment
- Create a well structured lab architecture
- Create and configure a Domain Controller
- Create users, groups ,Organizational Units(OUs) and client computers
- Manage groups and implement Group Policy Objects (GPOs)
- Conduct a controlled real-world cyber attack simulation against the environment
- Investigate and respond to security incidents
- Implement appropriate security controls to prevent future attacks
- Conduct Digital Forensic and Incident Response (DFIR) Investigations
- Document security controls , lessons learned and improvements
- Document investigation findings and provide appropriate recommendations



## Lab Architecture


The lab consists of a virtualized Windows-based corporate environment designed to simulate a small organization's Active Directory Infrastructure

### For a lab with Windows Operating System as the Host Machine the Lab Architecture will be as shown below

<img width="1129" height="1162" alt="image" src="https://github.com/user-attachments/assets/dd0b0974-1821-43b6-910f-33b8ce87e418" />

### For a lab with Kali Linux Operating System as the Host Machine the Lab Architecture will be as shown below

<img width="735" height="836" alt="image" src="https://github.com/user-attachments/assets/b6faf89c-6698-4443-a467-858cf7842d75" /> 

### For a lab with Windows Operating System as the Host Machine the Network Architecture will be as shown below


<img width="919" height="1024" alt="image" src="https://github.com/user-attachments/assets/48cf3af4-d462-4cee-bb57-186e961ad92a" />

### For a lab with Kali Linux Operating System as the Host Machine the Network Architecture will be as shown below

<img width="919" height="1024" alt="image" src="https://github.com/user-attachments/assets/d7dc16d8-2080-4ed3-9d8c-32be11c96dfd" />



### Environment Roles

<img width="1612" height="917" alt="image" src="https://github.com/user-attachments/assets/527019bd-59e3-4b63-8921-b2e71b2c3ecc" />



## Core Components

- Kali Linux Physical Host
- Oracle VirtualBox
- Windows Server -  Domain Controller (DC01)
- Windows 11 virtual machines(VMs) - Client computers (PC01 and PC02)
- A kali virtual machine(VM) - The attacker/Adversary virtual machine(VM)
- Domain: kapalala.local
- Active Directory Domain Services(AD DS)
- Network - NAT & Internal network
- Security monitoring and investigation tools - Wazuh and Splunk (SIEM)


  
## Network Configuration

The lab uses VirtualBox networking to provide connectivity between the Domain Controller, Windows client virtual machines, and the Kali Linux attacker virtual machine.

### Network Design

- NAT(Network Address Translation) — Provides internet connectivity where required
- Internal Network (10.10.10.0/24)— Provides isolated communication between the lab machines
- Domain Controller (DC01) — Provides Active Directory and DNS services
- Windows 11 clients (PC01 and PC02) — Join the `kapalala.local` domain
- Kali Linux VM — Used as the attacker/adversary machine for controlled security testing


  ### Network Diagram


  <img width="1060" height="1148" alt="image" src="https://github.com/user-attachments/assets/e81be2f9-cf49-4b62-aff6-696e1a8af031" />


### Network Requirements

-  All domain members must be able to communicate with DC01
-  Windows clients must use the Domain Controller as their DNS server
-  The `kapalala.local` domain must resolve correctly
-  The attacker machine must be able to reach the systems required for controlled attack simulations
-  The internal network should remain isolated from the physical host network where appropriate

### IP Addressing

<img width="2121" height="771" alt="image" src="https://github.com/user-attachments/assets/f78693d5-1594-4189-8fdc-6623ba37d7fc" />



  

## Technology and Tools


### Virtualization 
- Oracle VirtualBox

  
### Operating Systems
- Windows Server 2022
- Windows 11
- Kali Linux

  
### Identity and Access Management
- Actve Directory Domain Services(AD DS)
- Group Policy Objects(GPOs)

  
### Security monitoring and SIEM
- Wazuh
- Splunk


### Threat Intelligence and Attack Framework
- MITRE ATT&CK Framework


### Security and Investigation 
- Windows event logs
- Sysmon
- Kali linux security tools
- Digita Forenscic and Incident Response(DFIR) tools


## Project Milestones

Project construction roadmap:
The following milestones define the construction and security testing roadmap for the KAPALALA CORPORATION Active Directory lab.


### LEVEL01 - Foundation 
- Set up virtualization environment
- Install Windows Server 2022
- Install Windows 11 client machines
- Install Kali Linux attacker machine
- Configure the virtual network
- Verify connectivity

### LEVEL02 - Active Directory
- Configure DC01 as a Domain Controller
- Create the kapalala.local domain
- Install and configure Active Directory Domain Services(AD DS)
- Create Organization Units(OUs)
- Create users and security groups
- Join Window 11 clients/VMs to the domain

### LEVEL03 - Group Policy and Security
- Implement password and account security policies
- Configure user and computer permissions
- Apply appropriate security controls
- Configure Windows Security auditing
- Deploy and configure Sysmon

### LEVEL04 - Security Monitoring
- Configure Wazuh for security monitoring
- Configure Splunk for log analysis
- Collect Windows security events
- Monitor authentication and system activity
- Identify suspicious activities and security alerts

### LEVEL05 - Attack Simulation
- Perform controlled attack simulations against the lab enivronment
- Generate realistic Security events
- Identify Indicators Of Compromise(IOCs)
- Map observed activities to the MITRE ATT&CK framework
 
### LEVEL06 - Incident Handling and DFIR
- Detect and analyze security incidents
- Perform incident triage
- Collect and preserve relevant evidence
- Investigate Windows artifactcs and event logs
- Perform containment and eradication
- Recover affected systems
- Document findings and lessons learned
 
### LEVEL07 - Final Documentation
- Document the complete lab architecture
- Document attack scenarios and findings
- Document security controls and improvement
- Document DFIR investigations results
- Publish the final project documentation on GitHub

 

## Active Directory Configuration 

The Active Directory environment is built around a Windows Server 2022 Domain Controller named DC01. The Domain Controller provides a centralized authentication , authorization , DNS, and directory management for the kapalala.local domain.

### Domain Controller
- Hostname: DC01
- Operating System: Windows Server 2022
- Role : Domain Controller
- Domain : kapalala.local
- Services : Active Directory Domain Services (AD DS) and DNS

  ### Active Directory Structure
The Active Directory environment is organized using Organization Units (OUs) to provide logical management of users,groups and client computers.

Planned Structure :

kapalala.local domain will consist of (users, groups ,workstations/client computers and security)

### User and Group Management

The lab will include;
- Security groups
- Domain user accounts
- Organizational Units (OUs)
- Group Policy Objects (GPOs)
- Computer accounts for domain-joined clients

### Client Computers

The Windows 11 virtual machines will be joined to the kapalala.local domain

- PC01 - Windows 11 domain client
- PC02 - Windows 11 domain client

### Attacker Machine

The lab includes a dedicated Kali Linux virtual machne that acts as the attacker/adversary system during controlled cyber security attack simulations

Hostname : KALI-ATTACKER
Operating System : Kali Linux
Role : Attacker/Adversary virtual machine
Domain Membership : Not joined to kapalala.local
Network Access : Connected to the lab network for authorized security testing

### Purpose of the Attacker Machine 

- The Kali Linux virtual machine is used to , perform controlled attack simulations against the lab environmentt.
- Generate realistic security events and Indicators of Compromise (IOCs)
- Test Active Directory security controls
- Validate detection and monitoring using Wazuh and Splunk.
- Support Incident Response and Digital Forensics (DFIR) investigations

<img width="2600" height="1083" alt="image" src="https://github.com/user-attachments/assets/cc185f12-17da-4783-84d6-b1c8074a78ca" />
