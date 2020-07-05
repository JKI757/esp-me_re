# esp-me_re
Reverse Engineering the remote control protocol on an ESP-ME
The intent of this project is to build a reasonably intelligent remote control to replace the LNK wifi module rainbird provides.  If the remote protocol is more complex than is reasonable to reverse, the faceplate connection will be the next area of research as its output is likely far more simple (most likely just an encoded set of commands to turn on solenoids).  

BOM:
Board P/N: Assy 638321-01
ESPME CPU 19JN15 A-01

PCF2123, 622.103, 14521

HI541, 51K, A9SK

MC9S08LL64CLK, 1N70B, QAR1448K -- this is the main MCU, has LCD controller, Serial, I2C, and SPI interfaces.  
 - https://www.nxp.com/docs/en/data-sheet/MC9S08LL64.pdf
 - Serial is connected to ISP/Debug J3 (6-pin connector without header installed).
 - SPI traces appear to go under the LCD, along with the LCD specific traces from the right side of the MCU.  
 - https://www.nxp.com/docs/en/reference-manual/MC9S08LL64RM.pdf
 
Remote control - J6 on board back, five pin, no ground connection, 1.5vdc on right-most pin (viwing from back of board) with power applied to the board through 9vdc backup battery.  

Old style remote control: RM-1R Remote -- unavailable except from ebay, no reference on rainbird site.
Current style remote: LNK Wifi Module.  Is NOT compatible with this ESP-ME faceplate.  

LNK module:
 - the main chip in this is P/N 450-0163 R3, FCC Id: 0218234 01203 LSR.  Almost certainly this is the wifi chip, but the FCC Database is down so I can't verify this right now. 
 - A secondary MCU (U2) is 441 HD 1BT2
 - Also contains a crystal, 11.059, ABM3C 17F
 - 3630 7182 e3
 - 5 pin connector is marked "ACIN", "MOSI", "GND", "MISO","ACIN"
