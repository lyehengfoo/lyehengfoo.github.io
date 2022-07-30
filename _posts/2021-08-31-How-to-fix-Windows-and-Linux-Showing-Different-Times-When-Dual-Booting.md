---
title: "How To Fix Windows and Linux Showing Different Times When Dual Booting"
# date: 2022-01-01 14:30:00:00 +0800
author: foo
layout: post
icon: linux
tags: linux, ubuntu
# published: false
---

Your computer stores the time in a hardware clock on its motherboard.
The clock keeps track of time, even when the computer is off.
By default, Windows assumes the time is stored in local time,
while Linux assumes the time is stored in UTC time and applies an offset.
This leads to one of your operating systems showing the wrong time in a dual boot situation.

To fix this, you have two options: Make Linux use local time, or
make Windows use UTC time. Don’t follow both steps of instructions
or they still won’t be speaking the same language!

It is recommended to make Linux use local time i.e. as shown in *Option 1* below.

## Option 1: Make Linux Use Local Time

    timedatectl set-local-rtc 1 --adjust-system-clock

To check your current settings, run the following command, and you should see *RTC in local TZ: yes* status.

    timedatectl

## Option 2: Make Windows Use UTC Time

Use RegEdit, go to: *HKEY_LOCAL_MACHINE\System\CurrentControlSet\Control\TimeZoneInformation*

Create a new registry key *RealTimeIsUniversal* of type *REG_DWORD* and set its value data to *1*. 

## Notes

If you’re wondering why Windows uses local time instead of UTC like other operating systems,
official Microsoft blog [The Old New Thing](https://devblogs.microsoft.com/oldnewthing/)
explains it there.
In short, it was to preserve backwards compatibility with Windows 3.1 systems and
to prevent people from getting confused when they set the time in the computer’s BIOS.
Of course, PC manufacturers chose local time to be compatible with Windows and
Windows chose local time to be compatible with the decision PC manufacturers chose,
so the cycle became self-reinforcing.

There’s currently no standard for labeling whether a time is stored as UTC or local time
in BIOS or UEFI firmware, which would probably be the most logical solution.
But it would require some work, and most people will never even notice different
operating systems use different time formats—except in dual-boot configurations.
