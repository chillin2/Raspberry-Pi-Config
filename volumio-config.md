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

