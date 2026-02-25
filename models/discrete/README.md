# Discrete-Time PMSM Electrical Model

This directory contains the discrete-time dq electrical model of the PMSM used to represent the electrical state-update layer of the drive system in executable form.

The model expresses the linear dq electrical dynamics under a rotor-flux-aligned reference frame and serves as a structural abstraction artefact within the overall system framework.

Its purpose is to make the electrical state evolution observable and interpretable at discrete time resolution, without introducing optimisation or implementation commitments.

---

## Modelling Scope

The model includes:

- Linear dq electrical state dynamics
- Discrete-time representation of the electrical state equations
- Explicit closed discrete state-update structure with delayed feedback
- Cross-axis coupling representation
- Back-EMF term under rotor-flux alignment
- Consistent discrete-time execution environment

The emphasis is on structural clarity and executable consistency rather than numerical convergence or performance evaluation.

---

## Explicitly Excluded

The following aspects are intentionally outside the scope of this model:

- Mechanical dynamics
- Control-loop implementation or tuning
- Parameter optimisation or performance iteration
- High-fidelity physics-based motor modelling beyond the linear dq abstraction
- Hardware construction or experimental validation

This model represents an abstraction layer only and should not be interpreted as a final design commitment.

---

## Model File Governance

- `pmsm_discrete_model.slx`  
  Mainline discrete electrical model.

- `pmsm_discrete_variant_*.slx`  
  Variant models created for exploratory or non-ideal studies.  
  These do not replace the mainline model.

---

## Cross-Phase Traceability

For structured cross-phase traceability between Phase-2 engineering judgement and Phase-3 executable artefacts, see:

`docs/validation_mapping.md`.