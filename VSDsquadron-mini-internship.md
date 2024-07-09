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



# Task 4: RISC-V Instructions







