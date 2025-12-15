---
layout: post
title: "Week 1 Struggles"
---

### The Goal
This week was supposed to be a routine infrastructure update. My objective was to migrate **Vardhana Lab's** networking scheme from a standard home subnet (`192.168.20.x`) to my new Enterprise Architecture (`10.0.10.x`). On paper, it was a simple configuration change. In reality, it was a masterclass in distributed system fragility.

### The Failure
I prepared the physical layer (switch and router) for the new VLANs, but when I applied the IP changes to the Proxmox nodes, the cluster immediately fractured. I discovered that a "simple IP change" is destructive in a hyper-converged environment for three specific reasons:

1.  **Ceph's Rigid Trust:** Ceph Monitors (MONs) and OSDs map deeply to specific IP addresses. Changing the host IP doesn't just break connectivity; it breaks the cryptographic trust and consensus map that holds the storage together.
2.  **The "Hidden" Configs:** Proxmox relies on Corosync for cluster quorum. Corosync binds to specific interface IPs in files like `/etc/pve/corosync.conf`, which becomes read-only when quorum is lost—creating a "chicken and egg" lock-out scenario.
3.  **Data Recovery Paradox:** Because Ceph stripes data across nodes, you can't just "pull a drive" to recover data. If the cluster map is broken, the raw data on the disks is effectively unintelligible.

### The Recovery
The cluster was unrecoverable. I initiated a **"scorched earth" protocol**: a full wipe and reinstall of Proxmox on all nodes with the new, permanent `10.0.10.x` IP scheme. While I lost the initial configuration, I had no critical data loss thanks to the fresh start.

### Lessons Learned
* **Immutable IPs:** In a Ceph/Proxmox cluster, the management and cluster IPs should be treated as immutable once deployed. Future changes require a new cluster build, not an edit.
* **Backup Gravity:** "Data" is not just files; it's the *configuration*. Future states must include off-site backups of the `/etc` configs and VM dumps, not just reliance on the cluster's health.
* **Documentation vs. Reality:** I underestimated the "stickiness" of the old IPs in the config files.

### Current Status
**Vardhana Labs** is back online. I have used this opportunity to implement better templating. I now have a dedicated network manager VM for my Ubiquiti AP running permanently.

**Next steps:** Rebuilding the OPNsense firewall and deploying the Hybrid AD environment on the new, stable network.
