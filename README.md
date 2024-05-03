
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
Steps: 
# cd Desktop
# cd work/tools/
# cd operlane_working_dir
# cd openlane
# docker ./flow.tcl -interactive
# % package require openlane 0.9
# % prep -design picorv32a -tag workshop

![WhatsApp Image 2024-04-29 at 3 20 41 PM](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/5eeabf20-66d6-4bc3-94b7-950d68b2bf0a)

![WhatsApp Image 2024-04-29 at 3 22 03 PM](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/baa4b747-a662-481e-806e-10e65cf85dd0)

![WhatsApp Image 2024-04-29 at 3 27 48 PM](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/7fa5270f-819b-49f9-ad7a-c4c53b459fd5)

![WhatsApp Image 2024-04-29 at 3 28 56 PM](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/b29bb38f-189e-4735-b525-90937b3a7263)

![WhatsApp Image 2024-04-29 at 3 29 12 PM](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/a199b435-241d-4575-a66b-279889ed8488)

![WhatsApp Image 2024-04-29 at 3 31 56 PM](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/c600b905-d580-4151-be37-afa22918201e)

![WhatsApp Image 2024-04-29 at 3 33 41 PM](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/af53d350-40e0-4b5f-b8de-a1f5d2115986)

![WhatsApp Image 2024-04-29 at 3 36 26 PM](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/cd92915b-9538-4633-8d07-a0eea8b564a9)

![WhatsApp Image 2024-04-29 at 3 37 12 PM](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/0fee72fd-0559-4e39-8ac0-aee45d33e178)

![WhatsApp Image 2024-04-29 at 3 37 49 PM](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/5cb94cb8-92c1-4e78-8fa7-fee5081354b7)

![WhatsApp Image 2024-04-29 at 3 39 24 PM](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/8aecd21b-0577-48f6-80a3-c332b321a786)

![WhatsApp Image 2024-04-29 at 3 39 47 PM](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/b9eb4291-f7a3-49d0-862c-9b90bd55cb23)

![WhatsApp Image 2024-04-29 at 3 40 00 PM](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/6196436d-5b94-4855-804e-f5532d5abca7)

# Synthesis
# % run_synthesis



![WhatsApp Image 2024-04-29 at 3 41 11 PM](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/02a30c6c-34b6-40f1-b977-5c93267e4a4f)

![WhatsApp Image 2024-04-29 at 3 41 46 PM](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/d46601ca-cd48-43a9-8216-b8e682e91e48)

![WhatsApp Image 2024-04-29 at 3 42 56 PM](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/641ee6b7-e4e2-4ef6-b9ee-bbfde984e6f8)

![WhatsApp Image 2024-04-29 at 3 44 33 PM](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/b5f80e1e-f85b-4fc1-951a-61684d6d25b2)

![WhatsApp Image 2024-04-29 at 3 45 14 PM](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/a3ca45ea-2f1e-4910-b48f-078b8cb84d20)

![WhatsApp Image 2024-04-29 at 3 49 50 PM](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/493c9ec0-44c7-42a1-9b8c-0b1181756b01)

![WhatsApp Image 2024-04-29 at 3 50 00 PM](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/4c916d68-fe05-42d7-8b18-074a6c682fb7)


![WhatsApp Image 2024-04-29 at 4 12 51 PM](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/c6924894-c043-454f-ab3e-3f000bdfe317)

![WhatsApp Image 2024-04-29 at 4 11 41 PM](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/939c05e4-f950-43cb-a24b-151725a8b0cf)

![WhatsApp Image 2024-04-29 at 4 04 26 PM](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/039f5a9d-efdb-4af7-a479-7a8636caff80)

![WhatsApp Image 2024-04-29 at 4 02 39 PM](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/4a83b0cb-6f6a-4a60-85b4-c5cdc1bb4a85)

![WhatsApp Image 2024-04-29 at 4 01 04 PM](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/676d16af-fbe9-4436-8e37-292121b5aebb)

![WhatsApp Image 2024-04-29 at 3 59 52 PM](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/8039ce08-e423-4ad3-8914-595b74ec9d7f)

![WhatsApp Image 2024-04-29 at 3 54 03 PM](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/a2a57335-6981-43ff-b397-ac79190a701d)

![WhatsApp Image 2024-04-29 at 3 52 54 PM](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/3212a818-88b8-4b87-af4c-c80aadb6a85d)

![WhatsApp Image 2024-04-29 at 3 51 34 PM](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/f2e25a4e-e9a8-4763-82c3-b5af5bfd52b9)

![WhatsApp Image 2024-04-29 at 3 50 58 PM](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/8298fc31-87d2-493a-9390-ecf3856084c7)

>> magic -T /home/vsdworkshop/Desktop/work/tools/openlane_working_dir/pdks/sky130A/libs.tech/magic/sky130A.tech lef read ../../tmp/merged.lef def read picorv32a.floorplan.def &


![picorv32a floorplan def](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/8fcf9a65-abe9-4084-acac-f843cedebed8)


# Flop area : No. of D FF/ No. of cells  = 1613/ 14876 = 0.1084 = 10. 84 %


# FloorPlanning

# % run_floorplan

![WhatsApp Image 2024-04-29 at 4 31 39 PM](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/4a4468aa-d01a-4dd1-b443-6ee8e601c6f3)

![WhatsApp Image 2024-04-29 at 4 25 53 PM](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/02e99795-da69-4ff3-8b20-c4480cacc0aa)

![WhatsApp Image 2024-04-29 at 4 22 07 PM](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/5094c669-e87c-41c8-9331-62f4caa31923)

![WhatsApp Image 2024-04-29 at 4 21 49 PM](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/76cef911-c622-4089-9013-97c055ef28a2)

![WhatsApp Image 2024-04-29 at 4 13 36 PM](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/e669e848-daef-40ad-b43d-da89fe1b650d)

Die area = 660.683 x 671.405 um^2
design area  =        420473.3 u^2

# Placement

# %run_placement

>> magic -T /home/vsdworkshop/Desktop/work/tools/openlane_working_dir/pdks/sky130A/libs.tech/magic/sky130A.tech lef read ../../tmp/merged.lef def read picorv32a.placement.def &

![picorv32a placement def](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/77db7ba4-92f2-44df-98b2-e0cce3492b1f)

![placement](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/079ce0fc-d23f-447e-9ab5-065ec214335e)


# Day 3: Steps to Display std_cells Using Magic tool

step 1: Git clone the files from GitHub to your local pc

git clone https://github.com/nickson-jose/vsdstdcelldesign.git

step 2: Copy technology file- sky130A.tech from sky130A pdk folder, to the vsdstdcelldesign folder

Step 3: Give magic command to display the CMOS inverter layout

magic -T sky130A.tech sky130_inv.mag


![Screenshot from 2024-05-03 15-13-35](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/900c41fe-3a03-43b8-a2f6-f0f1babd470f)

![Screenshot from 2024-05-03 15-37-22](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/949d4c6c-5257-420f-b7f0-ca47c63e7ad2)

