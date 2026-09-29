### Networking Notes

Concepts I actually had to understand properly to get this projects going, rather than copy-pasting

<pre>

## Physical setup


´´´
[Router] (living room)
    |
    | Long ethernet cable
    |
[Switch] (study room)
    |--Tower PC
    |--Thinkpad X230
    |--Thinkpad W540
    |--Dell Wyse 5070 (server)
´´´

</pre>

# Switch vs router

Switch: extends local network to multiple devices plugged into it. All devices plugged into it are on the same network.

Router: 
- Hands out IP addresses to devices automatically. 
- Gateway to the internet. 


# Private vs public IP address

- Currently all devices in the local network share this address 192.168.0.x. They are private and only work inside the local network.
- Router has a separate public IP, assigned by the ISP, which represents my home to the outside internet. Can be found out with wieistmeineip.de

--> Reaching the public IP only gets to the router, not automatically inside the home network. 

- NAT Network Address Translation: rewrites outgoing traffic so the internet only sees the public IP, never the individual device private one like the 192.168.0.x


# Static IP vs DHCP

A static IP instead of DHCP would need to be set for the server, so that I can find it reliably on my own network. 

Important note: It only stops the device from asking for a new address, it doesn't stop the router from theoretically handing the same address to something else via DHCP. 

# Port

IP address gets only to the right device, but a port gets to the right service on the machine. 

- SSH: port 22
- Jellyfin: port 8096
- Samba: port 445/139


## SSH login on LAN

To access the server, this command line would need to be entered in the terminal:

ssh <username>@192.168.0.x

# What actually happens in the background?

1. ARP: the connecting device broadcasts "Who has this IP?" on the local network.
2. Target device responds with its MAC address (unique identifier for a device).
3. The connection doesn't involve the router, since this never leaves the local network.
4. SSH prototol then takes over, creating an encrypted connection between the devices. 



