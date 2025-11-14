---
layout: post
title: "OPNsense Setup and Struggles"
---

This week was a large change for how I want to run my network, I have decided to go from my Edgerouter-4 router to a virtualized instance of OPNsense on my servers. 
There are a lot of risks involved in this but I have taken the precautions to circumvent them:

- 24/7 Online: A router and modem needs to be on 24/7 for the network to work, I have made my old modem to my room connected to a ups and to ensure the new router is always on the servers are on a ups and will be up 24/7 as all the standard settings are configured as needed.
- Network Speed: My proliants each have 8 ethernet ports so I have allocated 2 for my current OPNsense, one for WAN and one for LAN. I plan on running a future HA setup with my OPNsense router and dedicating more ports but that is for another time.
- Security: With the new router I now have to make sure my network is tightly connected to prevent intrusions.

The reason why I switched was mainly for the firewall support. My old setup did not have a great firewall setup and was difficult to manage. 
With this new router I can implement the principle of least privilege and ensure everything is truly segmented and a great amount of plugins and features I can add on top of everything.
During the new setup I have quite a few problems attempting to create it like:

1. Current Router: I decided to stop having my router on a native 192.168.1.1 place and instead used 192.168.1.2 as the ip and tried to connect and failed.
2. DNS Issues: When I was able to successfully connect I had some problems with DNS. I could ping the server but could not use the web which was bad.

It took time to make the VM and do initial setup, and since I did not have too much time this weekend I went back to the old setup and factory resseted the OPNsense router.
