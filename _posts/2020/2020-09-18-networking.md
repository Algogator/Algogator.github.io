---
layout: "post"
title: "Networking"
date: "2020-09-18 12:13"
---

I've been messing around with the RPi 4 a lot lately.

`sudo apt-get install network-manager`

Installs nmcli and don't foget to purge (https://gist.github.com/truh/de723a3bc0f837f75d3673ddf101e108)

`sudo apt purge openresolv dhcpcd5`

else nmcli d wifi won't work

Some other useful avahii commands:

`avahi-browse -a`

Useful nmcli commands:

`nmcli d wifi connect my_wifi password <password>`

can't seem to connect to the AP on another RPi 4 but worked fine with wpa_supplicant

Useful wpa_supplicant commands:

`sudo wpa_supplicant -c /etc/wpa_supplicant/wpa_supplicant.conf -i wlan0`

`wpa_passphrase <ssid> <pass> > /etc/wpa_supplicant/wpa_supplicant.conf`
Been trying to find a way to detect all the devices connected to the access point.
