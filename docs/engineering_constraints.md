# Engineering Constraints

## Purpose

This document records the principal engineering constraints and working assumptions used to interpret the Phase-4 current-control path within the project **15 kW High-Voltage Auxiliary PMSM Drive (800 V Platform)**.

Its purpose is to define the **engineering boundary** within which the Phase-4 closed-loop structure should be understood, so that later control-path artefacts and behavioural observations remain consistent with the frozen modelling foundation inherited from Phase 3.

These constraints are presented as **engineering framing assumptions** for Phase-4 interpretation, not as controller-tuning targets, implementation specifications, or validation conclusions.

---

## Current-Control Bandwidth Considerations

Phase 4 adopts a qualitative current-control interpretation rather than a performance-driven control-design exercise.

Accordingly, the current loop is understood to operate within a bandwidth region that is:

- sufficiently below the switching action to preserve a meaningful separation between control action and switching behaviour
- sufficiently above slow operating variation to allow representative current-tracking behaviour to be observed
- consistent with the adopted sampling and control-update timing assumptions
- consistent with the use of a simplified and interpretable dq current-control structure

At this stage, the bandwidth is treated as an engineering constraint rather than a numerically optimised design target.

No final bandwidth value, tuning method, or robustness margin is defined here.

Its role is simply to preserve an interpretable current-loop context for Phase-4 behavioural observation.

---

## Switching-Frequency Assumption

The Phase-4 control interpretation assumes that inverter switching behaviour remains governed by the switching-side baseline inherited from Phase 3.

Within this project context, the switching frequency is treated as a fixed modelling assumption that provides the timing basis for:

- modulation-side behaviour
- inverter-stage switching behaviour
- interaction between switching activity and current-loop behaviour

It also preserves continuity between the Phase-3 switching artefact and the Phase-4 closed-loop interpretation.

For Phase 4, the switching frequency is not treated as an optimisation variable.

Its role is to provide a stable switching-side context within which the current-control path can be exercised against the frozen inverter-stage modelling basis.

---

## DC-Bus Stability Assumptions

The Phase-4 current-control interpretation is established under a bounded DC-bus condition.

For the purposes of this phase, the DC bus is assumed to remain sufficiently stable for the following modelling interpretation to hold:

- DC-bus variation does not dominate the observed current-loop behaviour
- the modulation-side voltage command remains meaningful as a control-facing quantity
- inverter-stage behaviour can be interpreted without introducing a broader DC-source dynamics study
- observed current-loop behaviour can be read primarily in relation to the control path and plant-side electrical response

This assumption does not imply that DC-bus variation is absent.  
It defines the engineering boundary within which Phase-4 behavioural interpretation remains focused on the electrical current-control structure.

Accordingly, upstream source dynamics, severe bus-instability scenarios, and bus-design optimisation are outside the present scope.

---

## Sampling Considerations

The Phase-4 current-control interpretation also depends upon a consistent sampling-side assumption.

At this stage, sampling is understood as part of the control-facing timing structure required to maintain consistency across:

- dq-axis current feedback
- current-control decision updates
- modulation-side command transfer
- inverter-stage switching response

This document does not define implementation-level sampling architecture or embedded real-time execution detail.  
Its purpose is to record that Phase-4 current-loop behaviour is interpreted under a timing assumption that is internally consistent and engineering-plausible.

---

## Interpretation Boundary

The engineering constraints documented here define the intended interpretation boundary for Phase 4.

Within that boundary:

- the current loop is examined as a control-facing electrical loop
- the switching inverter remains the behavioural power-conversion basis inherited from Phase 3
- the PMSM electrical model remains the plant-side electrical response basis inherited from Phase 3
- behavioural observations are interpreted qualitatively within a constrained engineering context

These constraints support technical credibility and cross-phase consistency, while keeping clear separation from later implementation or validation work.

---

## Relation to Existing Phase-4 Artefacts

This document should be read together with:

- `docs/control_plant_context.md`

Within the current Phase-4 structure:

- `control_plant_context.md` defines the structural control–plant relationship
- `engineering_constraints.md` defines the principal engineering assumptions under which that relationship is interpreted

Together, these artefacts provide the control-facing interpretation baseline for later Phase-4 control-path work and behavioural exploration.