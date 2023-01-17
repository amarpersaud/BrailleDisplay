# Electronic Braille Display Module
Electronic Refreshable Braille Display Module (8 dot) which uses latching solenoids with an integrated microcontroller and H-bridge drivers to drive each dot.

The design is inspired by MOLBED, a design which uses a latching solenoid formed by a solenoid coil, two metric nuts or washers, and neodymium magnets alongside 3d printed components. Some aspects of this design are similar, including the solenoid style of actuation. Several iterations of the design exist.  

## Physical Design Versions

### Version A (discontinued)
The first design consideration (Version A) (discontinued) consisted of an solenoid powered device with a physical latching mechanism, rather than the magnetic mechanism of MOLBED. Due to its low actuation force, complexity, and issues with actuation errors due to physical loading while actuating, it is no longer a consideration. Another major downside to this design is that all solenoids representing an extended dot must be simultaneously powered due to the physical latching mechanism locking all 8 dots at the same time, increasing the instantaneous power draw. Version B and C are two separate branching models under consideration.

### Version B
Version B uses a directly actuated latching solenoid which utilizes the force of a magnet hold the solenoid in the top position, more similar to MOLBED. The design is altered to reduce part count and complexity while improving actuation and holding force, and giving space to integrate electronics. This produces a module which has self contained drivers, with high holding force in the extended position, and high actuation force.

### Version C
Version C uses a similar solenoid as is used in Version B, however its mechanism is similar to that of multi-layer devices. The patent on such devices is no longer active and thus such devices can be produced. This uses a moving ramped section to push the dots up and down. The ramp allows a greater mechanical advantage, raising the actuation force. The holding force is also extremely high, as the pin is physically blocked from moving downwards. 

Due to the physical advantage in actuation for Version C, a lower force is needed to actuate the dots, meaning a larger or less efficient solenoid can be used. This means that the rare earth magnets (e.g. neodymium magnets) used in Version B could be swapped for weaker but more renewable and cheaper magnets.

The disadvantage of the Version C design is that it is much less compact. This is potentially an acceptable tradeoff, as it could be cheaper and more environmentally friendly, while allowing more room for electronics, but is harder to tile in a multi-row display. Due to the tradeoffs, it was deemed better to explore and refine both options in order to determine which design holds the advantage.

## Electronics
Electronics design for the device involved creation of a development board, codevelopment of the firmware and hardware using the development board, and a final board design created based on the physical CAD design. 

The development board design is available in the Hardware folder, and involves a microcontroller which drives two shift registers to control four dual H-bridge drivers, thus one H-bridge per dot or solenoid. The board is fairly large with hand solderable 0603 components, with additional GPIO and headers for development of the TWI/I2C, USART, and SPI communication protocols.

The development of the final board is still in progress and will likely consist of several boards connected together in order to keep it compact enough to fit inside the module (limited in size by the Braille standard) while still using off the shelf components.

## Firmware
The firmware for the device is still being developed. The firmware running on the embedded microcontroller creates several virtual registers which can be written to or read. Particularly, the device maintains a single byte register representing the 8 dots to be displayed, feedback sensing of the dot positions, operation completion, error detection using position detection as closed loop feedback, and configuration such as wether to immediately display the dots when the register is written or to automatically attempt to re-write to the display should an error in a dot be detected.

The device ID consists of two bytes written to EEPROM, allowing overwriting of the ID should the firmware be flashed to use many characters on a single bus such as with TWI or USART without an explicit select pin as afforded by SPI. This also allows setting the hardware address during runtime, without reflashing the firmware.