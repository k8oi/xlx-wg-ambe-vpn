## XLX - Build Process
### Purpose: Describe, step by step, the process to configure a WireGuard XLX point to point VPN connection
---
#### WireGuard Install
Run all as root. XLX WireGuard config is located at `/etc/wireguard/wg0.conf` Thanks to Miguel Mota and his [WireGuard setup page](https://miguelmota.com/blog/getting-started-with-wireguard/)
1. `mkdir -p /etc/wireguard/keys`
1. `cd /etc/wireguard/keys`
1. `umask 077`
1. `wg genkey | tee privatekey | wg pubkey > publickey`
1. `vi /etc/wireguard/wg0.conf # See XLX Server config on Github: wg0-XLX`
1. `vi /etc/sysctl.conf # uncomment line "net.ipv4.ip_forward=1"`
1. `sysctl -p`
1. `wg-quick up wg0`
1. `systemctl enable wg-quick@wg0.service`
---
#### Update XLX Server Startup IP Addresses
Change the default AMBE server address from `127.0.0.1` to the WireGuard interface for the AMBE server (`10.0.0.2`) Run all as root.
1. `cd /etc/init.d`
2. edit `xlxd`
    * Change the line (it will be specific to your installation) : `ARGUMENTS="XLX000 <your host ip address x.x.x.x> 127.0.0.1`
    * The new line should look like: `ARGUMENTS="XLX000 <your host ip address x.x.x.x> 10.0.0.2"`

