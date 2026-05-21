# C64-Universal-SRAM-memory-replacement
Replace that old unreliable DRAM in your C64 with SRAM!

 Inspired by penfold42 on the Lemon64 forum.

Bonus for shortboard users!
---------------------------------------
Testing so far has shown that this mod eliminates the VSP bug!

The main goal of this little experiment is to see if the SRAM has any immunity to the VIC-II VSP bug that plagues many shortboard C64s and some longboard C64s.

This board has been designed to fit under the character generator ROM on either the long or short motherboards.  It will also work in the KERNAL and BASIC sockets on the long board.

Basic construction
-------------------------

64KB, 128KB and 256KB SRAMs in a "SOP32L" or similar package,  are compatible as long as they conform to the standard pinout.  64KB SRAMS can be harvested (carefully) from SNES Stuntrace FX and DooM carts.  128KB SRAMS are still relatively easy to come by new (as of 2016).  Use those, cause destroying working carts for parts is a crime...  Okay, it /should/ be. 

C1 and C2 are basic power bypass caps.  I just used some spare 100nf parts I had lying around.

The small IC just above the caps is a single inverter gate.  There are differing part numbers among the various manufactures, but what you are looking for is a inverter in a SOT23-5 package designed for 5V operation.  It would probably help to get the TTL compatible version.  The part number printed (74HCT1G04) is a guide only.

Header Wiring
--------------------
Pins 1,3,4 & 5 connect the the motherboard's DRAM address lines MA4, MA5, MA6 & MA7.  For the 4146s used on most longboards, these are pins 9,10,11 & 13.  For the 41464 used on the shortboards and later longboards, use pins 7,8,10 & 14.  Do not cross check these with the datasheets as Commodore did not.  Following the datasheet (for the 41464 at least) will result in screen corruption and a lower bytes free reported on bootup.  These can be connected in any order, Commodore didn't care and so doesn't the memory!

Pin 2 is connected to the DRAM R/W line, which is pin 3 and 4 for the 4146 and 41464 respectively.

Pin 6 is connected to the DRAM CAS line.  Pin 15 for the 4146 and pin 16 for the 41464.

Finally, pin 7 is connected to the DRAM RAS line.  Pin 4 for the 4146 and pin 5 for the 41464.
