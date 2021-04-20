###Using OpenVPN and RaspberryPI to create plug-n-play URL whitelisted router

Basic idea here is. Attach a wireless-adapter | ethernet cable to RPI. Power on the device. And it automatically connects to default ovpn tunnel. And then uses defualt wlan0 (inbuilt wireless adapter) to create a hotspot. And pipes traffic from hotspot to OVPN tunnel. In between we use iptables rules to filter out traffic based on DNS 52 port ACCEPT/DROP rules.
