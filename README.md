# Educational 10-bit FPGA Processor Implementation

A SystemVerilog implementation of a simple 10-bit processor designed for FPGA platforms, featuring a custom instruction set, 1024x10 RAM, register file, ALU, and 7-segment display output. Perfect for teaching computer architecture fundamentals and hardware design concepts.

## Overview
This project implements a complete 10-bit processor system with the following key components:
- 10-bit data bus architecture
- 1024x10 RAM module for program and data storage
- Register file with multiple addressing modes
- Multi-stage ALU for arithmetic and logical operations
- Seven-segment display output system
- Debounced input handling for switches and buttons

## Components

### Top Level Module (`top_level_10bit`)
The main system controller that integrates all components and manages the control flow. It includes:
- Clock management and debouncing
- Data bus coordination
- Instruction execution control
- I/O handling

### RAM Module (`ram_1024x10`)
A 1024-word memory system with:
- 10-bit word width
- Synchronous write operations
- Asynchronous read operations
- Address register for bus operations

### Output Logic (`outputlogic`)
Handles all display and indicator functions:
- Three 7-segment displays for data visualization
- Current timestep indicator
- LED output for data bus monitoring
- Operation completion status

## Setup and Usage

1. Load the design onto a compatible FPGA board
2. Use the input switches to provide data and instructions
3. Monitor execution through:
   - 7-segment displays showing current values
   - LED strip displaying data bus contents
   - Status indicators for operation completion

## Control Signals
- `Clock_Button`: Manual clock control
- `Peek_Button`: Display internal register values
- `Raw_Data_From_Switches`: Data input interface
- Various enable signals for component control

## Display System
- `DHEX0`, `DHEX1`, `DHEX2`: Three 7-segment displays showing current values
- `THEX_Current_Timestep`: Shows current execution step
- `LED_B_Data_Bus`: Displays current data bus state
- `LED_D_Done`: Indicates operation completion

## Hardware Requirements
- FPGA development board with:
  - Minimum 10 input switches
  - At least 4 seven-segment displays
  - LED strip for data visualization
  - Two push buttons for control

## Implementation Notes
- All operations are synchronized to the negative edge of the clock
- Input debouncing is implemented for reliable button operation
- High-impedance states are used for bus management
- Modular design allows for easy modification and expansion

## Contributing
Feel free to submit issues and enhancement requests. PRs are welcome.
