# Power-Stage Design

This document records the **system-level design reasoning and trade-off considerations** for the inverter power stage of the 15 kW High-Voltage Auxiliary PMSM Drive.

All reasoning in this document is based on the **baseline reference configuration** defined in  
`power_stage_baseline.md`.

Numerical design, component selection, detailed modelling, and implementation-level decisions are explicitly deferred to later phases.

---

> **Status Snapshot (Phase 2 — In Progress)**  
>  
> This document is a **living reasoning record** for Phase 2.  
>  
> The following topics are currently covered:
> - Semiconductor technology considerations  
> - dv/dt awareness and system-level implications  
>  
> The following topics will be added progressively in later Phase 2 steps:
> - Switching frequency selection logic  
> - DC-link behaviour and ripple considerations  
> - Protection philosophy and fault response strategy


## 1. Role of This Document in Phase 2

Within the overall project structure:

- The **power-stage baseline**, defined in a separate document, specifies *what* configuration is assumed.
- This document explains *how* engineering judgement is applied **based on that baseline**.

The purpose of this document is to articulate **engineering awareness, trade-off dimensions, and constraint relationships**, rather than to converge on a final hardware solution.

---

## 2. Semiconductor Technology Considerations

At system level, the inverter power stage may be realised using different semiconductor technologies.  
Two representative classes are considered for reasoning purposes:

- Silicon (Si) IGBT–based solutions  
- Silicon Carbide (SiC) MOSFET–based solutions  

This discussion is intentionally **technology-oriented**, not **device-specific**.

### 2.1 System-Level Behavioural Differences

From a system perspective, different semiconductor technologies exhibit characteristic behavioural tendencies, including:

- Switching speed and transient behaviour  
- Loss distribution between conduction and switching mechanisms  
- Gate-drive interaction and control sensitivity  
- Thermal stress distribution under dynamic operation  

These tendencies influence system-level constraints without directly determining a specific implementation.

### 2.2 Impact on Engineering Trade-Off Space

The choice of semiconductor technology does not represent a binary optimisation, but rather shifts the **engineering trade-off space**, affecting:

- Acceptable switching frequency range  
- dv/dt stress levels experienced by connected subsystems (e.g. motor, cabling, sensing interfaces)  
- Sensitivity to parasitic effects and layout quality  
- Requirements placed on insulation, filtering, and protection concepts  

As a result, semiconductor technology should be treated as a **structural variable** that conditions subsequent design reasoning, rather than as an isolated component decision.

---

## 3. dv/dt Awareness and System-Level Implications

Independent of the specific device selected, inverter operation inherently introduces voltage transients characterised by finite dv/dt.

At Phase 2, dv/dt is treated as a **system-level awareness topic**, not a numerical design parameter.

### 3.1 Affected System Domains

Elevated dv/dt levels may influence multiple parts of the system, including:

- Electrical insulation stress within the motor and cabling  
- Common-mode voltage and current behaviour  
- Electromagnetic interference (EMI) susceptibility  
- Robustness of sensing and control interfaces  

These effects are coupled to overall system architecture rather than to any single component.

### 3.2 Engineering Implications

From a reasoning standpoint, dv/dt considerations:

- Constrain feasible combinations of semiconductor technology and switching strategy  
- Influence acceptable assumptions regarding insulation coordination and EMC environment  
- Motivate clear separation between **conceptual design reasoning** and **implementation-level mitigation**

This document intentionally does **not** enter PCB layout practices, EMI filtering techniques, or dv/dt numerical limits, as such topics belong to later design phases.

---

## 4. Relationship to Subsequent Design Decisions

The considerations described above directly inform, but do not determine:

- Switching frequency selection logic  
- DC-link behaviour and ripple characteristics  
- Protection philosophy and fault response strategy  

These topics are addressed in subsequent sections and documents, where detailed **design reasoning** is developed based on the awareness established here.

---

## 5. Boundary to Later Phases

The following activities are **explicitly outside the scope** of this document:

- Semiconductor part-number selection  
- Datasheet comparison or quantitative loss calculation  
- dv/dt numerical estimation or simulation  
- PCB layout, EMI filter design, or thermal modelling  

Such activities are deferred to Phase 3 and beyond, where sufficient modelling and validation context is available.

---

## 6. Summary

This document establishes a **clear system-level reasoning framework** for semiconductor technology and dv/dt awareness within the power-stage baseline.

By articulating how these factors influence engineering trade-offs—without committing to numerical or implementation detail—it supports disciplined and traceable design evolution in later phases.
