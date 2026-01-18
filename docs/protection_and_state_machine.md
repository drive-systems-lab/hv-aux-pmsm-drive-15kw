# Protection and State Machine — System-Level Perspective

## 1. Purpose and Positioning

This document provides a **system-level perspective on protection** within the Phase 2 scope of the project.  
Its purpose is to articulate how protection should be **understood and reasoned about at the system level**, rather than to define protection mechanisms, architectures, or behaviours.

The focus is on establishing a clear **engineering viewpoint** on protection as a system concern, including its conceptual relationship with system operating states, while deliberately avoiding design or implementation commitments.

This document is **distinct from the fault-domain reasoning boundaries** discussed in `power_stage_design.md`.  
While the latter describes the limits of validity of nominal power-stage reasoning under abnormal conditions, this document addresses how protection is positioned and interpreted at the system level from an engineering judgement perspective.

---

## 2. System-Level vs Device-Level Protection

Protection considerations in power electronic systems naturally span multiple layers.  
At Phase 2, it is important to explicitly distinguish between **system-level protection** and **device-level protection**, as they serve different engineering purposes.

### 2.1 Device-Level Protection

Device-level protection focuses on the immediate safeguarding of individual components, such as power semiconductors or passive elements.  
It is typically characterised by:

- Localised scope, acting on a single component or subassembly  
- Fast response requirements  
- Limited or no awareness of overall system operating context  

Device-level protection is essential for component survivability but does not, by itself, define system behaviour.

### 2.2 System-Level Protection

System-level protection addresses protection from the perspective of the **overall system behaviour and operating intent**.  
Its key characteristics include:

- A global viewpoint across multiple subsystems  
- Consideration of operating modes or states  
- Alignment with system-level objectives such as controlled shutdown, degradation, or recovery  

At Phase 2, system-level protection is treated as a **conceptual engineering concern**, not as a defined implementation or architecture.

---

## 3. Engineering Interpretation of Fast and Slow Faults

Faults and abnormal conditions are often informally described as *fast* or *slow*.  
Within this document, these terms are used **only in an engineering interpretation sense**, rather than as formal classifications.

### 3.1 Fast Faults

Fast faults are understood as conditions that demand **immediate interruption of energy flow** to prevent damage or unsafe operation.  
From a system engineering perspective, they imply:

- Extremely high urgency  
- Limited opportunity for system-level decision-making  
- Priority given to immediate protective action  

No assumptions are made at this stage regarding detection mechanisms, response timing, or implementation strategies.

### 3.2 Slow Faults

Slow faults are understood as conditions that allow **system-level reasoning and response** before irreversible harm occurs.  
From an engineering viewpoint, they imply:

- Lower immediacy compared to fast faults  
- Potential interaction with operating modes or states  
- Opportunity for controlled degradation, derating, or orderly shutdown  

Again, this interpretation is qualitative and conceptual, without defining how such faults are detected or handled in practice.

---

## 4. Protection and System Operating States

Protection cannot be meaningfully interpreted without reference to **system operating states**.  
A system is not always in a single, uniform mode of operation, and the implications of protection actions depend on the current state.

At this stage, the relationship between protection and system states is treated conceptually:

- Protection relevance and interpretation may differ between normal operation, degraded operation, or shutdown conditions  
- System-level protection reasoning implicitly assumes awareness of the system’s current operating context  
- State awareness provides a framework for understanding why identical fault conditions may warrant different system-level responses  

This document does **not** define a state machine, state transitions, or behavioural logic.  
It establishes only the conceptual linkage between protection considerations and system operating states.

---

## 5. Phase 2 Scope Boundary

To maintain Phase 2 integrity, the following topics are explicitly outside the scope of this document:

- Protection circuit topology or component selection  
- Fault detection algorithms or sensing mechanisms  
- Timing constraints, thresholds, delays, or coordination logic  
- State transition conditions or detailed state machine definitions  
- Safety standards, certification, or compliance analysis  

These topics are intentionally deferred to later phases where quantitative models, detailed architectures, and validation context are available.

At Phase 2, this document functions solely as a **system-level judgement reference**, ensuring that protection-related discussions are framed with appropriate engineering awareness without constraining future design decisions.
