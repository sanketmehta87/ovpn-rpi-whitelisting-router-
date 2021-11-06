
## Using OpenVPN and RaspberryPI to create plug-n-play URL whitelist filtered + tunneled hotspot.

Basic idea here is. Attach a USB wireless-adapter |or| ethernet cable to RPI. Power on the device. And the new hotspot created acts as tunneled + filtered router.

Internally it automatically connects eth0/wlan1 to OpenVPN tunnel on boot. Then uses default wlan0 (inbuilt wireless adapter) to create a hotspot. Piping traffic from hotspot to OVPN tunnel. In between we use iptables rules to filter out traffic based on DNS 52 port ACCEPT/DROP rules.

![repo](https://user-images.githubusercontent.com/80457775/140620877-d64ed737-3d7e-4e19-9a35-4a248ee322bf.JPG)
![repo](https://github.com/sanketmehta87/ovpn-rpi-whitelisting-router-/blob/main/turning.png?raw=true)

Some of the links that I refered to create this configurations. All this files along with same directory names resides inside `/etc/` folder of raspbian os.

[Setting up RPi3 as an access point](https://learn.sparkfun.com/tutorials/setting-up-a-raspberry-pi-3-as-an-access-point/all)

[How to domain filtering in Linux?](https://unix.stackexchange.com/questions/137904/how-to-do-domain-filtering-in-linux)

[How to use your RPi as a wireless access point](https://thepi.io/how-to-use-your-raspberry-pi-as-a-wireless-access-point)

[Install OVPN for Raspbian](https://ovpn.com/en/guides/raspberry-pi-raspbian)

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
Donate on USDC or eth:
0x35B22e17c06F15a9c2D05C0947a48288AD8d9bb8
btc:
bc1qcf5nfy2kf8apk6vmklgl9mr4qhueld32awffvq
Or coinbase @sunmeta Wallet.
