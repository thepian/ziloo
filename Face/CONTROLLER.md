The Face Board will normally be connected to the Hub Board, but can also be connected to a Raspberry Pi 
via a dedicated cable to test or interface directly.


## Controller Connector

Above one eye there is a 40 pin FPC connector for direct control of the board.
The same connector is duplicated on flipside of the board.
The connector is made to fit well with [Raspbery Pi 4 GPIO pins](https://elinux.org/RPi_BCM2711_GPIOs#I2CSL_SCL_SCLK).

1. JTAG TMS
2. JTAG TCK
3. JTAG TDO
4. JTAG TDI
5. GND
6. Control SDA
7. Control SCL
8. nc
9. Occi1 TXD.2
10. Occi1 RXD.2
11. Occi2 TXD.3
12. Occi2 RXD.3
13. Occi1 Power
14. Occi1 ISP
15. Occi2 Power
16. Occi2 ISP
17. Sensor Power1
18. Sensor Power2
19. Crosslink Power
20. Control SPI SCK
21. Control SPI MOSI
22. Control SPI MISO
23. Control SPI Crosslink SS
24. Control SPI Occi Flash SS
25.  GND
26.  GND
27.  GND
28. VSYS
29. VSYS
30. VSYS

Separate JTAG pinouts/connector?

//23. DAT1 - 3 ?
32. 
33. 
39. FastLED / ZIO 3


While being similar to the GPIO 40 pin connector it differs a bit so it can be adopted using different cables between the two connectors. It can be connected to do:

- Direct programming ISP UART (with RTS/CTS on test boards)
- Direct programming ISP UART with Feature pins RST/EN/BOOT
- Direct OpenOCD JTAG with SPI
- Direct read/write to Occi1/Occi2/Tempor/Common flash chips/SD Card
- Inspection of Power/Sensor component states over I2C
- Disabling [The Stem](./STEM.md)
- Taking over [The Stem](./STEM.md) master SPI/I2C roles

The signals must be 3.3V. They are not protected, so care must be taken to not connect 5V signals.
The 5V supply can be used to drive the device board when it isn't self powered. The maximum draw is 1A.
The supplied voltage can be 3.5V - 5V.
