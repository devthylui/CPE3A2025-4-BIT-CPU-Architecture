# CPE3A2025 4-BIT CPU ARCHITECTURE

[cite_start]This repository contains the full design, implementation, and verification suite for the **CPE3A2025**, a custom 4-bit CPU architecture[cite: 1]. [cite_start]Developed in March 2025, this project features a 12-bit instruction word designed for efficient arithmetic, logical, and control flow operations[cite: 4, 6].

---

## Project Overview

[cite_start]The **CPE3A2025** is a hardware description language (HDL) implementation of a microprocessor. [cite_start]It uses a dedicated 8-bit **Working Register (W)** for data manipulation and a 5-bit addressing scheme for memory-mapped operations[cite: 6].

### Key Specifications
* [cite_start]**Instruction Width**: 12 bits (4-bit Opcode, 8-bit/5-bit Operand)[cite: 6].
* [cite_start]**Registers**: 8-bit Working Register (W)[cite: 6].
* [cite_start]**Addressing**: 5-bit Memory Address (up to 32 locations)[cite: 30, 36].
* [cite_start]**Clock Cycles**: Variable timing (2 to 5 cycles per instruction)[cite: 13, 73].

---

## Instruction Set Architecture (ISA)

[cite_start]The CPU supports a 16-instruction set[cite: 5, 6]. Below is the summary of the architectural mnemonics and execution timing:

| Mnemonic | Opcode | Operand | Description | Cycles |
| :--- | :--- | :--- | :--- | :--- |
| **NOOP** | `0000` | NULL | [cite_start]CPU sleeps for 1 cycle [cite: 6, 10] | [cite_start]2 [cite: 13] |
| **LOADW** | `0001` | 8-BIT Input | [cite_start]Load W from external input [cite: 6, 16] | [cite_start]3 [cite: 19] |
| **MOVW** | `0010` | 8-BIT Literal | [cite_start]Load W with immediate data [cite: 6, 22] | [cite_start]3 [cite: 25] |
| **MOVWM** | `0011` | 5-BIT Addr | [cite_start]Move data from W to memory [cite: 6, 28] | [cite_start]3 [cite: 31] |
| **MOVMW** | `0100` | 5-BIT Addr | [cite_start]Move data from memory to W [cite: 6, 34] | [cite_start]4 [cite: 37] |
| **CMP** | `0101` | 8-BIT Literal | [cite_start]Compare W with immediate data [cite: 6, 40] | [cite_start]4 [cite: 43] |
| **SKIPE** | `0110` | NULL | [cite_start]Skip next instruction if ZF is 1 [cite: 6, 46] | [cite_start]2 [cite: 49] |
| **JMP** | `0111` | 5-BIT Addr | [cite_start]Jump to target instruction address [cite: 6, 52] | [cite_start]2 [cite: 55] |
| **OUTW** | `1000` | NULL | [cite_start]Output W to output port [cite: 6, 58] | [cite_start]2 [cite: 61] |
| **ADDW** | `1001` | 8-BIT Literal | [cite_start]Add immediate data to W [cite: 6, 64] | [cite_start]4 [cite: 67] |
| **ADDMW** | `1010` | 5-BIT Addr | [cite_start]Add memory value to W [cite: 6, 70] | [cite_start]5 [cite: 73] |
| **SUBW** | `1011` | 8-BIT Literal | [cite_start]Subtract immediate data from W [cite: 6, 76] | [cite_start]4 [cite: 79] |
| **SUBMW** | `1100` | 5-BIT Addr | [cite_start]Subtract memory from W [cite: 6, 82] | [cite_start]5 [cite: 85] |
| **ANDW** | `1101` | 8-BIT Literal | [cite_start]Bitwise AND W with literal [cite: 6, 88] | [cite_start]4 [cite: 91] |
| **ORW** | `1110` | 8-BIT Literal | [cite_start]Bitwise OR W with literal [cite: 6, 94] | [cite_start]4 [cite: 97] |
| **NOTW** | `1111` | NULL | [cite_start]Bitwise NOT W [cite: 6, 100] | [cite_start]4 [cite: 103] |

---

## Repository Contents

* **`/hdl`**: Verilog source files (`.v`) for the CPU core and sub-modules.
* **`/rtl`**: RTL schematics and structural block diagrams.
* **`/testbench`**: Functional verification scripts and test vectors.
* **`/docs`**: Full datasheet, timing diagrams, and pin assignment logs.
* **`/sim`**: Simulation waveforms and timing analysis.

---

**Implementation**: Verilog HDL
