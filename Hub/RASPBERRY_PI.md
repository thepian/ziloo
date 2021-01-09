## Test with RPi

Early testing hooking up directly to Occi1 via 8,9,10,11,

            3v3         5v
CTS.2       GPIO 2      5v
RTS.2       GPIO 3      GND
TDI / TXD.3 GPIO 4      GPIO 14     CTS.5 / TXD.0
            GND         GPIO 15     RTS.5 / RXD.0
SPI CS1     GPIO 17     GPIO 18     SPI CS0
TMS         GPIO 27     GND
            GPIO 22     GPIO 23     TCK/SWDCLK
            3v3         GPIO 24     TDO/SWO
Slave SDA   GPIO 10     GND
RXD.4       GPIO 9      GPIO 25
Slave SCL   GPIO 11     GPIO 8      TXD.4
            GND         GPIO 7      RTS.3

TXD.2       GPIO 0      GPIO 1      RXD.2
RXD.3       GPIO 5      GND
CTS.3       GPIO 6      GPIO 12     TXD.5
RXD.5       GPIO 13     GND
SPI MISO    GPIO 19     GPIO 16     SPI CS2
            GPIO 26     GPIO 20     SPI MOSI
            GND         GPIO 21     SPI SCLK


UART2: Occi1 (RST Boot vs Master I2C)
UART3: Occi2
UART4: Tempor (RST Boot vs Slave Gut I2C)
UART5: Monitor

TXD White
RXD Green
CTS Grey (ISP Mode)
RTS Purple (RESET)

Gut SCL
Gut SDA
SWD
SPI Client

Advice on programming pins: https://elinux.org/RPi_Low-level_peripherals

RPi3 Pins: https://elinux.org/RPi_BCM2835_GPIOs
RPi4 Pins: https://elinux.org/RPi_BCM2711_GPIOs


```python
    import RPi.GPIO as GPIO
    GPIO.setmode(GPIO.BCM)
```

CH340C on MAIX Dock (cicle at pin 1)

1 GND    VCC 16
2 TXD    R232 15
3 RXD    RTS 14 - Purple cable
4 V3     DTR 13
5 UD+    DCD
6
7
8         CTS 9 - Grey cable 


## Raspberry Pi Configuration

The UARTs are enabled on the Rpi4 exposing 4 separate. UART 2, 3, 4, 5.

        TXD RXD CTS RTS     Board Pins
uart0   14  15              8   10
uart1   14  15              8   10
uart2   0   1   2   3       27  28  (I2C) - O1
uart3   4   5   6   7       7   29        - O2  
uart4   8   9   10  11      24  21  (SPI0)
uart5   12  13  14  15      32  33  (gpio-fan)  - Monitor

First add overlays to config.txt
check /boot/overlays/README

dtoverlay=uart2
dtoverlay=uart3
dtoverlay=uart4
dtoverlay=uart5

Boards are available on 

* /dev/ttyAMA1 - Occi1
* /dev/ttyAMA2 - Occi2
* /dev/ttyAMA3 - Tempor
* /dev/ttyAMA4 - Monitor


## anyspi overlay ?

## OpenOCD overlay ?


## Gut I2C

Initially connection is established as I2C Slave in Alt3 mode. If this times out due to 
no master on the bus, it switches mode to Alt5 SDA5 / SCL5.
