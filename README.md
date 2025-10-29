# Single-Cycle Processor Design Project

**Course:** ENCS2380 – Computer Organization and Microprocessor  
**Project Title:** Design and Verification of a 32-bit Single-Cycle Processor  
**Prepared by:**  
- Saifeddin Saleh – 1231474  
- Omar Shoubaki – 1230329  
- Ibrahim Irshaid – 1231870  
**Instructor:** Abualseoud Hanani  
**Date:** 15/6/2025  

---

## 📘 Project Overview
This project involves the **design and implementation of a 32-bit single-cycle processor** in Logisim, based on a custom 24-bit instruction set architecture (ISA).  
The processor integrates all major hardware components — the **register file**, **ALU**, **control unit**, **PC controller**, and **datapath** — into a unified system capable of executing arithmetic, logic, memory, and branching operations.

The processor supports three main instruction formats:
- **R-Type** – Register operations (e.g., ADD, AND, SLT)  
- **I-Type** – Immediate operations and branching (e.g., ADDI, BEQ, LW, SW)  
- **J-Type** – Jump operations (e.g., J, JAL)

---

## ⚙️ Processor Components
### 1. Register File
- Contains **16 general-purpose 32-bit registers** (R0–R15).  
- R0 is hardwired to zero.  
- Includes **one write port (Rx)** and **two read ports (Ry, Rz)** controlled by decoders.  

### 2. Arithmetic Logic Unit (ALU)
- Supports 12 operations including: `AND`, `CAND`, `OR`, `XOR`, `ADD`, `NADD`, `SEQ`, `SLT`, `SLL`, `SRL`, `SRA`, and `ROR`.  
- Built using a 16x1 multiplexer and 32-bit logic circuits.  

### 3. Control Unit
- Decodes instruction opcodes and generates control signals for datapath components.  
- Handles signals like **RegDst**, **RegWrite**, **MemWrite**, **ALUsel**, and **WbData**.  

### 4. PC Controller
- Determines program counter updates based on instruction type:  
  - PC += 3 for normal execution  
  - PC += (Imm8 << 1) for branches  
  - PC += (Imm16 << 1) for jumps  

### 5. Datapath
- Integrates all modules for instruction fetch, decode, execute, memory, and write-back cycles.  
- Includes RAM, ROM, RegSel, and control multiplexers to manage instruction flow.

---

## 🧪 Simulation and Testing
Each instruction was tested in **Logisim** using waveform analysis to confirm proper behavior.  
Key tested instructions include:

| Type | Example | Function |
|------|----------|-----------|
| R-Type | `ADD R5, R1, R2` | Adds two registers |
| I-Type | `ADDI R8, R1, 3` | Adds register and immediate |
| Branch | `BEQ R1, R2, 2` | Branches if equal |
| Memory | `LW R6, R0, 4` / `SW R1, R0, 4` | Load/store |
| Jump | `J 2`, `JAL 2` | Jump and link |

All instructions produced correct results across multiple test programs.  
Simulation verified correct data movement, PC updates, control signals, and branch execution.

---

## 🧩 Results
- The processor successfully executed all R-type, I-type, and J-type instructions.  
- Control logic and datapath synchronization were validated through simulation.  
- The **done flag**, **branch decisions**, and **PC behavior** were consistent with expectations.  
- The final design demonstrates proper integration between all hardware components.

---

## 📈 Tools Used
- **Logisim** – For circuit design and simulation  
---

## 🧠 Key Concepts Demonstrated
- Custom ISA design and decoding  
- Control unit generation using ROMs and logic  
- Single-cycle datapath integration  
- Branching, memory access, and jump execution  
- Modular hardware design and testing methodology  

---

## 📎 Documentation
For full technical details, schematics, and simulation results, refer to the complete project report:  
📄 [Download Report (PDF)](./Orga%20Report%20(1).pdf)

---

## 🏁 Conclusion
This project demonstrates the successful design and verification of a **single-cycle processor** capable of handling arithmetic, logical, memory, and control instructions in one clock cycle.  
The processor showcases efficient datapath design, correct control signal generation, and functional branching — providing a strong foundation for understanding **computer architecture and microprocessor design**.

---

