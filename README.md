# Personal Homelab

This is my personal homelab server. I like to keep things simple running everything with `docker-compose` for now.
I might migrate to Kubernetes using k3d if I ever decide to scale out.

## Services used

In regards to my personal setup, I like to keep things simple. Below is the list of services I'm currently using.

### Traefik

For accessing all the services contained in my homelab, I route a domain name from Cloudflare to a private IP address
to simplify some work around my local DNS server. Then I use [Traefik](https://doc.traefik.io/traefik/) as my reverse proxy solution for routing based on subdomains.
I migrated to this tool from [Nginx Proxy Manager](https://nginxproxymanager.com) as it offers a more cohesive integration with Docker. Simplifying a lot of my setup.

### Pihole

I originally provisioned [PiHole](https://pi-hole.net) to use it not only as an ad-blocker, but also as my DNS server and advertise to my network all my private subdomains,
but, as mentioned before, this was replaced by Cloudflare private reserved IPs. So this is only living in my server to block ads on a router level. Not the greatest, but it
does the job.

### Portainer

I like to keep an eye from time to time on the containers running in this stack, and for that I started using [Portainer](https://www.portainer.io) a while ago. Who likes
ssh-ing to a server and running `docker compose ps` every time?

### Gluetun VPN client

I configured a VPN client with [Gluetun](https://github.com/qdm12/gluetun) that is provisioned as a custom network mode for Docker compose. That way, I can redirect all the
traffic of any service I deploy through my VPN provider and hide it from my ISP. My current provider is ExpressVPN.

Shameless ad: Use my referral link and we both get 30 days free of [ExpressVPN](https://www.expressrefer.com/refer-a-friend/30-days-free?referrer_id=98613392&utm_campaign=referrals&utm_medium=copy_link&utm_source=referral_dashboard)

### Aria2

This service is conformed by two sub-services, the UI, and the RPC server. Aria2 is a lightweight multi-protocol & multi-source, cross platform download utility.
The RPC service is routed through VPN by default, because I'm not interested in my ISP to know what I download through my network. Nothing illegal, of course, just a matter
of privacy.

### Jellyfin

[Jellyfin](https://jellyfin.org) is an open-source media solution where I host all my rips and backups of DVDs and Blu-Rays. They are quite active and pretty great, so please
consider [donating](https://opencollective.com/jellyfin/donate?interval=oneTime&amount=5&name=&legalName=&email=) a few bucks if you adopt it.

I'll be updating this repo and list over time if I decide to adopt more services. There are some other settings I'm not mentioning here, because they are not concerning to
the repo, such as observability, and local VPN server.


# Legal Disclaimer

The software and documentation contained within this GitHub repository (the "Repository") are provided on an "AS-IS" basis without any warranties or conditions of any kind.

By accessing, downloading, or using the contents of this Repository, you acknowledge that:

* I am not responsible for any unauthorized use or distribution of the content.
* You are solely responsible for ensuring that your use of the content does not infringe on any copyright, trademark, or other rights.
* You release me from all liability in case of any claims related to the Repository.

**USE AT YOUR OWN RISK**

You are free to modify, distribute, and use the content of this Repository in any way you see fit. This includes but is not limited to:

* Commercial or non-commercial purposes
* Creating derivative works
* Distributing copies to anyone you want

The contents of this Repository are licensed under the MIT License (the "License"). To view a copy of the License, visit <https://opensource.org/licenses/MIT>.

By using this Repository, you acknowledge that you have read and agree to be bound by these terms. If you do not agree with any of these terms, please refrain from accessing or using this Repository.
