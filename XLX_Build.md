## AMBE - Build Process
### Purpose: Describe, step by step, the process to configure a WireGuard AMBE point to point VPN connection

#### WireGuard Install
Run all as root. AMBE WireGuard config is located at /etc/wireguard/wg0.conf Thanks to Miguel Mota and his [WireGuard setup page](https://miguelmota.com/blog/getting-started-with-wireguard/)
1. `mkdir -p /etc/wireguard/keys`
1. `cd /etc/wireguard/keys`
1. `umask 077`
1. `wg genkey | tee privatekey | wg pubkey > publickey`
1. `vi /etc/wireguard/wg0.conf # See AMBE Server config on Github: wg0-AMBE`
1. `vi /etc/sysctl.conf # uncomment line "net.ipv4.ip_forward=1"`
1. `sysctl -p`
1. `wg-quick up wg0`
1. `systemctl enable wg-quick@wg0.service`
#### Next Steps
Pop a cold beverage, take a deep breath and reboot the Pi...
