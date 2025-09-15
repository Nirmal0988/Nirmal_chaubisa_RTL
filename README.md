# UART AXI4-Stream RTL Design (Verilog)

This repository contains an **RTL implementation of UART (Universal Asynchronous Receiver Transmitter)** using **Verilog HDL**.  
It includes both **TX (transmit)** and **RX (receive)** modules, designed for **AXI4-Stream interface integration** on FPGA.

---

## 📂 Repository Contents

- **`uart_rx.v`** → UART **Receiver (RX)** module  
  - Stable and verified  
  - No changes required  

- **`uart_tx.v`** → UART **Transmitter (TX)** module  
  - Initial design had a **state machine bug**  
  - Issue fixed in the current version  

- **`README.md`** → Documentation (this file)

---

## 🛠️ Features

- Verilog RTL design for UART TX and RX  
- AXI4-Stream compatible interfaces  
- Fully synthesizable and FPGA-ready  
- Modular design for easy integration  
- TX bug fixed (state machine correction)

---

## ✅ Bug Fix Summary

- **Issue:** UART TX module had an error in one state of the FSM (Finite State Machine).  
- **Fix:** The TX FSM was corrected and validated.  
- **RX Module:** No changes, remains stable.  

---

## 🚀 Usage

1. Clone the repository:
   ```bash
   git clone https://github.com/Nirmal0988/Nirmal_chaubisa_RTL.git
   cd Nirmal_chaubisa_RTL
