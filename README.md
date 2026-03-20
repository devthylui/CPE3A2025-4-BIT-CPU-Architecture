# CPE3A2025 4-BIT CPU ARCHITECTURE

[cite_start]This repository contains the design, implementation, and verification of the **CPE3A2025**, a custom 4-bit CPU architecture. [cite_start]Developed as a comprehensive digital design project, this processor features a 12-bit instruction word and supports arithmetic, logical, and control flow operations[cite: 6].

---

## ## Project Overview

[cite_start]The **CPE3A2025** is an HDL implementation of a microprocessor designed for efficiency and simplicity. [cite_start]It utilizes an 8-bit **Working Register (W)** for data manipulation and a 5-bit addressing scheme for memory-mapped operations[cite: 6].

* [cite_start]**Architecture**: 4-bit CPU.
* [cite_start]**Instruction Width**: 12 bits (4-bit Opcode, 8-bit/5-bit Operand)[cite: 6].
* [cite_start]**Design Date**: March 2025[cite: 4].

## ## Key Features

* [cite_start]**Flexible Operands**: Supports 8-bit literals for immediate data and 5-bit addresses for memory access[cite: 6].
* [cite_start]**Memory Management**: 5-bit addressing allows for up to 32 unique memory locations[cite: 6, 30].
* [cite_start]**Control Flow**: Features a **SKIPE** (Skip if Equal) instruction that checks the Zero Flag (ZF) and a **JMP** instruction for target address branching[cite: 48, 54].
* [cite_start]**ALU Capabilities**: Includes Addition, Subtraction, bitwise AND, OR, NOT, and Comparison[cite: 6].

## ## Instruction Set Architecture (ISA)

[cite_start]The processor executes a 16-instruction set[cite: 6]. Below is the summary of mnemonics and cycle timing:

| Mnemonic | Opcode | Operand | Description | Cycles |
| :--- | :--- | :--- | :--- | :--- |
| **NOOP** | `0000` | NULL | [cite_start]CPU sleeps for 1 cycle [cite: 6] | [cite_start]2 [cite: 13] |
| **LOADW** | `0001` | 8-BIT Input | [cite_start]Load W from external input [cite: 18] | [cite_start]3 [cite: 19] |
| **MOVW** | `0010` | 8-BIT Literal | [cite_start]Load W with immediate data [cite: 24] | [cite_start]3 [cite: 25] |
| **MOVWM** | `0011` | 5-BIT Addr | [cite_start]Move data from W to memory [cite: 30] | [cite_start]3 [cite: 31] |
| **MOVMW** | `0100` | 5-BIT Addr | [cite_start]Move data from memory to W [cite: 36] | [cite_start]4 [cite: 37] |
| **CMP** | `0101` | 8-BIT Literal | [cite_start]Compare W with immediate data [cite: 42] | [cite_start]4 [cite: 43] |
| **SKIPE** | `0110` | NULL | [cite_start]Skip next instruction if ZF is 1 [cite: 48] | [cite_start]2 [cite: 49] |
| **JMP** | `0111` | 5-BIT Addr | [cite_start]Jump to target instruction address [cite: 54] | [cite_start]2 [cite: 55] |
| **OUTW** | `1000` | NULL | [cite_start]Output W to output port [cite: 60] | [cite_start]2 [cite: 61] |
| **ADDW** | `1001` | 8-BIT Literal | [cite_start]Add immediate data to W [cite: 66] | [cite_start]4 [cite: 67] |
| **ADDMW** | `1010` | 5-BIT Addr | [cite_start]Add memory value to W [cite: 72] | [cite_start]5 [cite: 73] |
| **SUBW** | `1011` | 8-BIT Literal | [cite_start]Subtract immediate data from W [cite: 78] | [cite_start]4 [cite: 79] |
| **ANDW** | `1101` | 8-BIT Literal | [cite_start]Bitwise AND of W with literal [cite: 90] | [cite_start]4 [cite: 91] |
| **NOTW** | `1111` | NULL | [cite_start]Bitwise NOT of W [cite: 102] | [cite_start]4 [cite: 103] |

## ## Repository Structure

* **`/hdl`**: Verilog source files implementation.
* **`/rtl`**: RTL schematics and block diagrams.
* **`/testbench`**: Functional verification scripts and test vectors.
* **`/docs`**: Timing diagrams and the original [CPE312025 CPU - DATASHEET.docx].
* **`/sim`**: Simulation results and waveform outputs.
* **`/constraints`**: Hardware pin assignments and configuration files.

---

**Author**: Computer Engineering Student  
**Affiliation**: Technological University of the Philippines – Visayas  
**Status**: Academic Portfolio Project
