# Nmap
Nmap Documentation.

	 Network Scanning & Enumeration Using Nmap

BY: S Aryan Malto

DATE: 19-03-2026

Cybersecurity is an important aspect for organizations trying to secure their networks and systems from security breaches. To make sure the networks and systems are secure companies hire penetration testers who hack through the system and search for exploitable vulnerabilities to fix them. This process in a nutshell is called penetration testing. Scanning and enumeration are two significant phases of a penetration test as it aims to search and identify vulnerabilities throughout the network or system using various tools and techniques. In this article, we are going to deep dive into the scanning and enumeration aspect of a penetration test.
1.	Scanning and Enumeration in Cybersecurity
Scanning and enumeration are two critical activities in cybersecurity that help identify potential security threats and vulnerabilities in a computer network. Scanning is the process of sending requests to a target system to gather information about its network topology, open ports, and running services.
Enumeration is the process of using the information gathered during scanning to identify specific details about a target system, such as its operating system, applications, and user accounts. By combining the information gathered from scanning and enumeration, testers can build a comprehensive profile of a target system, and use this information to develop a strategy for attacking it.
2.	Why network scanning matters
Our network changes all the time. New devices connect, cloud workloads spin up and users add shadow IT without telling anyone. If we don’t actively scan your attack surface, you leave blind spots open for attackers.
Here’s why we need it:
•	Scanning reveals unmanaged devices like personal laptops, rogue wireless access points or forgotten servers.
•	Attackers often scan for open ports to find easy entry points. You can close those doors first.
•	A scan tells you if you’re missing critical patches or security settings are weak.
•	Support compliance requirements like PCI DSS, which mandates regular internal and external vulnerability scans, and HIPAA, which requires continuous risk analysis to protect electronic patient health information.
•	With a clear network map, you can remove unused services, segment networks and harden critical assets.
Without regular scanning, you’re leaving your network security up to chance.
3.	How network scanning works
When you start a network scan, the scanner doesn't just blast packets randomly. It uses a systematic approach to find devices. 
Here's how to scan a network for vulnerabilities:
•	Discovery: The scanner checks which IP addresses respond. It uses techniques like ping sweeps, ARP requests or DNS lookups to find live hosts.
•	OS fingerprinting: It analyzes responses to identify operating systems, running services, software versions and other details.
•	Device enumeration: It digs deeper into open ports, probing services like HTTP, SSH or SMB to gather configuration information.
•	Reporting: It compiles the results into a network inventory map detailing devices, services and potential vulnerabilities.
4.	Active vs. passive network scanning
Conduct an active scan by sending signals to see which devices respond. The downside is it creates extra traffic on your network, so you'll want to plan for it and maybe do it during off-hours.
Do a passive scan, which just listens to the traffic that's already happening on your network. 
It works great when dealing with sensitive systems like factory equipment or hospital networks, where you can't risk disruptions. The catch is that quiet devices might slip by unnoticed.
For the most visibility, combine both approaches.

5.	Types of Scans and Enumerations
Several types of scans and enumerations can be performed during the scanning and enumeration phase of a penetration test. Some of the most common types include:
•	Port Scans:
A port scan is a type of scan that is used to determine which network services and ports are open and available on a target system. This type of scan helps to identify the types of services that are running on the target system and to determine the state of the ports on the target system (open, closed, or filtered). There are several types of port scans, including TCP connect scans, SYN scans, FIN scans, Xmas scans, and Null scans.
•	Version Scans:
A version scan is used to determine the version of software that is running on a target system. This type of scan is useful for identifying known vulnerabilities in the software, as well as for determining which types of exploits are likely to be successful.
•	OS Detection Scans:
An OS detection scan is used to determine the type of operating system that is running on a target system. This type of scan is useful for identifying known vulnerabilities in the operating system, as well as for determining which types of exploits are likely to be successful.
•	Vulnerability Scans:
A vulnerability scan is used to identify known vulnerabilities in software and operating systems that are running on a target system. This type of scan is useful for identifying the potential impact of a vulnerability, as well as for determining the priority for remediation efforts.
•	Network Mapping:
Network mapping is a technique used to create a map of the target system's network, including the systems and services that are running on the network. This type of scan is useful for identifying potential attack vectors, as well as for developing a comprehensive understanding of the target system's network infrastructure.
•	User Enumeration:
User enumeration is a technique used to determine the names of valid users on a target system. This information can be used to mount targeted attacks against specific users or to perform social engineering attacks.
•	System Enumeration:
This involves actively trying to gather information about the target system, such as its operating system, version, and other details.
•	Service Enumeration:
In service enumeration, the attacker actively tries to gather information about the services running on a target system, network, or device, such as the services offered, the versions being used, and other details.


6.	What is Nmap?
Nmap (Network Mapper) is a free, open-source tool for network discovery, security auditing, and port scanning. It allows administrators to identify active devices on a network, detect open ports and services, discover operating systems, and uncover potential security vulnerabilities. It is widely used by cybersecurity professionals. 
Key Features and Capabilities:
•	Port Scanning (-sS, -sT): Identifies open ports on target hosts (TCP and UDP) to see what services are running. 
•	Ping scanning(-sn): Ping scanning (host discovery) is used to find active/live hosts in a network.
•	Host Discovery (-sn): Identifies active devices (live hosts) on a network.
•	Service/Version Detection (-sV): Determines what applications and versions are running on open ports.
•	OS Detection (-o): Identifies the operating system of the target machine.
•	Aggressive Scan (-A): Combines OS detection, version detection, script scanning, and traceroute.
•	Nmap Scripting Engine (NSE) (--script =): Automates advanced tasks, including vulnerability detection and advanced network mapping.
•	Flexibility: Supports various scan techniques to bypass firewalls and filters.
•	GUI & CLI: Available as a command-line tool or through a graphical interface called Zen map.

7.	Installing Nmap on Kali Linux
Kali Linux usually comes with Nmap pre-installed, since it is one of the most commonly used penetration testing tools. However, if it is not installed or you want to update it to the latest version, you can do so with the following commands:
1. Refresh the package index
sudo apt update
2. Install Nmap
sudo apt install nmap -y
3. Confirm the Installation
nmap --version
If installed successfully, you’ll see output similar to:
 


8.	Steps / Procedure
Step 1: Authorization Confirmation
Before starting the scan, proper authorization was confirmed.
Snapshots/backups were taken where virtual machines were involved.
Step 2: Host Discovery (Ping Scan)
Command used:
nmap -sn 18.215.103.147/24
Purpose:
To identify which hosts are active before performing detailed scans. 
 
Host discovery results
Step 3: Port Scanning (TCP SYN Scan)
Command used:
nmap -sS 18.215.103.147
Purpose:
To detect open TCP ports on the target system.
Options like -p or --top-ports 100 can be used for focused scanning.
 
Open ports identified
Step 4: Service and Version Detection
Command used:
nmap -sV 18.215.103.147
Purpose:
To identify services running on open ports along with their version numbers.
 
Service and version details



Step 5: OS Detection and Traceroute
Command used:
nmap -O --traceroute 18.215.103.147
Purpose:
To attempt operating system fingerprinting and determine the network path to the target.
(OS detection may require administrative/root privileges.)
 
OS detection output
Step 6: Aggressive Scan (Authorized Lab Use Only)
Command used:
nmap -A 18.215.103.147
Purpose:
Performs a comprehensive scan including OS detection, service detection, script scanning, and traceroute.
 
Step 7: UDP Scanning (Optional)
Command used:
 nmap -sU -p 53,161 18.215.103.147
Purpose:
To identify open UDP services such as DNS and SNMP.
UDP scans are slower and should be used selectively.
Result
Nmap successfully identified live hosts, open ports, running services, and probable operating system details of the target system.

