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


