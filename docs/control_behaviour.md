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

The main view provides the full-window overview of the present current-step case and is used to assess whether `i_q_fb` follows `i_q_ref` in a readable and bounded manner on the frozen Phase-4 closed-loop baseline.

At the present stage, readable tracking is interpreted qualitatively through observable response direction, bounded response development, and interpretable approach toward the commanded current level, rather than through tuned ripple suppression or optimised dynamic-performance closure.


### Transient View

![Current Step Response — Transient View](../images/behaviour/current_step_transient.png)

The transient view complements the main overview by examining the local response formation around the applied `i_q_ref` step.

Within the present behavioural-observation boundary, this figure is used to improve visibility of the step-response development, including response onset, approach toward the commanded level, and overall transient readability on the frozen closed-loop baseline.

A locally stepped or ripple-like response appearance is visible in the present transient view. At the current stage, this appearance is retained as part of the observable closed-loop behaviour and does not prevent qualitative interpretation of response direction, bounded transient formation, or interpretable approach toward the commanded current level. It is not interpreted here as a switching-device-level or implementation-level conclusion.

The present view is intended to support qualitative transient interpretation only, rather than to claim tuned settling performance, optimised controller quality, or final implementation-level dynamic behaviour.

### Supporting View

![Current Step Response — Supporting View](../images/behaviour/current_step_aux.png)

The supporting view complements the main and transient views by observing:

- limited and interpretable d-axis response through `i_d_fb`
- control-side command behaviour through `v_d_ref` and `v_q_ref`

This supporting material is intended to improve cross-axis and control-side interpretability of the present current-step case, rather than to claim complete decoupling, tuned controller quality, or implementation-facing control maturity.