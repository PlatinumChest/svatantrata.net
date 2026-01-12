---
layout: post
title: "Massive Changes"
---
Happy New Year!

For the new year I will be shifting to a bi-weekly posting schedule. This allows me to document larger milestones in detail rather than smaller, fragmented updates. This post covers a major hardware pivot, a full cluster rebuild, and my plans to turn this site into a more comprehensive digital portfolio.

### The 10G Backbone: Arista and Ceph
I have officially moved the lab backbone to 10G. After acquiring an **Arista DCS-7050S-64-R** (48x 10GB SFP+), I installed **Mellanox ConnectX-3** cards and **DAC cables** across my Proxmox nodes. 

Reinstalling the cluster was necessary to properly configure the networking stack for this bandwidth. The impact on **Ceph** has been immediate: storage operations are significantly more responsive, and I no longer see the latency spikes that occurred on the 1G Juniper links during heavy I/O. This provides a stable foundation for **NeuroStore**, where I’ll be fine-tuning storage for AI Vector Databases.

### The New Lab Environment (Cyber Range)
With the clean Proxmox install, I’ve deployed a structured set of VMs designed for both development and security research:
* **Infrastructure:** Ubuntu-based services for core networking and SDN testing.
* **Security & Monitoring:** **Security Onion** for network traffic analysis and **Kali Linux** for internal penetration testing.
* **Legacy/Exploit Testing:** I’ve provisioned **Windows XP** and **Windows 7** instances specifically to test legacy exploits and vulnerability research.
* **Enterprise:** **Windows Server 2022** and **Windows 11** for modern environment simulation.

### Tolteca Systems & Branding
I am officially transitioning all my coding projects to the **Tolteca Systems** brand. This shift moves away from Sanskrit and aligns with my own heritage. While the Tolteca Systems site will eventually be the "friendly" face for my products (like **FluxGPU** and **Project Itzli**), this blog will remain the primary technical repository for my progress.

### Svatantrata.net Site Revisions
I have several plans to upgrade the functionality of this portfolio to make it a true "command center" for my work:
1.  **Network Mappings:** Interactive diagrams of my SDN/VXLAN setups and physical lab topology.
2.  **Media Integration:** A dedicated gallery for photos and videos. I plan to use my **Canon VIXIA HF R80** to capture a "2000s era" aesthetic for my lab vlogs.
3.  **Timeline of Work:** A visual history of my technical progression, from my first server to my current AAS IT degree milestones.
4.  **Live Project To-Do:** A real-time tracker showing the development status of my 5-year project list (e.g., *NetBridge*, *PatchGuard*, *Lazarus*).

Integrating these features will help bridge the gap between my IT infrastructure work and my software development side. More will be added once the next semester begins.
