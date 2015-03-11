Raspberry Pi 2
==============


Writing image to the SD card
--------------------------------------------------
df -h

umount /dev/mmcblk0p1
umount /dev/mmcblk0p2
umount /dev/mmcblk0p3

dd bs=4M if=OpenELEC-RPi.arm-4.0.5.img of=/dev/mmcblk0

sync


OSMC
--------------------------------------------------

Install the SSA/ASS library to display embeded subtitles in videos.

`sudo apt-get install libass5`