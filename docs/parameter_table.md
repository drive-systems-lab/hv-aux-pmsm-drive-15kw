# Parameter Table – 15 kW HV Auxiliary PMSM Drive (800 V Platform)

> Initial draft – parameters will be refined after architecture and modelling work during Phase 1.  
> Values are mostly placeholders/TBD at this stage; focus is on **parameter structure** rather than exact numbers.

---

## 1. System-Level Parameters

| Item                    | Symbol   | Value | Unit | Notes                                  |
|-------------------------|----------|-------|------|----------------------------------------|
| DC Bus Nominal Voltage  | U_dc,nom | 800   | V    | 800 V EV HV platform (nominal)         |
| DC Bus Operating Range  | U_dc     | TBD   | V    | Min / max to be confirmed              |
| Continuous Power Rating | P_cont   | 15    | kW   | As per project definition              |
| Overload Capability     | P_ovld   | TBD   | kW   | Short-time overload (e.g. 10 s)        |
| Cooling Method          | –        | TBD   | –    | Oil / water cooling to be confirmed    |
| Ambient Temp Range      | T_amb    | TBD   | °C   | Vehicle auxiliary bay environment      |

---

## 2. PMSM Machine Parameters

| Item                       | Symbol  | Value | Unit  | Notes |
|----------------------------|---------|-------|-------|-------|
| Rated Speed                | n_n     | TBD   | rpm   | Nominal operating point (datasheet) |
| Base Speed                 | n_base  | TBD   | rpm   | Upper limit of constant-torque region (voltage-limited, model-dependent) |
| Maximum Speed              | n_max   | TBD   | rpm   | min(mechanical limit, FW capability) |
| Rated Torque               | T_n     | TBD   | N·m   | Continuous torque capability (datasheet) |
| Peak Torque (short-time)   | T_peak  | TBD   | N·m   | Short-time overload capability (thermal + inverter limited) |
| Pole Pairs                 | p       | TBD   | –     | Datasheet value |
| Rated Line-to-Line Voltage | U_LL,n  | TBD   | V RMS | Datasheet value |
| Rated Phase Current        | I_ph,n  | TBD   | A RMS | Continuous RMS current at rated torque (datasheet) |
| Maximum Phase Current      | I_ph,max| TBD   | A RMS | System current limit (min of motor & inverter limits) |
| Rotor Inertia              | J       | TBD   | kg·m² | Required for mechanical model and speed-loop design |
| Cooling Type               | –       | TBD   | –     | Oil / water cooling (system TBD) |

---

## 3. Inverter Parameters

| Item                       | Symbol   | Value | Unit  | Notes                                                                 |
|----------------------------|----------|-------|-------|-----------------------------------------------------------------------|
| Topology                   | –        | 2L    | –     | 3-phase 2-level VSI (initial design assumption)                       |
| Device Type                | –        | TBD   | –     | SiC / IGBT under evaluation (to balance cost / loss / EMI)            |
| Rated Line Current         | I_line,n | TBD   | A RMS | Continuous line current at 15 kW and nominal DC bus                   |
| Switching Frequency        | f_sw     | TBD   | kHz   | Design variable – constrained by losses, EMI and control bandwidth    |
| DC Link Capacitance        | C_dc     | TBD   | µF    | To be sized from DC-ripple and transient ride-through requirements    |
| Allowed DC Voltage Ripple  | ΔU_dc    | TBD   | %     | System-level constraint – peak-to-peak, relative to U_dc,nom          |
| Inverter Efficiency Target | η_inv    | TBD   | %     | Target efficiency at nominal operating point (system requirement, TBD)|

---

## 4. Control-Related Parameters

| Item                    | Symbol | Value | Unit | Notes                                                             |
|-------------------------|--------|-------|------|-------------------------------------------------------------------|
| Current Loop Bandwidth  | f_bw,i | TBD   | Hz   | To be designed from inverter + PMSM plant model                   |
| Speed Loop Bandwidth    | f_bw,ω | TBD   | Hz   | Typically 5–10× lower than current loop (final value to be tuned) |
| Current Sampling Period | T_s,i  | TBD   | s    | Tied to PWM period and DSP timing constraints                     |
| Speed Control Period    | T_s,ω  | TBD   | s    | Integer multiple of current loop sampling period                   |

---

## 5. Sensor & Interface Parameters

| Item                         | Symbol | Value | Unit | Notes                                                     |
|------------------------------|--------|-------|------|-----------------------------------------------------------|
| Resolver Type                | –      | TBD   | –    | Resolver feedback expected (AD2S1205-based front-end candidate) |
| Resolver Excitation Voltage  | U_exc  | TBD   | V    | As per resolver and excitation-driver datasheet           |
| DC Bus Voltage Sensing       | –      | TBD   | –    | Resistor divider + ADC; scaling and resolution to be defined |
| Phase Current Sensing        | –      | TBD   | –    | Phase-current measurement (shunt / Hall topology TBD)     |
| Inverter Temperature Sensing | –      | TBD   | –    | For thermal monitoring, derating and protection           |
| Communication Interface      | –      | TBD   | –    | CAN expected; final interface set to be confirmed         |

---

## 6. Open Points (Day 4)

- PMSM datasheet and exact ratings (torque, current, speed, voltage class) pending supplier confirmation.  
- Detailed PMSM model parameters (Rs, Ld/Lq, Ψf, losses) pending for Phase 2 modelling.  
- Semiconductor device selection (SiC vs IGBT), including voltage class & loss/EMI trade-offs, still open.  
- Thermal limits and cooling architecture (oil / water) to be confirmed with mechanical/vehicle team.  
- Control bandwidths and sampling periods to be set after small-signal modelling and plant identification.  
- Protection thresholds and derating strategy to be defined after thermal & electrical modelling.  
- Final DC bus operating range, sag tolerance and overload profile to be agreed with system requirements.

