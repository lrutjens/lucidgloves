Firmware Pinouts. Trigger and Calibration are shared by default on ESP32.
| Input           | Optional? | Nano Pin | ESP32 Pin |
|:--------------- |:---------:|:--------:|:---------:|
| Pinky Finger    | Required  | `A0`     | `36`      |
| Ring Finger     | Required  | `A1`     | `39`      |
| Middle Finger   | Required  | `A2`     | `34`      |
| Pointer Finger  | Required  | `A3`     | `35`      |
| Thumb           | Required  | `A4`     | `32`      |
| Joystick X Axis | Optional  | `A6`     | `33`      |
| Joystick Y Axis | Optional  | `A7`     | `25`      |
| Joystick Click  | Optional  | `7`     | `26`      |
| Button 1        | Optional  | `8`     | `27`      |
| Button 2        | Optional  | `9`     | `14`      |
| Trigger         | Optional  | `10`    | `12`      |
| Grab            | Optional  | `11`    | `13`      |
| Pinch           | Optional  | `12`    | `23`      |
| Calibration     | Required  | `13`    | `12`      |
| Pinky Motor     | Optional  | `2`     | `5`       |
| Ring Motor      | Optional  | `3`     | `18`      |
| Middle Motor    | Optional  | `4`     | `19`      |
| Pointer Motor   | Optional  | `5`     | `21`      |
| Thumb Motor     | Optional  | `6`     | `17`      |
| Menu            | Optional  | `8`     | `27`      |

The buttons are in pullup configuration. If you need different pin numbers, no problem, just change them in the firmware (`lucidgloves-firmware.ino`).

## Prototype 4 wiring diagram (ESP32 Version)
This method uses two powerbanks or a powerbank with two outputs.
![Prototype 4 ESP32 Wiring Diagram](https://media.discordapp.net/attachments/784992216707760128/884805008917401661/unknown.png?width=1188&height=660)