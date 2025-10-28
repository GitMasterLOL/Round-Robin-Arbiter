# 8 bit Priority based Round Robin Arbiter – ASIC Design and Verification

This repository contains the complete RTL design, verification environment, and synthesis analysis for a **Round Robin Arbiter**.  
It demonstrates the full ASIC design flow — from specification to simulation and timing verification — following industry-standard structure and documentation practices.

---

## Overview

A **Round Robin Arbiter** grants access among multiple requesters in a fair, cyclic order.  
When multiple clients request access simultaneously, each is served in turn — ensuring *no starvation* and *deterministic latency*.

---

## Repository Structure

```
Round-Robin-Arbiter/
├── docs/         # Specifications, architecture, timing reports, and diagrams
├── pd/           # Physical design including floorplan, placement and routing
├── rtl/          # Synthesizable Verilog design modules
├── signoff/      # Physical and timinig verification
├── sim/          # Simulation logs, waveforms, and summaries
├── synth/        # ASIC synthesis scripts and timing reports
├── tb/           # Testbench, test plan, and test cases
└── README.md     # This file
```

---

## Features

- Fair round-robin arbitration among `N` requesters with different priority levels
- Configurable number of request lines (`NUM_REQ` parameter)
- Encoded grant output with 1-cycle latency
- Asynchronous active-high reset
- Fully synthesizable, ASIC/FPGA compatible
- Verified through directed and randomized test cases

---

## Functional Specification

- At any given clock cycle, the arbiter outputs an encoded grant value indicating which requester index (0 to N−1) is currently granted access.
- The arbiter remembers the **last granted requester** and gives next-cycle priority to the following requester.
- On **reset**, the priority starts from requester 0.
- If no requests are active, the grant output is invalid (`valid` bit is 0) and no requester is selected.

---

## Design Flow

| Stage | Tool | Description |
|-------|------|-------------|
| RTL Design | Verilog | Synthesizable logic for arbiter |
| Simulation | Cadence Xcelium | Functional verification |
| Synthesis | Cadence Genus | Timing, area, and performance reports |
| Physical Design | Cadence Innovus | Floorplan, placement, routing |
| Timing signoff | Cadence Tempus | Static Timing Analysis post clock routing |
| Documentation | Markdown, (Drawing tools) | Specs and architecture diagrams |

---

## Author

**Mahendra**  
Electronics Engineer with specialization in VLSI Design and Technology | VIT, India  
Project: *ASIC Design and Verification of a Round Robin Arbiter*
