# NETWORKWALKS-B084-2YU-WK2-PENATRATION-TESTING-REPORT
Week 2 lab report from my cybersecurity internship at Networkwalks. Covers footprinting a website and scanning my own network with Kali Linux tools and Zenmap.
Week 2 Lab Report: Finding Out What a Website and a Network Give Away

Name: Roopa dhakshitha kakarlapudi
Programme: Cybersecurity internship, Networkwalks IT Solutions & Training
Batch: B084
Date: 12-11-2026
Modules: PENETRATION TESTING

1. Before I started (permission)

I only tested things I was allowed to test. For the website part, Networkwalks gave me permission to look at domain. For the network part, I scanned my own home/student network only. I did not touch anyone else’s devices. This report is for learning, and nothing in it should be used to break into systems that don’t belong to you.

2. What this report is about

This week had two parts. In the first, I played the role of someone who knows nothing about a website and tries to learn as much as possible about it using only public information. In the second, I scanned my own network to see which devices were connected.

Together they show how an attacker usually starts: first collect information, then look for what’s alive on the network. This week was only about looking. I didn’t try to break into anything.

3. Tools I used
Tool	What I used it for
WHOIS	Who registered the domain and when
WhatWeb	What the website is built with
Nslookup	Turning the domain name into an IP address
Curl -I	Reading the hidden “header” info the site sends back
Wafw00f	Checking if a firewall protects the site
DNSRecon	Listing the domain’s DNS records
Zenmap	Finding devices on my network
Command Prompt (ipconfig)	Finding my own IP address and subnet
4. What I did and what I found
Part A: Learning about the website

WHOIS. I ran WHOIS on domain to see the registration details. It showed [registrar, creation/expiry dates, name servers].

WhatWeb. This told me what the site runs on. It found [CMS, version, plugins, server]. 

Nslookup. I used this to find the site’s IP address, which was [IP]. 

Curl -I. This showed the headers the server sends back. I noticed [e.g. server type, any extra technical details, any visible links like /wp-json/]. 

Wafw00f. I checked whether a web firewall was in front of the site. Result: [firewall name, or “none detected”]. 

DNSRecon. This listed the DNS records. I found [name servers, mail servers, TXT/SPF records, anything else]. 

Part B: Scanning my own network

First I ran ipconfig to get my IP address ([your IP]) and subnet . Then I put the subnet into Zenmap and ran a Ping Scan.


5. What these findings could mean

I want to be clear: these are things I noticed, not proven weaknesses. I only gathered information. I didn’t try to exploit anything, so I can’t say the system is vulnerable.

What I noticed	Why it matters	Risk
Website software and version can be seen	Someone could look up known problems for that version	[Low/Medium]
Server IP is easy to find	It shows where the site is hosted	[Low]
Headers show technical details	Gives small clues about how the site is set up	[Low]
Firewall type can be detected	Tells an attacker what protection is in place	[Low]
DNS records are public	They show mail servers and other services	[Low/Medium]
Several devices visible on the network	An unknown device would be easy to miss	[Low/Medium]


6. What I would suggest
Hide what isn’t needed. Check what the website shows about its software and headers, and remove extra details where possible.
Update everything. Keep the CMS, plugins and server software up to date.
Check DNS records now and then. Make sure only the records that are needed are public.
Keep the firewall on and set up properly. A firewall helps, but it needs regular checking.
Scan your own network sometimes. It’s the easiest way to spot a device you don’t recognise.
Keep a list of your devices. Then you know what should and shouldn’t be there.
Always get permission first. Scanning without it can be illegal.

8. What I learned

Before this week, I didn’t realise how much anyone can find out about a website without logging in or breaking anything. A few simple tools gave me the website’s software, its IP, its DNS records and whether it has a firewall.

The scan also showed me how quickly a network can be mapped. I’d never really thought about how many devices were on mine until I saw them in a list.

The other thing I learned is how to write things up. A good report says what I did, what I saw, why it matters and what to do about it. And none of this should ever be done without permission.

8. Evidence
Screenshot 1: WHOIS
Screenshot 2: WhatWeb
Screenshot 3: Nslookup
Screenshot 4: Curl -I
Screenshot 5: Wafw00f
Screenshot 6: DNSRecon
Screenshot 7: ipconfig
Screenshot 8: Zenmap ping scan

