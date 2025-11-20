# FPGA-Basics

<!--toc:start-->

- [FPGA-Basics](#fpga-basics)
  - [PHASE 1 — Foundations & RTL Mastery (Days 1–30)](#phase-1-foundations-rtl-mastery-days-130)
    - [Week 1 — RTL Warm-Up](#week-1-rtl-warm-up)
      - [Week 1 Topics](#week-1-topics)
      - [Week 1 Hands-on](#week-1-hands-on)
    - [Week 2 — FPGA Toolchain + Simulation](#week-2-fpga-toolchain-simulation)
      - [Week 2 Topics](#week-2-topics)
      - [Week 2 Hands-on](#week-2-hands-on)
    - [Week 3 — Bus Protocols (Soft Entry to HFT Workflows)](#week-3-bus-protocols-soft-entry-to-hft-workflows)
      - [Week 3 Topics](#week-3-topics)
      - [Week 3 Hands-on](#week-3-hands-on)
  - [Week 4 — Your First Real Accelerator](#week-4-your-first-real-accelerator)
    - [Week 4 Topics](#week-4-topics)
      - [Week 4 Hands-on Project](#week-4-hands-on-project)
  - [PHASE 2 — HFT Skills + Processor Design (Days 31–60)](#phase-2-hft-skills-processor-design-days-3160)
    - [Week 5 — Low-Latency Design Mindset](#week-5-low-latency-design-mindset)
      - [Week 5 Topics](#week-5-topics)
      - [Week 5 Hands-on](#week-5-hands-on)
    - [Week 6 — Networking + Packet Parsing](#week-6-networking-packet-parsing)
      - [Week 6 Topics](#week-6-topics)
      - [Week 6 Hands-on Project](#week-6-hands-on-project)
    - [Week 7 — Processor Design Track Begins](#week-7-processor-design-track-begins)
      - [Week 7 Topics](#week-7-topics)
      - [Week 7 Hands-on](#week-7-hands-on)
    - [Week 8 — CPU Pipeline + Hazard Handling](#week-8-cpu-pipeline-hazard-handling)
      - [Week 8 Topics](#week-8-topics)
      - [Week 8 Hands-on](#week-8-hands-on)
  - [PHASE 3 — HFT-Level Work + Portfolio Projects (Days 61–90)](#phase-3-hft-level-work-portfolio-projects-days-6190)
    - [Week 9 — Hardware-Accelerated Networking (Real HFT Stuff)](#week-9-hardware-accelerated-networking-real-hft-stuff)
      - [Week 9 Topics](#week-9-topics)
      - [Week 9 Hands-on](#week-9-hands-on)
    - [Week 10 — HFT Mini Feed Handler](#week-10-hft-mini-feed-handler)
      - [Week 10 Topics](#week-10-topics)
      - [Week 10 Hands-on Project](#week-10-hands-on-project)
    - [Week 11 — CPU Specialization: Custom ISA Accelerator](#week-11-cpu-specialization-custom-isa-accelerator)
      - [Week 11 Topics](#week-11-topics)
      - [Week 11 Hands-on Project](#week-11-hands-on-project)
    - [Week 12 — Final Portfolio Project](#week-12-final-portfolio-project)
      - [Week 12 Hands-on Project](#week-12-hands-on-project)

<!--toc:end-->

## PHASE 1 — Foundations & RTL Mastery (Days 1–30)

Goal: Become solid at RTL, timing, and FPGA workflows.

### Week 1 — RTL Warm-Up

#### Week 1 Topics

- Combinational vs Sequential
- Nonblocking vs blocking
- Reset/clock strategies
- Metastability (your weak area → we will fix this)
- Synchronizers / Clock Domain Crossing (CDC)

#### Week 1 Hands-on

- Debouncer
- 2-FF synchronizer
- Edge detector
- Fix a metastability bug in simulation

### Week 2 — FPGA Toolchain + Simulation

#### Week 2 Topics

- Vivado basics
- Synthesis vs Implementation
- Static Timing Analysis
- Constraints (XDC)
- Waveform viewing
- Testbench writing

#### Week 2 Hands-on

- Build your RegisterFIFO properly with TB
- Add waveform-based debugging

### Week 3 — Bus Protocols (Soft Entry to HFT Workflows)

#### Week 3 Topics

- AXI4-Lite (register access)
- AXI4-Stream (data pipe — used everywhere in HFT)
- Simple DMA flow

#### Week 3 Hands-on

- AXI4-Stream passthrough pipeline
- Add a register-controlled filter block

## Week 4 — Your First Real Accelerator

### Week 4 Topics

- Pipelining
- Throughput vs Latency
- Multicycle paths & false paths

#### Week 4 Hands-on Project

- Build a 4-stage pipelined Packet Header Extractor Input: 64-bit “fake packet”
  Output: src/dst + type. This becomes foundational for your HFT parser later.

## PHASE 2 — HFT Skills + Processor Design (Days 31–60)

Goal: Become functional in both domains.

### Week 5 — Low-Latency Design Mindset

#### Week 5 Topics

- Nanosecond-level design
- Register slices
- Cut-through pipelines
- Congestion + timing closure
- Backpressure

#### Week 5 Hands-on

- Build a “Latency-Optimized FIFO” (2-cycle pass-through)

### Week 6 — Networking + Packet Parsing

#### Week 6 Topics

- Ethernet basics
- UDP/TCP header structure
- Checksum logic
- MAC interfaces (Xilinx CMAC basics)

#### Week 6 Hands-on Project

- 10G-style packet parser (simulated) → Extract MAC, IP, UDP headers → Count
  packets → Only 1–2 cycles per stage. This is literally “starter HFT feed
  handler logic.”

### Week 7 — Processor Design Track Begins

#### Week 7 Topics

- ISA basics
- Single-cycle CPU architecture
- Datapath design
- Control unit
- Register file

#### Week 7 Hands-on

- Build a single-cycle RISC-V subset CPU. Run a few assembly programs in your
  simulator

### Week 8 — CPU Pipeline + Hazard Handling

#### Week 8 Topics

- IF / ID / EX / MEM / WB
- Forwarding
- Hazard detection
- Branch predictor (optional)
- Clock gating basics

#### Week 8 Hands-on

- Turn your single-cycle CPU → 5-stage CPU Demonstrate: correct stall cycles
  forwarding handle load-use hazard

## PHASE 3 — HFT-Level Work + Portfolio Projects (Days 61–90)

Goal: Build resume-ready HFT + CPU projects.

### Week 9 — Hardware-Accelerated Networking (Real HFT Stuff)

#### Week 9 Topics

- Multicast
- Ingress pipelines
- Timestamping engines
- CRC32 / checksum acceleration
- Nanosecond measurement

#### Week 9 Hands-on

- Add hardware timestamp logic to your parser: Output (timestamp, packet type)

### Week 10 — HFT Mini Feed Handler

#### Week 10 Topics

- Binary formats
- Latency budgeting
- No-ops vs combinational passes
- Queues + priority mechanisms

#### Week 10 Hands-on Project

- Build an FPGA Feed Handler (Simplified): Receive fake 64B packets Parse header
  Parse a few “market data entries” Push to order-book module

### Week 11 — CPU Specialization: Custom ISA Accelerator

This ties your compiler backend experience to hardware.

#### Week 11 Topics

- Custom instruction design
- Accelerator datapath
- CPU–accelerator interface
- Inline accelerator calls from C

#### Week 11 Hands-on Project

- Add 1 custom instruction (e.g., dot-product)
- Modify your 5-stage CPU to support it
- Run end-to-end program on simulator
- This shows you can do: ✔ Compiler backend ✔ Processor design ✔ Hardware
  acceleration

### Week 12 — Final Portfolio Project

#### Week 12 Hands-on Project

- HFT Track: “Low-Latency Market Data Router” parses fake packets updates a
  small order book responds with top-of-book data latency target: < 50 cycles
  end-to-end

- CPU Track: “Mini Out-of-Order RISC-V” (basic issue queue) 2-wide issue ROB
  Bypassing Functional units
