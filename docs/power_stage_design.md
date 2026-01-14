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
> - Switching frequency selection logic 
> - DC-link behaviour and ripple considerations   
>  
> The following topics will be added progressively in later Phase 2 steps:
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

## 4. Switching Frequency Selection Reasoning

Switching frequency is treated as a **system-level trade-off variable** rather than an independently tunable parameter.

Its selection is inherently constrained by semiconductor technology, dv/dt-related system considerations, control objectives, and DC-link behaviour. As a result, switching frequency reasoning must be conducted at system level, rather than through isolated optimisation.

### 4.1 Coupling with Semiconductor Technology

The choice of semiconductor technology conditions the feasible switching frequency range through differences in switching behaviour, loss distribution, and gate-drive sensitivity.

Higher switching speeds enabled by wide-bandgap devices may relax certain performance constraints, while simultaneously tightening others related to dv/dt stress and system robustness.

### 4.2 Coupling with dv/dt and EMI Considerations

Switching frequency directly influences the repetition rate of voltage transitions and associated dv/dt-related effects.

As switching frequency increases, dv/dt-related stresses and EMI susceptibility may become more pronounced, reinforcing the need to consider frequency selection in conjunction with system-level dv/dt awareness rather than as an isolated parameter.

### 4.3 Coupling with Control Bandwidth and Modulation

Switching frequency selection affects the achievable control bandwidth, modulation resolution, and current regulation performance.

Conversely, control objectives and modulation strategies impose lower and upper bounds on practical switching frequency selection, linking control design considerations back to power-stage reasoning.

### 4.4 Interaction with DC-Link Behaviour (Awareness Level)

Switching frequency influences the spectral characteristics of inverter current draw and associated DC-link ripple behaviour.

At Phase 2, this interaction is acknowledged at awareness level, without entering quantitative ripple analysis or component sizing, which are addressed in later design phases.

### 4.5 Engineering Trade-Off Perspective

From an engineering standpoint, switching frequency selection represents a balance between competing objectives, including efficiency, controllability, electromagnetic compatibility, and system robustness.

Rather than converging on a single preferred value, Phase 2 reasoning establishes the **constraint relationships and trade-off dimensions** that govern feasible frequency selection under different system assumptions.

---

## 5. DC-Link Behaviour and System Role

Within the inverter power stage, the DC-link serves not merely as a passive energy reservoir, but as a **system-level buffering and decoupling element** between the high-voltage DC source and the switching inverter.

At Phase 2, DC-link considerations are treated at a **behavioural and architectural level**, focusing on its role in shaping power-stage dynamics rather than on component-level design.

### 5.1 DC-Link as an Energy Buffering Element

From a system perspective, the DC-link performs several foundational roles:

- Providing short-term energy buffering between the HV DC source and the inverter  
- Decoupling source-side dynamics from inverter switching activity  
- Supporting transient power imbalance during load changes and modulation events  

These roles are intrinsic to the power-stage architecture and exist independently of specific capacitor technologies or sizing choices.

### 5.2 Sources of DC-Link Voltage and Current Variation

At system level, DC-link voltage and current behaviour is influenced by multiple interacting factors, including:

- Inverter switching activity and modulation patterns  
- Load dynamics and operating conditions of the PMSM  
- Assumptions regarding source stiffness and upstream impedance  

The resulting DC-link behaviour reflects **aggregate system interactions**, rather than the characteristics of any single subsystem.

### 5.3 Qualitative Relationships to Other Power-Stage Elements

From a reasoning standpoint, DC-link behaviour exhibits qualitative relationships with:

- Inverter switching frequency and switching strategy  
- Load-dependent power pulsation and torque dynamics  
- System-level operating assumptions, such as allowable voltage fluctuation and transient tolerance  

These relationships condition feasible design assumptions without, at this stage, imposing numerical constraints or design commitments.

### 5.4 Engineering Implications at Phase 2

At Phase 2, DC-link behaviour reasoning serves to:

- Clarify how energy buffering assumptions affect power-stage robustness  
- Identify dependencies between inverter operation and DC-link stress at conceptual level  
- Establish awareness boundaries for later quantitative analysis  

Detailed ripple calculation, capacitor sizing, impedance modelling, and lifetime assessment are intentionally deferred to subsequent design phases.

---

## 6. Relationship to Subsequent Design Decisions

The considerations described above directly inform, but do not determine:

- Switching frequency selection logic  
- DC-link behaviour and ripple characteristics  
- Protection philosophy and fault response strategy  

These topics are addressed in subsequent sections and documents, where detailed **design reasoning** is developed based on the awareness established here.

---

## 7. Boundary to Later Phases

The following activities are **explicitly outside the scope** of this document:

- Semiconductor part-number selection  
- Datasheet comparison or quantitative loss calculation  
- dv/dt numerical estimation or simulation  
- PCB layout, EMI filter design, or thermal modelling  

Such activities are deferred to Phase 3 and beyond, where sufficient modelling and validation context is available.

---

## 8. Summary

This document establishes a **clear system-level reasoning framework** for semiconductor technology and dv/dt awareness within the power-stage baseline.

By articulating how these factors influence engineering trade-offs—without committing to numerical or implementation detail—it supports disciplined and traceable design evolution in later phases.
