# Evidence and Evaluation

Use this reference to make claims traceable, establish a baseline when metrics are missing, and test whether a system is both more efficient and user-friendly.

## Table of contents

1. Evidence contract
2. Evidence Ledger
3. Lightweight baseline sprint
4. Metric tree
5. User-friendly evaluation
6. Efficiency success rule
7. Evaluation kit
8. Readiness and decision rules

## 1. Evidence contract

Use evidence levels to limit the strength of claims:

| Level | Basis | Allowed conclusion |
|---|---|---|
| E0 Stated | Artifact, stakeholder description, unverified claim | Opportunity or risk hypothesis |
| E1 Walked through | Reconstructed task, expert walkthrough, analogue | Directional friction and testable design hypothesis |
| E2 Observed | Small set of real users, tasks, or cases | Initial behavioral pattern; not population prevalence |
| E3 Measured | Stable analytics, operational, research, cost, or quality data | Quantified baseline and associations within data limits |
| E4 Tested | Comparative prototype, pilot, quasi-experiment, or experiment | Evidence of improvement and, when design permits, causality |

Treat level as evidence for a specific claim, not a grade for the whole project. One project may have E3 task-time evidence and only E0 trust assumptions.

Mark claim type separately:

- **Observed fact:** directly present in a source, behavior, or measurement.
- **Reported fact:** supplied by a participant or stakeholder.
- **Inference:** reasoned from evidence.
- **Assumption:** chosen so work can continue.
- **Target:** desired future value or threshold.
- **Unknown:** material gap.

Do not convert a target, estimate, or directional reduction into a measured result.

## 2. Evidence Ledger

Use stable claim IDs so later decisions can cite evidence without repeating it.

| Claim ID | Claim | Type | Source | Level | Confidence | Decision affected | What could disprove it | Next evidence action |
|---|---|---|---|---|---|---|---|---|
| C-01 | Agents re-enter account context in two tools | Observed fact | 4 task observations | E2 | Medium | Integrate account context | Logging shows rare occurrence | Inspect 20 recent cases |

Rules:

- Include only decision-relevant claims.
- Link every major design choice and expected benefit to at least one claim.
- Label conflicting evidence instead of averaging it away.
- Record evidence date, segment, sample, and material limitations when available.
- State when a source is a stakeholder belief rather than user or operational evidence.

## 3. Lightweight baseline sprint

Do not require mature analytics. Establish the smallest baseline that can guide the next decision.

### Minimum baseline

Capture:

1. A current, workaround, substitute, or analogous task chain.
2. At least one outcome or quality signal.
3. At least one user-effort or efficiency signal.
4. The most consequential failure and recovery path.

### Low-cost sequence

1. **Artifact review:** inspect screenshots, SOPs, tickets, forms, logs, spreadsheets, or prior research.
2. **Task walkthrough:** ask someone to narrate the last real case step by step; count decisions, inputs, switches, handoffs, waits, and restarts.
3. **Small observation:** when practical, observe a few representative cases and record time, success, errors, assistance, and perceived difficulty.
4. **Data request:** identify which existing analytics or operations fields could confirm prevalence or cost.

Use small observation to find problems and refine hypotheses, not to claim population precision. For 0-to-1 systems, measure the substitute behavior or compare competing concepts.

### Baseline record

```text
Task and segment:
Trigger and desired outcome:
Current/analogue chain:
Observed sample and context:
Outcome/quality signal:
Effort/efficiency signal:
Failure and recovery:
Evidence level and limitations:
```

## 4. Metric tree

Start with the user outcome. Choose a small set of metrics that can change a decision.

### Outcome and quality

- Task completion or verified success
- Accuracy, acceptance, defect, or rework rate
- Outcome latency or service-level attainment
- Completeness, consistency, or domain-specific quality

### Efficiency

- Active task time and total elapsed time
- User inputs, explicit decisions, prompts, or manual steps
- Context transfers, app switches, handoffs, and waits
- Recovery time and work lost after failure
- Human review or escalation time
- Financial, model, tool, or operational cost per successful outcome

### Experience guardrails

- Perceived ease or single-task ease
- Cognitive burden and attention demand
- Understanding of system scope, status, and commitments
- Ability to steer, correct, stop, partially apply, and recover
- Appropriately calibrated trust rather than maximum trust
- Accessibility for relevant abilities, devices, languages, and assistive technology

### Risk guardrails

- Harmful, unauthorized, or policy-violating action rate
- Sensitive-data exposure or provenance failure
- Unrecoverable failure or rollback failure
- False-positive action, missed escalation, or alert fatigue
- Unequal performance across material user or case segments

### Adoption and business outcomes

Use adoption, retention, conversion, revenue, or throughput only when they follow from the user outcome. Do not substitute engagement for user value.

## 5. User-friendly evaluation

Assess relevant dimensions independently:

| Dimension | Core question | Example evidence |
|---|---|---|
| Effectiveness | Can people complete the intended task correctly? | Completion, accuracy, rework |
| Efficiency | What time, attention, coordination, and cost are required? | Time, steps, handoffs, cost |
| Comprehensibility | Do people understand capability, limits, state, and impact? | Teach-back, prediction, error interpretation |
| Cognitive load | What must people remember, compare, monitor, or formulate? | Observation, workload rating, errors |
| Control | Can people steer, edit, decline, stop, and choose scope? | Task tests, control discovery |
| Recovery | Can people diagnose failure and continue without losing valid work? | Failure scenarios, recovery time |
| Trust calibration | Do people rely on the system when warranted and verify when needed? | Appropriate reliance by case quality |
| Accessibility | Can relevant people perceive, understand, operate, and recover? | Accessibility review and representative testing |

Use behavioral evidence alongside self-report. Satisfaction alone does not prove usability, and faster completion alone does not prove a better system.

## 6. Efficiency success rule

Before testing, define:

- **Primary efficiency metric:** the one measure expected to improve.
- **Outcome guardrail:** task success or result quality that must be maintained.
- **Human-control guardrail:** control, comprehension, or recovery threshold.
- **Safety guardrail:** unacceptable events and maximum allowed rate.
- **Cost boundary:** acceptable human, model, tool, or operational cost.
- **Decision threshold:** continue, revise, pause, or roll back.

Call a change successful only when the primary efficiency metric improves and every agreed guardrail passes. Report mixed outcomes explicitly. Do not combine all dimensions into a weighted score that hides a safety or quality regression.

When no numeric threshold is defensible, specify the decision procedure and evidence required to set it. Never invent a universal percentage improvement.

## 7. Evaluation kit

Produce these artifacts for a full blueprint:

### Metric specification

| Metric | Definition | Unit | Population/segment | Source | Baseline | Target | Guardrail/primary | Owner |
|---|---|---|---|---|---|---|---|---|

### Task protocol

- Participant or case criteria
- Realistic trigger and starting context
- Task and success definition
- Allowed help and system conditions
- Failure or uncertainty scenario
- Data to record
- Debrief questions

### Observation sheet

Record start/end, outcome, errors, assists, inputs, decisions, switches, waits, AI corrections, commitment understanding, recovery, comments, and anomalies.

### Interview prompts

- What did you think the system would do next?
- What information did you believe it used?
- Where did you feel uncertain or out of control?
- What did you verify, and why?
- If the result were wrong, what would you do?
- What should remain your decision?

### Event instrumentation

For each event define name, trigger, timestamp, actor, object, state before/after, action scope, success/failure, latency, model/tool version when relevant, confirmation, correction, rollback, and privacy constraints. Do not log hidden reasoning or unnecessary sensitive content.

### Pilot design

Define cohort, exposure, comparison, duration or case count, training, support, monitoring, escalation owner, stop conditions, rollback path, and review cadence. Prefer the smallest reversible pilot that tests the riskiest assumption.

## 8. Readiness and decision rules

Rate each relevant area `Ready`, `At risk`, `Not ready`, or `Unknown`:

- Goal and user value
- Baseline and evidence
- Workflow and interaction integrity
- Technical and operational feasibility
- Human control and recovery
- Safety, privacy, and permissions
- Measurement and pilot readiness

Never average these states into a maturity total. A single `Not ready` safety or recovery condition may block a pilot even when other areas are strong.
