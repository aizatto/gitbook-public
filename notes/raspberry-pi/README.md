# Raspberry Pi

## Finding Hardware in Malaysia

I've confirmed these work

* Raspberry Pi 4
  * [Cytron: Raspberry Pi 4, 4GB](https://my.cytron.io/p-raspberry-pi-4-model-b-4gb)
* Mini HDMI to HDMI \(Raspberry Pi 4\)
  * [Lazada: UGREEN](https://www.lazada.com.my/products/ugreen-micro-hdmi-to-hdmi-cable-male-to-female-micro-hdmi-adapter-supports-4k-3d-for-gopro-hero-5-tablets-laptopasus-vivobook-s14zenbook-ux305ux330cameras-etc20cm-i13642239-s16735359.html)
* USB to TTL Serial Cable
  * [Cytron: PL2303HX USB to TTL Serial Cable](https://my.cytron.io/p-pl2303hx-usb-to-ttl-serial-cable)
* Wireless USB Adapter
  * [Lazada: tp-link: TL-WN725N\(US\) Ver: 3.0](https://www.lazada.com.my/products/tp-link-150mbps-wireless-n-nano-usb-adapter-wn725n-usb-20-i568056973-s1133310273.html)

### tp-link: TL-WN725N\(US\) Ver: 3.0

From [https://www.lazada.com.my/products/tp-link-150mbps-wireless-n-nano-usb-adapter-wn725n-usb-20-i568056973-s1133310273.html](https://www.lazada.com.my/products/tp-link-150mbps-wireless-n-nano-usb-adapter-wn725n-usb-20-i568056973-s1133310273.html)

Works out of the box on Raspbian Buster \(2019-07-10\)

`lsusb`:

> Bus 001 Device 003: ID 0bda:8179 Realtek Semiconductor Corp. RTL8188EUS 802.11n Wireless Network Adapter

### USB to TTL Serial Cable \(macOS 10.14.6\)

From [https://my.cytron.io/p-pl2303hx-usb-to-ttl-serial-cable](https://my.cytron.io/p-pl2303hx-usb-to-ttl-serial-cable
)

1. Enable UART by default
   1. See instructions below
2. Install macOS drivers [http://www.prolific.com.tw/US/ShowProduct.aspx?p\_id=229&pcid=41](%20http://www.prolific.com.tw/US/ShowProduct.aspx?p_id=229&pcid=41)
   1. Requires restarting computer
3. Plug in leads, refer to [https://pi4j.com/1.2/pins/model-zerow-rev1.html](https://pi4j.com/1.2/pins/model-zerow-rev1.html)
   1. Pin 2: Red, V\_USB \(Optional if not using USB Power\)
   2. _Blank_
   3. Pin 6: Black, GND
   4. Pin 8: White, USB\_RX
   5. Pin 10: Green, USB\_TX
4. Restart computer
5. Plug in Raspberry Pi to USB Port
6. Discover serial device: `ls /dev/cu.*`
   1. Mine was `/dev/cu.usbserial`
7. Connect to device: `screen /dev/cu.usbserial 115200`

Instructions adapted from [https://learn.adafruit.com/adafruits-raspberry-pi-lesson-5-using-a-console-cable/software-installation-mac](https://learn.adafruit.com/adafruits-raspberry-pi-lesson-5-using-a-console-cable/software-installation-mac
)

## Raspbian Boot Config

Great to do this before booting the Pi for the first time.

File referred to here are inside the micro SD Card.

### Enable SSH by default

Create empty file: `/boot/ssh`

### Enable Wifi by default

Create file: `/boot/wpa_supplicant.conf`

{% code-tabs %}
{% code-tabs-item title="/boot/wpa\_supplicant.conf" %}
```text
ctrl_interface=DIR=/var/run/wpa_supplicant GROUP=netdev
update_config=1
country=MY

network={
    ssid="YOUR_SSID"
    psk="YOUR_PASSWORD"
}
```
{% endcode-tabs-item %}
{% endcode-tabs %}

### Enable UART by default

Append to: `/boot/config.txt`

{% code-tabs %}
{% code-tabs-item title="/boot/config.txt" %}
```text
enable_uart=1
```
{% endcode-tabs-item %}
{% endcode-tabs %}

## Tips

### Hostnames

Using `sudo raspi-config` set your hostname to something memorable. For example, in my network I have

* pi3
* pi4

This allows me to easily do `ssh pi@pi3.local`

### File Browser

Edit code via Visual Studio Code [https://code.visualstudio.com/docs/remote/ssh](https://code.visualstudio.com/docs/remote/ssh)

{% hint style="danger" %}
Editing code doesn't work with a Raspberry Pi Zero, because the armv6l architecture is not supported. Raspberry Pi 3 and Raspberry Pi 4 run armv7l.
{% endhint %}

Browse files using SSHFS

* homebrew: brew install sshfs
* GUI [https://github.com/dstuecken/sshfs-gui](https://github.com/dstuecken/sshfs-gui)

