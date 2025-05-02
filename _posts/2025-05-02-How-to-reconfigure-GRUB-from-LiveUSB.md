---
title: "How To Reconfigure GRUB from LiveUSB"
# date: 2022-01-01 14:30:00:00 +0800
author: foo
layout: post
icon: linux
tags: linux, ubuntu, windows, grub
# published: false
---

On a dual boot computer, a corrupted GRUB may happen after performing a major Windows update.
In order to fix the broken GRUB, please boot using a Ubuntu LiveUSB (or LiveCD).

After the computer is booted in Ubuntu, open a Terminal window, and type the following commands to re-install GRUB.

## Re-installing GRUB 
   
    # Example (for the case Linux is installed at /dev/sda5):
    # Otherwise, change all /dev/sda5 to your /dev/sda<#> or /dev/sdb<#>
    # NOTE: If not sure which partition has Linux been installed on,
    # you may run 'fdisk -l' to view partition information first.
    
    sudo mount /dev/sda5 /mnt
    sudo mount --bind /dev /mnt/dev
    sudo mount --bind /sys /mnt/sys
    sudo mount --bind /proc /mnt/proc
    sudo mount /dev/sdaX /mnt/boot   #only if /boot is mounted as separate partition at /dev/sdaX

    sudo chroot /mnt
    sudo update-grub
    sudo grub-install /dev/sda
    exit

    sudo umount /mnt/dev
    sudo umount /mnt/sys
    sudo umount /mnt/proc
    sudo umount /mnt/boot   #Only if you mounted it earlier
    sudo umount /mnt/
    sudo reboot

Hope this solution helps you.

If it doesn't, you may also try an alternative fix (suggested by others):

## Alternative Fix
    sudo mount /dev/sda5 /mnt
    sudo grub-install --root-directory=/mnt /dev/sda
    sudo umount /dev/sda5
    sudo reboot
