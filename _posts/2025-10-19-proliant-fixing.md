---
layout: post
title: "Fixing Proliant Fan Issue and 'Overheating' Problems"
---

After a few weeks with my servers my current solution of running a cronjob every 10 minutes was not working the best. 
All my servers but 1 proliant are having the fan issue and with my solution the fan is loud in that reset and sometimes when it fails the fans are loud for 10 minutes straight. 
This is a problem for a few reasons:

- Power Surge: Everytime the fan rises and uses up to a 100 extra watts of power and on a ups this is a problem as it could go over my 900w quota.
- Money: With the extra power means the potential of a higher power bill.
- iLO4: Every reset makes the iLO4 unavailable for around 2 minutes and harder to manage the server with it.
- Noise: A loud noise means my parents are disturbed every 10 minutes or work for 10 minutes and during sleep is very disruptive.

I first checked the logs on iLO4 and in the IML it showed that a a drive had reported an overheated condition during boot.
Checking the temperatures it showed everything well below a critical let alone cautionary level as I had an AC unit to cool down my servers.
Another issue is that proliant 1 showed constant IOPS while proliant 2 showed non with the lights in front and I took a few steps to troubleshoot it:

1. I gracefully shut down all services and made proliant 2 the manager for the ceph cluster.
2. Check the drives physically, one of them was a SHDD hybrid drive so I swapped it out, cleared the logs fully and booted up.
3. Allow for the RAID 1 setup rebuild then boot up.
4. Issue persisted and logs came back so I created a CephFS and backed up all data on RAID 1 to it.
5. Remove RAID 1 setup and disconnect drives.
6. Clear all longs and boot up.
7. Success! The fans are now quiet.
 
It was a relatively simple problem but it took me a while as I currently don't have a Server Rack and it was hard to remove the panel of the server.
I checked the server for anything physical prior to this like fans and such but everything was working.
Thankfully I did not have to risk my servers iLO4 firmware with a custom firmware and instead now the fans on the proliants run at a cool 29% speed going up if the temperature runs high.
Now I have quieter fans which means lower power draws, lower electricity bill, and a happier family.
