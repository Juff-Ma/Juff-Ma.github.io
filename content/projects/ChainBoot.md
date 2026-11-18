---
title: "ChainBoot"
date: "2026-06-08"
tags: ["Linux", "Firmware"]
topics: ["Projects"]
type: "blank"
draft: false
---
Building LinuxBoot as a chainloader

# [ChainBoot](https://github.com/Juff-Ma/ChainBoot)

ChainBoot is an out of the box way to run [LinuxBoot](https://linuxboot.org) as a chainloader.

Usually LinuxBoot's kernels are very minimal since they only need to do the job of a common BIOS. However, sometimes a BIOS isn't enough. Linux usually ships a bootloader like GRUB since almost no BIOS is capable of reading Linux filesystems. Also sometimes, especially on complex systems, the BIOS doesn't support the hardware you want to boot from.

On a system which supports LinuxBoot directly you can just add the necessary drivers to the Kernel and be done. On a UEFI system that could theoretically be possible with EFI drivers but many UEFI implementations are too locked down. On BIOS it's pretty much impossible without shipping a custom option ROM.

So how can we solve this problem? We just load LinuxBoot, a firmware whose drivers we can easily augment, using the computer's builtin firmware. We chainload. LinuxBoot does not replace the BIOS but rather the bootloader like GRUB.

ChainBoot does exactly that. It is an out of the box way to replace your bootloader with something that's as powerful as Linux. Because it is Linux.

## Usecases

There are probably dozens of usecases I cannot think of, but here are two I actively use it for:

### NVMe booting

Many older firmwares do not support booting from NVMe devices. LinuxBoot can detect the drive an boot from it.

### Unsupported RAID/HBA cards

Server firmware is really picky about which adapter you can use for booting your OS. LinuxBoot can detect the adapter and boot just fine.
