# Phase 3 Artefact Alignment – Switching-Level Inverter and Discrete-Time PMSM Models

## Purpose & Context

During Phase 3, two executable artefacts are intentionally maintained at different abstraction levels:

- A switching-level inverter model  
- A discrete-time PMSM dq electrical state-update model  

These artefacts operate at distinct abstraction layers and serve complementary structural roles within the overall system framework.

This document clarifies the abstraction-layer relationship between the switching-level inverter model and the discrete-time PMSM dq electrical state-update model.

The objective is to document architectural alignment across modelling layers without asserting waveform equivalence, plant unification, or performance validation.

---

## Abstraction-Layer Alignment

| Aspect | Switching Model | Discrete Model |
|--------|-----------------|----------------|
| Modelling Role | Inverter switching behaviour representation | PMSM electrical state evolution abstraction |
| Resolution Level | Switching resolution | Averaged discrete-time state update |
| High-Frequency Effects | Explicitly represented | Intentionally not represented |
| Electrical Representation | Phase-domain waveform representation | dq-domain state representation |


### Switching-Level Inverter Model

The switching-level inverter model:

- Represents a three-phase two-level inverter topology  
- Operates at switching resolution with explicit phase-domain waveform behaviour
- Includes an R–L load as a structural motor-interface placeholder  
- Makes switching-frequency effects directly observable  

The R–L load serves as a structural execution interface only.  
It does not represent PMSM dq electrical dynamics.


### Discrete-Time PMSM Electrical Model

The discrete-time PMSM electrical model:

- Represents dq electrical state evolution under a dq reference frame 
- Implements discrete-time state updates for i_d and i_q  
- Includes cross-axis coupling and back-EMF terms  
- Intentionally excludes switching-frequency ripple and phase-domain waveform effects  

This model captures averaged electrical state propagation.

---

## Boundary Declaration

The two artefacts do not represent alternative abstractions of the same physical system.

- The switching-level inverter model captures inverter switching behaviour with an R–L placeholder load.  
- The discrete-time PMSM model captures dq electrical state evolution at an averaged abstraction level.

They are structurally independent and are not physically interconnected in Phase 3.

This alignment note does not imply waveform equivalence, plant unification, or integrated system representation.
