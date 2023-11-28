# EPDiy v7 smaller version

The goal of this PCB is to make a version with a smaller footprint and minimal components.
All this might change as the idea develops but initially the plan is the following:

- Same v7 idea using TPS65185 and PCA9535PW as IO expander and slow signals manager
- Only 8 bit connectors for now: 6 inch (33 pin) and 9 inch (34 pin) FPC if possible located in a way where the USB is left at the edge of the case
- SD Card, since we have many IOs available, connected with 4 data pins so it is as fast as possible. This does not necessarily needs to be at the side of the case since we have an USB port that can be used as internal mass storage device.
- Only one USB that goes directly to S3, this might be used to flash it too, but additionally we will provide
- External UART pinup: TX, RX, RST, DTR, 5V, GND in case you need to flash it and the DFU USB does not work (Might happen)
- No UART chip, hence no need to add an additional LDO, saving space
- Expose all non-used GPIOs. 

The first version will not have epdiy but only the bare silicon and some GPIOs exposed. The goal is to make many checks in the first revision to have the basics right before even attempting to add the epdiy high voltage circuit and rest of the signals for an 8 bit epaper display.

**IMPORTANT: Do not send this by any means to fabrication.** The RF is like dark Magic for me and I'm 99% sure that the WiFi / BLE part of this board will not work.
As you can read below, learning this is actually very hard, and RF is not something you can **copy and paste** from another board. The RF part has to match and be callibrated for your board in S3 and newer chips, otherwise the Silicon itself might get hot and do not work correctly.

## Selected S3 SoC

[ESP32-S3(FN8)](https://jlcpcb.com/partdetail/EspressifSystems-ESP32_S3_FN8/C2913196) 8 MB flash needs external PSRAM chip


## SD schematic

For the SD schematic we are going to base our design on the one we already tested in https://vroland.github.io/epdiy-hardware/ (check epdiy v7 tester board w/ SD)

![v7 tester PCB with SD card](https://vroland.github.io/epdiy-hardware/boards/40_pins_PCB_tester-front.png)

## The RF problematic

After publishing this idea and [sharing it with my colleagues in twitter](https://twitter.com/martinfasani/status/1728160953789829346), my electronic mentors, that know a hell lot more than myself told me:

> Learning about PCB stack-ups and impedance matching - super helpful skill well beyond RF stuff. Learning how to use a VNA + PCB inductance/capacitance/reactance is also good knowledge to have in the toolkit. 

> S2 and original ESP32 you can connect a shoelace to the LNA pin and it will kinda work. S3 and newer chips are completely unforgiving - They get super duper hot if there's a mismatch, and the S3 loves to shut down the TX side without provocation!
(Seon, @unexpectedmaker)

As a base we are going to use a board from designers that know how to resolve the RF problematic. This topic is still on research.

## Research links

https://github.com/tinypico/tinypico-hardware/blob/master/TinyPICO%20V2%20Schematics/TinyPICO_V2_P2_Schematic.pdf
https://github.com/sparkfun/ESP32_Thing/tree/master/Hardware Sparkfun has most of their boards open source (Note: They use Eagle software to design their boards)
https://esp32.com/viewtopic.php?t=31083 S3 only with SoC
https://www.reddit.com/r/PrintedCircuitBoard/comments/yhefyf/schematics_design_review_request_for_my_esp32s3/ esp32S3 review schematics
https://jlcpcb.com/partdetail/Ect-ECT818000071/C437252 Inner needle IPEX Board Edge 1.25mm 
