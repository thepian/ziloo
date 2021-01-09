## GPIO Extension

### 16 bit IO via I2C

[MCP23017](https://revspace.nl/MCP23017)
[Adafruit MCP230xx](https://github.com/adafruit/Adafruit_CircuitPython_MCP230xx)

![IO Expander board](https://cdn-learn.adafruit.com/assets/assets/000/072/344/original/adafruit_products_GPIOBonnet_Pinouts_Address_Select.jpg?1551823655)

[IO Expander board](https://learn.adafruit.com/assets/72344)

### 16 bit IO via SPI

10MHz

MCP23S18 has chip select.

[MCP23S17 datasheet](http://ww1.microchip.com/downloads/en/DeviceDoc/20001952C.pdf)
[MCP23S18 datasheet](http://ww1.microchip.com/downloads/en/DeviceDoc/22103a.pdf)


### Fast Shift registers

Max 45MHz
[SN74ALS166 8-bit PISO](https://www.ti.com/lit/ds/symlink/sn74als166.pdf)

Max 100MHz
[74F164 8-bit SIPO](http://www.farnell.com/datasheets/72100.pdf)


### LVDS Transmitter

238Mb/s throughput 4:28 3.3V
[SN75LVDS83 FlatLink Transmitter](https://www.ti.com/lit/ds/symlink/sn75lvds83.pdf?ts=1610292513091&ref_url=https%253A%252F%252Fduckduckgo.com%252F)

1.8V - 3.3V input
135Mpixels/s 4 channel : 28 bit
[SN75LVDS83B](https://www.ti.com/lit/ds/symlink/sn75lvds83b.pdf?ts=1610211046035&ref_url=https%253A%252F%252Fwww.ti.com%252Fproduct%252FSN75LVDS83B)

1.8V - 3.3V input
135Mpixels/s 28bit:4channel 
[SN65LVDS93A-Q1](https://www.ti.com.cn/lit/ds/symlink/sn65lvds93a-q1.pdf?ts=1610299075910&ref_url=https%253A%252F%252Fduckduckgo.com%252F)

21:3 channel
SN75LVDS84A

14 bit full duplex
[SN75LVDT1422](https://www.ti.com/product/SN75LVDT1422)

1.8V
SubLVDS 1755Mbps
[SN65LVDS301 Flatlink 3G](https://www.mouser.ch/new/texas-instruments/ti-sn65lvds301-display-serial-interface-transmitter/)



### Flat Panel Display Link (FPD-LINK)

Due to the higher demand for better displays, bridging applications has become increasingly popular. One very common application interface is the Flat Panel Display Link (FPD-LINK) interface. The Low Voltage Differential Signaling (LVDS) standard is commonly used for high-speed differential interface in consumer devices, industrial control, medical and automotive. The LVDS interface offers low voltage, low power and improved signal integrity advantages over single-ended technology. Applications such as Channel Link, FPD-Link, and Camera Link use LVDS interface for physical layer.

7:1 LVDS interface is a popular standard for source synchronous interfaces which consist of multiple data bits and clocks. Typically, 1 channel of 7:1 LVDS interface consists of 5 LVDS pairs (1 clock, 4 data) depending on the data type it supports.

[Lattice FPD-LINK Transmitter](https://www.latticesemi.com/en/Products/DesignSoftwareAndIP/IntellectualProperty/IPCore/IPCores04/FPDLINKTransmitter)

[Open LVDS Display Interface (OpenLDI) v0.95 specifications](https://glenwing.github.io/docs/OpenLDI-0.95.pdf)

[Display Industry Standards Archive](https://glenwing.github.io/docs/)

[Displayport over USB-C](https://www.displayport.org/displayport-over-usb-c/)

[DisplayPort Alt-Mode](https://vesa.org/featured-articles/vesa-releases-updated-displayport-alt-mode-spec-to-bring-displayport-2-0-performance-to-usb4-and-new-usb-type-c-devices/)

DS90C387
DS90C388


### References

[AG9321 USB-C to HDMI/I2C Dock chipset](https://www.dianyuan.com/upload/community/2020/06/09/1591689193-33039.pdf)
[ANX7688 4K HDMI + USB3 -> USB-C MUX Bridge](https://www.analogix.com/en/system/files/AA-002281-PB-6-ANX7688_Product_Brief.pdf)

