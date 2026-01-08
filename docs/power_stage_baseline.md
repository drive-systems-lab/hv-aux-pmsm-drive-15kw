# Power-Stage Baseline Definition

This document defines the **Phase 2 power-stage baseline** for the 15 kW High-Voltage Auxiliary PMSM Drive (800 V platform).

The purpose of this document is to establish a clear and explicit **system-level reference configuration** for power-stage-related engineering judgement and trade-off activities within Phase 2.

This baseline definition is intentionally limited to **structural and conceptual aspects**. Numerical design, component selection, detailed modelling, and implementation-level decisions are explicitly deferred to later phases.

---

## 1. Baseline Scope and Intent

The power-stage baseline defined in this document serves as a **common engineering anchor** for Phase 2. It enables consistent system-level reasoning about power-path structure, interfaces, and operational behaviour, without committing to detailed hardware realisation.

The baseline is intended to:  

- Anchor Phase 2 design reasoning at system level  
- Provide a stable reference for evaluating power-stage-related engineering judgements and trade-offs  
- Preserve flexibility for informed evolution in subsequent phases  

This document does **not** represent a final or optimised hardware design.

---

## 2. Baseline Inverter Topology

For Phase 2 reasoning and discussion, the inverter power stage baseline is defined as a **three-phase, two-level voltage-source inverter (2-level VSI)** supplied directly from the high-voltage DC bus.

This topology is adopted as a **baseline reference configuration** for the following reasons:  

- Provide a well-understood and widely applicable structural reference  
- Support clear system-level reasoning without premature optimisation  
- Enable consistent definition of power paths and interfaces  

At this stage, the baseline is defined strictly at **topology and functional level**. No assumptions are made regarding:  

- Semiconductor device technology or ratings  
- Switching frequency or modulation strategy  
- Loss distribution, efficiency, or thermal performance  

---

## 3. Power Path and Functional Structure

At system level, the baseline power stage consists of the following functional elements:  

- High-voltage DC bus interface  
- DC-link energy buffering stage  
- Three-phase inverter bridge  
- AC-side connection to the PMSM  

The baseline assumes a **direct DC–AC conversion path**, without any intermediate DC/DC stage. Detailed circuit realisation, component sizing, parasitic effects, and layout considerations are intentionally outside the scope of this definition.

---

## 4. Measurement and Control Interfaces

The baseline defines the presence of essential **measurement and control interfaces** required for safe and controllable operation, including:  

- DC bus voltage sensing  
- Phase current sensing  
- Inverter temperature monitoring  
- Gate-drive control interface  
- Enable / disable and fault signalling paths  

Specific sensing technologies, signal conditioning methods, sampling strategies, and control-loop implementation details are deferred to later phases.

---

## 5. Protection and Safe-State Concept

From a baseline perspective, the power stage is assumed to support a clear **safe-state philosophy**, including:

- Identification of major fault categories (electrical, thermal, control-related)  
- Definition of a non-energised safe state  
- Support for controlled enable and shutdown transitions  

Protection thresholds, response timing, and implementation mechanisms are not defined at this stage.

---

## 6. Reconsideration and Evolution Conditions

The 2-level VSI topology is adopted as a **baseline reference**, not as an irreversible commitment.

Alternative inverter topologies may be reconsidered in later phases if system-level constraints—such as voltage stress margins, efficiency envelope, or EMI considerations—cannot be adequately satisfied within the baseline configuration.

Any such reconsideration would be addressed through explicit trade-off analysis and documented decision records.

---

## 7. Boundary to Subsequent Phases

In accordance with the Phase 2 scope definition, the following activities are **explicitly outside the scope** of this baseline document:

- Numerical design calculations  
- Detailed electrical or thermal modelling  
- Component-level sizing and part-number selection  
- Simulation-based verification  
- Hardware construction or experimental validation  

These activities belong to **Phase 3 and beyond**.

---

## 8. Summary

This document establishes a **clear and defensible power-stage baseline** for Phase 2. By explicitly defining the reference topology and system-level structure, it enables coherent engineering judgement while preserving flexibility for controlled evolution in subsequent phases.
