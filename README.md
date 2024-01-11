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
  - Setting up XLX - You should have a working XLX server
  - Setting up an AMBE server - You have a working AMBE server
  - Figuring out how to configure AMBE devices


### Hardware
  - I used a brand new Rasp Pi4 for the AMBE server
