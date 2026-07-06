# Programmable Interrupt Controller (PIC) in Verilog

A synthesizable Verilog implementation of an **8-input Programmable Interrupt Controller (PIC)** supporting multiple interrupt servicing modes. The design is based on a finite-state machine (FSM) architecture and includes a complete simulation testbench.

---

## Features

- 8 external interrupt inputs
- Polling mode
- Custom programmable priority mode
- Dynamic priority table configuration
- Interrupt acknowledgement protocol
- Tri-state data bus interface
- FSM-based controller
- Fully synthesizable RTL
- Verilog testbench included

---

## Architecture

The interrupt controller consists of the following modules:

```
                 +-----------------------+
Interrupts ----->|                       |
                 | Interrupt Controller  |
CPU Data Bus <-->|
                 | FSM Control Unit      |
Acknowledgement->|
                 | Priority Manager      |
                 +-----------------------+
```

## Operating Modes

### 1. Polling Mode

- Interrupts are scanned sequentially.
- The first active interrupt is serviced.
- No fixed priorities.

### 2. Priority Mode

The processor can program the interrupt priority table.

Example:

```
Highest Priority

IRQ5
IRQ2
IRQ7
IRQ0
IRQ6
IRQ1
IRQ3
IRQ4

Lowest Priority
```

The controller services interrupts according to this table.

---

## Finite State Machine

Main controller states include:

- Reset
- Get Commands
- Polling
- Priority Scheduling
- Interrupt Transmission
- Interrupt Acknowledge
- ISR Completion

---

## Simulation

The repository contains a Verilog testbench that verifies:

- Reset functionality
- Polling operation
- Priority operation
- Interrupt acknowledgement
- State transitions

---

## Future Improvements

- Nested interrupts
- Interrupt masking
- Rotating priority
- Fully compatible 8259A mode
- Parameterized interrupt width
- SystemVerilog assertions
- UVM verification environment

---

## Tools

- Verilog HDL
- ModelSim / QuestaSim
- Vivado
- Icarus Verilog

---

## Author
Ridham Garg
2024epb1276@iitrpr.ac.in
Indian Institute of Technology, Ropar
