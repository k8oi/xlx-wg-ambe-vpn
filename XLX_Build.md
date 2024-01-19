## XLX - Build Process
### Purpose: Describe, step by step, the process to build an XLX server using a WireGuard VPN connection for AMBE access
#### Base OS Installation
1. Install latest Raspberry Pi 4 image to SD Card
    - Raspberry Pi OS Lite (64-bit)
    - `https://www.raspberrypi.com/software/operating-systems/`
    - Note: The [Raspberry Pi Imager](https://www.raspberrypi.com/software/) has the latest versions
1. Install SD card into Pi and boot Pi
1. Log in a root (userid: `pi` password: `raspberry`)
1. Update and install packages
    - `apt-get update`
    - `apt-get upgrade`
    - `apt-get install git iptables iptables-persistent wireguard apache2 php`
    - `reboot`
1. (Optional) Change `pi` password to something other than default.
#### XLX Installation
[N5AMD XLX Git Repo](https://github.com/n5amd/xlxd-debian-installer)
1. `git clone https://github.com/n5amd/xlxd-debian-installer`
1. `cd xlxd-debian-installer`
1. `./xlxd-debian-installer.sh`
1. `systemctl reload apache2`
#### WireGuard Install
[Getting Started with WireGuard](https://miguelmota.com/blog/getting-started-with-wireguard/)
1. `mkdir -p /etc/wireguard/keys`
1. `cd /etc/wireguard/keys`
1. `umask 077`
1. `wg genkey | tee privatekey | wg pubkey > publickey`
1. `vi /etc/wireguard/wg0.conf # See XLX Server config on Github: wg0-XLX`
1. `vi /etc/sysctl.conf # uncomment line "net.ipv4.ip_forward=1"`
1. `sysctl -p`
1. `wg-quick up wg0`
1. `systemctl enable wg-quick@wg0.service`
#### Update XLX Server AMBE IP Addresses
Change the default AMBE server address from `127.0.0.1` to the WireGuard interface for the AMBE server (`10.0.0.2`) Run all as root.
1. `cd /etc/init.d`
1. Edit `xlxd`
    - Change the line (it will be specific to your installation) : `ARGUMENTS="XLX000 <your host ip address x.x.x.x> 127.0.0.1`
    - The new line should look like: `ARGUMENTS="XLX000 <your host ip address x.x.x.x> 10.0.0.2"`
1. Update systemd to read the updated init file and restart xlxd:
    - `systemctl daemon-reload`
    - `systemctl restart xlxd`
### Cross Fingers
Reboot
