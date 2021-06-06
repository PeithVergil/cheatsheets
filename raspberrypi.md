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


Writing an image to the SD card (using macOS)
--------------------------------------------------

The disk must be unmounted before copying the image.

```bash
diskutil unmountDisk /dev/disk4
```

Copy the image.

```bash
sudo dd bs=1m if=nanopi-neo2_sd_friendlywrt_4.14_arm64_20191230.img of=/dev/disk4 conv=sync

sync
```

Eject the SD card.

```bash
diskutil eject /dev/disk4
```