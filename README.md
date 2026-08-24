# KAPALALA CORPORATION - Active Directory

## Project overview
A virtualized hands-on practical windows Sever active directory , with centralized domain controller, managing users, groups, Organization Units(OUs),and computer while ensuring security and Digital Forensic and Incident Response(DFIR)

## Objectives

- Use virtualization to create a Windows Sever Active Directory
- Create a well structured lab architecture
- Create and configure a Domain Controller
- Create users, groups ,Organization Units(OUs) and client computers
- Manage groups and implement Group Policy Objects (GPOs)
- Conduct a controlled real-world cyber attack simulation against the environment
- Investigate and respond to security incidents
- Implement appropriate security controls to prevent future attacks
- Conduct Digital Forensic and Incident Response (DFIR) Investigations
- Document security controls , lessons learned and improvement
- Document investigation findings and provide appropriate recommendations

## Lab Architecture
The lab consists of a virtualized Windows-based corporate environment designed to simulate a small organization's Active Directory Infrastructure

## Core Components

- Kali Linux Physical Host
- Oracle VirtualBox
- Windows Server -  Domain Controller (DC01)
- Windows 11 virtual machines(VMs) - Client computers (PC01 and PC02)
- A kali virtual computer - The attacker/Adversary virtual machine(VM)
- Domain: kapalala.local
- Active Directory Domain Services(AD DS)
- Network - NAT & Internal network
- Security monitoring and investigation tools - Wazuh and Splunk (SIEM)

## Technology and Tools

### Virtualization 
- Oracle VirtualBox
### Operating Systems
- Windows Server 2022
- Windows 11
- Kali Linux
### Identity and Access Management
- Acitve Directory Domain Services(AD DS)
- Group Policy Objects(GPOs)
### Security monitoring and SIEM
- Wazuh
- Splunk
- Mitre Att&ck Framework
### Security and Investigation 
- Windows event logs
- Sysmon
- Kali linux security tools
- Digita Forenscic and Incident Response(DFIR) tools


## Project Milestones - Project construction roadmap

### LEVEL01 - Foundation 
- Set up virtualization environment
- Install Windows Server 2022
- Install Windows 11 client machines
- Install Kali Linux attacker machine
- Configure the virtual network

### LEVEL02 - Active Directory
- Configure DC01 as a Domain Congroller
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
  - Configure Wazuh forsecurity monitoring
  - Configure Splunk for log analysis
  - Collect Windows security events
  - Monitor authentication and system activity
  - Identify suspicious activities and security alerts

  ### LEVEL05 - Attack Simulation
  - Perform controlled attack simulations against the lab enivronment
  - Generate realistic Security events
  - Identify Indicators Of Compromise(IOCs)
  - Map observed activities to the MITREATT&CK framework
 
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

 
    ## Lab Architecture

The lab simulates a small corporate Active Directory environment using virtual machines hosted on a Kali Linux physical host.

```text

<img width="735" height="836" alt="image" src="https://github.com/user-attachments/assets/b6faf89c-6698-4443-a467-858cf7842d75" />

<img width="1024" height="558" alt="image" src="https://github.com/user-attachments/assets/dcaa34a4-0b22-4e45-a82a-057d9ea276bc" />


### Environment Roles

| System    | Role                                          |
| --------- | --------------------------------------------- |
| DC01      | Domain Controller and Active Directory server |
| PC01      | Windows 11 domain client                      |
| PC02      | Windows 11 domain client                      |
| Kali VM   | Attacker/Adversary machine                    |
| Kali Host | Physical host running the virtual environment |



## Network Configuration

The lab uses VirtualBox networking to provide connectivity between the Domain Controller, Windows client virtual machines, and the Kali Linux attacker virtual machine.

### Network Design

* **NAT** — Provides internet connectivity where required
* **Internal Network** — Provides isolated communication between the lab machines
* **Domain Controller (DC01)** — Provides Active Directory and DNS services
* **Windows 11 clients (PC01 and PC02)** — Join the `kapalala.local` domain
* **Kali Linux VM** — Used as the attacker/adversary machine for controlled security testing

### Network Requirements

* All domain members must be able to communicate with DC01
* Windows clients must use the Domain Controller as their DNS server
* The `kapalala.local` domain must resolve correctly
* The attacker machine must be able to reach the systems required for controlled attack simulations
* The internal network should remain isolated from the physical host network where appropriate

### IP Addressing

| System         | Hostname      | IP Address | Role                    |
| -------------- | ------------- | ---------- | ----------------------- |
| Windows Server | DC01          | TBD        | Domain Controller / DNS |
| Windows 11     | PC01          | TBD        | Domain Client           |
| Windows 11     | PC02          | TBD        | Domain Client           |
| Kali Linux     | Kali-ATTACKER | TBD        | Attacker/Adversary      |






