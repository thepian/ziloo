# Surface mounted Bluetooth / USB Charging PCB Design

I'm looking for a connectivity PCB with nRF52840 that routes commands and images between a separate PCB and external
systems over USB and Bluetooth. It also plays audio over an I2S speaker(s).

It consists of a single board. [Hub Board](./HUB_BOARD.md)


You will,

* Design diagram for the board
* Review the chosen components
* Review the designs for future European compliance application
* Review suggestions with PO before finishing
* List BoM
* Plan ways to quality test the board
* Consider design improvements towards assembly and production
* Produce a small test batch with PCBWay or JCLPCB (White 1mm)
* Deliver test PCBs with mounted components & design files

It's all in a private GitHub repo. At the end I'd want to check design files into the repo.
I will want to have design files in addition to manufacturing files that can be used for future
revisions. They must be in a format(or alternate format) that can be revised by low cost software.

## Visual overview 

![Power Module](./Power_Module.jpg)


## LOG


Yes I will send 2 PCB to you, one I will left for me if we will need to figure out any issue, after you check it and they will work proper I may send it also to you but later.

For this moment I did the aditional wires and fixture for testing the PCB works, you may see them on the photo. I will sent 1 set to you, but for the first testing of the PCB you will need to buy 2 things:

1. MAX77860EVKIT https://eu.mouser.com/ProductDetail/Maxim-Integrated/MAX77860EVKIT?qs=%2Fha2pyFadugu5ENo7u8%252Bdppd4Gve%2FW8UUp7YZHVw1aMOk8bUTI3KwQ%3D%3D - this one you need to have access to the MAX77860 registers for configuration it.
2. Battery with 3 wires - i can't send you the battery, the post companny doeasn't allow me to do this. You may buy it here: I will prepare wires to connect it. https://www.ebay.com/itm/184854611075?hash=item2b0a318483:g:NuoAAOSw2QxcmEug - you may buy anywhere, but then please share link with me I will prepare wires for easily connect the battery.

For this moment, charger work and USB2.0, I need to check the USB3.0 and the max load current capabilities.

I will add the manufacturing cost(804$) offline in the Upwork.




[1/24/2021 10:11:01 PM] Henrik Vendelbo: About voltage. As I understand the nRF52840 it is in 1.8V or 3.3V for all IO, so all peripherals will use the same. Most sensors I plan for use 3.3 by default, and some need at least 2V. Can you tell me what the advantage of 1.8V is? Will level shifters be needed for 3.3V?

[1/24/2021 10:11:46 PM] Henrik Vendelbo: Did you get answer from support?

[1/25/2021 1:57:30 PM] Alex Sanok: Hello Henrik,

Yes they response us, but didn't give any reference design, so we take a solution from the Microchip.

Regarding the 1.8V or 3.3V supply, with 1.8V power consumption will be less. If you will use 3.3V sensor then, yes you will need to additional level shifter to communicate between 1.8V and 3.3V.

If we will not fit into 19mm then we will try to increase the width of PCB but before we will not.



The pins of the USB will not stick out on the bottom side.
I will double check our solution and try to use as small components as possible.
I will check datasheet of Raytac MDBT50Q-P1M and check the issue with 1.8V.

I checked datasheet about MDBT50Q-P1M and this module could use 1.8V .

