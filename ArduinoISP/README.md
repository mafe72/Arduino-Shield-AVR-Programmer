Arduino Shield AVR Programmer Sketch
----------------

This sketch turns the Arduino into a AVRISP and takes advantage of the Piezo Speaker on pin A3 to provide audible tones.

If you want to program anything other than the standard bootloaders, you will need to add the appropriate "cores" to the Arduino software:

* For a "Breadboard Arduino", which is an Atmega328 running on its internal crystal at 8 MHz, you must install the files from "Breadboard.zip" at http://arduino.cc/en/Tutorial/ArduinoToBreadboard into the "hardware" folder in your Arduino "sketchbook" folder.
* For Attiny chips, there are several cores available:
	* I like [Arduino-Tiny](https://code.google.com/archive/p/arduino-tiny/) core based on work by David A. Mellis, René Bohne, R. Wiersma, Alessandro Saporetti, and Brian Cook because it supports the tone() command if you want to play sounds on a piezo speaker.
	* If you want to program the Attiny2313, you can use the [Attiny](https://github.com/damellis/attiny/) core.

Leds & buzzer:
----------------

- Green LED : HEART - (Heartbeat) shows the programmer is running.
- Red LED : ERROR - Lights up if something goes wrong and the the piezo makes a continuous beep.
- Yellow LED: PROG - (Programming) In communication with the slave, once it is done, the piezo makes a short beep.
- Blue LED: SCK  - (Activity) active when data is transmitted.

Arduino Mega:
----------------

This shield will work with the mega, but needs a 2x2 female header added in the lower right corner and four jumper wires to connect with Mega pins 50 - 53.

Settings:
----------------

1. Upload the ArduinoISP.ino provided on this section. This sketch must be uploaded without the shield in place since the shield has a capacitor to over-ride the reset signal (or you could use a manual reset before upload, like in the old-old days). Alternatively you can use the stock Arduino software "ArduinoISP" sketch included in the "Examples" section. 
2. With the sketch uploaded, install the shield. You should see the green heart LED begin it's pulsing.
3. In the IDE, select "Tools" -> "Programmer" -> "Arduino as ISP".
4. Select the target chip type using "Tools" -> "Boards".
5. Place an IDC 6 Pin (2x3) X 2 Ribbon Cable (jumper cable can also be used) between the "ISP" header and the correct header for the chip type.

Burning:
----------------

Setting fuses is a scary and confusing topic if you look in to it much. Don't bother. They are basically setting that tell the chip how to behave and have to be done only once to a new chip.

1. Place the chip in the ZIFF socket, all the way to the left, with Pin 1 in the lower-left corner.
2. With the correct "board" selected for the target chip, select "Tools" -> "Burn Bootloader".
	* For an Atmega chip going in to a UNO or breadboard, this will set the fuses and upload the correct bootloader.
	* For an Attiny, this just sets the fuses. For us, this primarily concerns chip speed. 

Upload a Sketch:
----------------

1. Load the sketch for the target chip. Start with the basic blink "File" -> "Examples" -> "01.Basics" -> "Blink".
2. Change the "led" variable from "13" to "3".
3. Click the upload icon, or "File" -> "Upload".
4. You should see the yellow LED flash and get an "Upload Complete" message.
5. If all is well, the target chip should start blinking the yellow LED (attached to D3).
