# bpi-public
Info on IoT development using BPI boards that can be publicly shared
This repository holds information on developing software on BPI boards. The intent is to share information that might help other developers (or my future self :)) understand stuff which is unclear, undocumented or ill-documented.
## BPI R3 
### BPI R3 pinout
[Link to PDF file](https://github.com/rportab/bpi-public/blob/main/bpi-r3_con1.pdf)
This is a pinout description for CON1 connector (aka GPIO).

I found that there is little information on how to use GPIO on the R3 board and took me quite some time to understand the errors I was getting were due to the line being used by someone else (the kernel).

The main issue was [`gpioinfo` not working on OpenWRT 23.05](https://github.com/openwrt/packages/issues/23548), so I didn't find a way to tell which lines were used. Moving to OpenWRT 24.10.1 helped with that.

Pins in green are tested to be free both in OpenWRT 23.04 and 24.10.1. Although `gpioinfo` does not work on 23.05, `libgpiod` does work. I tested it using  [this simple example](https://github.com/brgl/libgpiod/blob/master/bindings/python/examples/toggle_line_value.py)

Info has been extracted from a schematic that can be found [here](https://cdn.hackaday.io/files/1861277963257568/BPI-R3-V11-SCH-Public.pdf)
