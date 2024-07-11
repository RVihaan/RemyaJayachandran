# VSDsquadron-mini-Reseach internship 2024
The VSDSquadron Mini RISC-V development board is a RISC-V development board. It contains a 32-bit RISC-V core. It has 16KB of flash memory, 2KB SRAM and operates at 24Mhz. The board has 15 GPIO pins and supports protocols such as I2C, SPI, and USART.
# Features:
>> Core Processor - The board is powered by CH32V003F4U6 chip with 32-bit RISC-V core based on RV32EC instruction set, optimized for high-performance computing with support for 2-level interrupt nesting and supports 24MHz system main frequency in the product function
>> 
>>  Clock and Reset Systems: Includes a built-in factory-trimmed 24MHz RC oscillator and a 128kHz RC oscillator, plus an external 24MHz oscillator option for varied clocking requirements
>> 
>> Robust GPIO Support: Boasts 3 groups of GPIO ports, totaling 15 I/O ports, enabling extensive peripheral connections and mapping to external interrupt capabilities
>> 
>> Flexible Communication Interfaces: Offers multiple communication protocols including USART, I2C, and SPI for versatile connectivity options
>> 
>> High-Speed Memory: Equipped with 2KB SRAM for volatile data storage, 16KB CodeFlash for program memory, and additional 1920B for bootloader functionalities

# Assignment 1: C code to RISC V
Write a C-program to sum the n mumbers. 
First install leafpad
use the command:
>> leafpad sum1ton.c &

to create file name sum1ton.c. Write the program and save the same. 
>>![Screenshot from 2024-06-23 10-38-49](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/893c0446-6c1f-4e2c-9d1c-8a1669c747e9)

Compile the C-program using the command:

>> gcc sum1ton.c
>>
To see the results type

>> ./a.out
>> ![Screenshot from 2024-06-23 10-39-04](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/de59a9f9-e5bd-41f8-8a5b-7159bba1b913)

>>
>> 
# RISC V

>> cat sum1ton.c
>>
To convert the C program to RISC V instruction set, type

>> riscv64-unknown-elf-gcc -O1 -mabi=lp64 -march=rv64i -o sum1ton.o sum1ton.c
>>
this will create the .o file of our C code

>> ![Screenshot from 2024-06-23 18-19-25](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/eaf549b4-3a47-44fd-a7bd-ae9539ddbaea)


![Screenshot from 2024-06-23 18-19-52](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/7347c2de-52c8-4183-9093-e314b9fd1099)

To visualize the assembly code

>> riscv64-unknown-elf-objdump -d sum1ton.o
>> riscv64-unknown-elf-objdump -d sum1ton.o | less
>>
this will take us to the RISC V format of the C-program that we have written.

![Screenshot from 2024-06-23 18-22-06](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/f85c2068-12cc-4890-b7d7-5c7d5dbb40d2)


![Screenshot from 2024-06-23 18-23-02](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/0d9a5ec8-4929-477d-8868-c3545e99309a)

![Screenshot from 2024-06-23 18-24-02](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/0f04d61b-5cea-451a-ba30-5a7c2e9d9ff3)

Do the same procedure with -Ofast and observe the difference. 

>> riscv64-unknown-elf-gcc -Ofast -mabi=lp64 -march=rv64i -o sum1ton.o sum1ton.c

![Screenshot from 2024-06-23 18-27-14](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/7d83d639-9f01-4162-9965-9f461e9e8f10)

![Screenshot from 2024-06-23 18-30-19](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/cd16c6ef-ee8d-4e95-b5ce-9af36c0c6c5e)

For -O1, there was 15 instruction to execute the C program, by using -Ofast the number of instructions reduced to 12 for the same rogram. 


# Task 2: Write C-program for Clock Cycle divider and compile with RISC V GCC

Simple program to divide 1 MHz clock signal

![Screenshot from 2024-06-23 21-58-19](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/d7a83077-a139-4c9b-8b83-4ea28ba928ae)

Output:

![Screenshot from 2024-06-23 21-58-51](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/a7c5a7be-f088-46e6-99b9-933496fd4aab)

![Screenshot from 2024-06-23 22-01-41](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/8c4d5471-202d-4ea4-98b8-e29596a63de7)

# RISC V: 
![Screenshot from 2024-06-23 22-02-43](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/4dfee6cf-0a97-471f-bb8d-8aa4505a6547)

![Screenshot from 2024-06-23 22-02-49](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/112ef71e-3b1b-45c7-8069-34805ed3c5a4)

![Screenshot from 2024-06-23 22-03-04](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/105ae4bf-d135-4813-8638-af2a3fa10285)


![Screenshot from 2024-06-23 22-03-42](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/5bbf3340-8b81-454d-a5a1-51264df754c3)



![Screenshot from 2024-06-23 22-04-09](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/302a9ce5-b299-4d87-93b6-318f138375de)

![Screenshot from 2024-06-23 22-04-43](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/5c134ee0-a50d-4250-a620-f68fa86dcf7a)

![Screenshot from 2024-06-23 22-05-11](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/28ebbaf7-29da-4bd9-bac3-a53d5e813c4f)


![Screenshot from 2024-06-23 22-05-47](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/1655ba1f-de33-4b30-bc6c-8333e2455fab)


# Task 3: Compile the c program with the spike command and observe it with -o1 and -ofast Command

Testing the SPIKE Simulator

Command: riscv64-unknown-elf-gcc -o1 -mabi=lp64 -march=rv64i -o clkDiv.o clkDiv.c
 -o1 command is used for moderate and quick level of optimizations for debugging the code

![Screenshot from 2024-07-09 20-27-24](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/a5c156a1-07be-408b-bdd6-8a00b542a7a2)

Assembly Code Address with -o1 Command:

![Screenshot from 2024-07-09 20-48-51](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/0cf67c84-172c-49c4-8762-d3a4d6496f91)


![Screenshot from 2024-07-09 20-32-36](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/0fafb686-02a9-42f8-bcca-a2f0260c0118)


![Screenshot from 2024-07-09 20-38-29](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/ed864f8c-76dd-45f7-8493-5c536abaef65)


![Screenshot from 2024-07-09 20-40-18](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/bd720c3a-9b89-4ed7-89c7-0468b0912db5)


-ofast command is used for aggressive optimizations, prioritizes performance over strict compliance and accuracy and may lead to non-standard behavior
Command: riscv64-unknown-elf-gcc -ofast -mabi=lp64 -march=rv64i -o clkDiv.o clkDiv.c


![Screenshot from 2024-07-09 20-51-54](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/b1245a2d-2ca5-4b38-ba25-fd2f33f5ce37)


Assembly Code Address with -ofast Command:

![Screenshot from 2024-07-09 20-53-23](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/e49e5b34-0b0e-47cb-916e-79de3938cee4)


![Screenshot from 2024-07-09 20-53-38](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/562c69f1-1e1f-4845-8ee4-3c5f5f2543c8)

gcc and spike outputs are same

# Task 4: RISC-V Instructions

RISC-V Instruction Set Architecture (ISA) is a free and open ISA for designing processors

The main instruction formats include:

 R-Type: Used for register-register operations.

 I-Type: Used for immediate operations.

 S-Type: Used for store operations.

 B-Type: Used for branch operations.

 U-Type: Used for upper immediate operations.

 J-Type: Used for jump operations.

 (The two types of Base Integer Instructions, 1. RV32I: The 32-bit base integer instruction set. 2.RV64I: The 64-bit base integer instruction set)

 ![image](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/829926d1-ba4f-4aef-a645-063077146b47)

 ![image](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/cb430d65-dece-4431-99cb-8c81074ca893)



![image](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/f398ca55-40ee-41c9-85e6-fa346ba59f97)

# R-type for Register to register operations
# R-Type instruction format consists of six fields:

 1. funct7: A 7-bit field used to specify the function code for the operation.

 2. rs2: A 5-bit field used to specify the second source register.

3. rs1: A 5-bit field used to specify the first source register.

4. funct3: A 3-bit field used to specify the function code for the operation.

5. rd: A 5-bit field used to specify the destination register.

6. opcode: A 7-bit field used to specify the opcode of the instruction

# I -type instruction for immediate transfer

imm[11:0]: A 12-bit immediate value.

rs1: A 5-bit field specifying the source register.

funct3: A 3-bit field specifying the function code for the operation.

rd: A 5-bit field specifying the destination register.

opcode: A 7-bit field specifying the opcode of the instruction.

# S-Type Instruction Format is used for store operations, which involve writing data from a register to memory. This format includes a 12-bit immediate value split across two fields.

S-Type instruction format consists of the following fields:

imm[11:5]: The upper 7 bits of the 12-bit immediate value.

rs2: A 5-bit field specifying the second source register.

rs1: A 5-bit field specifying the first source register.

funct3: A 3-bit field specifying the function code for the operation.

imm[4:0]: The lower 5 bits of the 12-bit immediate value.

opcode: A 7-bit field specifying the opcode of the instruction.

# B-Type Instruction is used for conditional branch instructions. This format includes a 12-bit immediate value split across several fields.


imm[12]: The 12th bit of the immediate value

imm[10:5]: Bits 10 to 5 of the immediate value

rs2: A 5-bit field specifying the second source register

rs1: A 5-bit field specifying the first source register

funct3: A 3-bit field specifying the function code for the operation

imm[4:1]: Bits 4 to 1 of the immediate value

imm[11]: The 11th bit of the immediate value

opcode: A 7-bit field specifying the opcode of the instruction


# U-Type Instruction Format is used for instructions that involve a 20-bit immediate value that is shifted left by 12 bits. 


imm[31:12]: A 20-bit immediate value.

rd: A 5-bit field specifying the destination register

opcode: A 7-bit field specifying the opcode of the instruction

# J-Type Instruction is used for jump instructions, which combines a large immediate value and an offset for branching.


imm[20]: The 20th bit of the immediate value.

imm[10:1]: Bits 10 to 1 of the immediate value.

imm[11]: The 11th bit of the immediate value.

imm[19:12]: Bits 19 to 12 of the immediate value.

rd: A 5-bit field specifying the destination register.

opcode: A 7-bit field specifying the opcode of the instruction.

![image](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/54a40e78-ac5e-478c-8029-3591524b5ec6)


# Task 4: Assignment

1. ADD r1,r2,r3
   R-type
32-bit Instruction Code is 0000000 00011 00010 000 00001 0110011

opcode: 0110011
rd: 00001
func3: 000
rs1: 00010
rs2: 00011
func7: 0000000


2. SUB r3,r1,r2
   R-type
32-bit Instruction Code is 0100000 00010 00001 000 00011 0110011

3. AND r2,r1,r3
      R-type
      32-bit Instruction Code is 0000000 00011 00001 111 00010 0110011
4. OR r8,r2,r5
  
       32-bit Instruction Code is 0000000 00101 00010 110 01000 0110011

5.XOR r8,r1,r4
         32-bit Instruction Code is 0000000 00100 00001 100 01000 0110011

 6. SLT r10,r2,r4
            SLT-Set Less Than
            32-bit Instruction Code is 0000000 00100 00010 010 01010 0110011

7. ADDI r12,r3,5
               I-type
               opcode: 0010011

               32-bit Instruction Code is 000000000101 00011 000 01100 0010011

8. SW r3,r1,4
                  SW- Store word
                         Immediate data 04- 000000000100
                  32-bit Instruction Code is 0100011 00011 00001 000000000100

   9. SRL r16,r11,r2
                      SRL- Shift Logically Right
                     32-bit Instruction Code is 0000000 00010 01011 101 10000 0110011

      10. BNE r0,r1,20
                         Branch not equal

                         32-bit Instruction Code is 1100011 001 00000 00001 000000010100

      11. BEQ r0,r0,15
                             Branch if equal

                             32-bit Instruction Code is 000000001111 00000 000 00000 0001100

      12. LW r13,r11,2
                                 Load word
                                 32-bit Instruction Code is 0000011 01011 01101 000000000000010

      13. SLL r15,r11,r2
                                     shift logical left
                                     32-bit Instruction Code is 0000000 00010 00011 001 01111 0110011

 #  Task 5: To create Verilog Code and Testbench for RISC-V and to verify the functional simulation and to generate Waveforms

Install iverilog and Gtkwave
>> sudo apt install iverilog gtkwave
>> 
![Screenshot from 2024-07-10 21-47-19](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/5d19b7e8-6ae6-4a64-93d9-13d8d328c068)

Clone the repository 

>> git clone https://github.com/vinayrayapati/iiitb_rv32i
>> cd iiitb_rv32i
 ![Screenshot from 2024-07-10 21-50-30](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/5bbb8690-c719-4618-b2d9-a2f10dba473f)

![Screenshot from 2024-07-10 21-51-32](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/b630485e-cff0-4d97-bbf5-aa637ccb5293)

To simulate and run the verilog code , enter the following commands in your terminal.

 >> iverilog -o iiitb_rv32i rj_rv32i.v rj_rv32i_tb.v

                       ![Screenshot from 2024-07-10 22-00-55](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/e1d6e050-0615-4eab-b45b-de6c09f5fd57)

>> ./iiitb_rv32i

![Screenshot from 2024-07-10 22-03-56](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/f4bd1e10-76b6-4ef2-9e5d-b5695836d638)

To visualize the output use the command

>> gtkwave iiitb_rv32i.vcd
>>
![Screenshot from 2024-07-10 22-04-41](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/8837728e-c89b-4e38-8430-f00c8851267e)


Check each instructions

![Screenshot from 2024-07-10 22-10-18](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/07a3e688-a125-4b37-b828-b246127e1989)

![Screenshot from 2024-07-10 22-04-49](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/06dbb01a-602b-47e2-a962-df8f7c2e50cd)

1. ADD r1,r2,r3
                       
     ![Screenshot from 2024-07-10 22-15-46](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/f36b0bcb-12b0-4502-8283-661581d49433)


2. SUB r3,r1,r2
   
![Screenshot from 2024-07-10 22-18-38](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/b91a2aea-55e7-495a-ad70-8c599a7e73e8)

3. AND r2, r1, r3

   ![Screenshot from 2024-07-10 22-21-33](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/0e6c92eb-0eda-44fb-8baf-3d0cf9f36c93)

 4. OR r8, r2, r5
    ![Screenshot from 2024-07-10 22-23-04](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/472b6d9b-c2fa-48d7-9e7e-8a1ac8d3059b)

    5. XOR r8, r1, r4
       
![Screenshot from 2024-07-10 22-24-15](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/586ce7e4-b943-4484-ae7b-8573407bb472)

6. SLT r10, r2, r4
![Screenshot from 2024-07-10 22-26-37](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/0fafe0bf-59d3-41ce-be36-243191031737)

7.. ADDI r12, r3, 5
   ![Screenshot from 2024-07-10 22-27-04](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/99e36de6-0b17-42ca-b48e-c37e2129d4c4)

8. SW r3, r1, 4
    ![Screenshot from 2024-07-10 22-27-31](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/e833d044-241e-430f-88d5-51a6c6308556)

9. SRL r16, r11, r2
    ![Screenshot from 2024-07-10 22-29-41](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/997567bf-ad91-4fa3-86bf-fe29b317445e)

10. BNE r0, r1, 20
   ![Screenshot from 2024-07-10 22-30-13](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/2e4df6a8-970b-4991-9788-de55d60fe1e6)
11. SLL r15, r11, r2
    ![Screenshot from 2024-07-10 22-31-32](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/9c4b6e60-8c3d-47ce-9586-da76af172040)

![Screenshot from 2024-07-10 22-32-17](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/b7da4042-d77a-40b5-b33f-d9ed52d5f691)


This task made to understand the instruction sets. The output waveform for the list of instructions are obtained in GTKWAVE.

# Task 6 Clock Divider Circuit using VSDminiquadron

This project involves designing a digital clock divider circuit using the VSDSquadron Mini board. The circuit functions to reduce the input clock signal frequency, generating lower frequency outputs essential for all integrated circuits designs.

# Components Required:
>> Power Supply
>> VSDSquadron Mini FPGA Board
>> Clock Source
>> Breadboard
>> Jumper Wires
>> LEDs
>>
# Circuit Connection:

>> Input Clock Source to VSDminiquadron board: Connect the clock source to the clock input pin on the VSDSquadron Mini. Ensure proper voltage levels matching the FPGA's requirements.
>> Output Pins: Configure multiple GPIO pins on the VSDminiquadron board as clock outputs. 
>> Power and Ground: Connect the power supply and ground to the VSDminiquadron board
>>
# Program

module clkDiv(
   input clk,          // Input clock signal
   input reset,        // Reset signal
   output reg clk_o1, 
   output reg clk_o2  
);

reg [31:0] N1; //counter1
reg [31:0] N2; //counter2

// Parameters for division
parameter DIV_1 = 10_000_000; // Desired frequency1
parameter DIV_2 = 5_000_000; // Desired frequency2

always @(posedge clk or posedge reset) 
begin
   if (reset) begin
      N1 <= 0;
      clk_o1 <= 0;
   end else begin
      if (N1 == DIV_1 - 1) begin
          N1 <= 0;
          clk_o1 <= ~clk_o1;
     end else begin
          N1 <= N1 + 1;
     end
   end
end
always @(posedge clk or posedge reset) 
begin
    if (reset) begin
        N2 <= 0;
        clk_o2 <= 0;
    end else begin
        if (N2 == DIV_2 - 1) begin
            N2 <= 0;
            clk_o2 <= ~clk_o2;
        end else begin
            N2 <= N2 + 1;
        end
     end
  end
endmodule


