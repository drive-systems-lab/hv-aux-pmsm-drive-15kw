# Control–Plant Context

## Purpose

This document establishes the control–plant interpretation baseline for Phase 4 of the project **15 kW High-Voltage Auxiliary PMSM Drive (800 V Platform)**.

Its purpose is to define how the closed-loop current-control path introduced in Phase 4 relates to the executable plant foundation established in Phase 3.

This document does **not** introduce controller implementation, optimisation activity, or integration finalisation.  
Its role is to provide a stable interpretive reference for subsequent Phase-4 work, so that later control-path and integration artefacts remain structurally consistent with the frozen modelling basis inherited from Phase 3.

---

## Closed-Loop Structural View

The control-oriented structural view adopted for Phase 4 is:

`current reference → FOC controller → modulation interface → inverter stage → PMSM electrical plant → current feedback`

This expression defines the intended closed-loop interpretation boundary for Phase 4.

At this stage, it should be understood as a **structural and modelling reference**, rather than as a statement that the full closed-loop assembly has already been formally established as an executable baseline.

---

## Plant Foundation Inherited from Phase 3

Phase 4 builds directly upon the frozen modelling artefacts established in Phase 3.

The plant-side foundation consists of two distinct modelling layers:

- the **switching-level inverter model**, which provides the inverter-stage behavioural basis
- the **discrete-time PMSM model**, which provides the electrical plant basis

Together, these artefacts define the executable plant foundation upon which the Phase-4 control interpretation is built.

Phase 4 does not replace these artefacts, redefine their modelling role, or weaken their frozen baseline status.

---

## Control–Plant Relationship in Phase 4

Within the Phase-4 interpretation, the control path and plant foundation are related as follows:

- the **current reference** defines the electrical control target
- the **FOC controller** represents the current-control decision layer
- the **modulation interface** represents the control-side signal transfer toward the inverter stage
- the **inverter stage** represents the switching-side power-conversion layer inherited from the Phase-3 switching baseline
- the **PMSM electrical plant** represents the electrical response layer inherited from the Phase-3 discrete PMSM baseline
- the **current feedback** closes the electrical current-control loop at the interpretation level adopted for Phase 4

This relationship is introduced here as a modelling baseline only.  
Its purpose is to clarify how later Phase-4 execution work should be interpreted, not to claim that all closed-loop artefacts have already been completed in final form.

---

## Cross-Phase Governance

The governance relationship between Phase 3 and Phase 4 is defined as follows:

- the **Phase-3 switching baseline remains frozen**
- the **Phase-3 discrete PMSM baseline remains frozen**
- **Phase 4 builds upon these artefacts without replacing, refreezing, or redefining them**
- later closed-loop integration work must remain structurally consistent with the modelling basis established in earlier phases

Accordingly, this document serves as a cross-phase interpretation reference rather than a baseline replacement document.