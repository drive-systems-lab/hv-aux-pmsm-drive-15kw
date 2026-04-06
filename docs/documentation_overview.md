# Documentation Overview

This document provides a structured navigation overview of the documentation artefacts within the repository.

It organises documentation by engineering role and phase alignment.  
No additional technical claims or validation statements are introduced here.

---

## System Design & Scaffolding (Phase 1)

High-level system architecture and requirement-related documentation.

- `system_requirements.md`
- `system_architecture.md`
- `control_architecture.md`
- `architecture_tradeoffs.md`
- `parameter_table.md`

---

## Power Stage Design (Phase 2)

Inverter power-stage design reasoning and trade-off documentation.

- `phase2_scope.md`
- `power_stage_baseline.md`
- `power_stage_design_judgement.md`
- `power_stage_design.md`
- `protection_and_state_machine.md`
- `power_stage_tradeoff_matrix.md`

---

## Modelling & Structural Validation (Phase 3)

Switching simulation, discrete modelling, abstraction-layer alignment, and traceability documentation.

- `switching_discrete_alignment.md`
- `validation_mapping.md`

Executable models are located under:

- `models/switching/` (model-level documentation provided in directory README)
- `models/discrete/` (model-level documentation provided in directory README)

---

## Control Integration & Behaviour Exploration (Phase 4)

Control-facing interpretation, engineering-constraint framing, executable closed-loop baseline development, and representative behavioural documentation for the frozen Phase-4 baseline.

Documentation artefacts include:

- `control_plant_context.md`
- `engineering_constraints.md`
- `control_behaviour.md`

Executable models are located under:

- `models/control/` (control-side and top-level closed-loop baseline artefacts)
- `models/switching/` (including the closed-loop integration variant alongside the preserved Phase-3 switching baseline context)
- `models/discrete/` (including the closed-loop integration variant alongside the preserved Phase-3 discrete PMSM baseline context)