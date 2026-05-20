# MESI Cache Coherence Controller in Verilog

**Overview**
This project implements a MESI (Modified, Exclusive, Shared, Invalid) Cache Coherence Controller using Verilog HDL. The design models the MESI finite state machine (FSM) commonly used in multiprocessor systems to maintain cache coherence between multiple processing cores.
The controller handles CPU read/write requests and snoop requests from other processors, performing appropriate MESI state transitions and generating coherence signals such as invalidate and writeback.

The design was synthesized and implemented successfully using Xilinx Vivado.

**Project Objectives**
Implement the MESI cache coherence protocol
Design a synthesizable finite state machine in Verilog
Demonstrate cache coherence state transitions
Generate RTL schematic using Vivado
Verify coherence behavior using simulation

**MESI Protocol**
The MESI protocol uses four states:

State	Description
| Current State | Event       | Next State |
| ------------- | ----------- | ---------- |
| Invalid       | CPU Read    | Exclusive  |
| Invalid       | CPU Write   | Modified   |
| Exclusive     | CPU Write   | Modified   |
| Exclusive     | Other Read  | Shared     |
| Exclusive     | Other Write | Invalid    |
| Shared        | CPU Write   | Modified   |
| Shared        | Other Write | Invalid    |
| Modified      | Other Read  | Shared     |
| Modified      | Other Write | Invalid    |

**Design Features**
Synthesizable Verilog RTL
FSM-based coherence controller
CPU request handling
Snoop request handling
Invalidate signal generation
Writeback signal generation
Vivado compatible
Clean RTL architecture
FPGA implementation compatible

**Inputs and Outputs**
| Signal      | Description                      |
| ----------- | -------------------------------- |
| clk         | System clock                     |
| rst         | Reset signal                     |
| cpu_read    | CPU read request                 |
| cpu_write   | CPU write request                |
| other_read  | Read request from another cache  |
| other_write | Write request from another cache |

**RTL Architecture**
The design is implemented as a finite state machine (FSM) with sequential state registers and combinational next-state logic.

<img width="1897" height="542" alt="rtl_vivado" src="https://github.com/user-attachments/assets/e94329ce-cca4-4f09-a127-794269a74a99" />


**Vivado Flow**
Tool Used
Xilinx Vivado

The RTL schematic generated in Vivado shows:

FSM sequential registers
State transition LUTs
Output logic
Input/output buffers


**Applications**
Multiprocessor systems
Cache coherence mechanisms
Computer architecture education
FPGA-based architecture projects
RTL and FSM design practice

**Future Improvements**
Dual-cache coherence system
Full cache controller integration
UVM-based verification
Functional coverage
Assertions
Multi-core cache simulation
LRU replacement policy
BRAM-based cache storage

**Conclusion**
This project demonstrates the implementation of a MESI cache coherence finite state machine using Verilog HDL. The design successfully models MESI state transitions and coherence behavior while remaining synthesizable and FPGA compatible.
The project provides a strong foundation for understanding cache coherence protocols, finite state machine design, and RTL-based hardware implementation.
