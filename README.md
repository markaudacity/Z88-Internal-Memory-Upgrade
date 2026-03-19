This is a very alpha-stage design for a single-board internal RAM/Flash ROM upgrade for the Cambridge Z88 computer. 

The Z88 can address up to 4 MB of RAM and ROM in three physical expansion slots and the internal RAM and ROM. Since the internal RAM and ROM are addressed as logical slot 0, they can use the full address space, which is not used by the base 32 kB RAM and 128 kB ROM. Normally to upgrade internal memory like this, one would just desolder the original RAM and ROM, replace them with sockets, and install new flash and bigger RAM, but in the Z88, there is both: 
1) very little room between the board and the keyboard frame, and
2) the existing chip footprint does not have the A17 and A18 address lines required to increase the RAM and ROM to 512kB, from 32kB and 128kB, respectively.

There is an existing mod to upgrade the internal memory that has been floating around since some time in the early 90s, which involves lifting pins on the replacement 512 kB flash and SRAM chips and soldering three or four fly wires to various locations on the board. Very much not a straightforward job, and the best writeup for it available on the internet has at least two of the address lines mislabeled, so the top two address bits are flipped. This doesn't really matter for RAM, since everything is going to be written with those same address lines swapped, but it sure does for the ROM. I chased this around for several hours over a few weeks before I realized the writeup had it wrong. 

Since the A17 and A18 address lines and slot-select lines are all available on vias, I had the idea to create a board that has pins at the corresponding locations that can simply be soldered into place like any other through-hole device.

**As of March 2026, I have still not had boards made or soldered up any prototypes, so if you build one of these, it is the most YMMV, do-so-at-your-own-risk, safety-third, hold-my-beer project.**
