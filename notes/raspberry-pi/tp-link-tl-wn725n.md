# tp-link: TL-WN725N

On the box it is called: TL-WN725N\(US\) v3

Official Site: [https://www.tp-link.com/us/home-networking/usb-adapter/tl-wn725n/](https://www.tp-link.com/us/home-networking/usb-adapter/tl-wn725n/)

{% hint style="info" %}
This has been tested on Raspbian Buster \(2019-07\)
{% endhint %}

Purchase from [https://www.lazada.com.my/products/tp-link-150mbps-wireless-n-nano-usb-adapter-wn725n-usb-20-i568056973-s1133310273.html](https://www.lazada.com.my/products/tp-link-150mbps-wireless-n-nano-usb-adapter-wn725n-usb-20-i568056973-s1133310273.html)

`lsusb`:

> Bus 001 Device 003: ID 0bda:8179 Realtek Semiconductor Corp. RTL8188EUS 802.11n Wireless Network Adapter

Chipset: `RTL8188EUS` 

Highlights:

* Works on Rasbpian Buster out of the box
* No additional drivers needed on Raspbian Buster \(2019-07\)

Issues:

* Solved: Raspbian would switch interfaces names, even with "Predictable Network Names" enabled
* Solved: dhcpcd did not recognize wlan1 as a wireless interface
* Unsolved: Cannot get hostapd working

Notes:

* wlan0 refers to the onboard wifi
* wlan1 refers to the usb wifi

## Hard Coding Network Names

Problem: With the WiFi plugged, on boot it could be randomly assigned either wlan0 or wlan1. This really makes it unpredictable. Even with "Predictable Network Names" enabled, the onboard wifi can be either wlan0 or wlan1, with the USB wifi being wlxXXXX.

Create `/etc/udev/rules.d/70-my_network_interfaces.rules`:

{% code-tabs %}
{% code-tabs-item title="/etc/udev/rules.d/70-my\_network\_interfaces.rules" %}
```bash
SUBSYSTEM=="net", ACTION=="add", ATTR{address}=="dc:a6:32:aa:aa:aa", NAME="wlan0"
SUBSYSTEM=="net", ACTION=="add", ATTR{address}=="50:3e:aa:aa:aa:aa", NAME="wlan1"
```
{% endcode-tabs-item %}
{% endcode-tabs %}

References:

* [https://raspberrypi.stackexchange.com/questions/63749/how-do-you-unconfuse-raspbian-when-it-has-wlan0-and-wlan1-reversed](https://raspberrypi.stackexchange.com/questions/63749/how-do-you-unconfuse-raspbian-when-it-has-wlan0-and-wlan1-reversed
  )

## `dhcpcd` Recognizing wlan1 as a wireless device

Problem: `dhcpcd` would not use `wpa_supplicant` on `wlan1` because it was not recognized as a wireless device.

Modify `/etc/dhcpcd.conf`:

{% code-tabs %}
{% code-tabs-item title="/etc/dhcpcd.conf" %}
```text
interface wlan1
env ifwireless=1
```
{% endcode-tabs-item %}
{% endcode-tabs %}

Try restarting `dhcpcd`:

```text
sudo service dhcpcd restart
```

References:

* [https://www.raspberrypi.org/forums/viewtopic.php?t=191061](https://www.raspberrypi.org/forums/viewtopic.php?t=191061)

### Tips for Debugging

Below are some logs and files that helped me debug this.

Logs:

* grep dhcp /var/log/syslog
* grep wpa /var/log/syslog

Interesting files:

* /etc/dhcpcd.conf
* /lib/dhcpcd/dhcpcd-hooks/10-wpa\_supplicant

Commands:

* `dpkg -L dhcpcd5`
  * Displays which files were installed by `dhcpcd`

