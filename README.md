
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

# Application Software - > System Software - > Hardware chip
Apps enter into a block of system software and system software converts the entire program into binary language. There are some layers inside the system software - Operating System, Compiler, Assembler
Operating system handles input/output operations and allocate memory also it manage the low level system functions.
Compiler takes the output from the operating system as C,C++,Java and convert them into instructions. This instruction depends upon which hardware is used.(For eg. ARM processor then the instruction set will be ARM set)
Assembler takes the instructions from compiler and converts them into respective binary numbers. This binary language now sends to hardware and hardware performs output based on the function it receives and gives the output. Instruction acts as abstract interface between C-language and the hardware.

![7](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/c48bc420-3647-4a8d-89d1-6843e63fa5ee)
![6](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/ea33a9eb-852c-4ec9-b7df-0830e6f28562)

# SoC Design using OpenLane
Introduction to Open source Digital ASIC Design 

What is RTL design? 
In digital circuit design, register-transfer level (RTL) is a design abstraction which models a synchronous digital circuit in terms of the flow of digital signals (data) between hardware registers, and the logical operations performed on those signals. For these designs many open sources are available.

What are EDA tools? 
The term Electronic Design Automation (EDA) refers to the tools that are used to design and verify integrated circuits (ICs), printed circuit boards (PCBs), and electronic systems. Many open sources tools are available like Qflow, OpenROAD, OpenLANE, etc...

What is PDK?
Process Design Kit (PDK) is a software tool used in the design and simulation of semiconductor manufacturing processes. It provides a comprehensive set of tools and libraries for modelling and simulating various aspects of the manufacturing process, including process flow, equipment layout, and process parameters. PDK is used by semiconductor manufacturers to design and optimize their manufacturing processes, from the early stages of process development to the final stages of production. It helps to identify bottlenecks and potential problems in the process, reduce the risk of defects and improve the overall yield and quality of the devices being manufactured.

![9](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/59d6a023-c06c-4535-aed7-42a1992a7db9)
![10](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/53d05f40-a8a2-4bb6-8cb9-9de4f32d540f)


In 2020, GOOGLE released the open source PDK for FOSS 130nm production with the skywater technology. The current Technology node is in 3 nm. But in many applications, the advanced node is not required, and the cost of the advanced node is also high as compared to 130 nm processors. This 130nm processor is also a fast processor. 
For example, Intel: P4EE @3.46 GHz(Q4'o4), sky130_OSU (single cycle RV32i CPU) pipeline version can achieve more than 1 GHz clock.
![11](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/dfdfd3b9-a8c7-4b19-8589-60b697e5854a)

# Simplified RTL to GDS Flow

![12](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/9c30fe22-4b8c-4767-9f33-8b9935143fcd)
Step 1. Synthesis:- In the synthesis, the design RTL is translated to a circuit out from the standard cell library (SCL). The resultant circuit is described in HDL - gate level netlist. The gate level net list is functionally equivalent to the RTL. 

![13](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/da35c21d-67f6-4286-bddb-a2c23babd2d5)

Step 2. Floor/Power Planning:-
Floor planning is the process of dividing the silicon area of a chip into smaller regions or blocks, and distributing the components and interconnects within those blocks. The main objective of floor planning is to optimize the layout of the components and interconnects to reduce the distance between them, minimize the number of interconnects, and improve the overall performance of the chip.

In floor planning, the chip is divided into smaller areas called "dies," and each die is further divided into smaller regions called "cores." The components and interconnects are then placed within these cores to optimize the layout.

The main objective here is to plan the silicon area and distribute the power to the whole circuit. In the chip floor planning, the partition chip dies between different system building blocks and places the i/o pads. In micro floor planning, we define the dimensions, pin locations, and rows. In power planning, the power network is constructed. Typically, the chip is powered by multiple VDD and GND. so; the total components are connected to the power supply horizontally and vertically by metal strips. Here parallel structures are used to reduce the resistance thereby IR drop. To address the electromagnetization problem, the power distribution network uses upper metal layers, which are thicker than lower metal layers. Hence have less resistance.

![14a](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/859bb7b2-7a83-4d06-bbfd-a66b536b9fbd)
![14](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/ec2b4082-ac60-4c7a-a700-479fb477230b)


Step 3. Placements
After floor and power planning, next is the placements. For macros, we will place the gate-level netlist itself. Cells are placed very close to each other in rows and columns to avoid the interconnect delays. Typical two types of Placements- Global followed by detailed placements. 
![15](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/d49ba403-ab1e-4d16-86dd-404007129363)

Step 4: Clock tree synthesis
After placements, then we have to distribute the clock before routing the signals. The clock trr synthesis step performs the distribution of the clock signals with minimum skew.
Clock tree synthesis  - H-tree, X-tree, fish-bone, hybrid of all these.
![16](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/e6395899-2b57-4f6b-a2d2-7ea90e34b241)

Step 5: Routing
After clock tree synthesis, is the signal routing. Given a placement and  Fixed number of metal layers is required to find the valid pattern of horizontal and vertical wires to implement the wires that connects the cells together. The router uses the available metal layer from the PDK where the properties are mentioned- thickness, width, length, vias, etc. 
![17](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/9a191ac2-55eb-46d6-b913-e29d96ab71b1)

SKYwater PDK defines the routing layers- lowest layer- local interconnect layer- TiN layer, then following 5 metal layers- Aluminium layers
Most routers are grid routers. Metal track forms the routing grids which is very huge and use divide and conquer method. Ie, global routing that generates routing guides and detailed routing uses fine grain methods and routing guides to use implement the wires. 

Once the routing is completed we can move on to the final layout – verification
DRC- design rule check – makes sure that the final layout obeys the design rules, LVS – layout versus schematic check 
Finally, timing verification using static timing analysis to check any timing violations 

# Introduction to Openlane and Strive chipsets

OpenLane is an automated RTL to GDSII flow based on several components including OpenROAD, Yosys, Magic, Netgen, CVC, SPEF-Extractor, KLayout, and several custom scripts for design exploration and optimization. The flow performs all ASIC implementation steps from RTL down to GDSII.
OpenLane can be used to implement Macros and chips.
Two modes of operations - Autonomous or interactive

![18](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/0a1a8f08-06a3-4005-ad4d-e0919e278356)
![19](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/9053b05d-104a-46ee-b7e8-8e1a1eda25e5)

# Flow diagram of OpenLane ASIC Flow: Design to GDSII

OpenLane contains many open source tool packages – MAGIC, OpenRoad, Fault, Yosys, QFlow etc.
Starts with RTL synthesis – RTL is fed to Yosys with design constraints- RTL to logic circuits using SCL components – optimized and mapped to synthesized cells using ABC,- hence in the form of ABC scripts.

![20](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/a5e7fe72-f9bc-4b53-95be-0f0a673eff0b)

Synthesis exploration can provide you the report about the delay and area of the synthesized netlist and we can optimize the design 
Openlane has a Design exploration utility that can be used to pick the best configurations for any given design as per the design specifications. 
This is useful for finding the best configurations that results in best layout.
OpenLane regression report gives the best-known results and give us information about any timing violations in the design.

![21](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/f5693bc9-eaf9-49e5-8c5f-bf2d47066a78)

DFT test is optional – uses FAULT tool

After this step is the physical implementation – which includes several steps – uses OpenROAD app. – performs floor & power planning, decoupling capacitors and tap cell insertion, placements, clock tree synthesis, and routing – also known as automated PnR.

![22](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/8caab3fb-fef8-45ad-a1b1-d4f692d04e3f)

After  physical implementation – which includes several steps – uses the OpenROAD app.
 – performs floor & power planning, decoupling capacitors and tap cell insertion, placements, clock tree synthesis, and global routing – also known as automated PnR. The antenna rule specifies the maximum tolerance for the ratio of a metal line area to the area of connected gates. VLSI process starts from the substrate, device layer, and then metal layers. The Etch process builds up the electrical charges on metal layers. Inserting antenna diode in the gate netlist is also performed in the synthesis process.

The optimization results in a transformation in gatelevel netlist, which is performed in the synthesis process in OpenRoad, is compared in the logic equivalence Check (LEC) using the YoSys tool to make sure that the design is functionally equivalent. Detailed routing is performed after LEC by yosys. Then Antenna violation check is performed and swap the positions of the antenna diodes to remove the antenna violations in the design. Antenna diodes are available in SCL.


![23](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/d9c3325d-ad4e-4106-ac2b-84df13e54690)

![24](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/c4bf9bd4-06fe-42ff-8404-1c3fac3a9948)

![25](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/e8bff037-428f-4d9a-b328-17cecce599f1)

![26](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/ef7ebf3e-0d5d-4af0-9a60-152f22dcc3e9)

The sign-off in OpenLane involves STA, DRC, LVS, and interconnect RC extraction from the routed layout analysis. A set of reports is generated which helps in the Static timing analysis. 
RC extraction – DEF2SPEF
STA- OpenSTA (OpenROAD)


# Get familiar to OpenSource EDA tool




