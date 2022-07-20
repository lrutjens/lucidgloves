# Firmware Troubleshooting Guide

This is a page dedicated to troubleshooting common errors that can occur when flashing the Lucidgloves firmware to a microcontroller. Some of these errors may be board specific. 

This page assumes that you've already read the [Firmware Setup and Customization Tutorial](https://github.com/LucidVR/lucidgloves/wiki/Firmware-Setup-and-Customization-Tutorial)

## Upload Errors

**Error:** `A fatal error occurred: Failed to connect to ESP32: Timed out waiting for packet header`

Press and hold the BOOT/IOO button (whichever is on your board) when uploading, and hold the button down until the upload is done. Additionally, make sure that you've got both the correct board, and port selected in the IDE. 

**Error:** `...\main.ino: undefined reference to [x]` or `error: '[x] was not declared in this scope'` or `fatal error: [x]: No such file or directory`, etc

Make sure that you've downloaded **all** of the files in the firmware folder (The easiest way to be sure is to use the green `Code` button in the main folder. Additionally, be sure that you've unzipped all of the files, and that all the files are in a common directory. Done correctly, all of the files should automatically open together, like this:

![image](https://user-images.githubusercontent.com/33757254/155819538-3d21779c-8bda-499f-b9f6-49d3e30902eb.png)

**Error:** `haptics:4:26: fatal error: ESP32Servo.h: No such file or directory`

This means that you likely haven't installed the ESP32Servo library yet. To do so, follow [the Setup Guide](https://github.com/LucidVR/lucidgloves/wiki/Firmware-Setup-and-Customization-Tutorial#adding-required-esp-32-libraries) again

**Error:** 
``` markdown
c:/users/[user]/appdata/local/arduino15/packages/esp32/tools/xtensa-esp32-elf-gcc/1.22.0-97-gc752ad5-5.2.0/bin/../lib/gcc/xtensa-esp32-elf/5.2.0/../../../../xtensa-esp32-elf/bin/ld.exe: cannot find crt1-sim.o: No such file or directory

c:/users/[user]/appdata/local/arduino15/packages/esp32/tools/xtensa-esp32-elf-gcc/1.22.0-97-gc752ad5-5.2.0/bin/../lib/gcc/xtensa-esp32-elf/5.2.0/../../../../xtensa-esp32-elf/bin/ld.exe: cannot find _vectors.o: No such file or directory
   
collect2.exe: error: Id returned 1 exit status
```
Unfortunately, we don't quite know *why* this error occurs, but it can be fixed by:
* Uninstalling the Arduino IDE
* Deleting c:/users/[user]/appdata/local/arduino15
* Reinstalling the IDE and repeating setup steps for your board

If anyone knows a better way, please feel free to reach out. 

***

**This list is not comprehensive!** If you encounter any additional errors, please feel free to reach out on our [Discord Server](https://discord.gg/lucidvr)