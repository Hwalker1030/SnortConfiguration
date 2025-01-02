# Snort Configuration
Configuring snort and creating alert rules. Investigating logs.


<h1> Project Overview</h1>
In this project, I configure Network IDS/IPS software, Snort, onto a Ubuntu Server hosted by AWS. I created custom alerts and generated logs pinging the server with my Kali Linux VM. This was very fun to test out and very educational. Not only was I able to learn how to configure this software, I was also able to get in some Linux training. 



I started this project creating a virtual cloud network within Amazon Web Service. I installed a Ubuntu VM and went straight to the console. 

I installed Snort using the command:
sudo apt-get install snort -y

I went ahead and made a back up of the snort configuration files incase I needed to back track. I also edited the ip var to get snort working on my virtual network in the snort config files. 

I wanted to create some custom rules instead of the already configured rules in the snort configuration file just to get a blank slate and see how the custom rules work.

![Screenshot 2025-01-01 063650](https://github.com/user-attachments/assets/9b96fb98-8cae-4058-91f6-30cf816a9aed)

That being said, I edited the snort rules page using nano command.


![Custom rules config file](https://github.com/user-attachments/assets/5cf7dd69-1a95-4a61-9e11-83200531c7ff)

I created an alert that will notify when an ICMP packet intiates a request to the server. 

![ICMP fixed rule](https://github.com/user-attachments/assets/b2525c39-37c1-4a8c-a18e-366d609eeceb)


ONE PROBLEM I RAN INTO while testing out snort on the virtual network was that the AWS security rules blocked inbound ICMP traffic. I had to go into the security rules and allow that traffic to enter the network, for testing purposes. I was wondering why I wasn't getting alerted when my attacker machine was dropping the request. 

![OPEN PORTS ON AWS](https://github.com/user-attachments/assets/0f608374-5438-405a-b43e-458315893a83)

After I fixed that mess, I was NOW! generating those alerts. And I had more friends than just my fake attacker machine! :D

![LOG GENERATED](https://github.com/user-attachments/assets/5d72e3eb-9c66-4d36-9d9e-112a36d59f25)

I thought that was interesting to see, I didn't expect seeing more than my Kali Linux IP pings. 

![ICMP IPS](https://github.com/user-attachments/assets/d56e23db-ce59-42d3-8900-17859ee7020a)


That being said, the custom alerts are triggered by the Intrusion Detection System (IDS) based on predefined or dynamically configured rules, enabling the detection of suspicious network activity, potential security breaches, or anomalies. This is one of many tools security analyst use to detect malicious activity on a network. This was fun to set up and inspires me to test out more IDS/IPS software. Not only did I get more Linux experience from conducting this project, I was able to get an hands on experience analyzing network traffic. 




