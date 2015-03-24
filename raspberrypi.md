Raspberry Pi 2
==============


Writing an image to the SD card
--------------------------------------------------

```bash
df -h

umount /dev/mmcblk0p1
umount /dev/mmcblk0p2
umount /dev/mmcblk0p3

dd bs=4M if=OSMC_TGT_rbp2_20150315.img of=/dev/mmcblk0

sync
```


OSMC
--------------------------------------------------

Install the SSA/ASS library to display embeded subtitles in videos.

`sudo apt-get install libass5`