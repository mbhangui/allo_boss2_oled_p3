# Overview
This BOSS2 OLED application runs on Python 3.x. This application is used for displaying status and controlling Allo boss2

1. amixer controls
2. volume settings
3. Filter settings
4. RMS voltage control


# Steps for Installation

```
Login as root or use sudo to become root

# apt-get -y update
# apt-get install python3
# apt-get install python3-lgpio
# apt-get install python3-pil
# apt-get install python3-rpi-lgpio
# apt-get install python3-smbus
# mkdir /usr/local/src
# cd /usr/local/src
# git clone https://github.com/mbhangui/allo_boss2_oled_p3.git
# cd allo_boss2_oled_p3/boss2_oled_p3
# cp boss2oled.service /usr/lib/systemd/system
# systemctl enable boss2oled.service
# systemctl start boss2oled.service
```

enable i2c manually or check `i2cdetect -y 1`
