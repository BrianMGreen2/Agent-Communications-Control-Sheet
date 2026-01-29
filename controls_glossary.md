# Controls Glossary — Agent Communications Guardrail

## Decision outcomes
- **ALLOW**: Proceed automatically.
- **HOLD**: Pause execution until required controls are satisfied (approval, preview confirmation, review queue).
- **BLOCK**: Stop execution. Only a break-glass override can proceed.

## Core governance controls
- **Blast radius**: scope of harm if wrong (recipient count, DLs, external domains, public links).
- **Recipient threshold**: configured limits that trigger safeguards.
- **Dual control**: two distinct authorized humans approve before execution.
- **Role-match approval**: approvers must match topic (HR/Legal/Security/Exec Comms).
- **Digital signature**: verifiable approval artifact tied to payload (who/what/when).
- **Step-up authentication**: extra verification for privileged actions.
- **Least privilege**: agents draft by default; privileged actions require explicit grants + policy clearance.
- **Fail-closed**: if checks can’t run, default to HOLD/BLOCK.
- **Policy-as-Code**: rules in versioned, testable YAML (or equivalent).
- **Policy Gate**: enforcement step that returns ALLOW/HOLD/BLOCK.

## Content & data protection controls
- **Sensitivity classification**: public/internal/confidential/restricted based on keywords, topics, DLP.
- **Topic classifier**: labels content HR/Legal/Security/M&A/etc.
- **Channel-topic constraint**: blocks topics in disallowed channels (e.g., termination via calendar invite).
- **DLP**: detects regulated/sensitive data in attachments/links (PHI/PCI/trade secrets).
- **Public link check**: prevents “anyone with link” sharing for sensitive docs.
- **External recipient control**: safeguards when any recipient is outside the org.

## Draft safety controls
- **Draft detection**: flags TODO/DRAFT/templates/test markers.
- **Rendered preview**: shows exact outgoing message + recipients + attachments.
- **Undo window**: delayed send to allow cancel.

## Critic & sanity checks
- **Critic model**: secondary model checking tone, finality, ambiguity, harm.
- **Semantic sanity check**: mismatch between intent and action.
- **Temporal consistency**: tone/action align with scheduling context.
- **Audience fit**: appropriate content for recipient group + channel.

## Evidence & auditability
- **Content hash**: proves what was evaluated without storing plaintext.
- **Decision trace**: which rules fired and why.
- **Immutable audit log**: append-only approvals, decisions, metadata.
- **Retention policy**: how long evidence is kept.
- **Replayability**: reconstruct why action was allowed/held/blocked.

## Break-glass override
- **Break-glass**: exceptional override with senior approvals + required ticket reference.
- **Compensating controls**: alerts, post-action review, time-limited permissions.
