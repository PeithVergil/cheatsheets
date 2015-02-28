Mercurial
=========


Writing image to the SD card
--------------------------------------------------
df -h

umount /dev/mmcblk0p1
umount /dev/mmcblk0p2
umount /dev/mmcblk0p3

dd bs=4M if=OpenELEC-RPi.arm-4.0.5.img of=/dev/mmcblk0

sync