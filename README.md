# VSDSquadron Research Internship 
The program is based on the RISC-V architecture and uses open-source tools to teach people about VLSI chip design and RISC-V. The instructor for this internship is Kunal Ghosh Sir.                                                                  

# Basic Details
**Name:** Vivek M R              
**College:** Vidyavardhaka College of Engineering                                                                 
**Email ID:** vivekachar31@gmail.com          
**GitHub:** [Vicky_3120](https://github.com/Vicky)                                                                
**LinkedIN:** [Vivek M R](https://www.linkedin.com/in/vivek-m-r-b9873727a/)                                       
---

<details>
<summary> <b>task 1 :</b> The objective of this task is to thoroughly review the lab videos on C programming and RISC-V architecture to build a solid understanding of both topics. Afterward, you will apply this knowledge by compiling a C program using two different compilers:                                                              
-C language based LAB                                                                                             
-C and RISC-V based LAB          
</summary>
<br>
Task is to refer to C based and RISCV based lab videos and execute the task of compiling the C code using gcc and riscv compiler.
**C Language based LAB**

**C and RISC-V Based Labs**

This repository demonstrates the processes involved in compiling C programs and generating assembly code using both a standard GCC compiler and a RISC-V GCC compiler. It includes comprehensive steps and explanations to guide users through each stage of the compilation and debugging workflow.

**C Language-Based Lab**

Steps to Compile a .c File on Your Machine:

1. Open the bash terminal and navigate to the directory where you want to create your file.
2. Use the following command to create and edit a new .c file:
   ```sh
   leafpad sum1ton.c


**Steps to Compile a .c File on our Machine:**
 ```sh
 gcc sum1ton.c
 ./a.out
```

 
Compilation and execution complete.

![2](https://github.com/Vicky3120/vsd-riscv/blob/2450167e355d9fdaf2a71cea1f4825810287e987/task1/Screenshot%202025-03-23%20112659.png)
)

RISC - V Based lab
**Steps to Compile Using RISC-V GCC Compiler:**
1. Ensure the RISC-V GCC compiler is installed and accessible on your system.
2. Verify the .c file contents using the cat command:
   ```sh
   cat sum1ton.c


3. Compile the C program for RISC-V architecture using 01 option:
 ```sh
riscv64-unknown-elf-gcc -o1 -mabi=lp64 -march=rv64i -o sum1ton.o sum1ton.c
```
4. Disassemble the object file to view its assembly code using:
 ```sh
riscv64-unknown-elf-objdump -d sum1ton.o
```
5.minimize the assembly by using following code:
```sh
riscv64-unknown-elf-objdump -d sum1ton.o | less
```
 a)we extract main function's assembly code by using:
   ```sh
/main
```
6. Use /main in the terminal to locate the main function in the assembly output.
![4](https://github.com/Vicky3120/vsd-riscv/blob/2450167e355d9fdaf2a71cea1f4825810287e987/task1/Screenshot%202025-03-23%20112719.png)
)

7.Compile the C program for RISC-V architecture using ofast option:
```sh
riscv64-unknown-elf-gcc -Ofast -mabi=lp64 -march=rv64i -o sum1ton.o sum1ton.c
```
8.Disassemble the object file to view its assembly code using:
```sh
riscv64-unknown-elf-objdump -d sum1ton.o
```
9.minimize the assembly by using following code:
```sh
riscv64-unknown-elf-objdump -d sum1ton.o | less
```
 a)we extract main function's assembly code by using:
 ```sh
  /main
```
10. Use /main in the terminal to locate the main function in the assembly output.
![4](https://github.com/Vicky3120/vsd-riscv/blob/2450167e355d9fdaf2a71cea1f4825810287e987/task1/Screenshot%202025-03-23%20112749.png)
)

Explanation of Key Commands and Options: 
1. -mabi=lp64: Specifies the Application Binary Interface (ABI) for 64-bit integers, pointers, and long data types, suitable for 64-bit RISC-V architecture.

2. -march=rv64i: Indicates the 64-bit RISC-V base integer instruction set architecture.

3. -O1: Enables basic optimization for better performance without significantly increasing compilation time.

4. -Ofast: Optimize the code aggressively for the best possible speed.

5. riscv64-unknown-elf-objdump: A tool for disassembling RISC-V binaries to examine the code structure and debug it effectively.
 
   </details>

---
<details>
<summary><b>Task 2:</b> Performing SPIKE Simulation and Debugging the C code with interactive Debugging Mode using SPIKE </summary>

### SPIKE SIMULAION

the target is to run ```sum1ton.c``` code using both ```gcc compiler``` and ```riscv compiler```, and both of the compiler must display the same output on the terminal. So to compile the code using **gcc compiler**, use the following command:
```
gcc sum_1ton.c  
./a.out
```
And to compile the code using **riscv compiler**, use the following command:  
```
spike pk sum_1ton.o
```
![Spike Simulation](https://github.com/Vicky3120/vsd-riscv/blob/39222efab0a3c052c76bfdae41ae52f1991aff86/task%202/Screenshot%202025-04-08%20185059.png)

##Steps to Debug the output
```sh
spike -d pk sum1ton.c
```
// Debugger Mode will open and the operation is performed as shown in the figure

![Spike Debugger](https://github.com/Vicky3120/vsd-riscv/blob/39222efab0a3c052c76bfdae41ae52f1991aff86/task%202/Screenshot%202025-04-08%20191804.png)

### Explination of Key Commands:
1. Spike: Spike is a open-source C++ simulator for the RISC-V ISA that models a RISC-V core and cache system. It can be used to run programs and a Linux Kernal, and can be a starting point for running software on a RISC-V target.

2. -d: This flag is for debugging mode. It tells Spike to run in debug mode, allowing step-by-step execution, inspecting registers, memory, etc. Useful for identifying the errors and analyzing program behaviour.

3. pk: This refers to the proxy kernal, which acts as a lightweight OS for RISC-V. The proxy kernal handles system calls and facilities program execution in the simulated environment.

</details>
</details>

---

<details>
<summary><b>Task 3:</b>Understanding the R, I, S, B, U and J Instructions</summary>


# BASICS

 ## Instruction Types and Fields

The RISC-V instructions are categorized into types based on their field organization. Each type has specific fields like opcode, func3, func7, immediate values, and register numbers. The types include:
- **R-type**: Register type
- **I-type**: Immediate type
- **S-type**: Store type
- **B-type**: Branch type
- **U-type**: Upper immediate type
- **J-type**: Jump type

## Opcode and Function Fields
- **Opcode**: Determines the type of instruction.
- **func3** and **func7**: Further specify the operation within the instruction type.
  - Example: In R-type instructions, func3 and func7 differentiate between operations like addition and subtraction.
## Immediate Values and Registers
- **Immediate Values**: Encoded in specific fields within the instruction.
  - Example: I-type instructions use a 12-bit immediate value field along with source and destination registers.
- **Registers**: Specified in fields such as rd (destination register), rs1 (source register 1), and rs2 (source register 2).
### Example - U-Type Instruction
Consider the `lui` (Load Upper Immediate) instruction:
- **Assembly**: `lui x5, 0x12345`
- **Encoding**: The immediate value `0x12345` is placed in the instruction’s immediate field, and the destination register `x5` is specified in the rd field.
- **Machine Execution**: The machine loads the upper 20 bits of the immediate value into the upper 20 bits of register `x5`.
   ## Arithmetic Instructions
- **ADD**: Adds values in two registers and stores the result in a third register.
  - Example: `ADD rd, rs1, rs2` (rd = rs1 + rs2)
- **ADDI**: Adds a register and an immediate value (constant) and stores the result.
  - Example: `ADDI rd, rs1, imm` (rd = rs1 + imm)
## Logical Instructions
- **AND, OR, XOR**: Perform bitwise operations.
  - Example: `AND rd, rs1, rs2` (rd = rs1 & rs2)
## Branch Instructions
- **BEQ**: Branch if equal.
  - Example: `BEQ rs1, rs2, offset` (if rs1 == rs2, PC = PC + offset)
- **BNE**: Branch if not equal.
  - Example: `BNE rs1, rs2, offset` (if rs1 != rs2, PC = PC + offset)
## Load and Store Instructions
- **LW**: Load word from memory.
  - Example: `LW rd, offset(rs1)` (rd = memory[rs1 + offset])
- **SW**: Store word to memory.
  - Example: `SW rs1, offset(rs2)` (memory[rs2 + offset] = rs1)
## Special Instructions
- **AUIPC**: Add upper immediate to PC.
  - Example: `AUIPC rd, imm` (rd = PC + imm << 12)
## Branch and Jump Instructions
- **Jump (J)**: Unconditional branch to a specified address.
- **Branch (B)**: Conditional branch based on a comparison.
## RV32I Extensions
RISC-V allows optional extensions for additional functionality:
- **M**: Integer multiplication and division.
- **A**: Atomic instructions.
- **F, D, Q**: Floating-point operations (32-bit, 64-bit, 128-bit).
- **C**: Compressed instructions.
### RISC-V R-Type Instructions
R-type instructions are used for operations that involve only registers. These instructions typically perform arithmetic, logical, and shift operations.
#### Format: 
![image](https://github.com/Vicky3120/vsd-riscv/blob/0348607a15c39ffe63a27ebc95b305d2876f9404/task%203/r%20type.png)
- **opcode**: Specifies the operation (e.g., 0110011 for integer register-register operations).
- **rd**: Destination register.
- **funct3**: Further specifies the operation.
- **rs1**: First source register.
- **rs2**: Second source register.
- **funct7**: Further specifies the operation.
### I-Type Instructions
I-Type instructions cover various operations, including immediate arithmetic, load operations, and certain control flow instructions.
### Extracting Immediate Value
- The immediate value spans bits [31:20].
- To extract this value:
  - Mask the instruction to isolate the relevant bits.
  - Perform a right shift to align the immediate value to the least significant bits (LSBs).
- **Example**: If the instruction value is `0x12345678`, the immediate value is extracted as follows:
  ```cpp
  uint32_t imm_i = (instruction & 0xFFF00000) >> 20;
![image](https://github.com/Vicky3120/vsd-riscv/blob/0348607a15c39ffe63a27ebc95b305d2876f9404/task%203/i%20type.png)
**Example: ADDI rd, rs1, imm**
- **opcode**: 0010011 (for immediate arithmetic operations)
- **funct3**: 000 (for ADDI)
- **imm**: Immediate value
- **rs1**: Source register 1
- **rd**: Destination register
### S-Type Instructions
![image](https://github.com/Vicky3120/vsd-riscv/blob/0348607a15c39ffe63a27ebc95b305d2876f9404/task%203/s%20type.png)
**Example: SW rs2, imm(rs1)**
- **opcode**: 0100011 (for store operations)
- **funct3**: 010 (for SW)
- **imm**: Immediate value (split into imm[11:5] and imm[4:0])
- **rs1**: Base address register
- **rs2**: Source register to be stored
### B-Type Instructions
![image](https://github.com/Vicky3120/vsd-riscv/blob/0348607a15c39ffe63a27ebc95b305d2876f9404/task%203/b%20type.png)
**Example: BEQ rs1, rs2, imm**
- **opcode**: 1100011 (for branch operations)
- **funct3**: 000 (for BEQ)
- **imm**: Immediate value (split into imm[12], imm[10:5], imm[4:1], imm[11])
- **rs1**: Source register 1
- **rs2**: Source register 2
### U-Type Instructions
U-Type instructions are used for operations like loading upper immediate (LUI) and adding upper immediate to PC (AUIPC).
### Extracting Immediate Value
- The immediate value in U-type instructions spans bits [31:12].
- To extract this value, you can mask the instruction with `0xFFFFF000`.
- **Example**: If the instruction value is `0x12345000`, applying the mask will yield `0x12345000`.
### Encoding and Usage
- The immediate value extracted directly forms part of the U-type instruction.
  - For **LUI**, this value is loaded into the destination register.
  - For **AUIPC**, this value is added to the current PC.
![image](https://github.com/Vicky3120/vsd-riscv/blob/0348607a15c39ffe63a27ebc95b305d2876f9404/task%203/u%20type.png)
**Example: LUI rd, imm**
- **opcode**: 0110111 (for LUI)
- **imm**: Upper 20 bits of the immediate value
- **rd**: Destination register
### J-Type Instructions
![image](https://github.com/Vicky3120/vsd-riscv/blob/0348607a15c39ffe63a27ebc95b305d2876f9404/task%203/j%20type.png)
**Example: JAL rd, imm**
- **opcode**: 1101111 (for JAL)
- **imm**: Immediate value (split into imm[20], imm[10:1], imm[11], imm[19:12])
- **rd**: Destination register (stores the return address)

# 32-Bit instruction code for 15 unique RISC-V instructions
![Instructions](https://github.com/Vicky3120/vsd-riscv/blob/0348607a15c39ffe63a27ebc95b305d2876f9404/task%203/main.png)

</details>
</details>


---
<details><summary><b>
Task 4:</b>Perform a functional simulation of the given RISC-V Core Verilog netlist and 
testbench. </summary>

<br>

Functional simulation of RISC-V cores involves verifying that the core behaves correctly according to its design specifications. This process includes testing all possible instructions, ensuring compliance with the RISC-V instruction set architecture (ISA), and checking for any security vulnerabilities or malicious logic


 # About iverilog and gtkwave
1. Icarus Verilog is an implementation of the Verilog hardware description language.
2. GTKWave is a fully featured GTK+ v1. 2 based wave viewer for Unix and Win32 which reads Ver Structural Verilog Compiler generated AET files as well as standard Verilog VCD/EVCD files and allows their viewing.

**Step 1: installation of iverilog and gtkwave**
   using the below commands in ubuntu
   ```sh
   $   sudo apt get update
   $   sudo apt get install iverilog gtkwave
   ```

 **Step 2: clone the repository and download the netlist files for simulation by entering the following commands in terminal.**
  ```sh
   $ git clone https://github.com/vinayrayapati/iiitb_rv32i
   $ cd iiitb_rv32i
   $ gedit iiitb_rv32i.v
   $ gedit iiitb_rv32i_tb.v
   ```
**Step 3: To simulate and run the verilog code , enter the following commands in your terminal.**
  ```sh
 $ iverilog -o iiitb_rv32i iiitb_rv32i.v iiitb_rv32i_tb.v
 $ ./iiitb_rv32i
   ```
**Step 4:To see the output waveform in gtkwave, enter the following commands in your terminal.**
 ```sh
 $ gtkwave iiitb_rv32i.vcd
   ```
# The output waveform :
As shown in the figure below, all the instructions in the given verilog file is hard-coded. Hard-coded means that instead of following the RISCV specifications bit pattern, the designer has hard-coded each instructions based on their own pattern. 

![image](https://github.com/Vicky3120/vsd-riscv/blob/356c8adb02203f6320da40c4a55ac8f6a21c76f7/task4/code.png)


## Analysis of output waveforms
The waveform includes the following key signals:

clk: The clock signal driving the design.

NPC [31:0]: The next program counter value.

WB_OUT [31:0]: The write-back output signal.


**1. add r6,r1,r2**
![ADD](https://github.com/Vicky3120/vsd-riscv/blob/356c8adb02203f6320da40c4a55ac8f6a21c76f7/task4/ADD.jpg))



**2. sub r7,r1,r2**
![SUB](https://github.com/Vicky3120/vsd-riscv/blob/356c8adb02203f6320da40c4a55ac8f6a21c76f7/task4/SUB.jpg)


**3. and r8,r1,r3**
![AND](https://github.com/Vicky3120/vsd-riscv/blob/356c8adb02203f6320da40c4a55ac8f6a21c76f7/task4/AND.jpg)


**4. or r9,r2,r5**
![OR](https://github.com/Vicky3120/vsd-riscv/blob/356c8adb02203f6320da40c4a55ac8f6a21c76f7/task4/OR.jpg)


**5. xor r10,r1,r4**
![XOR](https://github.com/Vicky3120/vsd-riscv/blob/356c8adb02203f6320da40c4a55ac8f6a21c76f7/task4/XOR.jpg)


**6. slt r11,r2,r4**
![SLT](https://github.com/Vicky3120/vsd-riscv/blob/356c8adb02203f6320da40c4a55ac8f6a21c76f7/task4/SLT.jpg)

 
**7. addi r12,r4,5**
![ADDI](https://github.com/Vicky3120/vsd-riscv/blob/356c8adb02203f6320da40c4a55ac8f6a21c76f7/task4/ADDI.jpg)


**8. sw r3,r1,2**
![WhatsApp Image 2025-02-10 at 15 42 05_af74797c](https://github.com/user-attachments/assets/a604fcf4-a0bd-4e7a-8dad-64a755dd7197)


**9.  lw r13,r1,2**
![LW](https://github.com/Vicky3120/vsd-riscv/blob/356c8adb02203f6320da40c4a55ac8f6a21c76f7/task4/LW.jpg)


**10.  beq r0,r0,15**
![BEQ](https://github.com/Vicky3120/vsd-riscv/blob/356c8adb02203f6320da40c4a55ac8f6a21c76f7/task4/BEQ.jpg)


---


<details><summary><b>
Task 5:</b>Implementation of Full Adder using VSDSquadron Mini Board.</summary>

## Project Overview
A full adder is a digital circuit that adds two binary digits and a carry-in digit to produce a sum and carry-out digit.


## Pin Configuration
| **Component** | **Pin** |
|----------------|---------|
| **VSD SQUADRON BOARD** | **Led** |
| **SUM LED ** | **Pin4(PD4)** |
| **Carry LED ** | **Pin5(PD5)** |


## Truth Table
![Truth table](https://github.com/Vicky3120/vsd-riscv/blob/146ea997bd6d9ab11cd10dde0e393ddf97036b35/task%205/1745232449966671_r4_311753843779268336.png)


## Circuit Diagram
![WhatsApp Image 2025-02-17 at 22 44 58_d3bfbe8d](https://github.com/Vicky3120/vsd-riscv/blob/146ea997bd6d9ab11cd10dde0e393ddf97036b35/task%205/1745232440572963_r4_311753843685108336.png)


## Working
Step-by-Step Working on the VSDSquadron Mini Board
1. Input Mechanism (GPIO Inputs)
The input values (A, B, and Cin) are provided using GPIO inputs through buttons or switches connected to the VSDSquadron Mini board. These GPIO inputs represent the binary bits that the full adder will process.

2. Logic Processing Using FPGA
The full adder logic is implemented in Verilog and synthesized onto the FPGA present on the VSDSquadron Mini board.
The Verilog code defines the Boolean logic for the Sum and Carry outputs:

Sum = A ^ B ^ Cin

Carry = (A & B) | (B & Cin) | (Cin & A)

The FPGA reads the input values in real-time from the GPIO pins, processes them using the logic implemented in Verilog, and generates the corresponding outputs.

3. Output Representation
The output signals, Sum and Carry, are connected to LEDs or 7-segment display segments on the VSDSquadron Mini board.
Depending on the logic result:

If the Sum or Carry output is HIGH (1), the corresponding LED lights up.

If the output is LOW (0), the LED remains off.

#Demonstration Video
(https://drive.google.com/file/d/1tuhI6xsBiz7pAaFAqvZJdvrKcOE6OaUm/view?usp=sharing)


</details>
</details>

---





