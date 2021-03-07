## Direct Out / LCD connector

The two Occi LCD outputs are routed via LCD 24 pin FFC connectors.
The power is only supplied to the LCD if feature 12/13 is enabled.

1. LEDK - GND
2. LEDA - 2V3
3. GND
4. VCI 3.3V
5. IOVCC 1.8V
6. NC
7. CS - IO 36
8. RST - IO 37
9. DC/RS - IO 38
10. WR - IO 39
11. RD - 1V8
12. DB7 - SPI D7
13. DB6
14. DB5
15. DB4
16. DB3
17. DB2
18. DB1
19. DB0 - SPI D0
20. GND
21. NC - IO 32? MIC0 BCK
22. NC - IO 33? I2S_WS
23. NC - IO 34? I2S_DA
24. NC - IO 33? I2S_BCK

TODO 1.8V or 3.3V IO


## DVP Input / 


AVDD 3.3V +- 5%
DVDD 1.8V +- 10%
DOVDD 1.7V .. 3.4V

1. STROBE
2. AGND
3. SIO_D - IO 40
4. AVDD 3.3V
5. SIO_C - IO 41
6. RESET - IO 42
7. VSYNC - IO 43
8. PWDN - IO 44
9. HREF - IO 45
10. DVDD 1.8V
11. DOVDD ?V
12. Y9
13. XCLK1 - IO 46
14. Y8
15. DGND
16. Y7
17. PCLK - IO 47
18. Y6
19. Y2
20. Y5
21. Y3
22. Y4
