CloudLight
===
Software for smart alarm, which should help to wake up earlier with gentle light during the alarm voice. 
Should be incredible helpful for MiracleMorning during the dark winter mornings.

### Overview
---
- (ongiong) ESP8266 for OTA and remote control of lightning
- (not started) STM32 for controlling peripherals (buttons, LEDs)
- (not started) iOS App for managing all this magic


### Prerequisites
---
- Linux Ubuntu OS (ideal)
- download toolset and SDK https://github.com/espressif/ESP8266_RTOS_SDK
- Main board ESP8266 WittyCloud
- Driver https://github.com/WCHSoftGroup/ch341ser_linux
- VSCode Action Buttons to support buttons for build and flash.

Change .vscode/settings.json with your environmental variables.
Run make manuconfig to update project with your settings.


### Troubleshooting
---
##### 1. Can't find ttyUSB0

1. dmesg shows
```
[ 738.783508] ch341-uart ttyUSB0: ch341-uart converter now disconnected from ttyUSB0

[ 738.783521] ch341 1-10:1.0: device disconnected

```

2. find the rule (can be with different rule, but the name contains brltty)

```
/usr/lib/udev/rules.d/90-brltty-device.rules

```

3. comment out

```
# ENV{PRODUCT}=="1a86/7523/*", ENV{BRLTTY_BRAILLE_DRIVER}="bm", GOTO="brltty_usb_run"

```

According to the google, reboot shoul be enough. But I also commented the main routine downside the rule, so reboot won't needed for me.

### History
---
10-24-2022 - Project started
10-25-2022 - ESP8266 firmware ongoing
