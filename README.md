# Smart Vending Machine Controller

![Verilog](https://img.shields.io/badge/HDL-Verilog-blue)
![Digital Design](https://img.shields.io/badge/Design-Digital%20Logic-orange)
![FSM](https://img.shields.io/badge/Architecture-FSM-green)
![FPGA](https://img.shields.io/badge/Target-FPGA-purple)
![Status](https://img.shields.io/badge/Status-In%20Development-yellow)

A Verilog HDL-based vending machine controller designed using finite-state-machine concepts for digital hardware implementation.

---

## Overview

This project implements a hardware-based vending machine controller using **Verilog HDL**.

The design demonstrates how a real-world vending machine can be modeled as a digital sequential system using:

- Finite State Machines (FSM)
- Sequential logic
- Combinational logic
- Clock division
- Input debouncing
- Product selection
- Transaction control
- Seven-segment display interfacing
- FPGA-oriented hardware design

The project is organized into multiple RTL modules that handle the vending-machine controller, clock management, input conditioning, display logic, and board-level integration.

---

## System Architecture

```text
                    +----------------------+
                    |     User Inputs      |
                    |                      |
                    | Product Selection    |
                    | Coin / Control Input |
                    +----------+-----------+
                               |
                               v
                    +----------------------+
                    |    Input Debouncer   |
                    |    debouncer.v      |
                    +----------+-----------+
                               |
                               v
                    +----------------------+
                    |   Vending Machine    |
                    |      Controller      |
                    |                      |
                    |      FSM Logic       |
                    +----------+-----------+
                               |
              +----------------+----------------+
              |                |                |
              v                v                v
       +-------------+  +-------------+  +-------------+
       |   Product   |  |   Balance   |  |   Change /  |
       |   Control   |  |   Control   |  |   Output    |
       +-------------+  +-------------+  +-------------+
              |                |                |
              +----------------+----------------+
                               |
                               v
                    +----------------------+
                    | Seven-Segment Display|
                    |       ssd.v          |
                    +----------------------+
                               |
                               v
                    +----------------------+
                    | FPGA Board Interface |
                    | vending_machine_     |
                    | board.v              |
                    +----------------------+
