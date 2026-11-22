# ASIC Design Roadmap — Digital Power Management

> FPGA-to-ASIC engineering programme for a digital power-management controller.

## Baseline
- **Target:** Four-channel digital power-management controller
- **Strategy:** FPGA reference design, then ASIC implementation
- **RTL:** SystemVerilog
- **FPGA reference:** Lattice ECP5
- **Initial ASIC learning platform:** SKY130
- **Tools:** Yosys, Verilator, cocotb, SymbiYosys, OpenROAD, OpenSTA, KLayout

## Purpose and scope
This repository captures requirements, architecture, RTL, verification evidence and physical-design results. The first silicon-oriented deliverable is a digital controller; external MOSFETs, gate drivers, comparators and ADCs remain outside the initial ASIC. Analogue/high-voltage integration is a later investigation.

Initial functions:
- Four-channel PWM, complementary outputs and configurable dead-time
- Hardware fault override and defined safe states
- Programmable multi-rail sequencing
- OVP, UVP, OCP and OTP fault handling
- SPI configuration/telemetry and ADC interface
- Watchdog, diagnostics and fault logging

## Design principles
1. Hardware protection overrides normal control independently of firmware/SPI.
2. Reset, clock failure and brownout behaviour are explicitly specified.
3. Complementary gate commands must never overlap.
4. RTL is synthesizable and portable between FPGA and ASIC where practical.
5. Requirements are traceable to verification evidence.
6. PPA results identify PDK, library, constraints and tool versions.
7. Open-PDK results do not imply production or safety qualification.

## Repository map
```text
docs/requirements/       System and block requirements
docs/architecture/      Architecture, interfaces and design decisions
rtl/{pwm,sequencer,protection,spi,adc_interface,top}/
verification/{testbenches,assertions,cocotb,regression}/
fpga/reference_implementation/
asic/{synthesis,constraints,floorplan,physical_design,signoff}/
scripts/
results/{timing,area,power}/
```

## Development flow
1. Requirements and architecture
2. RTL implementation and lint
3. Simulation, assertions and formal verification
4. FPGA reference implementation
5. ASIC synthesis and technology mapping
6. SDC constraints and static timing analysis
7. Floorplanning, placement, CTS and routing
8. Physical verification and PPA review
9. GDSII/OASIS export and documented sign-off assessment

## First milestone — PWM engine
Implement and verify four-channel PWM with programmable period/duty, complementary outputs, configurable dead-time, synchronous configuration updates, asynchronous hardware fault override, and defined reset/fault-recovery behaviour.

See [PROJECT_CHECKLIST.md](PROJECT_CHECKLIST.md) for the M0–M8 engineering checklist.

## Change control
Use GitHub Issues for defects/design questions and pull requests for reviewed changes. Store architecture decision records under `docs/architecture/`. Do not close a milestone without linked implementation or verification evidence.
