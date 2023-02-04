# Macintosh-IIx-RAM-SIMM

4MB PAL RAM SIMMs, for the Macintosh II and IIx

While the Macintosh II and IIx were designed with sufficient address lines to handle up to 128MB of RAM in two banks of 4 SIMMs (giving a total of 8 slots), standards for DRAM chip design changed between the design of these computers and the release of the first 4MB SIMMs causing issues. Additionally, both the Mac II and IIx have a number of other RAM oddities.

Both require either a replacement 32bit Clean ROM, or the "MODE32" extension to address more than  8MB of RAM. Additionally, the II also needs a PMMU to be able to address more than 8MB of memory. If using the original Mac II ROM and the MODE32 software, the II is then to 68MB of RAM (1MB SIMMs in Bank A and 16MB in Bank B) due to additional issues with the ROM. The Mac II can address the full 128MB of RAM if ROMs from a Mac IIx are swapped in.

Regarding changes to the DRAM chip standards, one specific change meant that a while in 1MB SIMMs, the WE signal was "don't care" during a CAS before RAS (CBR) refresh, on larger SIMMs, a test mode was added which would be triggered when the WE signal was held low during the CBR refresh.

This means that placing a conventional 30Pin SIMM in a II or IIx causes the RAM to almost instantly go into the test mode, become unresponsive, and the computer fails to boot, instead triggering a "death chime".

Manufacturers of SIMMs for the Macintosh realised that they could avoid this by capturing the refresh signals as they came onto the SIMM and applying additional logic through the use of a PAL (Programmable Array Logic) chip, designed to ensure that the specific circumstances did not occur. Later again, it was realised that this could be simplified through careful timing to a minimal circuit by using a single 4 gate "OR" chip (74F32).

The PCB described within is for a 4MB SIMM, using these (and all the other software and ROM changes required to fully take advantage of larger SIMMS), it is possible to extend the RAM of a II or IIx to 32MB - helpfully more than the 8MB ceiling caused by the use of normal 30 pin SIMMs!

To assemble, you will require -
* 4x PCBs.
* 32x MT4C1004 Memory chips (or equivalent - take care with equivalents).
* 36x 1210 220nF Capacitors - the height of these is critical. Buy an excess and only use the parts which are 0.6mm or less.
* 4x 74F32 logic chips.

Assembly is self explanatory, but difficult. The capacitors must be perfectly flat and reflow soldering is recommended for the RAM chips as there is insufficient room to easily get a soldering iron between the two ranks of chips (although it is possible, but you can't see what you're doing at all!).

Good luck. Let us know how it goes here : https://68kmla.org/forums/topic/59817-please-help-me-figure-out-what-the-deal-is-with-this-iix-ram/
