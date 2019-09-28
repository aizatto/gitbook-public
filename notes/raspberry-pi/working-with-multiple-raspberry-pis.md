---
description: >-
  I've been running multiple Raspberry Pis on my home network, so I thought I'd
  share my best practices
---

# Working with Multiple Raspberry Pis

## Predictable IP Addresses

Set a predictable IP address by either:

1. Setting your DHCP server to assign the IP
2. Setting up a static IP

Suggestions for IP Address: Set the IP Address to the Raspberry Pi Version, for example, this is my home network:

* 192.168.0.3 - Raspberry Pi 3
* 192.168.0.4 - Raspberry Pi 4 ethernet
* 192.168.0.40 - Raspberry Pi 4 wlan

If I get more Raspberry Pis, I may extend to use double digits, for Example:

* 192.168.0.30 - Raspberry Pi 3 \#1
* 192.168.0.31 - Raspberry Pi 3 \#2
* 192.168.0.40 - Raspberry Pi 4 \#1
* 192.168.0.41 - Raspberry Pi 4 \#2
* 192.168.0.42 - Raspberry Pi 4 \#3

## Disable SSH Strict Host Check

If you switch out your SD cards often enough, you may want to disable `StrictHostKeyChecking`. 

Inside `~/.ssh/config`:

```text
Host 192.168.0.10
  StrictHostKeyChecking no
  UserKnownHostsFile=/dev/null
```

## Cache repository requests

Assuming you are using Raspbian.

### Server

```bash
sudo apt install apt-cacher-ng
```

This will enable a HTTP maintenance page on the server, for example [http://192.168.0.3:3142/acng-report.html](http://192.168.0.3:3142/acng-report.html) \(change to your server ip\)

### Client

```bash
sudo apt install squid-deb-proxy-client
```

{% hint style="warning" %}
[Debian Wiki for AptCatcherNg](https://wiki.debian.org/AptCacherNg) issues a security warning as the server is detected on the network via mDNS.
{% endhint %}

{% hint style="danger" %}
Do not install `auto-apt-proxy` and `squid-deb-proxy-client` at the same time. `auto-apt-proxy`'s configuration will override  `squid-deb-proxy-client.`
{% endhint %}

### Testing

#### Server

```bash
tail -f  /var/log/apt-cacher-ng/apt-cacher.log
```

#### Client

We are going to install `rolldice` a simple package which is easily removable, so its great for testing

```bash
sudo apt install rolldice
```

On the `server`, observe you are getting a request from the `client`.

```text
1569616597|O|11680|192.168.0.4|raspbian.raspberrypi.org/raspbian/pool/main/r/rolldice/rolldice_1.16-1+b1_armhf.deb
```

To remove `rolldice`:

```bash
sudo apt remove rolldice
```

### How it works

`apt-cacher-ng` is a proxy and stores files in `/var/cache/apt-cacher-ng/` . `apt-catcher-ng` will  publicize it exists over mDNS using `avahi-daemon`.

#### Debugging

To test if the `server` is being detected run:

```bash
/usr/share/squid-deb-proxy-client/apt-avahi-discover
```

This should return the server URL, for example:

```text
http://192.168.0.3:3142/
```

If does not happen, test to see if the server is publicizing itself.

On the `client`, we first need `avahi-browse`, which exists in the `avahi-utils` package.

```bash
sudo apt install avahi-utils
```

On the `client` after installation we can run `avahi-browse`:

```bash
avahi-browse -a | grep apt_proxy
```

Look for a line similar to:

```bash
+   eth0 IPv4 apt-cacher-ng proxy on pi3                    _apt_proxy._tcp      local
```

If this line does not appear, then your `client` is not detecting your `server`.

If your client detects the server, but the server is not caching check your `client` apt directory `/etc/apt/apt.conf.d/` for files which may configure your apt proxy

```bash
grep -R Proxy /etc/apt/apt.conf.d/*
```

Links:

* [Apt-Catcher NG homepage](https://www.unix-ag.uni-kl.de/~bloch/acng/)
* Debian wiki: [https://wiki.debian.org/AptCacherNg](https://wiki.debian.org/AptCacherNg)
* Debian Packages:
  * [https://packages.debian.org/search?keywords=apt-cacher-n](https://packages.debian.org/search?keywords=apt-cacher-ng)g
  * [https://packages.debian.org/search?keywords=squid-deb-proxy-client](https://packages.debian.org/search?keywords=squid-deb-proxy-client) 

