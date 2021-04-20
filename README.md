##Using OpenVPN and RaspberryPI to create plug-n-play URL whitelisted filtered router.

Basic idea here is. Attach a USB wireless-adapter |or| ethernet cable to RPI. Power on the device. And the new hotspot created acts as tunneled + filtered router.
Internally it automatically connects eth0/wlan1 to OpenVPN tunnel on boot. Then uses default wlan0 (inbuilt wireless adapter) to create a hotspot. Piping traffic from hotspot to OVPN tunnel. In between we use iptables rules to filter out traffic based on DNS 52 port ACCEPT/DROP rules.

Some of the links that I refered to create this configurations.


Packages installed during setup.
```
sudo apt-get install dnsmasq
sudo apt-get install hostapd
sudo apt-get install openvpn
```

Some the commands that will be helpful
```
sudo iptables-restore < /etc/iptables.ipv4.nat

sudo systemctl restart hostapd.service 
sudo systemctl restart dnsmasq.service 
sudo systemctl restart openvpn.service 

```
