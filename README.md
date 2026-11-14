PENETRATION TESTING REPORT<br>
FOOTPRINTING & NETWORK SCANNING PHASES<br>
W2-PM-FINAL | CYBERSECURITY | NETWORKWALKS<br>
.<h1> Liability Disclaimer</h1><br>
I have performed these activities only on the systems & devices where I had secured written permission or the devices/systems that I own myself. All these materials are for education and research purpose only. Do not use anything from here to break the law. The instructor, the authors and Networkwalks are not responsible for what you do with this knowledge. Every action you take is your own responsibility. Misuse can lead to criminal charges, heavy fines, loss of your job and a permanent record. In most countries unauthorised access is a crime even when nothing is damaged.
<h1>2. Introduction</h1>h1>
This report covers footprinting the networkwalks.com domain using multiple Kali Linux tools (W2-PM1) and scanning my own local network with Zenmap (W2-PM5). One module covers the footprinting phase and the other covers the scanning phase, so together they show how an attacker moves from gathering public information to mapping live hosts on a network. It is the Week 2 part of my ongoing internship program at Networkwalks.
All commands were run in Kali Linux (footprinting) and on a Windows PC with Zenmap installed (scanning). Every step below includes the exact command used, the result I observed, a screenshot as evidence, and a short note on why the finding matters from an attacker's point of view.


<h1>3. Tools Used</h1>
Kali Linux & Windows	Operating systems- used for reconnaissance activities<br>
WHOIS	-Find domain registration details (owner, dates, name servers).<br>
Whatweb	-Fingerprint web technologies (server, CMS, plugins, IP).<br>
Nslookup	-Resolve the domain name to its IP address using DNS.<br>
curl -I	-Read the HTTP response headers of the website.<br>
wafw00f	-Detect whether a Web Application Firewall protects the site.<br>
Dnsrecon	-Enumerate all DNS records (NS, MX, SPF, TXT, SRV).<br>
Zenmap (Nmap GUI)	-Scan the local subnet to find live hosts, IPs and MAC addresses.<br>
Windows CMD	-Local IP and MAC address identification<br>

<h1>4. Activities Performed</h1>
4.1 Footprinting & Reconnaissance

I performed reconnaissance against the networkwalks.com domain using six Kali Linux tools: WHOIS, WhatWeb, Nslookup, Curl, Wafw00f and DNSRecon. Each tool was used to collect a different type of information about the target.
First, I used WHOIS to obtain publicly available domain registration information and identify the domain’s name servers. The results provided information about the domain registration and hosting infrastructure.
I then used WhatWeb to identify technologies used by the website. The results identified WordPress 7.0.4 and WP Download Manager 3.3.58, along with other information exposed by the website.
Using Nslookup, I resolved the domain name to its IP address. The provided result identified 192.232.216.135.
I used Curl with the -I option to inspect the HTTP response headers. This provided additional information about the web application and exposed the WordPress REST API endpoint /wp-json/.
Next, I used Wafw00f to determine whether a Web Application Firewall was protecting the website. The result identified ModSecurity (SpiderLabs).
Finally, I used DNSRecon to enumerate DNS records. The results provided information relating to name servers, mail servers, SPF/TXT records, service records and DNS software information.

4.2 Network Scanning with Zenmap
For the second activity, I used Zenmap to perform network discovery on my local network. The practical required me to identify my local IP address and subnet, discover live hosts, identify their IP and MAC addresses, and generate a network topology.
I first used the Windows ipconfig command to identify my local IP address and LAN subnet. I then entered the subnet into Zenmap and selected Ping Scan to identify active hosts.
The example results provided in the practical identified six live hosts:<img width="1920" height="1080" alt="Screenshot (54)" src="https://github.com/user-attachments/assets/d674973d-b122-499a-8b60-b52a1c775964" />
<h1>6. Recommendations</h1>
Based on the observations from these activities, I recommend the following security improvements:<br>
1.	Review publicly exposed technology information<br>
Organizations should regularly review what information about their web technologies, CMS and plugins is publicly visible.<br>
2.	Keep software updated<br>
CMS platforms, plugins and other web technologies should be regularly updated and reviewed against current security advisories.<br>
3.	Review HTTP headers<br>
HTTP response headers should be reviewed to determine whether unnecessary technical information is being exposed.<br>
4.	Review DNS records regularly<br>
DNS records should be checked periodically to ensure that only required information and services are publicly exposed.<br>
5.	Properly configure and monitor the WAF<br>
Keep the WAF (ModSecurity) enabled and tuned, since it already blocks naive attacks.<br>
6.	Perform regular internal network discovery<br>
Organizations should periodically scan their own networks to identify active devices.
7.	Investigate unknown devices<br>
Any unexpected device discovered during network scanning should be investigated and verified.<br>
8.	Maintain network documentation<br>
Network topology and device information should be documented and updated regularly.
9.	Perform security testing with authorization<br>
Reconnaissance and scanning should only be performed against systems and networks where appropriate authorization has been provided.<br>

<h1>7. Conclusion</h1>
During Week 2 of my Cybersecurity & Ethical Hacking internship, I completed practical activities covering footprinting, reconnaissance and network scanning.<br>
In the footprinting activity, I used six Kali Linux tools to collect information about the target domain. I learned how WHOIS can provide domain information, WhatWeb can identify web technologies, Nslookup can resolve domain names, Curl can inspect HTTP headers, Wafw00f can identify a WAF, and DNSRecon can provide additional DNS information.<br>
In the network scanning activity, I used Zenmap to identify my local network configuration and discover active hosts. I also collected IP and MAC address information and created a network topology.<br>
The exercises showed me that information gathering is an important part of cybersecurity. Even before attempting to exploit a system, a security professional can learn a significant amount about an environment by carefully analyzing publicly available information and network responses.<br>
I also learned that technical findings should be documented clearly. A good cybersecurity report should explain what was performed, what was discovered, what the observation means, what risk it may create, and what can be done to reduce that risk.<br>
Finally, I learned that reconnaissance and scanning must always be performed within an authorized scope. These activities were completed as part of the assigned educational cybersecurity lab.
<h1>Evidence collected</h1>

<img width="1920" height="892" alt="Screenshot_2026-11-11_17_03_36" src="https://github.com/user-attachments/assets/6829d28e-baf9-454a-90fe-cbea24286382" />
<img width="1920" height="892" alt="Screenshot_2026-11-11_16_57_24" src="https://github.com/user-attachments/assets/71d02046-d735-4702-90dd-bad3f9529a34" />
<img width="1920" height="892" alt="Screenshot_2026-11-11_16_54_48" src="https://github.com/user-attachments/assets/6225f235-cde6-42b0-a53d-8701199de5a7" />
<img width="1920" height="892" alt="Screenshot_2026-11-11_16_52_16" src="https://github.com/user-attachments/assets/40ad2dcb-59f1-4cbb-9081-e12068a1a8e3" />
<img width="1920" height="892" alt="Screenshot_2026-11-11_16_46_40" src="https://github.com/user-attachments/assets/c556fe2d-516f-4293-a60f-8f9575129d7f" />
<img width="1920" height="892" alt="Screenshot_2026-11-11_16_21_06" src="https://github.com/user-attachments/assets/d88955ab-b004-439d-8e53-ae75befa4286" />

👤 Author
Bosire Brian Nyambane
Cybersecurity Professional B084H
LinkedIn:  https://lnkd.in/p/dD4QRewU
________________________________________
📌 Project Information
Program Name: Cybersecurity program at Networkwalks | Week: 02 | Repository: GitHub


