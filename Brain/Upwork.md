# Diagram for Controller & Stem MCU programmer

I'm looking for a Diagram for a multi-MCU device with an external controller(Raspberry Pi).

The Brain board is primarily supplied by power via the Power FPC connector, but that also be run on
the power supplied via the Controller connector when not running all circuits, such as in resting mode.

Brain board functionality to include:

1. Feature switching with [MCP23017](./datasheets/MCP23017_20001952c.pdf) over I2C
2. Feature enabled powering of Occi1, Occi2, Tempor & Monitor.
3. Feature enabled reset MCU using the Power enable pin.
3. Feature enabled ISP boot of [Subsystems](./SUBSYSTEMS.md).
3. ISP programming via UART of Occi1, Occi2, Tempor & Monitor.
4. Disabling the Stem directly via connector pin
5. Direct OpenOCD JTAG with SPI
6. Direct OpenOCD  SWD with SPI
6. Jumper to support leaving one or more K210s disabled/removed.
7. Gut I2C with Controller vs Stem as master


You will,

* Design diagram in Eagle for the board
* Arrange components to support MCU Power enable/Reset on the same pin
* Propose ways to debug/test the board using SWD/JTAG/DAPLink

It's all in a private GitHub repo. At the end I'd want to check design files into the repo.
I will want to have design files in addition to manufacturing files that can be used for future
revisions. They must be in a format(or alternate format) that can be revised by low cost software.

