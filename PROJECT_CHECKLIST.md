# ASIC Project Engineering Checklist

Complete each item only when acceptance evidence exists in the repository or a reviewed pull request.

## M0 — Project setup and governance
- [ ] Confirm repository access, branch protection and review policy
- [ ] Decide licence and add contribution guidance
- [ ] Record tool versions and reproducible installation instructions
- [ ] Establish issue labels and milestone tracking
- [ ] Add CI for lint and basic simulation
- [ ] Define naming, formatting and coding conventions

## M1 — Requirements and architecture
- [ ] Define use cases and operating modes
- [ ] Define four-channel PWM frequency, resolution and duty requirements
- [ ] Define dead-time range, granularity and tolerances
- [ ] Define fault inputs, polarity, synchronisation and priority
- [ ] Define safe outputs for reset, fault, clock loss and brownout
- [ ] Define power sequencing, SPI register map and ADC interface
- [ ] Define clock, reset, CDC and reset-domain architecture
- [ ] Create top-level block diagram and interface-control document
- [ ] Record architecture decisions and open risks

## M2 — RTL development
- [ ] Establish SystemVerilog project and lint rules
- [ ] Implement PWM counter, period and duty controls
- [ ] Implement complementary outputs and dead-time insertion
- [ ] Implement synchronous configuration updates
- [ ] Implement independent hardware fault override and safe-state logic
- [ ] Implement power-sequencer FSM and fault capture/recovery
- [ ] Implement SPI register interface and ADC interface
- [ ] Integrate top-level module
- [ ] Review synthesizability and unintended latch risks

## M3 — Verification
- [ ] Create unit testbench for each RTL block
- [ ] Test minimum/maximum period and duty values
- [ ] Verify dead-time and no complementary overlap
- [ ] Verify atomic configuration updates and asynchronous fault response
- [ ] Verify reset assertion/deassertion and fault recovery
- [ ] Test simultaneous faults, malformed SPI and ADC timeouts
- [ ] Add assertions for safety invariants
- [ ] Add formal checks for PWM interlock and safe-state properties
- [ ] Establish automated regression and coverage reporting
- [ ] Archive passing verification evidence

## M4 — FPGA reference implementation
- [ ] Select ECP5 device and board I/O mapping
- [ ] Define clocking/reset and map PWM/fault interfaces
- [ ] Build and program FPGA image
- [ ] Verify PWM frequency/duty and measure dead-time/channel alignment
- [ ] Inject faults and verify shutdown
- [ ] Document test setup, oscilloscope captures and FPGA-specific deviations

## M5 — ASIC synthesis
- [ ] Select and pin PDK/library version; confirm cell/memory availability
- [ ] Define SDC clock and I/O constraints
- [ ] Run synthesis and technology mapping
- [ ] Review inferred cells, latches, unsupported constructs and warnings
- [ ] Inspect mapped netlist and record cell area/counts
- [ ] Run initial STA and estimate power with documented activity assumptions

## M6 — Physical implementation
- [ ] Define die/core assumptions and utilisation target
- [ ] Define I/O/pin placement and power planning
- [ ] Complete floorplan and placement
- [ ] Perform clock-tree synthesis and signal routing
- [ ] Run post-route STA; review setup/hold violations
- [ ] Review congestion and supported routing/physical DRC
- [ ] Record area, timing and power results

## M7 — Optimisation and sign-off assessment
- [ ] Review critical paths, high-fanout nets and reset distribution
- [ ] Review CDC/RDC and switching-activity opportunities
- [ ] Check RTL-to-netlist equivalence where supported
- [ ] Resolve or document sign-off violations
- [ ] Freeze source, constraints, PDK and tool versions
- [ ] Generate reproducible GDSII/OASIS and sign-off assessment
- [ ] Document open-PDK/flow limitations

## M8 — Silicon and board validation planning
- [ ] Define package/pinout assumptions and evaluation-board architecture
- [ ] Define external gate-driver/power-stage interfaces
- [ ] Define independent hardware protection paths
- [ ] Define current-limited bring-up and acceptance tests
- [ ] Define environmental/thermal tests and first-silicon issue triage

## Exit criteria
Requirements trace to implementation and tests; relevant automated tests pass; limitations are recorded; evidence is committed; and the milestone is reviewed.

> **Engineering caution:** This is a learning/prototype programme. Open-source tool checks or GDSII generation do not establish foundry sign-off, production readiness, functional safety, high-voltage qualification or suitability for safety-critical deployment.
