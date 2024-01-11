## AMBE - Build Process
### Purpose: Describe, step by step, the process to build a AMBE server on a Raspberry Pi4

1	Install latest Raspberry Pi 4 image to SD Card
	* Raspberry Pi OS Lite (64-bit)
	* `https://www.raspberrypi.com/software/operating-systems/`
2	Install SD card into Pi and boot Pi
3	Log in a root (userid: `pi` password: `raspberry`)
4	Update and install packages
		* `apt-get update
		* apt-get upgrade
		* apt-get install git iptables iptables-persistent wireguard`
