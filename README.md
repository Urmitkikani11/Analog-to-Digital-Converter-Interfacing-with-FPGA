# FPGA-Based ADC0809 Interface using Verilog

This project demonstrates the interfacing of the **ADC0809** analog-to-digital converter (ADC) with an **FPGA DE2 board** using **Verilog HDL**. The implementation captures analog input, triggers conversion, and retrieves 8-bit digital output data.

[![License: MIT](https://img.shields.io/badge/License-MIT-white.svg)](LICENSE)

---

## 📑 Project Overview

- **Title**: Analog-to-Digital Conversion using ADC0809 and FPGA  
- **Platform**: Altera DE2 FPGA Board  
- **Language**: Verilog HDL  
- **Submitted by**:  
  - Urmit Kikani (22BEC137)  
- **Institution**: Nirma University  
- **Guide**: Prof. Hardik Joshi  

---

## 🔧 Functionality

The Verilog module handles:
- Channel selection via address lines `a`, `b`, `c`
- Control signals: `ALE`, `SC`, `EOC`, `OE`
- Clock division (50 MHz → ~0.5 kHz)
- Digital data read from ADC0809
- Outputting captured 8-bit digital data to downstream logic

---

## 🔌 Pin Description

| Signal     | Direction | Description                                 |
|------------|-----------|---------------------------------------------|
| `clk_in`   | Input     | 50 MHz clock input from DE2 board           |
| `clk_out`  | Output    | Divided clock output (~0.5 kHz)             |
| `ale_out`  | Output    | Address Latch Enable signal to ADC          |
| `sc_out`   | Output    | Start Conversion trigger                    |
| `eoc`      | Input     | End Of Conversion signal from ADC           |
| `in_data`  | Input     | 8-bit digital output from ADC0809           |
| `out_data` | Output    | Captured 8-bit output to FPGA               |
| `a,b,c`    | Output    | Channel selection lines                     |
| `oe`       | Output    | Output Enable signal to ADC                 |
| `led`      | Output    | Status LED output                           |

---

## 🧠 System Flow

1. Select ADC input channel via selector lines
2. Trigger `Start Conversion` (SC)
3. Monitor `End Of Conversion` (EOC)
4. Enable output (OE)
5. Capture and store 8-bit output data

📄 [Flow Chart (PDF)](Flow%20chart/Flow%20chart.pdf)  
🧱 [Block Diagram (PDF)](Block%20diagram/Block%20Diagram%20.pdf)

---

## 📦 Repository Contents

- [`ADC.v`](Code/ADC.v) – Verilog module for ADC0809 interface  
- [`Report FPGA.pdf`](Report/22BEC137_FPGA%20REPORT.pdf) – Project report with diagrams, results, and conclusion  
- [`Flow chart.pdf`](Flow%20chart/Flow%20chart.pdf) – Logic flow of the system  
- [`Block Diagram.pdf`](Block%20diagram/Block%20Diagram%20.pdf) – Hardware connection overview  
- `README.md` – You are here 📘

---

## ✅ Output & Results

- Accurate real-time conversion and output display
- Tested with LED indicators and waveform viewers
- RTL and TTL results verified via ModelSim simulation

---

## 🚀 Future Scope

- Support multi-channel sampling with priority logic
- Integrate FIR filters for real-time signal conditioning
- Connect to GUI-based display for signal visualization

---

## 🛠️ Tools Used

- **Intel Quartus Prime** – FPGA development  
- **ModelSim** – RTL simulation & debugging  
- **DE2 Board** – FPGA hardware platform

---

## 📚 References

1. Roth Jr., C. H., & John, L. K. (2011). *Digital Systems Design Using Verilog*  
2. Palnitkar, S. (2003). *Verilog HDL*  
3. Smith, K. W. (1997). *Analog-to-Digital Conversion*  
4. Mazidi, M. A., & McKinlay, R. D. (2013). *The 8051 Microcontroller and Embedded Systems*

---

## 🙌 Acknowledgements

Special thanks to [**Neha Golani**](https://github.com/Nehagolani19) for contributing significantly to the project and supporting the hardware setup and documentation.  

---

## 📩 Contact

For questions, suggestions, or collaboration:  [Urmitkikani1184@gmail.com](mailto:Urmitkikani1184@gmail.com)

---


## 📄 License

This project is licensed under the [MIT License](LICENSE).
