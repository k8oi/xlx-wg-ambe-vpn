# xlx-wg-ambe-vpn
XLX AMBE Server running behind DHCP or non Data Center location using point-to-point WireGuard VPN
### Purpose
Run a XLX server in a datacenter with a static, public facing IP address with the ability to provide multi-protocol service for D-Plus, DMR, and YSF/C4FM. The AMBE server will run in a different location than the XLX server - home, different data center, whereever. 
### Goals
  - The AMBE server may reside "behind" a dynamically changing, public facing IP address.
  - Use a single Raspberry Pi4 for the AMBE host - no other networking routers, gear, etc.
  - XLX Server is running in a datacenter with a static IP address
  - WireGuard VPN connection routing the AMBE UDP packets
  - The AMBE server is running on a Raspberry Pi4B with 2 NW Digital ThumbDVs.
  - There is no VPN hardware
  - The AMBE WireGuard VPN will handle changes with home DHCP/external facing changes with a 25 second reconnect interval
  - No Port forwarding!

### Requirements
This document does not address:
  - Figuring out how to configure AMBE devices

### Hardware
  - Brand new Rasp Pi4 for the AMBE server
  - 2 Northwest Digital ThumbDV USB Sticks

### Terms
  - XLX is the XLX Server
  - AMBE is the AMBE (Pi-4B) Server

### Thanks
I really appreciate the following authors for their links:
  - https://n5amd.com/digital-radio-how-tos/create-xlx-xrf-d-star-reflector/
  - https://miguelmota.com/blog/getting-started-with-wireguard/
  - https://github.com/n5amd/ambed-debian-installer

73 de K8OI
2024-01-19
