
# NASSCOMM SOC DIGITAL VLSI DESIGN

DIGITAL-VLSI-SOC-DESIGN-AND-PLANNING

# Day 1:
 # Introduction to IC package, chip, pads, core and IPs

Integrated Circuits (ICs) are fundamental to modern electronic devices,
from smart phones to advanced computing systems. Understanding the
structure and function of ICs is to appreciate how electronic devices
operate at a fundamental level. The key components of ICs include their
packaging, chips, pads, core, and Intellectual Properties (IPs) etc.

Arduino microcontroller board : The highlighted section illustrates the
microprocessor (chip) which is connected to other elements on the board.
The design process of this chip, from an abstract level to its final
fabrication, is carried out using the RTL to GDSII flow. Arduino
encompasses both a programmable physical circuit board, commonly known
as a microcontroller, and a software component known as the IDE
(Integrated Development Environment). This software operates on a
computer and is used to create and transfer code to the physical board.

![1](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/ddfe22c0-20bc-4f3e-9044-a136ac58220d)

The processor / SoC is interfaced to external world through the other peripheral devices in the board namely JTAG, Flash, I2C-EEPROM, power ports, ADCs muxed with GPIOs, SDRAM etc. 
![2](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/6904b96a-0d3f-4c19-b196-a2ba7d4850f7)

If we open up the chip, it looks like this. Here, we consider the Quad Flat No-leads (QFN) -48 package chip design.  There are different types of packaging with different dimensions. The chip is placed at the centre of this package and the connections from each pin from the package to the respective pins in the chip are made using wire bonds.  Through this the external signals from outside world reaches the chip. 

![3](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/bd490c8c-568f-4cb8-a825-f5f766566e13)

When we open up the chip, we can visualize the various components inside namely PADS - through which we can transfer the signals to the chip and from the chip to the outside world, Core- where the entire circuit blocks /digital blocks are placed and Die- Present at the corner, it is the size of the entire chip. Typical core consists of SoC, SRAM, PLL, ADCs, DACs, etc. 
PLL, ADC, DAC, SRAM are known as Foundry IPs and SoC, SPIs are basically called as Macros (digital design).

![4](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/bda68795-151a-4204-ba6b-f7025e1b1a69)
(Foundry IPs: Needs intelligent to build these blocks)

# Introduction to RISC V –ISA
RISC-V is a open source instruction set architecture (ISA) that was developed at the University of California, Berkeley. It is based on established RISC principles and is provided under open source licenses. Several companies are offering or have announced RISC-V hardware, and open source operating systems with RISC-V support are available. The instruction set is supported in several popular software tool chains. The instruction set is designed to be versatile, with a fixed length of 32-bit naturally aligned instructions, and the ability to have variable length extensions with each instruction being any number of 16-bit parcels in length. The ISA also supports address space variants of 32-bit and 64-bit. Chip is connected to the package with the help of bond wires.
C-program -> using compiler converted to Assembly language -> Binary streams -> reaches the chip 
Another interface – HDL 
C-program-> RISC V specification in RTL then RTL to layout 

![5](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/4966c89b-0680-43ce-929d-f9e59487cdec)

# Application software to Hardware
![6](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/537c9a6e-0b61-4537-8c84-b0a56b8bdd11)




