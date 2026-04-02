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

The purpose of the present case is to establish an initial readable current-step behavioural view for the closed-loop baseline and to assess whether the resulting response remains bounded and interpretable under the present excitation. At the present stage, the case is used to support qualitative behavioural observation of the frozen baseline, rather than controller-optimisation closure or final dynamic-performance judgement.

### Working Parameters

The present current-step case uses the following controller working values, adopted here as behaviour-exploration settings rather than tuned-performance outcomes:

- `Kp_id = 5`
- `Ki_id = 100`
- `Kp_iq = 5`
- `Ki_iq = 100`

### Main View

![Current Step Response — Main View](../images/behaviour/current_step_main.png)

The main view provides the full-window overview of the present current-step case and is used to assess whether `i_q_fb` follows `i_q_ref` in a readable and bounded manner on the frozen Phase-4 closed-loop baseline.

At the present stage, readable tracking is interpreted qualitatively through observable response direction, bounded response development, and interpretable approach toward the commanded current level.

### Transient View

![Current Step Response — Transient View](../images/behaviour/current_step_transient.png)

The transient view complements the main overview by examining the local response formation around the applied `i_q_ref` step.

Within the present behavioural-observation boundary, this figure is used to improve visibility of the step-response development, including response onset, approach toward the commanded level, and overall transient readability on the frozen closed-loop baseline.

### Supporting View

![Current Step Response — Supporting View](../images/behaviour/current_step_aux.png)

The supporting view complements the main and transient views by observing:

- limited and interpretable d-axis response under the applied q-axis step through `i_d_fb`
- control-side response through `v_d_ref` and `v_q_ref`

This supporting material is intended to improve cross-axis and control-side interpretability of the present current-step case.

---

## Load Disturbance

### Case Setup

For the present load-disturbance case, the working setup is based on:

- `i_d_ref = 0 A`
- `i_q_ref = 10 A`
- `omega_e_input` step perturbation from `300 rad/s` to `350 rad/s`
- `Ts_ctrl = 1 / 5000 s`
- `f_sw = 5 kHz`

In the present case, a bounded perturbation was applied to `omega_e_input` on the frozen Phase-4 closed-loop baseline while the current-reference operating point was held constant.

Within the present Phase-4 interpretation boundary, this perturbation is used as a representative operating-condition disturbance and as a load-side surrogate within the existing electrical-only closed-loop context.

The purpose of the present case is not to establish a full mechanical-load validation or a broader electro-mechanical disturbance study. Instead, it is used to examine whether the frozen closed-loop baseline retains readable and bounded current regulation under the applied operating-condition change, and whether the associated controller-side reaction remains interpretable within the present modelling boundary.

### Main View

![Load Disturbance — Main View](../images/behaviour/load_disturbance_main.png)

The main view records the applied `omega_e_input` perturbation together with the resulting `i_q_fb` behaviour on the frozen Phase-4 closed-loop baseline.

In the present case, the applied operating-condition disturbance does not produce a large visible deviation in `i_q_fb`. Within the present current-control context, this is interpreted as an indication that the closed-loop baseline retains bounded and readable current regulation under the tested perturbation condition.

Accordingly, the present figure is used primarily to show that:

- a representative operating-condition disturbance is clearly introduced
- `i_q_fb` remains bounded and readable on the frozen closed-loop baseline
- the closed-loop baseline retains interpretable current regulation within the adopted electrical-only Phase-4 boundary

### Supporting View

![Load Disturbance — Supporting View](../images/behaviour/load_disturbance_aux.png)

The supporting view complements the main view by observing:

- limited cross-axis response through `i_d_fb`
- controller-side command adjustment through `v_d_ref` and `v_q_ref`

In the present case, the more direct evidence of disturbance handling is observed on the controller side rather than through a large visible excursion in `i_q_fb`.

The supporting view is therefore used to show that:

- `i_d_fb` exhibits only limited and interpretable cross-axis response under the applied operating-condition perturbation
- `v_q_ref` and `v_d_ref` exhibit coherent controller-side reaction following the disturbance
- the retained current regulation seen in the main view is supported by readable control-side adjustment within the present electrical-only modelling boundary

---

## DC-Link Disturbance

### Case Setup

For the present DC-link-disturbance case, the working setup is based on:

- `i_d_ref = 0 A`
- `i_q_ref = 10 A`
- `omega_e_input = 300 rad/s`
- `Ts_ctrl = 1 / 5000 s`
- `f_sw = 5 kHz`

In the present case, bounded DC-link variation was introduced within the existing inverter-side source/DC-link context on the frozen Phase-4 closed-loop baseline while the current-reference operating point was held constant.

For the present behaviour-exploration case, the source/DC-link-side working settings were adjusted as follows:

- Equivalent Source Impedance: from `0.01 ohm` to `0.2 ohm + 1 mH`
- DC-Link Capacitor: from `1 mF` to `10 uF`

Within the present Phase-4 interpretation boundary, these settings are used only as scenario-conditioning values to establish a bounded and readable DC-link-disturbance case.

The purpose of the present case is not to establish a broader DC-source dynamics study, DC-bus design optimisation exercise, or robustness-margin conclusion. Instead, it is used to examine whether the frozen closed-loop baseline retains readable and bounded current regulation under bounded DC-link variation, and whether the associated control-side command behaviour remains interpretable within the present modelling boundary.

### Main View

![DC-Link Disturbance — Main View](../images/behaviour/dc_link_disturbance_main.png)

The main view records the bounded `u_dc` variation together with the resulting `i_q_fb` behaviour on the frozen Phase-4 closed-loop baseline.

In the present case, the applied source/DC-link-side conditioning produces clearly visible DC-link variation while `i_q_fb` remains bounded and readable around the established current-reference operating point.

Accordingly, the present figure is used primarily to show that:

- bounded DC-link variation is clearly introduced
- `i_q_fb` remains bounded and readable on the frozen closed-loop baseline
- the closed-loop baseline retains interpretable current regulation within the adopted electrical current-control Phase-4 boundary

### Supporting View

![DC-Link Disturbance — Supporting View](../images/behaviour/dc_link_disturbance_aux.png)

The supporting view complements the main view by observing:

- control-side command behaviour through `v_d_ref` and `v_q_ref`

In the present case, the more direct supporting evidence for DC-link-disturbance interpretation is observed on the command side rather than through a large breakdown of current regulation.

The supporting view is therefore used to show that:

- `v_q_ref` and `v_d_ref` remain readable under the applied bounded DC-link variation
- control-side command behaviour remains interpretable within the present electrical current-control context
- the retained current regulation seen in the main view is supported by readable command-side adjustment within the existing Phase-4 modelling boundary