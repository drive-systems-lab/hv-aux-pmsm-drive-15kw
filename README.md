# 15 kW High-Voltage Auxiliary PMSM Drive (800 V Platform)

This repository presents a structured engineering workflow for a 15 kW high-voltage auxiliary PMSM drive designed for an 800 V EV platform.

The target applications are auxiliary loads such as oil pumps and coolant pumps, where reliability, thermal performance, environmental robustness, and compact power-electronics design are essential.

The repository is organised as an engineering portfolio project, structured to demonstrate end-to-end drive-system engineering.  
The full engineering scope spans system specification, architecture design, power-stage reasoning, modelling strategy, control design, simulation workflow, testing and debugging methodology, and engineering documentation, developed across phased project execution.

> **Phase snapshot: Phase 1 complete · Phase 2 complete · Phase 3 complete · Phase 4 complete (closed-loop baseline and representative behavioural evidence established)**
>
> **Phase 1** establishes and freezes the system-level definition, functional architecture, and control-boundary design. Parameters at this stage are architectural anchors and structural placeholders, rather than performance commitments. 
>
> **Phase 2** establishes the system-level power-stage reasoning baseline, consolidating architectural and behavioural judgements while intentionally remaining non-implementation-ready. Numerical design, detailed modelling, and validation activities are explicitly deferred to subsequent phases.
>
> **Phase 3** establishes executable modelling artefacts at switching and discrete abstraction layers. Structural traceability to Phase-2 engineering judgement has been consolidated through alignment and validation mapping documentation. No optimisation or implementation commitments are introduced at this stage.  
>  
>  **Phase 4** establishes the control–plant interpretation baseline, executable closed-loop control baseline, and representative behavioural evidence on the frozen structural baseline. The resulting artefacts remain qualitative, scope-disciplined, and non-implementation-finalised.    

All numerical parameters and models are illustrative and intended for demonstration rather than deployment.  
The system parameters and models represent a generalized abstraction inspired by typical high-voltage auxiliary drive architectures, and do not correspond to any specific commercial product.

---

# 1. Engineering Scope and Objectives

Building on the overview given above, this section outlines the overall engineering domains and deliverables addressed in this project.  
The work focuses on the following core elements (addressed progressively across phases, as outlined in the development plan):

### • System specification and use-case definition
Establishing operational requirements, environmental constraints and interface definitions.

### • Architecture design
Defining the overall system structure, functional decomposition, control architecture, signal interfaces, protection paths, and subsystem interactions.

### • Power-stage design reasoning
Performing power-stage design reasoning across inverter topology, semiconductor selection, switching-frequency rationale, DC-link behaviour, modulation constraints, protection concepts, and EMI/thermal considerations.

### • Modelling and simulation workflow
Developing system-level, control-oriented and switching models, together with a structured multi-stage validation workflow.

### • Control integration and behavioural observation
Establishing a baseline FOC/SVPWM current-control path, executable closed-loop control baseline, and representative behavioural evidence within a qualitative modelling boundary.

### • Engineering documentation
Producing clear, traceable engineering documentation aligned with industry practices, including system notes, modelling assumptions, design justifications, control–plant interpretation, engineering constraints, and behavioural documentation.

---

# 2. System Context and Initial Specifications

*(These items were established during Phase 1 and may be further refined in later phases.)*

* **Application:**  
  EV auxiliary drive (oil pump, coolant pump, etc.)

* **Rated power:**  
  15 kW power class for a high-voltage auxiliary drive system.  
  This rating represents a system-level power class rather than a guaranteed continuous mechanical output,  
  and reflects typical inverter, machine, duty-cycle, and thermal design constraints.

* **DC bus:**  
  800 V high-voltage EV architecture

* **Machine:**  
  Three-phase PMSM, liquid-cooled (typically water-cooled in EV auxiliary applications)

* **Control:**  
  Field-Oriented Control (FOC) with SVPWM

* **Controller:**  
  TI C2000-series DSPs (e.g. TMS320F28335 or TMS320F28377) are used as reference platforms; the concepts are applicable to other DSP/MCU platforms.

* **Key considerations:**  
  reliability, protection, thermal constraints, EMI considerations, and start-up behaviour.

More detailed requirements — torque-speed envelope, current limits, modulation constraints, efficiency objectives — will be further detailed in subsequent phases.

---

# 3. Repository Structure

The repository is organised to mirror a practical drive-system engineering workflow:

```text
/
├── docs/                # System requirements, architecture descriptions, control concepts,
│                        # protection strategies, modelling assumptions, and debugging notes
│
├── design/              # Power-stage reasoning: inverter topology, semiconductor selection,
│                        # switching-frequency rationale, DC-link behaviour, thermal/EMI aspects
│
├── models/              # System-level, control-oriented, and switching models,
│                        # plus validation and comparison workflows
│
├── src/                 # Pseudocode and reference algorithm structures for FOC, SVPWM,
│                        # limiters, delay compensation and state-machine scaffolding
│                        # (no proprietary or production-ready firmware)
│
├── images/              # Architecture and control block diagrams, schematics, plots,
│                        # and other documentation figures
│
└── README.md            # Project overview and navigation entry point
```
This structure is designed to clearly separate requirements, design reasoning, modelling, and algorithm development — reflecting real industry practices and supporting future extension.

---

# 4. Development Plan (Dec 2025 – Mar 2026)

The project follows a four-phase development timeline aligned with typical automotive and industrial drive-development workflows:

### Phase 1 — System Design & Scaffolding （Baseline Definition) (Dec 2025)

* Define system requirements  
* Establish repository structure  
* Draft initial models and documentation framework  

### Phase 2 — Power Stage Design (Reasoning Level) (Jan 2026)

* Semiconductor and topology reasoning  
* Switching-frequency justification  
* DC-link behaviour analysis  
* Protection and state-machine concepts  
* Preliminary thermal/EMI considerations  

### Phase 3 — Modelling & Structural Validation (Feb 2026)

* Establish switching-level executable inverter model  
* Establish discrete-time PMSM dq electrical model  
* Clarify abstraction-layer alignment  
* Consolidate structured validation mapping between Phase-2 reasoning and Phase-3 artefacts  
* Freeze modelling baseline without optimisation or implementation commitments

### Phase 4 — Control Integration & Behaviour Exploration (Mar 2026)

* Establish the control–plant interpretation baseline  
* Establish the executable closed-loop control baseline  
* Document representative behavioural observations on the frozen closed-loop baseline  
* Consolidate repository-facing documentation and readiness for v1.0 release

This plan may evolve as refinements or additional demonstrations are added, while maintaining overall structural consistency.

---

# 5. Project Status

Current phase: **Phase 4 — completed (closed-loop baseline and representative behavioural evidence established)**

Phase 4 establishes the control–plant interpretation baseline, executable closed-loop control baseline, and representative behavioural evidence on the frozen structural baseline, while maintaining strict scope discipline.
All Phase 4 outputs remain intentionally **qualitative, non-optimised, and non-implementation-finalised**.

Future updates may extend the repository through later release-facing refinement and polishing while preserving the current structural baseline.

---

# 6. Notes

* All models, diagrams, and algorithms are illustrative.  
* No proprietary firmware or commercial IP is included.  
* This repository focuses on engineering reasoning, structural clarity, and methodological demonstration rather than deployable embedded software or hardware-facing validation.
* See LICENSE for usage and redistribution terms.

