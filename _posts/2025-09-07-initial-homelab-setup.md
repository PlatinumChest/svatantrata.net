---
layout: post
title: "Initial HomeLab Setup"
---

Now that all the materials I bought have arrived I can begin the full construction of my homelab. 
I will also begin with weekly homelab updates to my blog every Sunday, explaining what is going with my homelab. 
I have configured my network with the following information on VLANS:

- VLAN 10: Management (192.168.10.0/24)
- VLAN 20: Servers (192.168.20.0/24)
- VLAN 30: External (192.168.30.0/24)
- VLAN 40: Guests (192.168.40.0/24)
- VLAN 50 Testing (192.168.50.0/24)
- VLAN 99: Default (192.168.1.0/24)
- 
I have given each server their own ip for management and LAN access on VLAN 20 as follows:

- Proliant 1: 192.168.20.10
- Proliant 1 Management: 192.168.20.11
- Proliant 2: 192.168.20.20
- Proliant 2 Management: 192.168.20.21
- C6100 Node 1: 192.168.20.30
- C6100 Node 1 Management: 192.168.20.31
- C6100 Node 2: 192.168.20.40
- C6100 Node 2 Management: 192.168.20.41
- C6100 Node 3: 192.168.20.50
- C6100 Node 3 Management: 192.168.20.51
- C6100 Node 4: 192.168.20.60
- C6100 Node 4 Management: 192.168.20.61

I have also installed Proxmox VE 9 on all the servers, currently they are unable to talk to each other but next weekend I will finish the base setup for my servers. 
All users of my wifi are able to access the internet and did not experience a downtime larger then 10 minutes.
