# Hardware
The hardware consists of a 3d CAD model for the module, an external development board for driving the latching solenoids, and several PCBs that form the final driver for the embedded device. 

## Definitions
- Holding force - Force the extended dots can withstand before device failure or depression of dot
- Actuation force - Force that an individual dot is capable of exerting while extending

## CAD model
Inspiration for the design came from the MOLBED project, and some aspects of the design are similar, including the solenoid style of actuation. Several iterations of the design exist. The first design consideration (Version A) (discontinued) consisted of an solenoid powered device with a physical latching mechanism, rather than the magnetic mechanism of MOLBED. Due to its low actuation force, complexity, and issues with actuation errors due to physical loading while actuating, it is no longer a consideration. Version B and C are two separate branching models under consideration. 

Version B uses a directly actuated latching solenoid which utilizes the force of a magnet hold the solenoid in the top position, more similar to MOLBED. The design is altered to reduce part count and complexity while improving actuation and holding force, and giving space to integrate electronics. This produces a module which has self contained drivers, with high holding force in the extended position, and high actuation force.

Version C uses a similar solenoid as is used in Version B, however its mechanism is similar to that of multi-layer devices. The patent on such devices is no longer active and thus such devices can be produced. This uses a moving ramped section to push the dots up and down. The ramp allows a greater mechanical advantage, raising the actuation force. The holding force is also extremely high, as the pin is physically blocked from moving downwards. 

Due to the physical advantage in actuation, a lower force is needed to actuate the dots, meaning a larger or less efficient solenoid can be used. This means that the rare earth magnets (e.g. neodymium magnets) used in Version B could be swapped for weaker but more renewable and cheaper magnets.

The disadvantage of the Version C design is that it is much less compact. This is potentially an acceptable tradeoff, as it could be cheaper and more environmentally friendly, while allowing more room for electronics, but is harder to tile in a multi-row display. Due to the tradeoffs, it was deemed better to explore and refine both options in order to determine which design holds the advantage.

## Development board - V0.1

The development board is available in the Development board folder.

<p align="center">
<img src="https://github.com/amarpersaud/BrailleDisplay/raw/main/Hardware/Development%20Board/V0.1/PCB%20Image.png"/>
</p>

The board features an ATMEGA808-XUR microcontroller and two SN74HCS264DR shift registers to control four DRV8836DSSR ICs, each of which is capable of driving two bi-directional loads (headers H4-H7). Additionally, the header on the left (H1/H3) allows for 8x GPIO (for reading dot position for closed loop control), and the header on the top (H2) allows access to VCC(3.3V/5V), I2C/TWI, USART, and SPI communications. This allows for development of the software to communicate over SPI/USART/TWI with a higher level controller. Header J1 allows programming of the microcontroller via UPDI.

The board was developed in EasyEDA as it is a simple board whose sole purpose is to develop the firmware for the device; the board simply connects a microcontroller to shift registers, and shift registers to H-bridge drivers.

## Embedded PCB
The embedded device controller is currently in development. The device will be completed after finalization of the physical model.
