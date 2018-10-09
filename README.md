# RPi QEMU Testing

After you have created your Pi Image, you can test it without needing to burn it
to a SD card and physically booting it by using QEMU.  These scripts provide you
the ability to do this

## File Origins

The kernel and versatile-pb.dtb are from https://github.com/dhruvvyas90/qemu-rpi-kernel 

## Requirements

QEMU - Download for your OS

* [Windows](https://qemu.weilnetz.de/w64/)

# Usage

qemu-system-aarch64 -cpu arm1176 -m 256 -kernel kernel-qemu-4.14.50-stretch -M versatilepb -dtb versatile-pb.dtb -no-reboot -serial stdio -append "root=/dev/sda2" -net nic -net user,hostfwd=tcp::5022-:22 -drive "index=0,media=disk,format=raw,file=2018-10-09-piscore-4GB.img"

Replacing the filename with whatever your image is, obviously.


