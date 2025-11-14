---
layout: post
title: "Wireguard Peers and UPS Tests"
---

This week I added an additional wireguard peer as well as running a few UPS tests which most failed and some have succeeded. 
For the time being I decided to add my friend's home which is being used as an offsite backup center to my Wireguard peers on his personal machine, laptop and server. 
This process was relatively simple and the current configurations were used:

- Personal Machine: 10.0.0.3
- Laptop: 10.0.0.4
- Server: 10.0.0.5

Until he is able to segment his network this will be the configuration, later on I plan on creating a site to site VPN for our different needs. 
Additionally this weekend I ran multiple non-disruptive and disruptive tests:

- Test 1 - Notification Test: I attempted to figure out if the notifications would be sent to my phone. This was non-disruptive as I only ran commands to simulate a UPS event. This test failed and I did not receive notifications.
- Test 2 - Retest Notifications: After some tweaks I tried again and this time I did receive notification to my phone so now I can connect the Pi to the UPS.
- Test 3 - UPS Test: Now with the UPS connected I ensured only the Pi would ever go down for the test to not disrupt services, but as soon as I connected it to the pi I received multiple battery critical events to my phone.
- Test 4 - Retest UPS: This time I did not receive the spam updates because the servers used so much power the battery had less then 5 minutes left but I also didn't receive any updates at all.
- Test 5 - Retest UPS Again: I figured the issue was a bug with the tools so instead I had a sem-static timer that still used the info on the UPS and gave the critical warning if 4 minutes remained on the battery.
- Test 6 - Full UPS Test: Now I am confident the UPS will work, I powered down all VMs and Services to ensure data would not be corrupted, then I unplugged the UPS from the wall.
At first I did receive the notifications for power cut and power critical but after a minute at critical the UPS shutdown and everything halted. This is not helpful to the situation.
- Test 7 - Retest UPS: The issue was the servers could not reach the Pi and receive the notifications and the Pi did not wait for the servers to power down. After I let the UPS recharge everything fully worked and my whole cluster is now protected from power problems.

There are a lot of reasons I wanted a UPS for my servers. The first is that if the power goes down while the disks are using heavy IOPS then it could corrupt or even destroy the drives. 
I also immediatley wanted a UPS when one time my homes power went off for only 1 second, and my entire room went quiet that 1 second. 
Now I don't have to worry about those issues and everything can run properly.


