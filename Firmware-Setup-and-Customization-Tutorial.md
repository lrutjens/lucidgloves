### Setup ### 
**The setup of how to flash the firmware onto your ESP32/Arduino is described in the Prototype 3.1 Tutorial** (Also applies to Prototype 4).  
You can see it here: https://youtu.be/Qj4hqRKiy8g?t=543
**Note: this video was made on an older version of the firmware which will display a legacy encoding scheme in the serial monitor (numbers seperated by `&`s). Newer versions of the firmware use alpha encoding (letters followed by a number, like `A2301B2391C3431D3313E1234`) and that's what you should be looking for.**

This is how to customize the configuration for the firmware to work with different boards, glove configs, etc.

This configuration is stored inside of **lucidgloves-firmware.ino**.

* `DEBUG_LED` - The pin on the board to be used for LED debugging.  
* `COMMUNICATION` - Set this to your preferred communication protocol.  
  - `COMM_SERIAL` - USB Serial Communication  
  - `COMM_BTSERIAL` - Bluetooth Serial Communication  
* `LOOP_TIME` - The time to be elapsed between loops, how many ms between data sends  
* `CALIBRATION_LOOPS` - The number of loops that should occur until the glove stops calibrating. Set to -1 to always calibrate.  
* `SERIAL_BAUD_RATE` - The baud rate of the serial communication. Only used if `COMMUNICATION` is `COMM_SERIAL`  
* `BTSERIAL_DEVICE_NAME` - The name of the Bluetooth device advertized. Only used if `COMMUNICATION` is `COMM_BTSERIAL`  

**Recommended Pin Configuration**  
| #define | Description | Nano | ESP32 |
|:--- |:--- |:---:|:---:|
| `PIN_PINKY` | The analog pin to be set for the pinky finger potentiometer | `A0` | `36` |
| `PIN_RING` | The analog pin to be set for the ring finger potentiometer | `A1` | `39` |
| `PIN_MIDDLE` | The analog pin to be set for the middle finger potentiometer | `A2` | `34` |
| `PIN_INDEX` | The analog pin to be set for the index finger potentiometer | `A3` | `35` |
| `PIN_THUMB` | The analog pin to be set for the thumb potentiometer | `A4` | `32` |
| `PIN_JOY_X` | The analog pin to be set for the joystick x-axis | `A6` | `33` |
| `PIN_JOY_Y` | The analog pin to be set for the joystick y-axis | `A7` | `25` |
| `PIN_JOY_BTN` | The GPIO pin to be set for the joystick click | `7` | `26` |
| `PIN_A_BTN` | The GPIO pin to be set for the A button | `8` | `27` |
| `PIN_B_BTN` | The GPIO pin to be set for the B button | `9` | `14` |
| `PIN_TRIG_BTN` | The GPIO pin to be set for a trigger button. *Unused if using gestures* | `10` | `12` |
| `PIN_GRAB_BTN` | The GPIO pin to be set for a grab button. *Unused if using gestures* | `11` | `13` |
| `PIN_PNCH_BTN` | The GPIO pin to be set for a pinch button. *Unused if using gestures* | `12` | `23` |

* `ANALOG_MAX` - The maximum analog value to be used. Depends on the ADC resolution.
  - Use `1023` for Arduino, `4095` for ESP32
* `FLIP_POTS` - Whether or not the finger potentiometer values need to be flipped.

* `TRIGGER_GESTURE` - Whether or not to recognize gestures for the trigger (closing your index finger)  
* `GRAB_GESTURE` - Whether or not to recognize gestures for grab (closing your hand)  
* `PINCH_GESTURE` - Whether or not to recognize gestures for pinch (pinching with thumb and index finger)  

* `JOYSTICK_BLANK` - Set this to true if you don't have a joystick plugged in. Set false if you have a joystick.
* `JOY_FLIP_X` - Flip the x-axis values in the joystick
* `JOY_FLIP_Y` - Flip the y-axis values in the joystick

* `NO_THUMB` - If you have no thumb plugged in.


### Adding Required ESP-32 Libraries ###

Using ESP-32 Dev Boards, which are required if you want to use Bluetooth Serial to connect your gloves wirelessly, requires you to install additional packages to your Arduino IDE and a specific driver. Below is the procedure for doing so.

Most boards use the Silabs CP210x USB to UART chip, for which you have to install the driver:

1. Go to [Silicon Labs' official driver download page](https://www.silabs.com/developers/usb-to-uart-bridge-vcp-drivers)
2. Go to the downloads section and download the "CP210x Windows Drivers" (third in the list).
3. Extract the .zip and run `CP210xVCPInstaller_x64.exe`.
4. Your ESP32 should now show up in your devices manager under ports as `Silicon Labs CP210x USB to UART Bridge (COM<number>)`. This is the port you should select in your IDE. If it doesn't show up, make sure you are using a data capable USB cable.

Adding the ESP32 package to your Arduino IDE:

1. Go to File > Preferences in your Arduino IDE
2. In the "Additional Board Manager URLs" field, enter this link: https://dl.espressif.com/dl/package_esp32_index.json and click the OK button
3. Go to Tools > Board > Boards Manager
4. Search "esp32" and install the "ESP32 by Espressif Systems" package.
5. Select your ESP32 board from Tools > Board  (Use ESP32 Dev Module if you are unsure)

**Adding ESP32Servo library for haptic servo control**
1. Go to Tools > Manage Libraries in Arduino IDE
2. Search for ESP32Servo in the search bar
3. Find the ESP32Servo library authored by Kevin Harrington, click 'More info...' and then Install

All of your packages should be installed and ready to go.
