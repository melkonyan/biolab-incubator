## Connecting to beaglebone 

When beaglebone is connected via use, ssh into it using `ssh debian@192.168.7.2` (password is `temppwd`)


When beaglebone is connected via wlan, ssh into it using `ssh debian@192.168.240.180`. Alternatively, search for the device using `nmap -sn 192.168.247.0/24`. If that doesn't work, make sure you're using the right mask, look up your IP using `ifconfig`. 


## Setup autoconnect 

Copy the following content into the `/etc/network/interfaces` file: 

```
auto wlan0
iface wlan0 inet static
address 192.168.240.180
netmask 255.255.255.0
gateway 192.168.1.1
wireless-ssid SSID_Name
wireless-key XXXXX
dns-nameservers 8.8.8.8 192.168.1.1
```
