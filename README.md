# IoT Smart Farm Project

Internet of Things DEMO - A Smart Farm Project Based on the Raspberry Pi

## Overview

With regard to the material:

 - [Raspberry Pi 3 Model B+](https://www.raspberrypi.org/products/raspberry-pi-3-model-b-plus/)
 - Analog sensors
  - DHT11
  - DS18B20
  - BMP180
 - [Dell Edge Gateways for IoT 5100](https://www.dell.com/en-us/work/shop/cty/pdp/spd/dell-edge-gateway-5100/xctoi5100us)


## Getting started

### Installation

#### Setting up Raspberry Pi

[Officical Installation Guide](https://projects.raspberrypi.org/en/projects/raspberry-pi-setting-up/1)

#### Configuring Raspberry Pi

##### SSH

`Start` -> `Preferences` -> `Raspberry Pi Configuration` -> `Interfaces` -> `SSH: Enable`

##### VNC

`Start` -> `Preferences` -> `Raspberry Pi Configuration` -> `Interfaces` -> `VNC: Enable`

VNC connect to RPi (macOS)

`cmd`+`k` -> `vnc://<ip>:5900`

##### Timezone

`Start` -> `Preferences` -> `Raspberry Pi Configuration` -> `Localisation` -> `Set Timezone: Asia, Hong Kong`

##### DNS

`$ sudo nano /etc/dhcpcd.conf`

```
static domain_name_servers=10.32.32.27
```

unplugged and replugged ethernet cable

check result:

`$ cat /etc/resolv.conf`  


##### NTP

`$ sudo nano /etc/systemd/timesyncd.conf`

```
NTP=time.ext.csclab.bj
```

`$ sudo systemctl enable systemd-timesyncd`

`$ sudo systemctl start systemd-timesyncd`

`$ sudo timedatectl set-ntp 1`

`$ sudo systemctl restart systemd-timesyncd`

Verify

`$ sudo timedatectl status`

```shell
      Local time: Fri 2019-01-04 11:17:52 HKT
  Universal time: Fri 2019-01-04 03:17:52 UTC
        RTC time: n/a
       Time zone: Asia/Hong_Kong (HKT, +0800)
 Network time on: yes
NTP synchronized: yes
 RTC in local TZ: no
```

>NTP synchronized: yes

##### Resolution

`Start` -> `Preferences` -> `Raspberry Pi Configuration` -> `Set Resolution: DMT mode 82 1920x1080 60Hz 16:9`

##### More Configuration

Check out more configuration under: [https://www.raspberrypi.org/documentation/configuration/](https://www.raspberrypi.org/documentation/configuration/)

### Usage

### Client Side - Raspberry Pi

### Server Side

Contributors
-------------------
* XinYe (nunchuk@live.com)
