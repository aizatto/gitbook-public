---
description: Domain Name System (DNS)
---

# DNS

Also see:

* [VPN](vpn.md)

macOS clear DNS cache. \(macOS 10.10.4 and above\)

Option 1:

```bash
sudo killall -HUP mDNSResponder
```

Option 2:

```bash
dscacheutil -fluscache
```

### Test

```bash
host -t ns aizatto.com
```

