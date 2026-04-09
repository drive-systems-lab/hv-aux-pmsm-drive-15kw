# Control–Plant Context

## Purpose

This document establishes the control–plant interpretation baseline for Phase 4 of the project **15 kW High-Voltage Auxiliary PMSM Drive (800 V Platform)**.

Its purpose is to define how the closed-loop current-control path introduced in Phase 4 relates to the executable plant foundation established in Phase 3.

This document does **not** introduce controller implementation, optimisation activity, or integration finalisation.  
Its role is to provide a stable interpretive reference by defining the control–plant relationship, principal signal interfaces, and coordinate-system context required for the Phase-4 control-path and integration artefacts to remain structurally consistent with the frozen modelling basis inherited from Phase 3.

---

## Closed-Loop Structural View

The control-oriented structural view adopted for Phase 4 is:

`current reference → FOC controller → modulation interface → inverter stage → PMSM electrical plant → current feedback`

This expression defines the intended closed-loop interpretation boundary for Phase 4.

It should be understood as a **structural and modelling reference** rather than as a statement that the executable closed-loop control baseline is fully established.

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

This relationship is introduced here as a modelling baseline for Phase-4 interpretation and executable control-path assembly.  
It does not define the full executable closed-loop control baseline.

---

## Control–Plant Signal Interfaces

To support a consistent Phase-4 interpretation, the principal control–plant signal interfaces are defined as follows.

### Reference-side signals

- `i_d_ref`  
  dq-axis direct-current reference used to express the control-side electrical target along the d axis.

- `i_q_ref`  
  dq-axis quadrature-current reference used to express the control-side electrical target along the q axis.

These quantities define the intended current-reference input to the current-control path adopted in Phase 4.

### Control-side internal signals

- `v_d_ref`  
  dq-axis direct-voltage reference produced by the current-control layer as the control-side voltage command along the d axis.

- `v_q_ref`  
  dq-axis quadrature-voltage reference produced by the current-control layer as the control-side voltage command along the q axis.

These quantities represent the principal control-side voltage commands passed toward the modulation-side path.  
They are documented as interpretation-level interface quantities within the Phase-4 modelling baseline.

### Feedback-side signals

- `i_d_fb`  
  dq-axis direct-current feedback quantity used to represent the plant-side current state returned to the control path.

- `i_q_fb`  
  dq-axis quadrature-current feedback quantity used to represent the plant-side current state returned to the control path.

Within the Phase-4 interpretation, these feedback quantities close the current-control loop at the electrical level only.

Taken together, the principal signal relationship can be interpreted as:

`(i_d_ref, i_q_ref) → current-control decision layer → (v_d_ref, v_q_ref) → modulation-side path → inverter stage → PMSM electrical plant → (i_d_fb, i_q_fb)`

This expression defines the signal-interface interpretation adopted for Phase 4.  
It should be understood as a modelling baseline only, not as a definition of the full integrated closed-loop control baseline.

---

## Naming Note

A deliberate naming distinction is used in the present document to separate physical-interface quantities from control-domain or otherwise processed signals.

For quantities that remain close to the physical interface, naming is kept relatively compact, even when suffixes are present (e.g. `iabc_fb`, `udc_fb`, `va_out`, `vb_out`, `vc_out`). For quantities expressed more explicitly within control, reconstruction, or coordinate-transformed contexts, a more explicitly separated style is adopted (e.g. `i_abc_fb`, `u_dc_fb`, `i_d_fb`, `i_q_fb`, `v_d_ref`, `v_q_ref`).

This convention is used to preserve signal-role readability and cross-artefact interpretability across the Phase-4 control–plant context.

---

## Coordinate-System Relationship

The control-oriented signal path in Phase 4 is interpreted across both three-phase and dq-coordinate representations.

### abc → dq feedback interpretation path

The inverter-stage and plant-side electrical behaviour ultimately exists in three-phase form at the interface between the switching inverter stage and the motor-side electrical system.

Within the Phase-4 control interpretation, this three-phase electrical behaviour is understood to be mapped into the dq frame in order to express the feedback quantities required by the current-control path.

Accordingly:

- the switching-stage current observation exists at the three-phase interface level
- the feedback path is interpreted through an `abc → dq` transformation context
- `i_d_fb` and `i_q_fb` represent the control-facing dq expression of the plant-side electrical current state

This transformation path is documented here as a coordinate-system interpretation boundary for the feedback side.

### dq → abc modulation-side path

The current-control path in Phase 4 is expressed primarily in dq coordinates.

Within this interpretation:

- `v_d_ref` and `v_q_ref` represent dq-axis voltage-reference quantities generated by the control side
- these dq-axis voltage-reference quantities are understood to pass through a `dq → abc` modulation-side path
- the modulation interface then provides the switching-facing signal route toward the inverter stage inherited from the frozen Phase-3 switching baseline

This path defines how control-side dq quantities are related to the inverter-stage switching interface at the modelling level adopted for Phase 4.

### Interpretation boundary

The coordinate-system relationship documented here serves an interpretive purpose only.

Its role is to clarify how control-facing dq-domain quantities relate to the three-phase inverter-stage and plant-side electrical representation inherited from Phase 3, without introducing implementation or validation claims.

---

## Cross-Phase Governance

The governance relationship between Phase 3 and Phase 4 is defined as follows:

- the **Phase-3 switching baseline remains frozen**
- the **Phase-3 discrete PMSM baseline remains frozen**
- **Phase 4 builds upon these artefacts without replacing, refreezing, or redefining them**
- the closed-loop integration artefacts must remain structurally consistent with the modelling basis established in earlier phases

Accordingly, this document serves as a cross-phase interpretation reference rather than a baseline replacement document.