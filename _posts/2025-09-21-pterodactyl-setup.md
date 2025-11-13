---
layout: post
title: "Pterodactyl Setup"
---

This weekend I setup 2 VMs on my cluster. 
One VM is used for the pterodactyl panel and the other is used for the pterodactyl game node. 
Pterodactyl is an open-source game management panel to create and configure multiple game servers in one panel. 
I will be configuring the servers on pve1 with the following ip addresses:

- Pterodactyl Panel: 192.168.20.12
- Pterodactyl Game Node: 192.168.20.13

I have set up multiple game servers already all port-forwarded and people have the ability to connect to them. 
During set up there were a few problems that I came across:

- Issue 1: Initial Hybrid Setup: At first for the game servers I decided to combine SSD for boot and HDD for storage but the problem is that the games filled up the SSD and not the HDD.
My solution was to only use the HDD which also comes with the benefit of easily migrating the VM's and total redundancy.
- Issue 2: Game Server Failed to Start: A game server failed to start up, my process was to look through the boot up logs to find the problem. The problem was that there was a library missing from the server so I simply installed it and it functioned.

After these issues were fixed we were able to fully play each game being hosted. 
