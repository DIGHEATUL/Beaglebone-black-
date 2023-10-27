# Beaglebone-black-
Interfacings With Beaglebone Black


For Starting First you need to check the all Available Uart in BBB for that Use

“ ls -l /dev/ttyO* ”

In BBB the UART PINS are


UART0 (console header) /dev/ttyS0 -- note: /sbin/agetty is running on this port

UART1        Tx - P9.24,  Rx - P9.26             /dev/ttyS1 

UART2        Tx - P9.21,  Rx - P9.22             /dev/ttyS2

UART3        Tx - P9.42   (Tx only)              /dev/ttyS3

UART4        Tx - P9.13,  Rx - P9.11             /dev/ttyS4

UART5        Tx - P8.37,  Rx - P8.38             /dev/ttyS5








You need to enable the pins with uBoot overlays:

You need to edit /boot/uEnv.txt:

Change these two lines: (Change as per Uart that you are used)

#uboot_overlay_addr6=/lib/firmware/<file6>.dtbo

#uboot_overlay_addr7=/lib/firmware/<file7>.dtbo

to

uboot_overlay_addr6=/lib/firmware/BB-UART1-00A0.dtbo

uboot_overlay_addr7=/lib/firmware/BB-UART2-00A0.dtbo

and then reboot.

Then Refer : 

[Linux Serial Ports Using C/C++ | mbedded.ninja](https://blog.mbedded.ninja/programming/operating-systems/linux/linux-serial-ports-using-c-cpp/)

For Detail Information (the Code given in Site is Fully Working).

Aslo Refer :

[Serial Programming/termios - Wikibooks, open books for an open world]     
(https://en.wikibooks.org/wiki/Serial_Programming/termios)https://en.wikibooks.org/wiki/Serial_Programming/termios
