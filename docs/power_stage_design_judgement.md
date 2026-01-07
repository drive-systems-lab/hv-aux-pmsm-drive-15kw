# Power Stage Design Judgement Framework

This document defines the **engineering judgement framework** used for power stage design decisions
in **Phase 2 — Power Stage Design** of the 15 kW High-Voltage Auxiliary PMSM Drive (800 V platform).

The purpose of this document is to make explicit **how design decisions are evaluated and prioritised** at system level, before committing to numerical design, detailed modelling, or implementation work in later phases.

This document does **not** present final design choices or calculated results. Instead, it establishes the **decision logic and constraints** that govern all Phase 2 power-stage-related discussions.

---

## 1. Role of Engineering Judgement in Phase 2

Phase 2 operates at a **system-judgement level**, positioned between architectural definition (Phase 1) and quantitative design execution (Phase 3).

At this stage, the objective is to:
- Identify **dominant constraints** affecting the power stage
- Understand **key trade-offs** inherent to the voltage and power level
- Establish **decision priorities** that guide subsequent detailed work

Engineering judgement in Phase 2 answers the question:

> *What power stage design directions are appropriate, and why, given the system context and risks?*

---

## 2. Primary Judgement Dimensions

Power stage design judgement in Phase 2 is organised around the following primary dimensions. These dimensions are considered **before** any numerical optimisation or component sizing.

### 2.1 Voltage Level and Insulation Stress

The high-voltage operating environment introduces system-level concerns such as:
- dv/dt-related insulation stress
- Partial discharge risk
- Long-term reliability under repetitive switching

These considerations influence acceptable switching behaviour and technology choices prior to any quantitative loss or thermal analysis.


### 2.2 Semiconductor Technology Suitability

Semiconductor technology selection is considered at a **category level**, focusing on:
- Device characteristics relative to voltage level
- Switching behaviour and controllability
- System integration risk and robustness

The objective is to assess **technology suitability**, not to select specific devices or part numbers.


### 2.3 Switching Behaviour and System Interaction

Switching behaviour is evaluated qualitatively with respect to:
- Interaction with the DC bus
- Electromagnetic interference awareness
- Impact on insulation and system stress

At this stage, switching frequency is treated as a **design dimension**, not as a fixed or optimised parameter.


### 2.4 DC Bus Energy Handling and Stability

DC bus considerations focus on:
- Energy buffering role at system level
- Ripple current awareness
- Interaction with inverter switching behaviour

The emphasis is on **design reasoning and methodology**, rather than final capacitor sizing or topology optimisation.


### 2.5 Protection Philosophy and Operational Safety

Protection is addressed from a **conceptual and structural perspective**, including:
- Fault category identification
- Safe-state definition
- High-level protection response philosophy

Detailed protection thresholds, timings, and implementation mechanisms are intentionally deferred.

---

## 3. Decision Priority and Constraint Hierarchy

Not all design dimensions carry equal weight. In Phase 2, judgement is guided by an implicit priority hierarchy:

1. **Safety and reliability constraints**
2. **System-level electrical stress and robustness**
3. **Architectural consistency with Phase 1**
4. **Performance and efficiency potential**

This hierarchy ensures that early decisions reduce systemic risk, rather than prematurely optimising secondary metrics.

---

## 4. Relationship to Subsequent Phase 2 Design Topics

All Phase 2 power-stage-related documents are expected to:
- Align with the judgement framework defined here
- Explicitly state which judgement dimensions they address
- Avoid numerical conclusions or implementation commitments

This framework provides a **common reference point** for:
- Semiconductor technology discussion
- DC bus design methodology
- Switching behaviour reasoning
- Protection and state-machine concepts

---

## 5. Boundary to Quantitative Design Work

As defined in `phase2_scope.md`, any topic that requires:
- Numerical calculation
- Detailed electrical modelling
- Executable simulation
- Component-level sizing

belongs to **Phase 3**, not Phase 2.

This judgement framework exists to ensure that Phase 2 decisions remain **traceable, defensible, and appropriately scoped**.

---

## 6. Summary

This document establishes the **decision logic foundation** for Phase 2 power stage design. By making engineering judgement explicit, it enables later phases to proceed with clear intent, controlled risk, and coherent design rationale.
