# Control Architecture Overview

> **Status (Phase 1 Snapshot)**  
> This document defines the system-level functional control architecture baseline for the 15 kW-class high-voltage auxiliary PMSM drive (800 V platform).  
> The scope is intentionally limited to architecture structure, signal interfaces, and functional partitioning. Control algorithms, parameterisation, and outer-loop or supervisory strategies are explicitly deferred to later phases.

---

## 2. Architecture Boundary (Phase 1 Definition)

The Phase 1 control architecture boundary is limited to:

- The **inner control functions** associated with interfacing between system-level references and the power stage
- The **functional partitioning** of control tasks
- The **signal flow and interfaces** between major control blocks

The following are **out of scope** in Phase 1 and therefore not specified here:

- Outer-loop or supervisory control logic  
- Detailed control algorithms or tuning parameters  
- Performance targets, stability margins, or validation results  

---

## 3. High-Level Control Structure

At system level, the controller is represented as a **functional block** consisting of two primary subsystems:

1. **Current Control (dq frame)**
2. **Modulation (SVPWM placeholder)**

These subsystems operate within a unified controller boundary and interact with external system elements through well-defined signal interfaces.

---

## 4. Current Control (dq Frame)

The **Current Control** block represents the inner control function responsible for regulating machine currents in the rotating dq reference frame.

### Functional role:
- Accepts current references `i_dq_ref` provided by an **outer loop or system supervisor** (defined in Phase 2+)
- Processes measured phase currents `i_abc`, transformed internally into the dq frame
- Utilises electrical position feedback `theta_e_meas` for reference frame alignment
- Generates voltage references `v_dq_ref` for downstream modulation

This block is treated as a **functional abstraction** in Phase 1.  
Specific control algorithms, observers, or tuning strategies are not defined at this stage.

---

## 5. Modulation (SVPWM Placeholder)

The **Modulation** block represents the functional interface between voltage references and inverter switching commands.

### Functional role:
- Accepts dq-frame voltage references `v_dq_ref`
- Receives DC-link voltage information `vdc`
- Produces phase-domain duty commands `d_abc` for the power stage

In Phase 1, this block is explicitly defined as a **placeholder**, representing the modulation function at architectural level rather than a committed implementation.  
At model level, this placeholder is instantiated as an *SVPWM skeleton* to provide a concrete but non-final executable structure.  

The exact modulation strategy, timing behaviour, and implementation details are deferred to later phases.

---

## 6. Signal Interfaces and Flow

The control architecture is characterised by a **clear and unidirectional signal flow**:

- **Inputs to the controller**:
  - `i_dq_ref` from outer-loop or supervisory control (Phase 2+)
  - `i_abc` from current sensing
  - `theta_e_meas` from position sensing
  - `vdc` from DC-link measurement

- **Internal signal flow**:
  - Current Control → Modulation via `v_dq_ref`

- **Outputs from the controller**:
  - Duty commands `d_abc` to the power stage

All signals are defined at **interface level only**, without assumptions on sampling rates, bandwidths, or numerical representation.

---

## 7. Relationship to System Architecture

Within the overall system architecture, the controller is a **subsystem** that:

- Receives references and constraints from higher-level system control
- Interfaces with sensing and actuation elements
- Does not define system-level objectives or energy management strategies in Phase 1

This ensures that control architecture remains **consistent with the system-level baseline**, without introducing premature implementation commitments.

---

## 8. Phase 1 Positioning

This control architecture serves as a **baseline definition** for subsequent phases:

- Phase 2 will refine control algorithms and higher-level control structures, as applicable
- Phase 3+ will address implementation, tuning, validation, and optimisation

Phase 1 intentionally focuses on **structure, interfaces, and boundaries**, rather than detailed control behaviour.
