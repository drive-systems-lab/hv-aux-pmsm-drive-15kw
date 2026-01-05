# Parameter Table – 15 kW HV Auxiliary PMSM Drive (800 V Platform)

>**Status (Phase 1 – Baseline):**  
> This table establishes the **system-level parameter baseline** for the 15 kW high-voltage auxiliary PMSM drive at Phase 1.  
> It records architectural anchors and parameter structure, while detailed component specifications, control tuning, and implementation-level parameters are intentionally deferred to subsequent phases.

---

## 1. System-Level Parameters

| Item                   | Symbol   | Value | Unit | Notes |
|------------------------|----------|-------|------|-------|
| DC Bus Nominal Voltage | U_dc,nom | 800   | V    | Nominal HV DC bus anchor for 800 V EV platforms |
| DC Bus Operating Range | U_dc     | TBD   | V    | External operating window (min/max), treated as a system constraint |
| System Power Class     | P_sys    | 15    | kW   | System-level power class anchor (not a guaranteed continuous rating) |
| Overload Capability    | P_ovld   | TBD   | kW   | Short-time overload capability/profile, if applicable |
| Cooling Method         | –        | TBD   | –    | Liquid-cooled auxiliary drive; coolant type TBD |
| Ambient Temp Range     | T_amb    | TBD   | °C   | Installation environment / ambient envelope – TBD |

--- 

## 2. PMSM Machine Parameters

| Item                       | Symbol  | Value | Unit  | Notes |
|----------------------------|---------|-------|-------|-------|
| Rated Speed                | n_n     | TBD   | rpm   | Nominal operating point (datasheet) |
| Base Speed                 | n_base  | TBD   | rpm   | Upper limit of constant-torque region (voltage-limited, model-dependent) |
| Maximum Speed              | n_max   | TBD   | rpm   | min(mechanical limit, voltage limit under the selected operating strategy)|
| Rated Torque               | T_n     | TBD   | N·m   | Continuous torque capability (datasheet) |
| Peak Torque (short-time)   | T_peak  | TBD   | N·m   | Short-time overload capability (thermal + inverter limited) |
| Pole Pairs                 | p       | TBD   | –     | Datasheet value |
| Rated Line-to-Line Voltage | U_LL,n  | TBD   | V RMS | Datasheet value |
| Rated Phase Current        | I_ph,n  | TBD   | A RMS | Continuous RMS current at rated torque (datasheet) |
| Maximum Phase Current      | I_ph,max| TBD   | A RMS | System current limit (min of motor & inverter limits) |
| Rotor Inertia              | J       | TBD   | kg·m² | Required for mechanical modelling and potential outer-loop or supervisory control design |
| Cooling Type               | –       | TBD   | –     | Liquid-cooled motor; oil/water details TBD  |

---

## 3. Inverter Parameters

| Item                         | Symbol   | Value | Unit  | Notes |
|------------------------------|----------|-------|-------|-------|
| Topology                     | –        | 2L    | –     | 3-phase 2-level VSI (initial design assumption) |
| Device Type                  | –        | TBD   | –     | SiC / IGBT under evaluation (to balance cost / loss / EMI) |
| Rated Line Current           | I_line,n | TBD   | A RMS | Line current corresponding to the 15 kW power class at nominal DC bus |
| Switching Frequency          | f_sw     | TBD   | kHz   | Design variable – constrained by losses, EMI and control bandwidth |
| DC Link Capacitance          | C_dc     | TBD   | µF    | To be sized from DC-ripple and transient ride-through requirements |
| Allowed DC Voltage Ripple    | ΔU_dc    | TBD   | %     | System-level constraint – peak-to-peak, relative to U_dc,nom |
| Inverter Efficiency Reference| η_inv    | TBD   | %     | System-level efficiency reference placeholder; final value TBD |

---

## 4. Control-Related Parameters

| Item                         | Symbol        | Value | Unit | Notes |
|------------------------------|---------------|-------|------|-------|
| Current Control Bandwidth    | f_i_bw        | TBD   | Hz   | Inner current loop bandwidth; to be designed in later phases |
| Current Control Period       | T_i           | TBD   | s    | Control update period for current regulation |
| Modulation Scheme            | –             | TBD   | –    | SVPWM or equivalent; to be defined |
| PWM Carrier Frequency        | f_pwm         | TBD   | kHz   | To be selected based on device loss/EMI trade-offs; typically aligned with inverter switching frequency in later phases.|
| Outer-Loop Bandwidth         | f_ol_bw       | TBD   | Hz   | Application-dependent outer-loop or supervision bandwidth (if applicable) |
| Outer-Loop Update Period     | T_ol           | TBD   | s    | Update period for outer-loop or operating-point supervision (if applicable) |

*Note: Outer-loop regulation is application-dependent and is not assumed as part of the Phase 1 baseline.*

---

## 5. Sensor & Interface Parameters

| Item                         | Symbol | Value | Unit | Notes |
|------------------------------|--------|-------|------|-------|
| Resolver Type                | –      | TBD   | –    | Resolver feedback expected (AD2S1205-based front-end candidate) |
| Resolver Excitation Voltage  | U_exc  | TBD   | V    | As per resolver and excitation-driver datasheet |
| DC Bus Voltage Sensing       | –      | TBD   | –    | Resistor divider + ADC; scaling and resolution to be defined |
| Phase Current Sensing        | –      | TBD   | –    | Phase-current measurement (shunt / Hall topology TBD) |
| Inverter Temperature Sensing | –      | TBD   | –    | For thermal monitoring, derating and protection |
| Communication Interface      | –      | TBD   | –    | CAN expected; final interface set to be confirmed |

---

## 6. Open Points (Phase 1 Carry-Over)

- PMSM datasheet and exact ratings (torque, current, speed, voltage class) pending supplier confirmation.  
- Detailed PMSM model parameters (Rs, Ld/Lq, Ψf, losses) pending for Phase 2 modelling.  
- Semiconductor device selection (SiC vs IGBT), including voltage class & loss/EMI trade-offs, still open.  
- Thermal limits and cooling architecture (oil / water) to be confirmed with mechanical/vehicle team.  
- Control bandwidths and sampling periods to be set after small-signal modelling and plant identification.  
- Protection thresholds and derating strategy to be defined after thermal & electrical modelling.  
- Final DC bus operating range, sag tolerance and overload profile to be agreed with system requirements.
