## openvpn-install
OpenVPN [road warrior](http://en.wikipedia.org/wiki/Road_warrior_%28computing%29) installer for Debian, Ubuntu and CentOS.

This script will let you setup your own VPN server in no more than a minute, even if you haven't used OpenVPN before. It has been designed to be as unobtrusive and universal as possible.

### Installation
Run the script and follow the assistant:

`wget https://git.io/vpn -O openvpn-install.sh && bash openvpn-install.sh`

install openvpn With `google-authenticator` use this repo script

```

# clone this repo : https://github.com/forfuns/openvpn-install.git
git clone https://github.com/forfuns/openvpn-install.git

cd openvpn-install

# use branch dev
git checkout dev

bash openvpn-install.sh
```

close selinux (if use `google-authenticator` must do this)
`setenforce 0`

fix outside network connectivity
```
/etc/sysctl.conf
net.ipv4.ip_forward = 1

iptables -t nat -A POSTROUTING -s 10.8.0.0/24 -o eth0 -j MASQUERADE

# remove POSTROUTING record
iptables -t nat -D POSTROUTING 1
```
Once it ends, you can run it again to add more users, remove some of them or even completely uninstall OpenVPN.

### I want to run my own VPN but don't have a server for that
You can get a little VPS from just $1/month at [VirMach](https://billing.virmach.com/aff.php?aff=4109&url=billing.virmach.com/cart.php?gid=1).

### Donations

If you want to show your appreciation, you can donate via [PayPal](https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=VBAYDL34Z7J6L) or [cryptocurrency](https://pastebin.com/raw/M2JJpQpC). Thanks!
