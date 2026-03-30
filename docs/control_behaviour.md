# Control Behaviour

## Scope and Boundary

This document records behaviour-oriented observations on the frozen Phase-4 closed-loop baseline.

The present material is intended to support interpretable closed-loop behavioural evidence within the current structural baseline, with emphasis on engineering readability, bounded response, and cross-signal interpretability.

The observations recorded here should not be interpreted as tuned-performance validation, implementation-frequency commitment, hardware-facing validation, or robustness-margin conclusion.

---

## Behaviour-Exploration Working Values

At the present stage, selected simulation-facing working settings may be adopted where needed to support readable and interpretable behavioural observation on the frozen structural baseline.

Such settings should be understood as behaviour-exploration working conditions used for structural closed-loop assessment, rather than final target-machine datasheet confirmation, implementation-level commitments, or tuned-performance outcomes.

Where needed, case-specific operating conditions and excitation settings are stated locally within each behaviour section.

---

## Current Step Response

### Case Setup

For the present current-step case, the working setup is based on:

- `omega_e_input = 300 rad/s`
- `i_q_ref` step excitation from `0 A` to `10 A`
- `Ts_ctrl = 1 / 5000 s`
- `f_sw = 5 kHz`

A bounded `i_q_ref` step was applied on the frozen Phase-4 closed-loop baseline while `i_d_ref` was held at zero and `omega_e_input` was kept constant.

The purpose of the present case is to establish an initial readable current-step behavioural view for the closed-loop baseline and to assess whether the resulting response remains bounded and interpretable under the present excitation.

### Working Parameters

The present current-step case uses the following controller working values, adopted here as behaviour-exploration settings rather than tuned-performance outcomes:

- `Kp_id = 5`
- `Ki_id = 100`
- `Kp_iq = 5`
- `Ki_iq = 100`

### Main View

![Current Step Response — Main View](../images/behaviour/current_step_main.png)

The main view is used to assess whether `i_q_fb` follows `i_q_ref` in a readable and bounded manner under the present closed-loop baseline.

At the present stage, the emphasis is placed on qualitative tracking readability and bounded response formation, rather than tuned dynamic-performance validation.

### Supporting View

![Current Step Response — Supporting View](../images/behaviour/current_step_aux.png)

The supporting view is used to complement the main current-tracking figure by observing:

- limited and interpretable d-axis response through `i_d_fb`
- control-side command behaviour through `v_d_ref` and `v_q_ref`

This supporting material is intended to improve behavioural interpretability of the current-step case, rather than to claim complete decoupling or tuned controller quality.