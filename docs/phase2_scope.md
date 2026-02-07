# Phase 2 Scope and Boundary Definition

This document defines the scope and boundary of **Phase 2 — Power Stage Design** for the 15 kW High-Voltage Auxiliary PMSM Drive (800 V platform).

The purpose of this document is to explicitly clarify **what is addressed** and **what is intentionally deferred** in Phase 2, in order to prevent scope creep into implementation-level work that belongs to later phases.

---

## 1. Scope of Phase 2

Phase 2 focuses on **system-level power stage design judgement and rationale**, rather than detailed implementation.

The scope of Phase 2 includes:

- Definition and justification of the **overall inverter power stage topology** consistent with the Phase 1 system architecture baseline.
- **Semiconductor technology selection at category level**, such as SiC MOSFET, IGBT, or hybrid approaches, including high-level trade-off considerations.
- Discussion of **switching frequency range**, dv/dt implications, and associated system-level risks (e.g. insulation stress, EMI awareness), without numerical optimisation.
- **DC-link capacitor design methodology**, including qualitative ripple current awareness and system-level design reasoning, without component sizing or quantitative evaluation.
- Definition of **power-stage-related protection concepts**, including fault categories and high-level protection philosophy.
- Definition of the **operational state machine structure** *(conceptual structure only; not executable logic)* relevant to power stage enable, fault handling, and safe-state transitions.

Phase 2 answers the question:
> *What power stage design choices are appropriate, and why are they reasonable at system level?*

---

## 2. Explicitly Out-of-Scope Items

To maintain a clear phase boundary, the following items are **explicitly excluded** from Phase 2:

- Detailed **PCB schematic or layout design**.
- **Thermal simulation**, heatsink design, or cooling system implementation.
- **EMC / EMI simulation or compliance analysis**.
- Final **component part number selection** or supplier-specific optimisation.
- Detailed **loss calculation**, efficiency mapping, or thermal derating curves.
- Control algorithm implementation, tuning, or real-time software design.
- Hardware prototype construction or experimental validation.

These items are intentionally deferred to later phases to ensure Phase 2 remains focused on
engineering judgement rather than implementation completeness.

---

## 3. Boundary Between Phase 2 and Phase 3

The boundary between Phase 2 and Phase 3 is defined as follows:

- **Phase 2** addresses **What and Why**:
  - Architectural choices
  - Design rationale
  - Trade-offs and constraints
  - System-level risks and assumptions

- **Phase 3** addresses **How and How Much**:
  - Numerical design calculations
  - Detailed electrical modelling
  - Component-level sizing
  - Simulation-based verification

As a guiding principle:

> If a topic requires numerical optimisation, detailed modelling, or executable simulation,
> it belongs to Phase 3 rather than Phase 2.

This boundary ensures that Phase 2 establishes a robust and defensible design foundation,
upon which detailed implementation can proceed in a controlled and traceable manner.
