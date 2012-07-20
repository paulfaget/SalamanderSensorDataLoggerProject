Salamander Project
BatBoard information

This portion of the salamander project is a daughter card that is intended to mate to the Moteiv tmote sky radio module. It acts as a voltage controller to provide 3v to the radio and 5v to the sensors and also provide level translation for connected sensors.

Input voltage range:5.38V-16V
Power switch on when switched AWAY from battery connector.

Pinouts: 
SV1:Pin 2 - GIO3 interface to Mote
SV2:Pin 2 - UART0 TX interface to Mote (SEE NOTE 1!)
SV2:Pin 6 - 3V power to Mote
SV2:Pin 10 - GND 
X1: P - 5V power to sensor board
X1: D - 5V level-translated 1-wire
X1: G - GND to sensor board

Resistor Positions:
R2: Populate to level-translate 3V logic UART TX to 5V on X1-D
P3: Populate to level-translate 1-wire from 5V to 3V
****DO NOT POPULATE BOTH RESISTORS SIMULTANEOUSLY!****

NOTE 1:
As the project currently stands, UART0 is not enabled on the radio board. The ability to choose between interfacing this board between 1-wire and the UART allows a radio to be assigned as a "listener," and to connect to loggers that can only accept 5V logic. This is accomplished by populating the R2 *OR* R3 positions with a 0 Ohm resistor as described above. With the firmware currently on the radios, UART0 is not enabled: the UART1 output must be tapped from the FTDI serial->USB chip, and jumpered to the left position of the R2 solder pad and neither R2 or R3 should be populated.