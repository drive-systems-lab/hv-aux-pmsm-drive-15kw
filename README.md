# 15 kW High-Voltage Auxiliary PMSM Drive (800 V Platform)

This repository presents a structured engineering workflow for a 15 kW high-voltage auxiliary PMSM drive designed for an 800 V EV platform.

It is organised as a release-facing engineering portfolio, with the current v1.0 snapshot centred on system definition, architecture reasoning, executable modelling continuity, closed-loop control baseline formation, and representative qualitative behavioural evidence.

The target application context is auxiliary loads such as oil pumps and coolant pumps, where reliability, thermal constraints, environmental robustness, and compact power-electronics integration are important engineering considerations.

> **Phase snapshot: Phase 1 complete · Phase 2 complete · Phase 3 complete · Phase 4 complete (closed-loop control baseline and representative behavioural evidence established)**
>
> **Phase 1** establishes and freezes the system-level definition, functional architecture, and control-boundary design. Parameters at this stage are architectural anchors and structural placeholders, rather than performance commitments. 
>
> **Phase 2** establishes the system-level power-stage reasoning baseline, consolidating architectural and behavioural judgements while intentionally remaining non-implementation-ready. Numerical design, detailed modelling, and validation activities are explicitly deferred beyond the Phase-2 reasoning boundary.
>
> **Phase 3** establishes executable modelling artefacts at switching and discrete abstraction layers. Structural traceability to Phase-2 engineering judgement is consolidated through alignment and validation mapping documentation. No optimisation or implementation commitments are introduced at this stage.  
>  
> **Phase 4** establishes the control–plant interpretation baseline, the executable closed-loop control baseline, and representative behavioural evidence within the adopted Phase-4 modelling boundary. The resulting artefacts remain qualitative, scope-disciplined, and non-implementation-finalised.   

This repository is not intended as an implementation-ready product package, a hardware-validated controller release, or a tuning-complete deployment artefact.

All numerical parameters and models are illustrative and intended for repository-facing demonstration rather than deployment.  
The system parameters and models represent a generalised abstraction informed by typical high-voltage auxiliary drive architectures and do not correspond to any specific commercial product.

---

# 1. Engineering Scope and Objectives

This repository is structured to demonstrate a disciplined end-to-end engineering workflow for the drive system through phased project execution.

The engineering scope addressed across the repository includes the following core domains:

### • System specification and use-case definition
Establishing operating context, environmental constraints, and interface boundaries at system level.

### • Architecture design
Defining the overall system structure, functional decomposition, control architecture, signal interfaces, protection paths, and subsystem relationships.

### • Power-stage design reasoning
Performing power-stage design reasoning across inverter topology, semiconductor selection, switching-frequency rationale, DC-link behaviour, modulation constraints, protection concepts, and related engineering constraints.

### • Modelling and executable artefacts
Developing system-level, switching-level, discrete-time, and closed-loop integration artefacts across clearly defined modelling layers.

### • Control integration and behavioural observation
Establishing a baseline FOC/SVPWM current-control path, executable closed-loop control baseline, and representative qualitative behavioural evidence within explicitly stated modelling boundaries.

### • Engineering documentation
Producing repository-facing documentation that supports traceability, structural clarity, scope discipline, and engineering interpretability across the repository.

Broader engineering considerations such as controller-platform awareness, practical implementation context, and design-side constraints are referenced where useful for interpretation, but they are not treated as primary v1.0 deliverable layers in this repository.

---

# 2. System Context and Initial Specifications

These items were established during Phase 1 and should be read as the released system-context baseline supporting the present repository snapshot.

* **Application:**  
  EV auxiliary drive (oil pump, coolant pump, etc.)

* **Rated power:**  
  15 kW power class for a high-voltage auxiliary drive system.  
  This rating represents a system-level power class rather than a guaranteed continuous mechanical output, and reflects typical inverter, machine, duty-cycle, and thermal design constraints.

* **DC bus:**  
  800 V high-voltage EV architecture

* **Machine:**  
  Three-phase PMSM, liquid-cooled (typically water-cooled in EV auxiliary applications)

* **Control:**  
  Field-Oriented Control (FOC) with SVPWM

* **Control platform:**  
  TI C2000-series DSPs (e.g. TMS320F28335 or TMS320F28377) are used as representative reference platforms; the underlying concepts are not restricted to a specific DSP/MCU family.

* **Key considerations:**  
  Reliability, protection, thermal constraints, EMI considerations, and start-up behaviour.

More detailed requirement-level parameters and design-side constraints remain outside the present README summary layer and are addressed selectively across the repository documentation within the current v1.0 scope.

---

# 3. Repository Structure

The repository is organised as follows in the current v1.0 release:

```text
/
├── docs/                # Repository-facing documentation covering requirements,
│                        # architecture, power-stage reasoning, control–plant interpretation,
│                        # engineering constraints, and behavioural documentation
│
├── design/              # Currently reserved in v1.0
│                        # No dedicated design-note layer is populated in the present release
│
├── models/              # System-level reference artefact, together with executable
│                        # modelling artefacts across switching-level, discrete-time,
│                        # controller-side, modulation-side, and closed-loop integration layers
│
├── src/                 # Currently reserved in v1.0
│                        # The present release does not include a source-code or pseudocode layer
│
├── images/              # Architecture figures, block diagrams, conceptual diagrams,
│                        # and curated behavioural plots
│
└── README.md            # Project overview and release-facing navigation entry point
```

For a guided view of the repository documentation and associated model locations,  
see [`docs/documentation_overview.md`](docs/documentation_overview.md).

---

# 4. Delivered Phase Structure (Dec 2025 – Apr 2026)

The repository is presented through a four-phase delivered development sequence.

### Phase 1 — System Design & Scaffolding (Baseline Definition) (Dec 2025 – Jan 2026)

* Define system requirements  
* Establish repository structure  
* Draft the initial documentation and modelling framework 

### Phase 2 — Power Stage Design (Reasoning Level) (Jan 2026 – Feb 2026)

* Establish semiconductor and topology reasoning  
* Establish switching-frequency rationale  
* Document DC-link behaviour reasoning  
* Consolidate protection and state-related concepts  
* Record associated engineering constraints

### Phase 3 — Modelling & Structural Validation (Feb 2026 – Mar 2026)

* Establish the switching-level executable inverter model  
* Establish the discrete-time PMSM dq electrical model  
* Clarify abstraction-layer alignment  
* Consolidate validation mapping between Phase-2 reasoning and Phase-3 artefacts  
* Freeze the modelling baseline without optimisation or implementation commitments  

### Phase 4 — Control Integration & Behaviour Exploration (Mar 2026 – Apr 2026)

* Establish the control–plant interpretation baseline  
* Establish the executable closed-loop control baseline  
* Document representative qualitative behavioural observations on the frozen closed-loop control baseline  
* Consolidate repository-facing documentation and release-facing closure for v1.0

---

# 5. Project Status

Current status: **v1.0 release-facing repository snapshot completed**

The present repository state provides:

- a coherent system-to-control documentation chain
- frozen Phase-3 modelling baselines
- Phase-4 control–plant interpretation and closed-loop control baseline artefacts
- representative qualitative behavioural evidence documented within explicit modelling boundaries

---

# 6. Notes

* All models, diagrams, and algorithms are illustrative.  
* No proprietary firmware or commercial IP is included.  
* This repository focuses on engineering reasoning, structural clarity, and methodological demonstration rather than deployable embedded software or hardware-facing validation.
* See LICENSE for usage and redistribution terms.
