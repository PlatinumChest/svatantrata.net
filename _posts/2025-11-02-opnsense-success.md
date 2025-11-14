---
layout: post
title: "OPNsense Success!"
---

I decided to retry configuring OPNsense this week and I succeeded. 
The answers to my old problems were relatively simple and with that I created 3 new VLANS and swapped around the others so this is the new VLAN setup:

- VLAN 10 - Management: 192.168.10.0/24 (Desktop and Raspberry Pi)
- VLAN 20 - Servers: 192.168.20.0/24 (Proxmox IP and Management IPs)
- VLAN 30 - External: 192.168.30.0/24 (WiFi and Other Users)
- VLAN 40 - Guest: 192.168.40.0/24 (Guest Users)
- VLAN 50 - DMZ: 192.168.50.0/24 (Publicly Facing Services)
- VLAN 60 - Test: 192.168.60.0/24 (Testing)
- VLAN 70 - Enterprise: 192.168.70.0/24 (For the simulated enterprise) 
- VLAN 100 - Router: 192.168.100.0/24 (For the router)

Most services did not need to move but the pterodactyl panel and server have been moved into the DMZ with the ips 192.168.50.10 and 192.168.50.11 ips respectively. 
I did this since it is bad practice to have my forward facing services and servers on the same VLAN so they have been moved and took some time making sure the configuration and such remained intact. 
In addition the LACP bond on each of my servers is now a trunk port allowing VLAN 20, 50 and 70 on them for next week's setup. 
With that these were the simple solutions to last weeks issues:

- Router IP: With the new VLAN its ip is now 192.168.100.1 and after I recreate the config and basic firewall rules I can do the swap of routers.
- DNS Issues: I realized that with a static ip on network manager I also need to put my own DNS servers and wont automatically take the same settings as the router so that fixed that issue.

With that my new router is setup, which concludes my current network setup and now the base of my entire homelab is stable and can begin on expanding the services.

