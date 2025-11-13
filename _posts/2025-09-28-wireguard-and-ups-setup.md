---
layout: post
title: "Wireguard and UPS Setup"
---

This week I have setup a Wireguard VPN for my laptop to my home network as well as setup the Network Utilities Tools Server to monitor the UPS for my servers. 
I decided to use wireguard since it is a lightweight and easily configurable modern VPN for remote to site connections. 
With the UPS monitoring tool I have it so its sends me notifications through ntfy for the following cases and what happens: 

- Power is Cut: A notification is sent to me if I need to vpn in and everything continues running.
- Power is Critical: When there is less then 4 minutes of power let, I am sent a notification and a timer of 60 seconds begins. If the power is not restored before the timer a command is sent to all servers to gracefully power down ensuring nothing becomes corrupted.
- Power is Restored: I get sent a notification and if its restored after the critical event occurs then the servers turns on all the servers with Wake on LAN, so that everything is back up and running.

My wireguard VPN functioned and along with that I setup sunshine on my main desktop. 
What sunshine allows me to do is have a direct stream of my computer to my laptop. 
I chose sunshine over classical models like RDP or VNC because in cases like games typical protocols do not work well for streaming.
