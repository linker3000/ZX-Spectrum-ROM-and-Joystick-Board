**This is a hobby project and comes with no official support. The PCB schematic and board design files are offered 'as is' with no claims made about their fitness for any specific purpose. Use at your own risk.**

# ZX-Spectrum-ROM-and-Joystick-Board

Based on the ZX Spectrum breakout board: https://github.com/linker3000/ZX-Spectrum-Breakout-Board

These are the design details for a ZX Spectrum expansion board that supports EPROM/ROM devices and also provides the control signals for two Kempston-compatible joystick interfaces. This is a self-build project and these notes are suitable for experienced electronics hobbyists and professional engineers who fancy a bit of DIY making.

![Image](proto1.JPG)

![Image](proto2.JPG)

This version of the board has been wire-wrapped. Feel free to use point-to-point wiring if you prefer!

## Features

* The design supports 27x64 (8K), 27x128 (16K) and 27x256 (32K) EPROMS and their EEPROM equivalents (eg: 28C64). The wiring could be adapted to support parallel flash - go for it!

* A rotary BCD DIP switch selects EPROM functionality:

  * 0 = 8K in 2764                                                    
  * 1 = 16K in 27128                                                  
  * 2 = 8K in 1st half of 27128                                       
  * 3 = 8K in 2nd half of 27128                                       
  * 4 = 16K in 1st half of 27256                                               
  * 5 = 16K in 2nd half of 27256                                               
  * 6 = 8K in 1st quarter of 27256                                            
  * 7 = 8K in 2nd quarter of 27256                                            
  * 8 = 8K in 3rd quarter of 27256                                            
  * 9 = 8K in 4th quarter of 27256   

* There's a ROM enable/disable jumper

The main control logic is based on a 22V10 GAL. This is a device that needs programming. I used the low-cost TL866II 'universal programmer' (IMPORTANT: Untick 'Encrypt Ch' otherwise the GAL may not program correctly). The .JED file is ready to upload to the programmer. If you want to edit/change the source .PLD file, you will need a copy of WinCUPL (free from https://www.microchip.com/design-centers/programmable-logic/spld-cpld/tools/software/wincupl) or another CUPL editor.

## Tested ROMS

* Dr Ian Logan's diagnostics ROM (8K): http://www.fruitcake.plus.com/Sinclair/Interface2/Cartridges/Files/ROM_Dumps/System_Test_ROM.bin
* Phil Ruston's excellent diagnostics ROM V1.5 (16K): http://blog.retroleum.co.uk/electronics-articles/a-diagnostic-rom-image-for-the-zx-spectrum/
* Brendan Alford's diagnostics ROM (16K): https://github.com/brendanalford/zx-diagnostics/wiki/Firmware

## Schematic

![Image](schematic.JPG)

 
