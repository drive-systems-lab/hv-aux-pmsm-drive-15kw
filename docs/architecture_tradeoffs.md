# Architecture Trade-offs  
15 kW-Class High-Voltage Auxiliary PMSM Drive (800 V Platform)

Project: HV Auxiliary PMSM Drive  
Phase: Phase 1 – System Design & Scaffolding  
Status: Finalised for Phase 1  
Purpose: System-level architectural trade-off record

---

## 1. Intent and Scope

This document records the evaluation of a key system-level architectural trade-off addressed during Phase 1 of the project.

The objective of Phase 1 is not to finalise component ratings, converter topologies, or detailed control implementations. Instead, Phase 1 focuses on:

- establishing a consistent system context,
- identifying viable architectural alternatives at system level,
- selecting an appropriate architectural baseline to frame subsequent project phases.

Accordingly, this document captures a single architectural trade-off that is both meaningful and decidable at the system level at this stage, while explicitly deferring detailed design decisions to later phases.

---

## 2. Drive Architecture Trade-off  
**Direct DC/AC Drive vs. DC/DC-Based Drive**

### 2.1 Considered Architectural Options

Two system-level drive architectures were considered for the high-voltage auxiliary PMSM drive:

1. **HV DC Bus → DC/DC Converter → Inverter → PMSM (DC/DC-Based Drive)**  
2. **HV DC Bus → Inverter → PMSM (Direct DC/AC Drive)**

In this context, *DC/DC-Based Drive* refers to a conversion structure in which an intermediate DC/DC stage is introduced between the vehicle high-voltage DC bus and the low- or medium-voltage inverter–machine subsystem. 

By contrast, *Direct DC/AC Drive* refers to a structure in which an inverter is supplied directly from the vehicle high-voltage DC bus, without an intermediate DC/DC conversion stage, and therefore implies the use of a high-voltage electric machine.

Both architectures are technically viable under modern EV high-voltage platforms and are employed in auxiliary-drive applications, depending on system constraints, integration strategy, and design priorities.

---

### 2.2 Architectural Implications at System Level

The two drive architectures outlined above—DC/DC-Based Drive and Direct DC/AC Drive—lead to distinct system-level implications, primarily through the resulting voltage class of the inverter–machine subsystem and its degree of coupling to the vehicle high-voltage DC bus.

In a DC/DC-Based Drive architecture, the introduction of an intermediate DC/DC stage enables a low- or medium-voltage inverter–machine subsystem that is electrically decoupled from the vehicle high-voltage DC bus. This facilitates the use of low- or medium-voltage motor platforms, reduces high-voltage exposure at the machine interface, and relaxes certain insulation and EMI constraints.

By contrast, a Direct DC/AC Drive architecture implies a high-voltage-rated electric machine that is directly coupled to the vehicle high-voltage DC bus characteristics. While this approach avoids an additional power-conversion stage, it increases the degree of coupling between DC-bus behaviour, inverter modulation, and motor electrical parameters, and introduces corresponding requirements on insulation coordination, voltage utilisation, and EMI robustness.

Taken together, these architecture-dependent implications influence overall system complexity, efficiency potential, control-structure integration, and component interaction, and therefore constitute a genuine system-level architectural trade-off.

---

### 2.3 Phase 1 Architectural Positioning

Based on Phase 1 system-level considerations, the project proceeds with a **direct DC/AC drive architecture** as the reference architectural context for subsequent phases.

This positioning establishes a coherent and realistic system baseline for modelling and architectural reasoning, while acknowledging that detailed implementation choices and constraint-driven refinements are addressed in later phases.

---

### 2.4 Rationale at System Level

The direct DC/AC drive architecture is adopted at Phase 1 primarily due to the following system-level considerations:

- **Reduced architectural complexity**  
  The absence of an intermediate DC/DC stage reduces component count, interfaces, packaging volume, and potential failure points, which is particularly relevant for space- and mass-sensitive automotive auxiliary applications.

- **Efficiency and power-flow clarity**  
  Eliminating an additional conversion stage avoids associated losses and simplifies the power-flow path from the vehicle DC bus to the electric machine, which is particularly relevant in vehicle applications where efficiency and thermal margin are closely linked to system reliability.


- **Simplified control partitioning**  
  A single-stage power-conversion structure avoids the need to manage integration between cascaded converter stages, thereby reducing overall system-level integration effort.


- **Representative high-voltage auxiliary-drive context**  
  The selected architecture reflects a commonly adopted configuration in modern high-voltage auxiliary systems, providing a realistic and engineering-relevant baseline for subsequent analysis.

This architectural positioning intentionally exposes voltage utilisation, modulation margin, and high-voltage machine capability as explicit system-level considerations, which are appropriate for the scope of this project and will be examined in later phases.

---

## 3. Boundaries and Deferred Decisions

The architectural positioning documented here is made strictly at the system level.

Detailed design aspects—including, but not limited to:

- inverter topology selection,
- semiconductor device choice and switching-frequency trade-offs,
- electric machine selection and electrical interface matching,
- thermal limits and cooling strategy definition,
- detailed efficiency optimisation,

are intentionally deferred to subsequent project phases, where sufficient modelling fidelity and design constraints become available.

---

## 4. Summary

This document records the single system-level architectural trade-off addressed during Phase 1 of the project:  
the positioning of a **direct DC/AC drive architecture** relative to a DC/DC-based alternative.

By resolving this trade-off at an appropriate level of abstraction, Phase 1 establishes a clear and consistent system baseline while avoiding premature fixation of implementation details.  
The resulting architectural context provides a stable foundation for modelling, power-stage reasoning, and control development in later phases.
