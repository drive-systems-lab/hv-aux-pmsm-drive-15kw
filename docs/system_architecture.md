# System Architecture – 15 kW HV Auxiliary PMSM Drive (800 V Platform)

> **Status (Day 5, Phase 1):**  
> Skeleton only. Content will be expanded after system requirements, block diagram, and top-level model stabilise.

---

## 1. System Composition (Draft)

The system consists of the following high-level functional elements:

- High-voltage DC bus (800 V platform)
- Power converter for auxiliary drive
- Auxiliary PMSM and associated mechanical load
- Control hardware, sensing, and signal conditioning
- Protection, cooling, and supporting subsystems (TBD)

---

## 2. Electrical Architecture (Placeholder)

- Overall power path from HV DC bus to PMSM (TBD)
- DC-link structure, filtering, and energy buffering (TBD)
- Key measurement points and protection elements (TBD)

---

## 3. Control Architecture (Placeholder)

- High-level speed / torque control hierarchy (TBD)
- Inner-loop current control and PWM generation (TBD)
- Protection logic and fault-state handling (TBD)

---

## 4. Interfaces (Placeholder)

This section describes system-level interfaces rather than signal-level implementations:

- High-voltage DC interface
- Motor phase electrical connections
- Low-voltage supply and control I/O
- Communication and diagnostics interface (scope TBD)

---

## 5. Open Points

- Alignment with system requirements definition
- Consistency with system block diagram representation
- Mapping to the `system_level.slx` top-level model structure
