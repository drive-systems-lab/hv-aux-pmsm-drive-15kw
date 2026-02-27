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

## Day 3 — Switching Dynamic Scenarios

### Scope

At this stage, minimal excitation scenarios are introduced to validate switching-level behavioural consistency, without modifying the power-stage structure.

The objective is behavioural coverage, not performance evaluation.

### Implemented Scenario Set

- **Scenario A — PWM Enable Step**  
  Validates gating activation/deactivation behaviour and DC-link interaction consistency.

- **Scenario B — Modulation Index Step**  
  Verifies switching response sensitivity to modulation index step changes.

- **Scenario C — Load Command (Reserved Placeholder)**  
  Structural excitation path prepared for future load disturbance studies.  
  The current R-L load remains fixed in this stage.

### Design Discipline

The following constraints are intentionally maintained:

- No power-path restructuring
- No dead-time modelling
- No control-loop integration
- No plant parameter switching
- No performance optimisation

Scenarios serve excitation coverage at switching resolution only.

---

## Day 5 — Baseline Consolidation & Freeze

Following behavioural validation under Scenario A, the switching-level baseline is consolidated and frozen under the following reproducible configuration:

- Discrete fixed-step solver (Ts = 1e-6 s)
- Discrete powergui (SPS environment)
- Carrier-based SPWM modulation strategy
- Relay-based gating decision (numerical hysteresis only, not dead-time)
- Parameters centralised in Model Workspace
- No modification to inverter power-path topology

This configuration defines the numerical and structural reference point for subsequent Phase 3 development.

Further behavioural exploration will extend from this frozen baseline without altering its architectural definition.

---

## Quick Run Guidance

The baseline configuration defaults to Scenario ID `3` (reserved placeholder).

To observe switching behaviour, select:

- `1` — PWM enable step  
- `2` — Modulation index step  

No optimisation, unified plant modelling, or quantitative performance validation is implied.

Tested with MATLAB R2023b (Simulink).

---

## Model File Governance

- `inverter_switching_model.slx`  
  Mainline switching-level model.

- `inverter_switching_variant_*.slx`  
  Variant models created for specific non-ideal or exploratory studies.  
  These do not replace the mainline model.

---

## Cross-Phase Traceability

For structured cross-phase traceability between Phase-2 engineering judgement and Phase-3 executable artefacts, see:

`docs/validation_mapping.md`.