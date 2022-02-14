---
layout: "default"
---

## System status

### [MITIGATED] Significant packet loss, starting 2021-02-08

Wob engineers have been debugging a significant packet loss issue that we noticed starting Tuesday, February 8.

We believe the fiber to SIX is the root cause. All SIX peering sessions are down while our colocation provider checks the cable.

All traffic is transiting via Cogent. We recently upgraded this transit to 1 Gbps, so the network should be back to "mostly normal" for everyone.
