# Raspberrypi Installation Guide

## Installing Raspberry Pi OS on microSD card
- Download the latest version of Raspberry Pi Imager from [here](https://www.raspberrypi.org/software/) and install it.
- Download Raspberry Pi OS Image 64 bit Raspbian Buster from [here](https://downloads.raspberrypi.org/raspios_arm64/images/) or direct download [here](https://downloads.raspberrypi.org/raspios_arm64/images/raspios_arm64-2022-01-28/2022-01-28-raspios-bullseye-arm64.zip).
- Install 64 bit Raspbian Buster with Raspberry Pi Imager on a microSD card.

## Enable Wifi and ssh
- Create a file in the `boot` directory of microSD card and named it `wpa_supplicant.conf`.
- Open it with a text editor and write the followings. Replace the `your_wifi_name` and `your_wifi_password` with your network ssid and password.
```
country=US
ctrl_interface=DIR=/var/run/wpa_supplicant GROUP=netdev 
update_config=1

network={
        ssid="your_wifi_name"
        psk="your_wifi_password"
        proto=RSN
        key_mgmt=WPA-PSK
        pairwise=CCMP
        auth_alg=OPEN
        id_str="phone"
        priority=9
}
```
- Create a file named `ssh` in the same `boot` directory and keep it blank.

## Boot Raspberry Pi
- Insert the microSD card to Raspberry Pi.
- Download PuTTY from [here](https://www.putty.org/)
- Open PuTTY with host name `raspberrypi`
- Login as `pi`
- Password `raspberry`
 
## Enable ARM I2C Interface
- Run following command in PuTTY.
```
sudo raspi-config
```
- Select `Interfacing Options`, select `I2C` and set `Yes`
- Press `Tab` and select `Finish`
