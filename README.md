### You've made it to the situation room.

Hey there. The homelab is currently down due to a power outage. Unless someone has an urgent need for it, it will be offline until Friday evening when I am back home. I will be posting updates to the das homelab Discord server.

Apologies for the downtime.

\- N

---

## What happened?

My house had a power outage at some point during the day. The homelab has powered *(heh)* through a power outage before, but this time, things did not go to plan. **tiny1**, the node that runs the file server where everything — and I mean ***everything*** — is stored, is supposed to turn on as soon as it has power after an unexpected loss of power, but it did not. This prevented all of the VMs and LXCs that all the individual services, such as Authentik and Gitea, run on from booting. The physical nodes that run the VMs and LXCs via Proxmox, **tiny2** and **tiny3**, booted up just fine, but they couldn't start their VMs. 

The brilliant wannabe sysadmin that I am didn't consider that the proxy I use to manage the homelab runs in an LXC on the Proxmox cluster with its virtual boot drive stored on **tiny1**. I can spin up another connector on another device to give me redundancy, but... I didn't. I will be fixing that this weekend, installing another connector on the Raspberry Pi that is on whenever it has power.

## When should this be resolved?

This weekend. Hopefully, this should have a simple fix. I think I just need to restart the cluster or manually start the VMs and LXCs. 

That's barring any issues though. I am expecting some data loss, as it experienced a sudden loss of power, but the critical services have frequent backups. Hopefully not too much data is lost — hopefully none.

I'll give y'all a biopsy when it's all over.
