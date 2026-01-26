# Power Stage Trade-Off Matrix

This document provides a **system-level trade-off matrix** that consolidates the key engineering judgement dimensions established during **Phase 2 — Power Stage Design**.

The matrix does **not introduce new design decisions**.  
Instead, it serves as a **structural index** that maps existing reasoning across documents into a single, scan-friendly reference.

All entries reflect **qualitative trade-off awareness**, not numerical optimisation or implementation commitments.

---

## Purpose and Positioning

The purpose of this matrix is to:

- Summarise the **primary trade-off dimensions** governing system-level power-stage judgement
- Make explicit **how different system concerns interact and constrain each other**
- Provide a **consolidation artefact** that supports transition into subsequent phases

This matrix is intended as a **navigation and interpretation aid**, not as a design output.

---

## Trade-Off Dimensions Overview

The matrix below maps the major system-level judgement dimensions and highlights their interactions.

| Judgement Dimension | Primary Concern | Interacting Dimensions | System-Level Interpretation |
|--------------------|-----------------|------------------------|------------------------|
| Voltage level & insulation stress | System safety and long-term reliability | Semiconductor technology, dv/dt behaviour | Constrains feasible switching behaviour and technology classes |
| Semiconductor technology (category) | Switching behaviour and robustness | Switching frequency, dv/dt, thermal stress | Conditions the overall trade-off space rather than determining a solution |
| Switching frequency (range) | Performance vs system stress | Semiconductor technology, dv/dt, DC-link behaviour | Treated as a qualitative trade-off variable, not an optimised parameter |
| dv/dt awareness | Insulation, EMI, and system robustness | Switching frequency, device technology | Considered at awareness level without numerical limits |
| DC-link energy buffering | System stability and decoupling | Switching behaviour, load dynamics | Reasoned at behavioural and architectural level |
| Control assumptions (implicit) | Validity of power-stage reasoning | DC-link behaviour, switching frequency | Assumed, not designed; defines power-stage abstraction validity |
| Protection philosophy | System safety under abnormal conditions | System states, power-path structure | Conceptual and system-structural, not implementation-level |
| System operating states | Interpretation context for behaviour | Protection perspective, nominal reasoning | Treated as system-level reasoning constructs, not control logic |

**Note:**   
This matrix functions as a *system-level reasoning map*, not as a decision table or design specification.  
No ordering or weighting is implied by the row sequence.

---

## Relationship to Existing Documents

The trade-off dimensions summarised above are developed and discussed across the following documents:

- `phase2_scope.md` — scope definition and phase boundary
- `power_stage_baseline.md` — structural reference configuration
- `power_stage_design_judgement.md` — decision logic and priority hierarchy
- `power_stage_design.md` — system-level design reasoning
- `protection_and_state_machine.md` — protection and state reasoning perspective
- `images/inverter_schematic.png` — conceptual system structure consolidation

This matrix does not replace or extend those documents.  
It provides a **cross-cutting index** that clarifies how their reasoning dimensions align.

---

## Phase Boundary Statement

This matrix deliberately excludes:

- Numerical comparisons or optimisation results
- Component-level sizing or selection
- Executable control or protection logic
- Simulation, validation, or performance metrics

Any topic requiring quantitative evaluation or implementation detail belongs to **Phase 3 or later**.

---

## Summary

This trade-off matrix consolidates the **system-level judgement landscape** established in Phase 2 into a single, coherent reference.

It supports disciplined transition to subsequent design phases by making assumptions, constraints, and interactions explicit—without constraining future implementation choices.
