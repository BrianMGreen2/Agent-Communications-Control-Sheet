# Controls Kit — Agent Communications Guardrail

This folder contains the **implementation-ready controls** that pair with the Policy-as-Code (PaC) rules in `policy/`.

Use this kit to quickly align cross-functional teams (Engineering, Security, Legal, HR, Exec Comms) on:
- what controls exist
- when they trigger
- what action is required
- what evidence/logs must be captured

## What’s in this folder

### One-page control sheet
File: `one_page_control_sheet.md`  
A compact table: **Rule | Trigger | Action | Owner | Evidence/Logs | Severity**

### Controls glossary
File: `controls_glossary.md`  
Shared definitions for terms like **blast radius**, **dual control**, **fail-closed**, **critic model**, and **break-glass**.

## How this maps to the policy

- Policy rules: `policy/agent_comms_guardrail.yaml`
- Canonical schema: `policy/event_schema.yaml`

Each control references a rule ID (e.g., `R4.high_risk_sensitivity_lock`).

## Recommended adoption path

Phase 1 (fast): recipient thresholds, sensitivity lock + dual control, DLP, audit logs  
Phase 2: staged sending, channel-topic constraints, external controls, fail-closed everywhere  
Phase 3: critic model + semantic sanity + anomaly detection
