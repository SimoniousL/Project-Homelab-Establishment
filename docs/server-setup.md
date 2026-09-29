## Server Setup

# Operating System

Installed Ubuntu Server 26.04.1 LTS (no desktop GUI) onto Wyse's internal 128GB SSD. 
- Designated to run headless (no monitor, keyboard)
- Save resources

--> During installation, it is crucial to enable OpenSSH server. It is the only way to reach the machine once it's disconnected from a monitor. 


# Static IP

Configured via Netplan (Ubuntu's network config tool) editing the YAML file at /etc/netplan/

# Storage mounting

External HDD (see hardware.md) gets mounted at /mnt/nasdrive automatically on every boot, via an en entry in /etc/fstab referencing the drive's UUID rather than its device name

# Samba (file sharing)

Installed Samba and created one share per folder, each at its own block in /etc/samba/smb.conf.
This is what lets any device on the network see these folders as normal network drives. 
