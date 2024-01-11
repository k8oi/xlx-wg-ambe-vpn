## AMBE - Build Process
### Purpose: Describe, step by step, the process to build a AMBE server on a Raspberry Pi4

1. Install latest Raspberry Pi 4 image to SD Card
    * Raspberry Pi OS Lite (64-bit)
    * `https://www.raspberrypi.com/software/operating-systems/`
1. Install SD card into Pi and boot Pi
1. Log in a root (userid: `pi` password: `raspberry`)
1. Update and install packages
    * `apt-get update`
    * `apt-get upgrade`
    * `apt-get install git iptables iptables-persistent wireguard`
1. Project used Northwest Digital Thumb Drives 
