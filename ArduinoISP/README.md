Arduino Shield AVR Programmer Sketch
----------------

This sketch turns the Arduino into a AVRISP and takes advantage of the Piezo Speaker on pin A3 to provide audible tones.

Leds & buzzer
----------------

- Green LED : HEART - (Heartbeat) shows the programmer is running.
- Red LED : ERROR - Lights up if something goes wrong and the the piezo makes a continuous beep.
- Yellow LED: PROG - (Programming) In communication with the slave, once it is done, the piezo makes a short beep.
- Blue LED: SCK  - (Activity) active when data is transmitted.
