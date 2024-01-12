## AMBE - Build Process
### Purpose: Describe, step by step, the process to build a AMBE server on a Raspberry Pi-4B

1. Install latest Raspberry Pi 4 image to SD Card
    * Raspberry Pi OS Lite (64-bit)
    * `https://www.raspberrypi.com/software/operating-systems/`
1. Install SD card into Pi and boot Pi
1. Log in a root (userid: `pi` password: `raspberry`)
1. Update and install packages
    * `apt-get update`
    * `apt-get upgrade`
    * `apt-get install git iptables iptables-persistent wireguard`
1. Project used [Northwest Digital ThumbDV](https://nwdigitalradio.com/products/thumbdv™) for transcoding; used 2 devices initially. These devices require FTDI drivers:
    * [FTDI Driver Location](https://ftdichip.com/drivers/d2xx-drivers/)
    * Used ARMv8 for the Raspberry Pi-4B
    * [1.4.27 ARMv8 hard-float driver](https://ftdichip.com/wp-content/uploads/2022/07/libftd2xx-arm-v8-1.4.27.tgz)
1. Download the FTDI driver to the `/root` folder and untar. The following directions are a summary from the release/ReadMe.txt from the driver tar file.
    * `wget https://ftdichip.com/wp-content/uploads/2022/07/libftd2xx-arm-v8-1.4.27.tgz`
    * `tar -xvf libftd2xx-arm-v8-1.4.27.tgz`
1. Peform the following steps as root:
    * `cd /root/release/build`
    * `cp libftd2xx.* /usr/local/lib`
    * `chmod 0755 /usr/local/lib/libftd2xx.so.1.4.27`
    * `ln -sf /usr/local/lib/libftd2xx.so.1.4.27 /usr/local/lib/libftd2xx.so`
    * `cd ..`
    * `cp ftd2xx.h /usr/local/include`
    * `cp WinTypes.h /usr/local/include`
    * `ldconfig -v`
