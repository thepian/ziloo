A Raspberry Pi 4 is used as an optional controller of the device. It can connect directly
to the dedicated MCUs and other chips without going through The Stem. With this form of connection
the Stem can be disabled.

## Control SPI

The Stem is Master by default. The Controller can take over. The Control SPI bus can be used while
resting or awake equally. Slaves are responsible for responding only when feasable. For instance,
direct MCU flash access should only be available when the MCU is off.

- Access MCU flash directly (MCU is off)
- Access Monitor SD Card directly (Monitor is off)
- Feature pins (direct CS pins)
- Sending instructions to Sensor MCUs

Controller is Master Pin: Determines if the Controller is master on Stem/Gut I2C and Control SPI.
Otherwise the Stem is the master.

The Control SPI is considered trusted in that it grants the sender full control of the system.
The Stream SPI is less trusted as it is exposed to the Monitor, which expose the device to the Internet.
For this reason the Control SPI is not connected to the Monitor MCU.


## Controller Connector

Above one eye there is a 40 pin FPC connector for direct control of the board.
The same connector is duplicated on flipside of the board.
The connector is made to fit well with [Raspbery Pi 4 GPIO pins](https://elinux.org/RPi_BCM2711_GPIOs#I2CSL_SCL_SCLK).

1.  Controller is Master (high if The Stem should be Control/Stem/Gut Slave)
2.  5V
3.  Spare I2C SDA 
4.  5V
5.  Spare I2C SCL
6.  GND
7.  TXD.3 Occi2
8.  CTS.5 Monitor / TXD.0 Spare
9.  GND
10. RTS.5 Monitor / RXD.0 Spare
11. Control SPI Features CE1
12. Control SPI Features CE0
13. JTAG TMS
14. TXD.1 Spare
15. RXD.1 Spare
16. JTAG TCK
17. SWDCLK
18. JTAG TDO
19. Slave(Master) Gut SDA
20. JTAG TDI
21. RXD.4 Tempor
22. SWDIO
23. Slave(Master) Gut SCL
24. TXD.4 Tempor
25. ZIO 1
26. RTS.3 Occi2 (Alt: ?)
27. TXD.2 Occi1
28. RXD.2 Occi1
29. RXD.3 Occi2
30. ZIO 2
31. CTS.3 Occi2 (Alt: ?)
32. TXD.5 Monitor
33. RXD.5 Monitor
34. (Master/Slave) Control SPI MOSI / (Slave) Control SDIO CMD
35. (Master/Slave) Control SPI MISO / (Slave) Control SDIO DAT0
36. (Master/Slave) Control SDIO DAT1
37. (Master/Slave) Control SDIO DAT2
38. (Master/Slave) Control SDIO DAT3
39. FastLED / ZIO 3
40. (Slave) Control SPI SCLK

While being similar to the GPIO 40 pin connector it differs a bit so it can be adopted using different cables between the two connectors. It can be connected to do:

- Direct programming ISP UART (with RTS/CTS on test boards)
- Direct programming ISP UART with Feature pins RST/EN/BOOT
- Direct OpenOCD JTAG with SPI
- Direct OpenOCD  SWD with SPI
- Direct read/write to Occi1/Occi2/Tempor/Common flash chips/SD Card
- Inspection of Power/Sensor component states over I2C
- Disabling [The Stem](./STEM.md)
- Taking over [The Stem](./STEM.md) master SPI/I2C roles

The signals must be 3.3V. They are not protected, so care must be taken to not connect 5V signals.
The 5V supply can be used to drive the device board when it isn't self powered. The maximum draw is 1A.
The supplied voltage can be 3.5V - 5V.

### Raspberry Pi Master Programmer

This is used to Flash updates to MCUs, and access Flash chips directly while the device is resting.

1.  Controller is Master - 3.3V 10KOhm
2.  5V
3.  Master Gut SDA - GPIO 2
4.  5V
5.  Master Gut SCL - GPIO 3
6.  GND
7.  TXD.3 Occi2 - GPIO 4
8.  CTS.5 Monitor - GPIO 14
9.  GND
10. RTS.5 Monitor - GPIO 15
11. Control SPI Features CE1 - GPIO 17
12. Control SPI Features CE0 - GPIO 18
13. JTAG TMS - GPIO 27
14. nc
15. nc
16. JTAG TCK - GPIO 25
17. SWDCLK - GPIO 22
18. JTAG TDO - GPIO 24
19. nc
20. JTAG TDI - GPIO 26
21. RXD.4 Tempor - GPIO 9
22. SWDIO - GPIO 23
23. nc
24. TXD.4 Tempor - GPIO 8
25. nc
26. RTS.3 Occi2 - GPIO 7
27. TXD.2 Occi1 - GPIO 0
28. RXD.2 Occi1 - GPIO 1
29. RXD.3 Occi2 - GPIO 5
30. nc
31. CTS.3 Occi2 - GPIO 6
32. TXD.5 Monitor - GPIO 12
33. RXD.5 Monitor - GPIO 13
34. (Master/Slave) Control SPI MOSI / (Slave) Control SDIO CMD - GPIO 20
35. (Master/Slave) Control SPI MISO / (Slave) Control SDIO DAT0 - GPIO 19
36. (Master/Slave) Control SDIO DAT1
37. (Master/Slave) Control SDIO DAT2
38. (Master/Slave) Control SDIO DAT3
39. FastLED / ZIO 3 - GPIO 16
40. (Slave) Control SPI SCLK - GPIO 21

Unallocated GPIO 10, 11


### SD Card / Flash Update Connector

This connector can be used to update Monitor SD Card and Common SPI while the device is resting.

1.  Controller is Master - GPIO 4
2.  5V
3.  Spare Gut SDA - GPIO 0
4.  5V
5.  Spare Gut SCL - GPIO 1
6.  GND
7.  nc
8.  nc
9.  GND
10. nc
11. Control SPI Features CE1 - GPIO 17
12. Control SPI Features CE0 - GPIO 18
13. nc
14. TXD.1 Spare - GPIO 8
15. RXD.1 Spare - GPIO 9
16. nc
17. nc
18. nc
19. Slave/Master Gut SDA - GPIO 10 - GPIO 2
20. nc
21. nc
22. nc
23. Slave/Master Gut SCL - GPIO 11 - GPIO 3
24. nc
25. nc
26. nc
27. nc
28. nc
29. nc
30. nc
31. nc
32. nc
33. nc
34. (Master/Slave) Control SPI MOSI / (Slave) Control SDIO CMD - GPIO 23 - GPIO 20
35. (Master/Slave) Control SPI MISO / (Slave) Control SDIO DAT0 - GPIO 24 - GPIO 19
36. (Master/Slave) Control SDIO DAT1 - GPIO 25
37. (Master/Slave) Control SDIO DAT2 - GPIO 26
38. (Master/Slave) Control SDIO DAT3 - GPIO 27
39. FastLED / ZIO 3 - GPIO 16
40. (Slave) Control SPI SCLK - GPIO 22 - GPIO 21

This connector also branches to the [Monitor connector](../Monitor/BOARD.md#20_pin_FPC_Connector) so 
the Raspberry Pi can test that role.

Stream SPI CE - GPIO 12
Stream SPI MISO - GPIO 13
Stream SPI MOSI - GPIO 14
Stream SPI SCLK - GPIO 15

Unallocated GPIO 5, 6, 10, 11

## Other connector types

Other connectors can be made for the Raspberry Pi Controller.

TODO Controller combinations
- High Speed SPI
- Render to LCD / SD Card
- Stream SPI
- More Monitor conectors
