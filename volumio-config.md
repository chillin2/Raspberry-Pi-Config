# Volumio Config

## 3.5 LCD\(touch screen\) Config

1.

```
git clone https://github.com/swkim01/waveshare-dtoverlays

sudo cp waveshare-dtoverlays/waveshare35a.dtbo /boot/overlays/waveshare35a.dtbo

echo dtoverlay=waveshare35a >> /boot/config.txt

sudo reboot
```

2.

```bash
sudo nano /boot/config.txt
​

initramfs volumio.initrd
gpu_mem=64
max_usb_current=1
dtparam=audio=on
dtparam=spi=on
dtoverlay=waveshare35a:rotate=90
audio_pwm_mode=2
dtparam=i2c_arm=on
disable_splash=1
hdmi_force_hotplug=0
```

3.

```bash
Install touch display Plug-in

screen
```

4.

```bash
sudo systemctl stop volumio-kiosk.service

sudo sed -i "s+/dev/fb0+/dev/fb1+" /usr/share/X11/xorg.conf.d/99-fbturbo.conf

cat /usr/share/X11/xorg.conf.d/99-fbturbo.conf

sudo systemctl start volumio-kiosk.service
```

5.

```bash
sudo nano /usr/share/X11/xorg.conf.d/99-callibration.conf

​Section "InputClass"
Identifier "calibration"
MatchProduct "ADS7846 Touchscreen"
Option "TransformationMatrix" "0 -1 1 1 0 0 0 0 1"
Option "SwapAxes" "0"
EndSection
```

