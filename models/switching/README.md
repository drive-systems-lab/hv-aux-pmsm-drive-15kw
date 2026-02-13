# Switching-Level Inverter Model

This directory contains the switching-level inverter simulation model established in Phase 3.

The model represents the inverter stage at switching resolution, including power-path topology and interface definitions.  
Behavioural capability is progressively introduced in subsequent iterations.

---

## Day 1 — Structural Skeleton

### Scope

At this stage, the objective is architectural completeness only.

- Three-phase inverter switching topology
- Simplified DC-link representation
- Motor/load interface presence
- Gate/control input ports (not actively driven)
- Measurement interface availability

The model defines structural and interface existence, not behavioural correctness.

### Out of Scope

The following are intentionally excluded at this stage:

- SVPWM implementation
- Field-oriented control (FOC)
- Closed-loop operation
- Dynamic scenario testing
- Switching waveform analysis
- Dead-time modelling
- Non-ideal semiconductor effects
- Parameter tuning / calibration
- Performance optimisation

Model execution is not required in this freeze stage.

---

## Day 2 — Switching Behaviour

### Scope

At this stage, switching activity is enabled through a basic carrier-based SPWM implementation.

The focus remains on execution stability and behavioural visibility.

- Carrier-based SPWM
- Complementary bottom-switch logic
- Relay hysteresis for numerical stability (not dead-time)
- Stable executable switching model
- Basic waveform visibility

### Out of Scope

- Dead-time modelling
- Modulation enhancement
- Performance optimisation
- Closed-loop control
- Dynamic scenario testing
- Non-ideal semiconductor modelling

---

## Model File Governance

- `inverter_switching_model.slx`  
  Mainline switching-level model.

- `inverter_switching_variant_*.slx`  
  Variant models created for specific non-ideal or exploratory studies.  
  These do not replace the mainline model.
