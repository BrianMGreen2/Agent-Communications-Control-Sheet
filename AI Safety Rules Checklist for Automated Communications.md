## AI Safety Rules Checklist for Automated Communications

### 1) Sensitivity & Content Classification

* ☐ **High-risk keyword/phrase detection** (termination, layoffs, fired, legal hold, acquisition, breach, “Project Dawn,” etc.)
* ☐ **Topic classifier** for HR / Legal / Security / Finance / Executive Comms categories (not just keywords)
+ ☐ **Severity scoring** (Low / Medium / High / Critical) based on topic + audience + channel
+ ☐ **Auto-lock “Send/Invite”** when severity ≥ High until additional controls are satisfied
+ ☐ **Redaction rules** for sensitive terms (e.g., replace with neutral placeholders in drafts)

### 2) Recipient Threshold & Blast-Radius Controls

* ☐ **Recipient count thresholds** (e.g., >50 triggers “mass-send” mode)
* ☐ **Distribution list detection** (flags DLs, aliases, org-wide groups, external domains)
* ☐ **Progressive send** (staged rollout: 5 → 25 → 50 → 250 → 1,000 with checkpoint approvals)
* ☐ **Quarantine mode** for large sends: message is generated but held for review
* ☐ **Rate limits** on automated comms per hour/day per agent and per channel

### 3) Approval, Signatures & Dual-Control (“Two Keys”)

* ☐ **Second human approval required** for any High/Critical message or large recipient count
* ☐ **Role-based approvers** (HR for HR topics, Legal for legal topics, Comms for public messaging)
* ☐ **Digital signature / cryptographic attestation** for final send actions (who approved what and when)
* ☐ **No silent overrides**: approvals must be explicit, logged, and non-replayable

### 4) Policy Alignment & Allowed-Action Rules

* ☐ **Safe Communication policy as code** (channels allowed, topics allowed, audiences allowed)
* ☐ **Channel-topic constraints** (e.g., HR/termination language cannot be sent via calendar invites)
* ☐ **External sharing rules** (block if any recipient is outside company for sensitive topics)
* ☐ **Attachment policy checks** (confidential docs blocked from public-facing invites or broad lists)
* ☐ **Time-of-send restrictions** for sensitive content (e.g., only during staffed hours)

### 5) Semantic Sanity & Tone Checks (Critic Model)

* ☐ **Tone/intent classifier** (finality, threats, emotionally charged language, sarcasm)
* ☐ **Temporal consistency check** (tone vs timing vs event schedule; “you’re fired” for a future meeting = flag)
* ☐ **Audience-fit check** (language appropriate for the recipient group and context)
* ☐ **Ambiguity detector** (flags unclear messages that could be misinterpreted at scale)

### 6) Draft vs Final Safeguards

* ☐ **Draft detection** (placeholders, TODOs, template markers, “test,” “sample,” “ignore”)
* ☐ **“Dry run” preview** showing recipients, subject, attachments, and exact rendered text
* ☐ **Forced confirmation prompt** that repeats the blast radius (e.g., “5,000 recipients”)
* ☐ **Send delay window** (e.g., 2–5 minute “undo” timer for any high-impact action)

### 7) Identity, Permissions & Least Privilege

* ☐ **Agent permissions scoped** to minimum (read-only by default; send/invite is privileged)
* ☐ **Separation of duties**: agent can draft but cannot send without approval token
* ☐ **Just-in-time access** (time-limited permissions for specific tasks)
* ☐ **MFA / step-up authentication** for privileged actions

### 8) Monitoring, Auditability & Forensics

* ☐ **Immutable audit logs** of prompts, drafts, policy checks, approvals, recipients, and timestamps
* ☐ **Real-time anomaly detection** (sudden surge in recipients, unusual topics, new domains)
* ☐ **Incident replay capability** (reconstruct exactly why the system allowed/blocked)
* ☐ **Automated alerts** to Security/Comms when high-risk rules trigger

### 9) Kill Switches & Safe Failure Modes

* ☐ **Emergency stop** to disable sending/inviting across all agents instantly
* ☐ **Fail-closed behavior**: if policy engine or critic model is unavailable, block sends
* ☐ **Quarantine queue** for anything the system can’t confidently classify
* ☐ **Rollback/recall procedures** (where possible) plus immediate comms escalation path

### 10) Testing, Red-Teaming & Change Control

* ☐ **Pre-deployment simulations** using “disaster scenarios” (mass send, leaked doc, wrong audience)
* ☐ **Regular red-team drills** focused on comms harm and brand risk
* ☐ **Policy versioning** (every ruleset change is reviewed, tested, and signed)
* ☐ **Post-incident updates**: new rules added after near-misses and failures

(c)2026, Agentic-Village.net d/b/a Health-Vision.AI, LLC
