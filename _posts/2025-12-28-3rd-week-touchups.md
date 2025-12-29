---
layout: post
title: "3rd Week Touchups"
---

While I am officially shifting away from the rigid 5-week sprint, I am still utilizing this time to ensure the foundation is fully operational before the next semester begins. The goal is to have a stable, production-ready environment so I can transition from building infrastructure to actually utilizing it for high-level learning.

## Infrastructure & Documentation
This week was heavily focused on the "logical" layer of the lab. I’ve finalized my **Master IP & VLAN Sheet**, which currently tracks approximately 20 VLANs. This number will likely grow as I integrate Active Directory and professional services. Having this level of documentation is critical for the "Clear Box" philosophy I want for my network.

## The Hardware Pivot: Entering the 10G Era
The biggest update is the addition of an **Arista Datacenter Switch**. This allows me to move critical services like **Ceph** onto a dedicated 10G backbone. We are moving away from standard speeds into the realm of microsecond (and even nanosecond) latency. 

To support this, I’ve acquired:
* **Arista Datacenter Switch** (10G/low-latency)
* **DAC (Direct Attach Copper) Cables** for all server nodes
* **High-speed Network Adapters** for the ProLiant and Dell nodes

## New Year’s Mission & Security
As we head into the New Year, my focus will shift to physical installation and hardening. The plan for the coming week includes:
* **Hardware Integration:** Swapping adapters and running DAC cables.
* **Service Deployment:** Provisioning personal/enterprise service nodes and dedicated game nodes.
* **Resilience:** Finalizing **NUT (Network UPS Tools)** configurations.
* **Security:** Enforcing **YubiKey MFA** across all homelab and personal resources to ensure a zero-trust environment.

## The Long Game: Building vs. Maintaining
My ultimate goal for the end of this period is to move from **Constant Construction** to **System Maintenance**. Once the lab is stable, I can finally focus on the other important domains besides just IT:
1. **Advanced Programming** (Python/Go)
2. **Hardware Engineering** (FPGA work)
3. **AI Development** (Project Itzli)
4. **Cybersecurity Concepts** (Red/Blue team labs)

It’s time to stop building the lab and start using it to build the future. **It’s time to get excited, see you next year.**
