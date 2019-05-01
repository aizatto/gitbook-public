---
description: Uncomplicated Firewall
---

# ufw

```bash
sudo ufw status
cat /etc/default/ufw
ufo show raw | less
ufo allow 22

ufw allow 60000:61000/udp # mosh
ufw app list
ufw app info mosh
ufw allow mosh
```

