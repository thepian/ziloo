
## 20 pin Power supply connector 522072033

The Power connector is a direct connection to the internals in the Power Module via 20 pin 1A FFC FPC.
The Molex connectors have 1A current rating, other connectors only have 0.5A current rating.

TODO Rather than vertical, this should probably be right angle.

1. V_SYS 3.5V - 4.4V
2. V_SYS 3.5V - 4.4V
3. V_SYS 3.5V - 4.4V
4. V_CHARGE 4.2V - 5V (Allows MCU board to charge battery)
5. GND
6. Gut SDA (400 KHz)
7. Gut SCL (400 KHz)
8. IRQ Charger
9. SBU1
10. SBU2
11. LEDEN / CHG_STAT (Internal)
12. GND
13. D+
14. D-
15. GND
16. RX+
17. RX-
18. GND
19. TX+
20. TX-

[Easy-On FFC/FPC Connector, 1.00mm Pitch, Slider Series, Vertical, 5.75mm Height, 20 Circuits, Tin-Silver-Bismuth Plating](https://www.molex.com/molex/products/part-detail/ffc_fpc_connectors/0526102034)


## Occi Face connector (40 pins)

The Occi camera sensors are either processed by the Crosslink FPGA or one of the Kendryte K210.
The frames are routed via the Crosslink or a K210 or both. The Crosslink can output to differential lanes.
The K210 can output OctoSPI results. Face I2C is used to set the Slave Select.
VSYS powers the Face sensor board.

TODO signal voltage
TODO convert parallel to 2x diff lane? 14 bit

1. USB RX+
2. USB RX-
3. GND
4. USB TX+
5. USB TX-
6. GND
7. USB D+
8. USB D-
9. GND
10. CSI Clock+
11. CSI Clock-
12. GND
13. CSI Data0+
14. CSI Data0-
15. GND
16. CSI Data1+
17. CSI Data1-
18. GND
19. Occi1 SBBC SDA
20. Occi1 SBBC SCL
21. Occi2 SBBC SDA
22. Occi2 SBBC SCL
23. Face I2C SDA
24. Face I2C SCL
25. Face Master OSPI SCLK
26. Face Master OSPI D0
27. Face Master OSPI D1
28. Face Master OSPI D2
29. Face Master OSPI D3
30. Face Master OSPI D4
31. Face Master OSPI D5
32. Face Master OSPI D6
33. Face Master OSPI D7
34. nc
35. nc
36. Face Sensor RST
37. Face MCU RST
38. VSYS
39. VSYS
40. VSYS


Face I2C/OSPI 
- Power sensors/circuits on/off/reset/program
- Control src/dest of OSPI

Molex 40 pin connector
[541324033 bottom contact](https://www.molex.com/molex/products/part-detail/ffc_fpc_connectors/0541324033)

Molex 40 pin connector (alternate)
[541044033 top contact](https://www.molex.com/molex/products/part-detail/ffc_fpc_connectors/0541044033)


## Face Control connector


Boot Flash SCLK
Boot Flash D0
Boot Flash D1
Boot Flash D2
Boot Flash D3
Boot Flash CS
Boot Flash CS_ALT
Boot Flash HOLD





A connector for programming the MCUs is placed on the Dev Board.

1. JTAG TCK
2. JTAG TDI
3. JTAG TMS
4. JTAG TDO
5. ISP RX
6. ISP TX
7. Occi1 RST
8. Occi2 RST
9. Tempor RST
10. Stem RST
11. (SWDIO)
12. (SWDCLK)
13. (SWO)
14. GND


## Controller connector

