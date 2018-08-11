---
layout: "default"
---

## Upcoming maintenance windows

### 2018-08-14 from 19:30 PDT to 20:30 PDT

#### Summary

We are performing an upgrade to our router software which will result in a full
loss of network connectivity for an estimated 20 minutes. The window is much
longer to account for the possibility of unexpected issues.

#### Details

SIX has requested us to increase our ARP cache timeout for inter-SIX traffic.

Our router runs OpenBSD, and unfortunately the only way to make this change
includes recompiling the kernel and rebooting into it.

We're taking the opportunity to also upgrade OpenBSD and possibly apply a patch
to allow peering with Google.

## Past incidents

### Upstream carrier maintenance (2017-05-18)

Our upstream carrier, Hurricane Electric, had planned maintenance that we were not notified about.

We are currently reviewing options for a backup transit provider.
