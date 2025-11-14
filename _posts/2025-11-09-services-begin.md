---
layout: post
title: "Creation of All Services"
---

This week will be the start for all the services that I want to run for my enterprise and personal alike. There are also a few weeks left before the semester ends so I do not have as much time as before but will still make progress towards my learning. 
With that said I have created a plan of what services I need for each side:

- Infrastructure Services:
  1. Portainer CE - To view and manage my containers
  2. Netbox - Used to document the server and network

- DMZ Services:
  1. Nginx Proxy Manager - To make some services face the web

- Untrusted Services:
  1. qBittorrent - For torrenting needs
  2. Pterodactyl Node - Moved once more for added security

- Enterprise Services:
  1. Vaultwarden - Passwords for servers and services in the enterprise
  2. Gitea - Enterprises Personal Github
  3. Nextcloud - Enterprise Personal Cloud
  4. BookStack- Enterprise Wiki  

- Personal Services:
  1. Jellyfin Media Server - For personal storage of media 
  2. Nextcloud - My own personal cloud
  3. Syncthing - Used for my personal Obsidian Vault notetaking
  4. Vaultwarden - Used for my own personal passwords no passwords for enterprise
  5. Pterodactyl Panel - Moved for added security


Instead of creating 1 VM per service I will be running 2 seperate VMs one for the personal services and the other for enterprise and will be using docker to containarize the services. 
In the future I would like to run a kubernetes cluster for my enterprise but at the moment I will setup the basic services for my documentation and entertainment. 
Since I am creating different services with different levels of trust I also need to create new VLANS for my network:

- VLAN 60: Already exists but will be named to Untrusted
- VLAN 80: Personal Services

This is a major change for my network and additions, but it is necessary to ensure that the network is protected from any possible attacks that could occur. The goal is to simulate an enterprise, not just host services. 
The current enterprise structure works as the following:

- The Svatantrata Group - Parent Holding Company
- Vardhana Labs - Infrastructure-as-a-service (Iaas) Provider
- Aegis Security Group - Security-as-a-service (Saas) Provider
- Nexus Services - Personal Services Tenant

My plan for the future is to ensure each company has their own documented pieces and also begin inviting friends to collaborate on the Svatantrata Group project to enhance everyone's learning.

Next week I plan on beginning deploying these services and hopefully fix the Wireguard VPN.
