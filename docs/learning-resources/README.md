# Learning resources

This folder is the curated study library for the FPGA-to-ASIC digital power-controller programme. Prefer official documentation, university course material and publisher pages. Use the sequence below rather than trying to read everything at once.

## Study sequence

| Stage | Study focus | Start here | Apply it to |
|---|---|---|---|
| 1 | RTL and digital design | SystemVerilog LRM/tool docs; Verilator | PWM counter, register interface |
| 2 | CMOS and VLSI foundations | Weste & Harris; Rabaey et al. | standard cells, timing, area and power |
| 3 | Digital power control | TI C2000 workshop; TI Power Supply Design Seminar library; Choi | PWM, sampling, control-loop and converter dynamics |
| 4 | Verification | cocotb, SymbiYosys, Verilator | PWM safety properties and fault injection |
| 5 | ASIC implementation | SKY130 docs; OpenROAD Flow; OpenLane 2 | synthesis through routed layout |
| 6 | Timing and physical design | OpenSTA/OpenROAD docs; university ASIC course notes | constraints, setup/hold, CTS, routing |

## Books

### Core digital IC / CMOS
1. **CMOS VLSI Design: A Circuits and Systems Perspective** — Neil H. E. Weste and David Money Harris. Core reference for CMOS logic, standard cells, timing, physical implementation and low-power design. Publisher/course references: [Pearson title search](https://www.pearson.com/) and [Columbia VLSI course textbook list](https://bioee.columbia.edu/courses/ee4321/textbooks.html).
2. **Digital Integrated Circuits: A Design Perspective (2nd ed.)** — Jan M. Rabaey, Anantha Chandrakasan and Borivoje Nikolić. Strong foundation in device/circuit effects, interconnect, timing, clocking and power. [Author's book page](https://www.janrabaey.com/digital-ics).
3. **Digital VLSI Chip Design with Cadence and Synopsys CAD Tools** — Neil H. E. Weste and David Money Harris. A practical end-to-end chip-design companion; its commercial-tool workflow is conceptually useful, but our implementation will use open tools. [Pearson book page](https://www.pearson.com/en-us/subject-catalog/p/digital-vlsi-chip-design-with-cadence-and-synopsys-cad-tools/P200000003316).

### Power conversion and control
4. **Pulsewidth Modulated DC-to-DC Power Conversion: Circuits, Dynamics, and Control Designs** — Byungcho Choi. Directly relevant to converter operation, dynamic models, voltage/current-mode control, compensation and sampling effects. [Wiley book page](https://onlinelibrary.wiley.com/doi/book/10.1002/9781118772188).

### Reading priority
Start with Weste & Harris for digital CMOS concepts, then Rabaey for deeper circuit/timing/power understanding. Use Choi as the power-stage/control reference when defining the controller's requirements. These are substantial textbooks; read the chapters relevant to each milestone, not cover-to-cover before writing RTL.

## Official tool and process documentation

- [SKY130 documentation](https://skywater-pdk.readthedocs.io/en/main/) — process/design information; read the limitations and maturity notes.
- [OpenLane 2 documentation](https://openlane2.readthedocs.io/en/stable/) — RTL-to-GDS flow configuration and steps.
- [OpenROAD Flow Scripts user guide](https://openroad-flow-scripts.readthedocs.io/en/latest/user/FlowTutorial.html) — practical flow tutorial and directory/results layout.
- [OpenROAD project](https://openroad.org/) — physical-design tool project and documentation entry point.
- [Yosys documentation](https://yosyshq.readthedocs.io/projects/yosys/en/latest/) — synthesis, RTLIL and technology mapping.
- [Verilator documentation](https://verilator.org/guide/latest/) — lint, simulation and coverage.
- [cocotb documentation](https://docs.cocotb.org/en/stable/) — Python-based HDL verification.
- [SymbiYosys documentation](https://symbiyosys.readthedocs.io/en/latest/) — formal verification front-end.
- [KLayout documentation](https://www.klayout.de/doc.html) — layout viewing and scripting.
- [OpenSTA project](https://github.com/The-OpenROAD-Project/OpenSTA) — static timing analysis engine.

## Digital power resources and white papers

- [TI C28x Digital Power Supply Workshop (PDF)](https://www.ti.com/en/download/mcu/C28x_DPS_Workshop.pdf) — structured workshop covering digital power fundamentals, PWM, ADC feedback, closed-loop control, high-resolution PWM and loop tuning. Although written around C2000 peripherals, the control concepts transfer to our RTL architecture.
- [TI Power Supply Design Seminar library](https://www.ti.com/en-us/about-ti/events/power-supply-design-seminar/psds-library) — seminar papers and presentations. Prioritise “Applying digital technology to PWM control-loop designs” (2008), “Designing a digital power supply” (2006), “Using PMBus for improved system-level power management” (2008), and the compensation/control-loop material.
- [TI C2000 Digital Power resources](https://www.ti.com/microcontrollers-mcus-processors/microcontrollers/c2000-real-time-control-mcus/overview.html) — useful reference for PWM/ADC/control peripheral behaviour; treat it as system-design reference, not an ASIC implementation template.

## University course material

- [Cornell ECE 6745 — Complex Digital ASIC Design readings](https://www.csl.cornell.edu/courses/ece6745/readings.html) — organised readings covering CMOS devices, standard cells, front-end ASIC flow and back-end flow.
- [Columbia EE4321 — VLSI Circuits textbook list](https://bioee.columbia.edu/courses/ee4321/textbooks.html) — useful reference list for core CMOS/VLSI texts.

## How to use this library

1. Add a short note in the relevant study log when a resource is used.
2. Record the chapter/section/page or specific document section.
3. Link each study item to a practical repository task or verification result.
4. Prefer official source links; do not commit copyrighted books or paywalled papers.
5. When a URL changes, update the link and record the date checked.

## Resource curation status

Initial curated list created 2026-11-22. Links should be rechecked when each study phase begins. This is a learning bibliography, not an endorsement of any specific foundry, process node or commercial tool.
