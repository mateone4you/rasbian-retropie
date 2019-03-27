# rasbian-retropie
Install Rasbian Lite + RetroPie + TFT 5″ 800x480 XPT2046

1.Download image from: https://downloads.raspberrypi.org/raspbian_lite_latest, ~300 mb.

2.Format sdcard: 
Windows - diskpart.exe
  list disk
  sel disk <our disk>
  clean
  exit

3.Write image: with etcher https://www.balena.io/etcher/.

4.Edit file on sdcard /boot/config.txt, only for TFT 5″ 800x480 XPT2046.
Add end of file:
###
max_usb_current=1
hdmi_force_hotplug=1
config_hdmi_boost=7
hdmi_group=2
hdmi_mode=1
hdmi_mode=87
hdmi_drive=1
hdmi_cvt 800 480 60 6 0 0 0
dtoverlay=ads7846,cs=1,penirq=25,penirq_pull=2,speed=50000,keep_vref_on=0,swapxy=0,pmax=255,xohms=150,xmin=200,xmax=3900,ymin=200,ymax=3900
###

5.Basic settings:
Boot raspberry with sdcard.

Enter login:password: (pi:raspberry)

Change password:
$ passwd

Enable Wi-Fi
$ sudo raspi-config
Network Option -> Wi-Fi -> Select country -> Enter SSID -> Enter passphase
check ping:
$ ping 8.8.8.8
$ ip a

Enable SSH:
$ sudo touch /boot/ssh



