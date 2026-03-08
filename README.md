# SPI Protocol Implementation in Verilog

## Description
This project implements the **Serial Peripheral Interface (SPI)** protocol using Verilog HDL. The design models a simple SPI transmitter controlled by a Finite State Machine (FSM). The module serially transmits a 16-bit input data through the MOSI line while generating the required SPI control signals.

The implementation demonstrates how SPI communication works at the hardware level and how serial data transmission is achieved using clock-driven logic.

---

## Features
- Verilog-based implementation of SPI communication
- 16-bit serial data transmission
- FSM-based control logic
- Generation of SPI signals: **CS (Chip Select), SCLK (Serial Clock), MOSI (Master Out Slave In)**
- Counter-based bit shifting
- Simulation verified using a testbench

---

## Working Principle
The SPI module operates as a transmitter. When the reset signal is released, the SPI controller begins the communication by activating the chip select signal. The input data is loaded and transmitted serially through the MOSI line.

The serial clock (SCLK) controls the shifting of data bits. A counter keeps track of the number of bits transmitted. Once all bits are sent, the controller resets the counter and returns to the initial state.

---

## Module Inputs and Outputs

| Signal | Description |
|------|-------------|
| clk | System clock |
| reset | Reset signal |
| datain | 16-bit input data |
| spi_cs_l | Chip select signal (active low) |
| spi_sclk | Serial clock signal |
| spi_data | Serial data output (MOSI) |
| counter | Bit counter |

---

## Simulation
A Verilog testbench is used to verify the functionality of the SPI module. The testbench generates clock and reset signals and applies different input data values to observe the SPI transmission behavior.

---

## Tools Used
- Verilog HDL
- ModelSim / Vivado Simulator
- FPGA Design Flow
