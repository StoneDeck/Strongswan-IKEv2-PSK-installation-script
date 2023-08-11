# Strongswan-IKEv2-PSK-installation-script
This script is designed to automatically install the Strongswan daemon. Use Ubuntu 20.04. On it this script is tested and works well.

# Installation
Before running the script, find out your network interface. Use command:
```
ip route show default
```
to find out your network interface. After applying the command, you will see output like:
```
default via your_server_ip dev eth0 proto static
```
After dev there will be the required interfaces, in this case it is eth0. Insert your interface in the script, use the search for this. Replace all eth0 in the script with your network interface.

To run the script use this command
```
yes | sudo sh startswan.sh
```
# Usage
You will need to add a username and password. Edit the file:
```
/etc/ipsec.secrets
```
Inside the file there is a template for how to add a new user. After saving the file, restart Strongswan using the command:
```
sudo systemctl restart strongswan-starter
```
