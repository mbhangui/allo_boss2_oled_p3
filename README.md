# Overview
This BOSS2 OLED application runs on Python 3.x. This application is used for displaying status and controlling Allo boss2

1. amixer controls
2. volume settings
3. Filter settings
4. RMS voltage control

You can also use alsamixer to view/set settings. Running aplay -l on raspberry PI will show something like this

```
boss:(pi) /home/pi/oled >aplay -l
**** List of PLAYBACK Hardware Devices ****
card 0: vc4hdmi0 [vc4-hdmi-0], device 0: MAI PCM i2s-hifi-0 [MAI PCM i2s-hifi-0]
  Subdevices: 1/1
  Subdevice #0: subdevice #0
card 1: vc4hdmi1 [vc4-hdmi-1], device 0: MAI PCM i2s-hifi-0 [MAI PCM i2s-hifi-0]
  Subdevices: 1/1
  Subdevice #0: subdevice #0
card 2: Headphones [bcm2835 Headphones], device 0: bcm2835 Headphones [bcm2835 Headphones]
  Subdevices: 8/8
  Subdevice #0: subdevice #0
  Subdevice #1: subdevice #1
  Subdevice #2: subdevice #2
  Subdevice #3: subdevice #3
  Subdevice #4: subdevice #4
  Subdevice #5: subdevice #5
  Subdevice #6: subdevice #6
  Subdevice #7: subdevice #7
card 3: Boss2 [Allo Boss2], device 0: bcm2835-i2s-allo-cs43130 allo-cs43130-0 [bcm2835-i2s-allo-cs43130 allo-cs43130-0]
  Subdevices: 1/1
  Subdevice #0: subdevice #0
```

Here you can see that the Allo Boss2 card has been detected as device #3. So you can run `alsamixer -c3` command

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
