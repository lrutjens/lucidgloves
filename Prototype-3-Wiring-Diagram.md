**Basic information on wiring is also included in the Prototype 3.1 Tutorial.**  
See it here: https://www.youtube.com/watch?v=Qj4hqRKiy8g&t=148s

In the most recent version of firmware, the order for fingers is as follows: 
(Corresponding from the pin of the Arduino/ESP32 to the center pin of the potentiometer)

| Input           | Optional? | Nano Pin | ESP32 Pin |
|:--------------- |:---------:|:--------:|:---------:|
| Pinky Finger    | Required  | `A0`     | `36`      |
| Ring Finger     | Required  | `A1`     | `39`      |
| Middle Finger   | Required  | `A2`     | `34`      |
| Pointer Finger  | Required  | `A3`     | `35`      |
| Thumb           | Optional  | `A4`     | `32`      |
| Joystick X Axis | Optional  | `A6`     | `33`      |
| Joystick Y Axis | Optional  | `A7`     | `25`      |
| Joystick Click  | Optional  | `D7`     | `26`      |
| Button 1        | Optional  | `D8`     | `27`      |
| Button 2        | Optional  | `D9`     | `14`      |

The buttons are in pullup configuration.
If you need different pin numbers, no problem, just change them in the firmware (`lucidgloves-firmware.ino`).

This diagram shows how to wire the potentiometers to a Nano. (The breadboard is just for demonstration)
![Wiring Diagram](https://cdn.discordapp.com/attachments/784833028379770930/821538168984698880/unknown.png)