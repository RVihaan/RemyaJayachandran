
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


# Flop ratio : No. of D FF/ No. of cells  = 1613/ 14876 = 0.1084 = 10. 84 %

........................................................................................................................................................
# DAY2 : Good Fllor Plan Vs Bad Floorplan and Introduction to Library Cells
# FloorPlanning

# % run_floorplan

![WhatsApp Image 2024-04-29 at 4 31 39 PM](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/4a4468aa-d01a-4dd1-b443-6ee8e601c6f3)

![WhatsApp Image 2024-04-29 at 4 25 53 PM](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/02e99795-da69-4ff3-8b20-c4480cacc0aa)

![WhatsApp Image 2024-04-29 at 4 22 07 PM](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/5094c669-e87c-41c8-9331-62f4caa31923)

![WhatsApp Image 2024-04-29 at 4 21 49 PM](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/76cef911-c622-4089-9013-97c055ef28a2)

![WhatsApp Image 2024-04-29 at 4 13 36 PM](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/e669e848-daef-40ad-b43d-da89fe1b650d)

Die area = 660.683 x 671.405 um^2
design area  =        420473.3 u^2
.....................................................................................................................................................................................
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

In tkcon to get the information about the cell layers use command what

![Screenshot from 2024-05-04 15-17-11](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/36aff2d8-0286-413e-a1f9-53f8d395604d)

# Spice netlist extraction
tkcon window: type  extract all

![Screenshot from 2024-05-04 15-32-01](https://github.com/RVihaan/RemyaJayachandran/assets/149866052
/b22cd497-fc1b-4a5e-9089-748a49b8ff50)

![Screenshot from 2024-05-04 15-32-18](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/40cc8105-5f32-4176-9455-bab4303e708b)

For extracting the parasictic components- capacitance, resistance in the inverter cell
tkcon window type: ext2spice cthresh 0 rthresh 0
type: ext2spice


![Screenshot from 2024-05-04 15-47-11](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/dfab3b74-0608-439a-8afc-fb625990728d)

![Screenshot from 2024-05-04 15-47-26](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/cb1d402f-46d7-4693-91e4-2e72dc26705b)


![Screenshot from 2024-05-04 15-47-54](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/a77d146e-0ad2-454a-b33f-27119f7379e0)



![Screenshot from 2024-05-04 15-56-34](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/c1ad56fb-6cb9-4da5-b3a5-a67b59de99bd)

Edit the spice file inorder to run the simulation in ngspice

![Screenshot from 2024-05-04 16-40-57](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/10a2657d-6c2e-47cd-9d74-c02f0b0deec3)


install ngspice
run ngspice using command : ngspice sky130_inv.spice

![Screenshot from 2024-05-04 16-30-40](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/0896dff1-9801-4edf-a4f1-02a6d39eba42)

To plot the transient response type: plot y vs time a

![Screenshot from 2024-05-04 16-39-34](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/e7201e21-c4ee-4d93-9e60-6e30b270dadb)

Transient response of CMOS Inverter with input time period 4 ns, simulation stop time 20 ns

![Screenshot from 2024-05-04 16-39-40](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/8842744b-5a8d-49c8-be8a-5bad05a300c3)

Parameter extraction from transient response

1. Rise time : change from 20 % to 80% of the rising edge of ouput signal

   ![Screenshot from 2024-05-04 16-52-34](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/ec4bdc4a-fbfe-4704-a083-186db3c9ba12)


![Screenshot from 2024-05-04 16-56-32](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/93fa313a-80d7-486f-aab4-d02a78e7e8fa)

rise time = 0.04374 ns

2. Fall time![Screenshot from 2024-05-04 17-01-01](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/614ed257-19da-4d2b-b66d-3f5ad1c51494)


   ![Screenshot from 2024-05-04 17-02-20](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/a6c1811a-740e-45ff-9836-f2ff1e508b41)


Fall time  = 0.02625 ns

3. propagation delay- Fall edge = 4.05297 ns - 4.05 ns = 0.00297 ns
4. propagation delay= Rise edge = 2.17796 ns - 2.15011 ns = 0.02785 ns

# DRC Corrections and rules

Download :wget http://opencircuitdesign.com/open_pdks/archive/drc_tests.tgz
Extract the folder

to run MAGIC
magic -d XR

open met3.mag file in the magic

![Screenshot from 2024-05-04 17-21-21](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/e60c753b-7078-48a9-9adc-a0221ec5d4cb)

![Screenshot from 2024-05-04 17-23-18](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/63843898-4368-4804-8b2c-a3205aa5cff3)


![Screenshot from 2024-05-04 17-25-30](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/dea5e9b2-a9af-4b8a-8c99-de5eb14b6646)

![Screenshot from 2024-05-04 17-27-02](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/c99d5f04-d562-4c1d-b1d8-98c0c3a2fc6e)

![Screenshot from 2024-05-04 17-27-13](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/985405f2-c10f-461a-ba2f-abf88a2e3569)



![Screenshot from 2024-05-04 17-29-41](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/8aa432cd-8bfd-46b4-aa49-2e947ba6ffc0)


![Screenshot from 2024-05-04 17-29-47](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/0a82c8bf-f148-4b7c-bf32-96d3071ebcdd)

![Screenshot from 2024-05-04 18-38-31](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/7e120434-c96f-4aae-a74c-9b668860f459)


# poly.9 error
open poly.mag file

![Screenshot from 2024-05-04 18-43-21](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/f9fedcab-d668-4617-bc2a-7ba6ff40a0db)



![Screenshot from 2024-05-04 18-45-56](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/3361cafa-80be-4a16-8861-817ac69e0962)

![Screenshot from 2024-05-04 18-47-39](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/7893ea6f-9e22-4ccd-b74d-32299b030948)

![Screenshot from 2024-05-04 18-49-46](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/2dda865c-2734-4268-a952-f648eba3e603)


![Screenshot from 2024-05-04 18-51-43](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/7033b8fd-9334-4502-b500-dffa8518a934)

![Screenshot from 2024-05-04 19-08-35](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/0b799dfd-ab03-409c-b6bb-b92e504a8bab)

![Screenshot from 2024-05-04 19-19-00](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/15f0c56e-2b5c-4370-96fb-6e43bee97e9f)


# DRC error as geometrical construct

![Screenshot from 2024-05-05 09-07-04](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/d853f088-4e7f-4fb0-9ac8-678f1a189443)

![Screenshot from 2024-05-05 09-08-42](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/503d094a-814d-4012-a413-3b1c33901cc0)

![Screenshot from 2024-05-05 09-11-21](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/468a6e7e-543c-41c4-921c-a2bccf92730b)

![Screenshot from 2024-05-05 09-16-38](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/047f4c43-e538-4be1-9e9c-626d66b24a07)

by adding the nsubstratecontact

![screenshot from 2024-05-05 23-01-25](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/65af3206-f629-42f8-9cb9-eba1b42be87e)


# Pre layout analysis and importance of good clock tree

Refer: https://github.com/nickson-jose/vsdstdcelldesign


![Screenshot from 2024-05-05 23-24-24](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/529fdbd7-1438-4601-9239-14fdfe022e12)

![Screenshot from 2024-05-05 23-26-07](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/8ea78c5d-5400-4b31-8ba2-5fb0d9c53e55)

![Screenshot from 2024-05-05 23-33-21](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/7fef41f7-c387-4c30-b333-fa2703b4511f)

![Screenshot from 2024-05-05 23-32-17](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/3f4bdcd6-2502-4531-9a60-9a073da4360c)
![Screenshot from 2024-05-05 23-33-21](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/4d0fcd9c-9dc3-4dbf-86d6-9f2d1fb4335b)
![Screenshot from 2024-05-06 09-22-55](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/f15538d5-0c42-4204-92f3-14484d6edcdc)
![Screenshot from 2024-05-06 09-23-07](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/9477763e-8b5d-46c8-b0c1-bec3053f186e)

![Screenshot from 2024-05-06 09-46-57](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/56f27705-d923-452f-a2b9-1d74cc2fa31e)

![Screenshot from 2024-05-06 09-47-05](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/1b12d367-bf73-469a-8593-ab0f57b7fc22)

![Screenshot from 2024-05-06 09-47-29](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/424b5438-ae04-45d3-97f2-f6e3c2890b28)

![Screenshot from 2024-05-06 09-50-20](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/6fae2d3e-e185-4631-928f-77ae72c5a0fa)

![Screenshot from 2024-05-06 09-53-08](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/3e016934-92a3-41c0-9a0a-590c48ea2f69)

copy the lef file to src file 
cp sky130_vsdinv.lef /home/vsduser/Desktop/work/tools/openlane_working_dir/openlane/designs/picorv32a/src


# Design
set ::env(DESIGN_NAME) "picorv32a"

set ::env(VERILOG_FILES) "./designs/picorv32a/src/picorv32a.v"
set ::env(SDC_FILE) "./designs/picorv32a/src/picorv32a.sdc"

set ::env(CLOCK_PERIOD) "5.000"
set ::env(CLOCK_PORT) "clk"


set ::env(CLOCK_NET) $::env(CLOCK_PORT)
set ::env(FP_CORE_UTIL) 65
set ::env(FP_IO_VMETAL) 4
set ::env(FP_IO_HMETAL) 3

set ::env(LIB_SYNTH) "$::env(OPENLANE_ROOT)/designs/picorv32a/src/sky130_fd_sc_hd__typical.lib"
set ::env(LIB_FASTEST) "$::env(OPENLANE_ROOT)/designs/picorv32a/src/sky130_fd_sc_hd__fast.lib"
set ::env(LIB_SLOWEST) "$::env(OPENLANE_ROOT)/designs/picorv32a/src/sky130_fd_sc_hd__slow.lib"
set ::env(LIB_TYPICAL) "$::env(OPENLANE_ROOT)/designs/picorv32a/src/sky130_fd_sc_hd__typical.lib"

set ::env(EXTRA_LEFS) [glob $::env(OPENLANE_ROOT)/designs/$::env(DESIGN_NAME)/src/*.lef]*




set filename $::env(OPENLANE_ROOT)/designs/$::env(DESIGN_NAME)/$::env(PDK)_$::env(STD_CELL_LIBRARY)_config.tcl
if { [file exists $filename] == 1} {
	source $filename
}

:q! - exit

# OPENLANE :- Now we will go to the open lane directory and execute the docker command

docker ./flow.tcl -interactive
package require openlane 0.9
prep -design picorv32a -tag workshop

set lefs [glob $::env(DESIGN_DIR)/src/*.lef]
add_lefs -src $lefs

run_synthesis

![Screenshot from 2024-05-06 14-12-03](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/2b70c934-0de9-4ed9-9f4b-09db78f367cd)


![Screenshot from 2024-05-06 14-12-32](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/65b38807-09a9-48e5-a488-eda21c2da119)


![Screenshot from 2024-05-06 14-12-56](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/d57f6db4-3ef7-42de-bc60-74511f2ce327)

![Screenshot from 2024-05-06 14-20-06](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/e4c5c738-e6b8-4f3d-ad7a-dd8ef9aebd1e)



run_floorplan

init_floorplan
place_io
tap_decap_or


