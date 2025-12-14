# 15 kW High-Voltage Auxiliary PMSM Drive (800 V Platform)

This repository presents a structured engineering workflow for a 15 kW high-voltage auxiliary PMSM drive designed for an 800 V EV platform.

The target applications are auxiliary loads such as oil pumps and coolant pumps, where reliability, thermal performance, environmental robustness, and compact power-electronics design are essential.

The repository is organised as an engineering portfolio project, demonstrating end-to-end drive-system engineering, including system specification, architecture design, power-stage reasoning, modelling, control design, simulation workflow, testing and debugging methodology and engineering documentation.

All numerical parameters and models are illustrative and intended for demonstration rather than deployment.  
The system parameters and models represent a generalized abstraction inspired by typical high-voltage auxiliary drive architectures, and do not correspond to any specific commercial product.

---

# 1. Engineering Scope and Objectives

Building on the overview given above, this section outlines the engineering domains and deliverables addressed in this project.  
The work focuses on the following core elements:

### • System specification and use-case definition
Establishing operational requirements, environmental constraints and interface definitions.

### • Architecture design
Defining the overall system structure, functional decomposition, control architecture, signal interfaces, protection paths, and subsystem interactions.

### • Power-stage design reasoning
Performing power-stage design reasoning across inverter topology, semiconductor selection, switching-frequency rationale, DC-link behaviour, modulation constraints, protection concepts, and EMI/thermal considerations.

### • Modelling and simulation workflow
Developing system-level, control-oriented and switching models, together with a structured multi-stage validation workflow.

### • Control design
Designing control algorithms, including FOC/SVPWM implementation logic, bandwidth selection, PI tuning, delay compensation, limiting strategies, nonlinear-region handling, and commissioning considerations.

### • Testing and debugging methodology
Conducting testing and debugging workflow, including measurement considerations, limiter and anti-windup behaviour, EMI-related effects, step-response testing, and practical debugging strategies.

### • Engineering documentation
Producing clear, traceable engineering documentation aligned with industry practices, including system notes, modelling assumptions, design justifications, and debugging insights.

---

# 2. System Context and Initial Specifications

*(These items will be refined and extended throughout Phase 1.)*

* **Application:**  
  EV auxiliary drive (oil pump, coolant pump, etc.)

* **Rated power:**  
  15 kW nominal, short-term peak capability

* **DC bus:**  
  800 V high-voltage EV architecture

* **Machine:**  
  Three-phase PMSM, water-cooled, medium-speed

* **Control:**  
  Field-Oriented Control (FOC) with SVPWM

* **Controller:**  
  TI C2000-series DSPs (TMS320F28335 or TMS320F28377), with concepts applicable to other DSP/MCU platforms.

* **Key considerations:**  
  reliability, protection, thermal constraints, EMI considerations, and start-up behaviour.

More detailed requirements — torque-speed envelope, current limits, modulation constraints, efficiency objectives — will be added as the system requirement document (SRD) evolves.

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

### Phase 1 — System Design & Scaffolding (Dec 2025)

* Define system requirements  
* Establish repository structure  
* Draft initial models and documentation framework  

### Phase 2 — Power Stage Design (Jan 2026)

* Semiconductor and topology reasoning  
* Switching-frequency justification  
* DC-link behaviour analysis  
* Protection and state-machine concepts  
* Preliminary thermal/EMI considerations  

### Phase 3 — Modelling & Simulation (Feb 2026)

* Develop switching, system-level and control-oriented models  
* Compare behaviour across modelling levels  
* Build validation workflow for tuning and performance checks  

### Phase 4 — Control, Debugging & Release v1.0 (Mar 2026)

* Document FOC/SVPWM logic and control structure  
* PI tuning workflow and delay-handling strategy  
* Limiting, nonlinear-region handling  
* Debugging methodology and commissioning notes  
* Final documentation and v1.0 packaging  

This plan may evolve as refinements or additional demonstrations are added, while maintaining overall structural consistency.

---

# 5. Project Status

Current phase: **Phase 1 — System Design & Scaffolding**

This phase focuses on establishing the system-level definition, architecture, and documentation framework.

Updates will be added throughout the development process as models, diagrams and documentation mature.

---

# 6. Notes

* All models, diagrams, and algorithms are illustrative.  
* No proprietary firmware or commercial IP is included.  
* The focus of this repository is engineering reasoning, clarity of structure, and methodological demonstration, rather than deployable embedded software.
