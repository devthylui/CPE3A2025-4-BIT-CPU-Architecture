# CPE3A2025 4-BIT CPU ARCHITECTURE

This repository contains the full design, implementation, and verification suite for the **CPE3A2025**, a custom 4-bit CPU architecture. Developed in March 2025, this project features a 12-bit instruction word designed for efficient arithmetic, logical, and control flow operations.

---

## Project Overview

The **CPE3A2025** is a Hardware Description Language (HDL) implementation of a microprocessor. It uses a dedicated 8-bit **Working Register (W)** for data manipulation and a 5-bit addressing scheme for memory-mapped operations. The digital logic design was synthesized and physically implemented on an **Intel Cyclone IV E** FPGA.

### Key Specifications
* **Instruction Width**: 12 bits (4-bit Opcode, 8-bit/5-bit Operand).
* **Registers**: 8-bit Working Register (W).
* **Addressing**: 5-bit Memory Address (up to 32 locations).
* **Clock Cycles**: Variable timing (2 to 5 cycles per instruction).
* **Hardware Target**: Intel Cyclone IV E FPGA.

---

## Instruction Set Architecture (ISA)

The CPU supports a 16-instruction set. Below is the summary of the architectural mnemonics and execution timing:

| Mnemonic | Opcode | Operand | Description | Cycles |
| :--- | :--- | :--- | :--- | :--- |
| **NOOP** | `0000` | NULL | CPU sleeps for 1 cycle | 2 |
| **LOADW** | `0001` | 8-BIT Input | Load W from external input | 3 |
| **MOVW** | `0010` | 8-BIT Literal | Load W with immediate data | 3 |
| **MOVWM** | `0011` | 5-BIT Addr | Move data from W to memory | 3 |
| **MOVMW** | `0100` | 5-BIT Addr | Move data from memory to W | 4 |
| **CMP** | `0101` | 8-BIT Literal | Compare W with immediate data | 4 |
| **SKIPE** | `0110` | NULL | Skip next instruction if ZF is 1 | 2 |
| **JMP** | `0111` | 5-BIT Addr | Jump to target instruction address | 2 |
| **OUTW** | `1000` | NULL | Output W to output port | 2 |
| **ADDW** | `1001` | 8-BIT Literal | Add immediate data to W | 4 |
| **ADDMW** | `1010` | 5-BIT Addr | Add memory value to W | 5 |
| **SUBW** | `1011` | 8-BIT Literal | Subtract immediate data from W | 4 |
| **SUBMW** | `1100` | 5-BIT Addr | Subtract memory from W | 5 |
| **ANDW** | `1101` | 8-BIT Literal | Bitwise AND W with literal | 4 |
| **ORW** | `1110` | 8-BIT Literal | Bitwise OR W with literal | 4 |
| **NOTW** | `1111` | NULL | Bitwise NOT W | 4 |

---

## Repository Contents

* **`/hdl`**: Verilog source files (`.v`) for the CPU core, ALU, and Control Unit.
* **`/rtl`**: RTL schematics and structural block diagrams.
* **`/testbench`**: Functional verification scripts and test vectors.
* **`/docs`**: Full datasheet, timing diagrams, and instruction set reference.
* **`/quartus`**: Intel Quartus Prime project files and Synthesis reports.
* **`/constraints`**: Pin assignment files (`.qsf`) for the Cyclone IV E board.
* **`/sim`**: Simulation waveforms and timing analysis.

---

**Status**: Academic Portfolio Project  
**Implementation**: Verilog HDL
