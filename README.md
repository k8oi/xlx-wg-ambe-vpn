# xlx-wg-ambe-vpn
XLX AMBE Server running behind DHCP or non Data Center location using point-to-point WireGuard VPN
### Purpose
Run a XLX server in a datacenter with a static, public facing IP address with the ability to provide multi-protocol service for D-Plus, DMR, and YSF/C4FM. The AMBE server will run in a different location than the XLX server - home, different data center, whereever. 
### Goals
  - The AMBE server may reside "behind" a dynamically changing, public facing IP address.
  - If the AMBE server IP address changes, the VPN will reestablish connection in under 30 seconds.
  - Use a single Raspberry Pi4 for the AMBE host - no other networking routers, gear, etc.

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
https://n5amd.com/digital-radio-how-tos/create-xlx-xrf-d-star-reflector/
https://miguelmota.com/blog/getting-started-with-wireguard/
https://github.com/n5amd/ambed-debian-installer
