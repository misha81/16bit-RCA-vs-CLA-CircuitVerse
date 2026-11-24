# Performance and Hardware Trade-offs: 16-Bit Ripple-Carry vs. Carry-Lookahead Adders

**Authors:** Mykhail Opanasiuk (75697), Vladyslav Lisovyi (75689)  
**Course:** Computer Architecture — Student Research Challenge  

## Overview
This repository contains the complete CircuitVerse project archive (`.cv`) supporting our empirical study comparing the time-versus-space complexity trade-offs between a **16-bit Ripple-Carry Adder (RCA)** and a **16-bit Carry-Lookahead Adder (CLA)**.

## Included Subcircuits
The project file includes all hierarchical digital logic modules constructed from basic logic gates (`AND`, `OR`, `XOR`):
- **1-Bit Half Adder & 1-Bit Full Adder**
- **2-Bit, 4-Bit, 8-Bit, and 16-Bit Ripple-Carry Adders (RCA)**
- **1-Bit Propagate/Generate (P/G) Block** ($P_i = A_i \oplus B_i$, $G_i = A_i \cdot B_i$)
- **4-Bit Lookahead Carry Unit (LCU)** (two-level AND–OR parallel carry logic)
- **4-Bit CLA Block**
- **16-Bit Carry-Lookahead Adder (CLA)** (4×4-bit block-ripple architecture)

## How to Open and Simulate
1. Download the `.cv` project file from this repository.
2. Open the online CircuitVerse simulator at [https://circuitverse.org/simulator](https://circuitverse.org/simulator).
3. In the top menu, click **Project → Import Project** and select the downloaded `.cv` file.
4. Switch between circuit tabs at the top of the workspace (e.g., `16-Bit Full Adder`, `4-Bit LCU`, `4-Bit CLA Block`, `16-Bit CLA`) to inspect the gate-level structure and test input vectors interactively.

## Verification Test Vectors
Both 16-bit adders can be verified in the simulator using the following test cases:
- **Zero Addition:** `A = 0000`, `B = 0000`, `Cin = 0` → `Sum = 0000`, `Cout = 0`
- **Intra-Block Carry:** `A = 000F`, `B = 0001`, `Cin = 0` → `Sum = 0010`, `Cout = 0`
- **Alternating Bits:** `A = AAAA`, `B = 5555`, `Cin = 0` → `Sum = FFFF`, `Cout = 0`
- **Worst-Case Carry Propagation:** `A = FFFF`, `B = 0001`, `Cin = 0` → `Sum = 0000`, `Cout = 1`
- **Maximum Overflow:** `A = FFFF`, `B = FFFF`, `Cin = 1` → `Sum = FFFF`, `Cout = 1`
