#Hardware
The hardware conssists of an external development board for driving the latching solenoids and several PCBs for the embedded device. 

##Development board - V0.1

The development board is available in the Development board folder.

<p align="center">
<img src="https://github.com/amarpersaud/BrailleDisplay/raw/530ab86d90bb288eb60380569fc5a5028fdb9907/Hardware/Development%20Board/V0.1/PCB%20Image.png"/>
</p>

The board features an ATMEGA808-XUR microcontroller and two SN74HCS264DR shift registers to control four DRV8836DSSR ICs, each of which is capable of driving two bi-directional loads (headers H4-H7). Additionally, the header on the left (H1/H3) allows for 8x GPIO (for reading dot position for closed loop control), and the header on the top (H2) allows access to VCC(3.3V/5V), I2C/TWI, USART, and SPI communications. This allows for development of the software to communicate over SPI/USART/TWI with a higher level controller. Header J1 allows programming of the microcontroller via UPDI.

The board was developed in EasyEDA as it is a simple board whose sole purpose is to develop the firmware for the device; the board simply connects a microcontroller to shift registers, and shift registers to H-bridge drivers.

##Embedded PCB
The embedded device controller is currently in development. The device will be completed after finalization of the physical model.