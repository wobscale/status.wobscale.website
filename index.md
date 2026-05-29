---
layout: "default"
---

## System status

### Planned maintenance, 2026-05-29 through 2026-05-31

As part of our upcoming data center move, we will be changing the topology of the customer network (209.251.245.0/24 and 2620:fc:c000::/48). This will result in a full outage for approximately 15 minutes sometime this weekend. Please join `#wob` on irc.wobscale.website for up-to-the-minute notices.

After the outage window, there may be maintenance windows in which latency to customers at the Westin Building is abnormally high.

#### Moving current customers

We will be reaching out over the next few weeks to customers that want to continue colocation with Wobscale. We will generally move one or two servers at a time to avoid killing ourselves. You can expect an outage window of a few hours for your server, largely depending on how fucked up your rails are. When we reach out we'll let you know about rate increases.

If you want to end colocation with us, we're happy to return your server in-person in the Seattle area, or you may allow us to keep it for parts. If you'd like a small virtual machine with your server's old IP, iliana can provide one.

#### Technical details for nerds

Our customer network is currently advertised via BGP from our core 1-Gigabit router at the Westin Building. We are also currently advertising test networks via two routers at our new facility at KOMO Plaza. (Yes, two routers! Redundancy! Incredible.)

Our current transit provider, who resells Cogent transit without us having to ever talk to Cogent sales, is ending their contract with Cogent on 2026-05-31. This has given us a hard deadline to actually get our data center move going, or otherwise enter a transit contract in a building we don't want to be in anymore.

We are setting up a Layer 2 tunnel to bridge our Westin Building and KOMO Plaza customer networks. This tunnel will run via our Seattle Internet Exchange ports at each site. At the end of our maintenance, our normal customer network will be advertised by the two KOMO routers, and the current Westin router will be out of service. (The tunnel endpoint on the Westin side will be advertising 2620:fc:c002::/48 to our other router, as well as to the route servers and Hurricane Electric as backups.)

We only have one SIX port at KOMO, which is used by the primary router. Connectivity will still be available if the primary router is down for maintenance, as Hurricane Electric provides free IPv6 transit over internet exchanges. (Thank you, HE!) However, because our new transit provider does not peer directly with HE, non-SIX traffic ends up routing through the San Francisco Bay Area, so latency will be extremely high during these brief windows. We are looking to mitigate this by improving peering.
