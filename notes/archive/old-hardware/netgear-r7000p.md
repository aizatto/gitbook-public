# Netgear R7000P

## Setting up VPN on a Netgear R7000P Nighthawk

### Access Router

Access your router (either):

* [http://192.168.1.1/ ](http://192.168.1.1/)
* http://www.routerlogin.net/

Default password ([Google query](https://www.google.com/search?q=default+password+Netgear+R7000P))

* default user: admin
* default password: password

So maybe one of these would work:

* [http://admin:password@192.168.1.1/](http://admin:password@192.168.1.1/)
* [http://admin:password@www.routerlogin.net/](http://admin:password@www.routerlogin.net/)

### Enable Dynamic DNS

Go to: Advanced > Advanced Setup > Dynamic DNS

### Enable VPN

Go to: Advanced > Advanced Setup > VPN Service

Change setting:

Clients will use this VPN connection to access All sites on the Internet & Home Network

### Download VPN Certificate

Download: "OpenVPN configuration package download" "For Smart Phone"

* Downloads a [smartphone.zip](http://smartphone.zip/)
* Unzip file
* Locate client3.ovpn

### Download VPN Client

### Download OpenVPN Client for Desktop

* [https://openvpn.net/vpn-server-resources/connecting-to-access-server-with-macos/](https://openvpn.net/vpn-server-resources/connecting-to-access-server-with-macos/)
* [https://tunnelblick.net/](https://tunnelblick.net/)

Official Open VPN client

* Install client
* Open it in Applications > OpenVPN > OpenVPN Connect
* Find it in the menu bar in the top right
* Click it, then "Import" > "From local file..."
* Select client3.ovpn
* Test vpn setup
