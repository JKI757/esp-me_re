# esp-me_re
Reverse Engineering the remote control protocol on an ESP-ME
The intent of this project is to build a reasonably intelligent remote control to replace the LNK wifi module rainbird provides.

BOM:
Board P/N: Assy 638321-01
ESPME CPU 19JN15 A-01

PCF2123, 622.103, 14521

HI541, 51K, A9SK

MC9S08LL64CLK, 1N70B, QAR1448K -- this is the main MCU, probably runs the display over SPI.  
 - https://www.nxp.com/docs/en/data-sheet/MC9S08LL64.pdf
 
Remote control - J6 on board back, five pin, no ground connection, 1.5vdc on right-most pin (viwing from back of board) with power applied to the board through 9vdc backup battery.  

Old style remote control: RM-1R Remote -- unavailable except from ebay, no reference on rainbird site.
Current style remote: LNK Wifi Module.  Is NOT compatible with this ESP-ME faceplate.  

