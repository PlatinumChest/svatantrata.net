---
layout: post
title: "The 5-Week Sprint"
---

I did not post last week because I was pushing to finish all my college courses a week early. I had a specific reason for this: I am not using the 5-week winter break to rest. Instead, I am using it to trigger a chain reaction for my lab's evolution and the next 9 months of hard work ahead of me.

For these next 5 weeks, I am executing a "Sprint" to upgrade my home lab into an Enterprise-Grade Datacenter. Here is the battle plan:

### The Weekly Roadmap

**Week 1 (Network Architecture)**
I am abandoning the standard `192.168.x.x` consumer IP space. I have architected a new mapping using the `10.x.x.x` private range to simulate a real datacenter environment.
* **The Schema:** The second octet signifies the **Site ID** (matching the hundreds place of the VLAN).
* **Rings of Trust:** Site ID `0` is Infrastructure Management (Core Control/Ring 0), while Site ID `9` is the Untrusted Zone (Malware/IoT).
* **Scalability:** The third octet matches the VLAN’s tens place, reserved for groups like Servers, Departments, and Clients. This ensures the network can scale logically without collisions.

**Week 2 (Identity & Workload)**
I will deploy two Windows Domain Controllers to establish Active Directory (AD) for my entire simulated conglomerate. I will also focus on automating client deployment for this AD and spinning up core enterprise services.

**Week 3 (Resiliency & Operations)**
Focus on "Day 2" operations: DR-Planning (Disaster Recovery), NUT (Network UPS Tools) configurations for power management, game servers, backups, and personal services.

**Week 4 (Security)**
Hardening the stack. I will implement SSH Key authentication, Zero Trust principles, Principle of Least Privilege (PoLP), and leverage my YubiKey hardware tokens for access control.

**Week 5 (Cloud Hybrid)**
I will move beyond the local network by working on a remote VPS and preparing Cloud-DR strategies.

---

### The Architecture: The Svatantrata Group

To make this lab realistic, I am simulating a corporate conglomerate that starts as a mid-sized company and grows into a global leader. This provides the context for my VLANs and permissions.

**The Svatantrata Group (Parent Company)**
* **Total Headcount:** 45
* **Departments:** C-Suite (5), Legal (5), Finance (15), HR (10), Executive Assistants (10).

**Vardhana Labs (IaaS Provider)**
* **Total Headcount:** 15
* **Departments:** Architecture (2), Sysadmins (5), Network (4), DevOps (4).

**Aegis Security Group (SecaaS)**
* **Total Headcount:** 25
* **Departments:** SOC (12), Offensive Security (5), GRC (5), Forensics (3).

**Nexus Services (Home Services / ISP)**
* **Total Headcount:** 60
* **Departments:** Support (3), Field Ops (6), Management (1), Clients (50).

**Aether Systems (R&D)**
* **Total Headcount:** 100
* **Departments:** Science (20), Engineering (40), Software (20), Fabrication Ops (20).

**Total Simulated Users:** ~245

While I cannot spin up 245 physical clients (yet), I can architect the Directory Structure, Subnets, and Group Policies to support that scale. I am incredibly excited about this 5-week sprint.

Tomorrow, it begins. I am pulling the plug and re-IPing critical services to the new Ring 0 architecture.

I will see you all on the other side.
