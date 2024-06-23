# VSDsquadron-mini-internship
The VSDSquadron Mini RISC-V development board is a RISC-V development board. It contains a 32-bit RISC-V core. It has 16KB of flash memory, 2KB SRAM and operates at 24Mhz. The board has 15 GPIO pins and supports protocols such as I2C, SPI, and USART.
# Features:
>> Core Processor - The board is powered by CH32V003F4U6 chip with 32-bit RISC-V core based on RV32EC instruction set, optimized for high-performance computing with support for 2-level interrupt nesting and supports 24MHz system main frequency in the product function
>>  Clock and Reset Systems: Includes a built-in factory-trimmed 24MHz RC oscillator and a 128kHz RC oscillator, plus an external 24MHz oscillator option for varied clocking requirements
>> Robust GPIO Support: Boasts 3 groups of GPIO ports, totaling 15 I/O ports, enabling extensive peripheral connections and mapping to external interrupt capabilities
>> Flexible Communication Interfaces: Offers multiple communication protocols including USART, I2C, and SPI for versatile connectivity options
>> High-Speed Memory: Equipped with 2KB SRAM for volatile data storage, 16KB CodeFlash for program memory, and additional 1920B for bootloader functionalities

# Assignment 1
>> leafpad sum1ton.c &
>>
>>![Screenshot from 2024-06-23 10-38-49](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/893c0446-6c1f-4e2c-9d1c-8a1669c747e9)

>> gcc sum1ton.c
>> ./a.out
>> ![Screenshot from 2024-06-23 10-39-04](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/de59a9f9-e5bd-41f8-8a5b-7159bba1b913)

>> 
# RISC V

>> cat sum1ton.c
>> 
>> riscv64-unknown-elf-gcc -O1 -mabi=lp64 -march=rv64i -o sum1ton.o sum1ton.c
>>
>> ![Screenshot from 2024-06-23 18-19-25](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/eaf549b4-3a47-44fd-a7bd-ae9539ddbaea)


![Screenshot from 2024-06-23 18-19-52](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/7347c2de-52c8-4183-9093-e314b9fd1099)

>> riscv64-unknown-elf-objdump -d sum1ton.o
>> riscv64-unknown-elf-objdump -d sum1ton.o | less
>>
>> 
![Screenshot from 2024-06-23 18-22-06](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/f85c2068-12cc-4890-b7d7-5c7d5dbb40d2)


![Screenshot from 2024-06-23 18-23-02](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/0d9a5ec8-4929-477d-8868-c3545e99309a)

![Screenshot from 2024-06-23 18-24-02](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/0f04d61b-5cea-451a-ba30-5a7c2e9d9ff3)

riscv64-unknown-elf-gcc -Ofast -mabi=lp64 -march=rv64i -o sum1ton.o sum1ton.c

![Screenshot from 2024-06-23 18-27-14](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/7d83d639-9f01-4162-9965-9f461e9e8f10)

![Screenshot from 2024-06-23 18-30-19](https://github.com/RVihaan/RemyaJayachandran/assets/149866052/cd16c6ef-ee8d-4e95-b5ce-9af36c0c6c5e)


