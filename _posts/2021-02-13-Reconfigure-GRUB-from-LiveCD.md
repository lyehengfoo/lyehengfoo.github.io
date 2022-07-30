---
title: "Reconfigure GRUB from LiveCD"
# date: 2022-01-01 14:30:00:00 +0800
author: foo
layout: post
icon: linux
tags: linux, ubuntu, grub
# published: false
---

There are times when you have a dual boot computer to boot into both Windows & Ubuntu (Linux).

And if you have to re-install Windows, chances are that Windows installation will overwrite
any existing GRUB installation, and make your Ubuntu not bootable anymore.

To solve this, prepare a LiveCD for the same version of Ubuntu (preferably), so that you have
the same GRUB bootloader version installed again. To prepare a LiveCD USB, you can download the
ISO file and use any ISO image to USB writer app. Some good examples of this writer app are 
[Universal USB Installer (UUI)](https://www.pendrivelinux.com/universal-usb-installer-easy-as-1-2-3/), [Rufus](https://rufus.ie/en/) and
[UNetbootin](https://unetbootin.org/).

If you wish to create a few flavours of Linux ISOs in the same pendrive, you could use
[YUMI](https://www.pendrivelinux.com/yumi-multiboot-usb-creator/)
or [MultiBootUSB](https://github.com/mbusb/multibootusb).

After you have prepared the LiveCD, boot your computer into the LiveCD. And here are the commands you need to use to re-configure GRUB after booting into Live CD. Please take note that the example
below is assuming /dev/sda2 is your Ubuntu/Linux partition (where the GRUB boot configuration is
stored), and Windows is installed in /dev/sda1 and that /dev/sda is the primary boot disk. If you
have something different, please replace accordingly. You can easily find out about your partition
from *fdisk -l* (Linux) or simply use tools like *GParted* (Linux) or *Minitool Partition Wizard* (Windows)

    fdisk -l   ### To find out about your partitions information

    sudo mount /dev/sda2 /mnt
    sudo mount --bind /dev /mnt/dev
    sudo mount --bind /sys /mnt/sys
    sudo mount --bind /proc /mnt/proc
    sudo mount /dev/sdaX /mnt/boot   ### Only if /boot is mounted as separate partition

    sudo chroot /mnt
    sudo update-grub
    sudo grub-install /dev/sda
    exit

    sudo umount /mnt/dev
    sudo umount /mnt/sys
    sudo umount /mnt/proc
    sudo umount /mnt/boot   ### Only if you mounted it earlier

    sudo reboot

Alternate fix:

    sudo mount /dev/sda2 /mnt
    sudo grub-install --root-directory=/mnt /dev/sda
    sudo umount /dev/sda2
    sudo reboot

You should be able to see the GRUB boot menu upon reboot.  To be sure that everything is
working (especially when you have more than one OS installed), please re-run OS detection
by running:

    sudo update-grub

Hope it has helped you.
