# System Requirements – 15 kW HV Auxiliary PMSM Drive (800 V Platform)

Draft system-level requirements for a 15 kW high-voltage auxiliary PMSM drive operating on an 800 V EV platform.

> **Status (Day 3, Phase 1):**\
> Initial structure only. All items are placeholders and will be refined as architecture, modelling and power-stage design progress through Phase 1.

***

## 1. Application and Use Case (Draft)

*   **Application type:**\
    EV auxiliary drive (oil pump / coolant pump / similar loads).

*   **Main objectives:**
    *   Stable and reliable operation on an 800 V HV DC bus.
    *   Adequate dynamic response for typical auxiliary-load transients.
    *   Reasonable efficiency under representative duty cycles.

*   **Environment (initial assumption):**
    *   Automotive HV DC bus environment.
    *   Under-hood or near-battery-compartment installation (exact conditions TBD).

Further details (duty cycles, thermal environment, mission profiles) will be added as the overall system architecture stabilises.

***

## 2. Electrical Ratings and Operating Conditions (Draft)

*   **Rated power:** 15 kW nominal (continuous).\
    Short-term overload capability TBD.

*   **DC bus:** 800 V nominal HV DC bus.\
    Operating range and derating behaviour TBD.

*   **Machine speed range:**\
    Mechanical limits, base speed and operating envelope TBD.

*   **Phase current:**\
    Continuous and peak limits TBD.

*   **Supply characteristics:**\
    DC bus quality, transient behaviour and permissible variations TBD.

*   **Efficiency targets:**\
    Overall and partial-load efficiency requirements TBD.

Exact numerical values will be established following initial power-stage sizing and architecture trade-off activities.

***

## 3. Electrical Interfaces (Initial Outline)

*   **DC side:**
    *   Connection to the 800 V HV DC bus (connector / busbar concept TBD).
    *   Pre-charge and inrush-current handling concept TBD.

*   **AC side:**
    *   Three-phase PMSM connection.
    *   Cable length, EMC considerations and grounding concept TBD.

*   **Grounding / shielding:**
    *   Protective earth (PE) and shield-termination strategy TBD.

More detailed interface diagrams will be added during the architecture definition phase.

***

## 4. Mechanical and Thermal Interfaces (Initial Outline)

*   **Machine:**\
    Three-phase PMSM, liquid-cooled (coolant type TBD).

*   **Mounting:**\
    Mechanical constraints for inverter and motor mounting TBD.

*   **Cooling:**
    *   Coolant type TBD.
    *   Approximate flow rate and inlet temperature range TBD.

*   **Vibration / shock:**\
    Requirements TBD; quantitative limits will be added once mechanical arrangements are confirmed.

***

## 5. Control, Monitoring and Communication (Draft)

*   **Control concept:**\
    High-level vector-control framework (specific algorithms and modulation strategies TBD).

*   **Feedback signals (initial list):**
    *   Phase currents
    *   DC bus voltage
    *   Rotor position / speed (sensor type TBD)

*   **Monitoring / protection signals:**\
    Preliminary list TBD.

*   **Communication interface:**\
    Interface type TBD (CAN / UART / SPI / other options under consideration).

A detailed control and communication specification will be developed in a dedicated architecture document.

***

## 6. Protection, Safety and Standards (Draft)

*   **Electrical protection:**\
    Over-current, over-voltage and ground-fault concepts TBD.

*   **Thermal protection:**\
    Inverter and machine temperature limits TBD.

*   **Functional safety / compliance:**\
    Applicable standards and interactions with system-level safety functions TBD.

This section will be refined as target application details and customer requirements become clearer.

***

## 7. Open Points and To-Be-Defined Items

The following elements are intentionally left open at this stage and will be refined during Phase 1:

*   Final torque–speed envelope and operating points.
*   Exact DC bus operating window and potential derating rules.
*   Cooling concept and thermal-limit definitions.
*   Choice of rotor-position sensing method.
*   Final communication interface and message definitions.
*   Detailed protection thresholds and coordination with system-level safety.
*   Any customer-specific mechanical, electrical or packaging constraints.

This list will evolve as further architecture, modelling and design work progresses.
