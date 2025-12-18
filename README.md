# 4-Bit BCD Multiplier

## 📌 Project Overview
This repository documents the design and implementation of a **4-Bit Binary Coded Decimal (BCD) Multiplier**.

The multiplier is implemented **entirely using basic logic gates, flip-flops, counters, and asynchronous/sequential logic**, without relying on any PC, processor, or software-based computation. All arithmetic operations are performed through hardware logic only.

---

## 🎯 Key Objectives
- Design a **4-bit BCD sequential multiplier**
- Accept **only valid BCD inputs (0–9)**
- Perform multiplication using **controlled shifting and addition**
- Display the final product on a **digital 7-segment display**
- Implement the system **without using a computer or programmable controller**
- Use **counters and asynchronous logic** to control the multiplication process

---

## 🧠 Design Philosophy
The design combines **combinational logic** for input validation and arithmetic control with **sequential logic** for shifting, counting, and result storage.

Key principles:
- **Pure hardware implementation**
- **Strict BCD compliance**
- **Controlled sequential operation using a down counter**
- **Automatic truncation and result holding**

---

## 🧩 System Architecture

### 🔹 Major Blocks
1. **BCD Input Validation Logic**
   - Ensures only valid BCD inputs (0000–1001) are accepted
   - Invalid inputs are forced to zero

2. **4-Bit PIPO Register (Multiplier)**
   - Stores the first BCD number
   - Supplies data conditionally based on multiplier bits

3. **4-Bit PISO Register (Multiplicand)**
   - Shifts bits sequentially
   - Controls when addition occurs using its LSB

4. **Full Adder with Shift Capability**
   - Adds partial products
   - Supports right shifting during multiplication

5. **4-to-0 BCD Down Counter**
   - Controls the number of shift/add cycles
   - Stops shifting when count reaches zero

6. **8-Bit Product Register**
   - Acts as:
     - **PISO** during multiplication
     - **PIPO** after completion to hold final value

7. **Binary-to-BCD Converter and Display**
   - Converts the 8-bit product to BCD
   - Displays result on a 7-segment display

---

## 🔁 Working Principle
1. Both inputs are validated to ensure BCD compliance.
2. The multiplicand shifts bit-by-bit through the PISO register.
3. When the current multiplier bit is `1`, the multiplicand is added to the product register.
4. A **down counter** controls the shifting cycles.
5. Once the counter reaches zero:
   - Shifting stops
   - The final product is stored and displayed
6. The output remains latched until the next operation.

---

## 🔧 Hardware Components Used

### ICs (7400 Series)
- **7408** – AND Gates  
- **7432** – OR Gates  
- **7404** – NOT Gates  
- **7474** – D Flip-Flops  
- **7476** – JK Flip-Flops  
- **7447** – BCD to 7-Segment Decoder  
- **74185** – Binary to BCD Converter  

### Other Components
- Toggle switches for inputs  
- Jumper wires  
- Common-cathode 7-segment display  
- Power supply and clock source  

> ⚠️ No PC, microprocessor, or software-based computation is used in the multiplication logic.

---

## ✅ Results & Observations
- Correct multiplication of all valid BCD inputs (0–9)
- Stable and reliable sequential operation
- Accurate display of results on 7-segment display
- Automatic truncation to fit display limits
- Strong correlation between theoretical design and practical implementation

---

## 📈 Applications
- Digital calculators  
- Financial and accounting systems  
- Embedded systems  
- Digital signal processing  
- Educational demonstration of sequential arithmetic circuits  

---

## 🚀 Future Improvements
- FPGA-based implementation for speed and scalability
- Improved display resolution
- Parallel multiplication architecture
- Optimized BCD arithmetic IC usage

---

## 📜 License
This project is intended for **academic and educational use only**.

---

> *This project demonstrates how complex arithmetic operations can be achieved using only fundamental digital logic concepts, reinforcing the practical importance of combinational and sequential circuit design.*
