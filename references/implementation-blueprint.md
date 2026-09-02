# Implementation Blueprint

Use this reference to turn the target experience into a cross-functional package that product, design, engineering, data, research, risk, and operations can act on. Treat it as a menu, not a completeness checklist. Include only what is necessary to deliver and evaluate the first coherent user outcome and address material risks.

## Table of contents

1. Decision Brief
2. Target Experience Blueprint
3. Interaction specification
4. AI system contract
5. Data, tools, and permissions
6. Failure and operations design
7. Delivery slices
8. Readiness gates

## 1. Decision Brief

Keep the main document short. State:

- User, trigger, underlying goal, and current substitute
- Value hypothesis and evidence level
- Recommended practical direction and North Star
- Expected efficiency mechanism; do not state unmeasured gains as facts
- Largest experience, feasibility, and safety risks
- Current gate status and next decision
- Links or IDs for the supporting appendices

For beginners, add a plain-language “what this means” and an owner-based next-action list. For experts, use compact IDs and decision tables.

## 2. Target Experience Blueprint

Compare Current or Analogue → Practical → AI-Native North Star.

| Dimension | Current/Analogue | Practical | North Star |
|---|---|---|---|
| Trigger and intent |  |  |  |
| Context acquisition |  |  |  |
| User responsibility |  |  |  |
| AI/system responsibility |  |  |  |
| Human or operational role |  |  |  |
| Tools and handoffs |  |  |  |
| Commitment points |  |  |  |
| Recovery |  |  |  |
| Continuity |  |  |  |
| Expected benefit and evidence |  |  |  |

Write the target chain as an end-to-end operating model:

```text
Trigger → Authorized context → Understanding → Preparation/plan →
User steering or policy check → Bounded action → Verification →
Outcome → Recovery, learning, or monitoring
```

Annotate owner, user involvement, required capability, evidence dependency, commitment, and recovery for every meaningful step. Explicitly identify removed, simplified, reused, automated, preserved, and newly introduced work. For each new entity, state the problem it solves and why an existing entity cannot do the job adequately.

## 3. Interaction specification

Specify critical moments and states, not every pixel. Merge states that do not differ in user choice, system behavior, commitment, visibility, or recovery.

| Moment | Entry condition | User sees | System does | User controls | Exit/commitment | Failure/recovery |
|---|---|---|---|---|---|---|

Use a state model such as:

```text
Understanding → Preparing → Awaiting input → Ready to act →
Acting → Verifying → Done
                       ↘ Failed → Recovering / Needs decision
```

For each state define:

- Visible status and affected scope
- Evidence, sources, assumptions, and uncertainty shown
- Editable objects and partial-apply behavior
- Stop, cancel, undo, retry, fallback, and resume behavior
- Timeout, stale-context, and concurrent-change handling
- Accessibility and non-conversational control needs

Prefer the interaction best suited to the task: direct manipulation, forms, tables, diffs, previews, queues, timelines, activity views, or chat. Do not make chat the default control surface for precise, parallel, spatial, or stateful work.

## 4. AI system contract

Define each necessary AI capability as a bounded contract. Do not create a separate capability when an existing capability or deterministic rule can meet the same need:

| Capability | Intended job | Required inputs/context | Output schema | Quality criteria | Confidence/uncertainty | Human role | Prohibited behavior | Fallback |
|---|---|---|---|---|---|---|---|---|

Specify:

- What the model decides, recommends, generates, classifies, or monitors
- What deterministic product logic must enforce
- What context is required, optional, stale, conflicting, or unavailable
- How output is validated before it affects people or external systems
- Model, prompt, retrieval, tool, and policy versioning needed for traceability
- Latency, availability, and cost budgets where they affect the experience
- How corrections are captured without promising that every correction trains the model

Do not use “the AI understands” as a requirement. Express observable inputs, outputs, behaviors, and limits.

## 5. Data, tools, and permissions

### Context and data map

Include only data needed for the stated outcome, safety, or evaluation. Reuse authorized context before adding a source, and do not collect speculative “future-use” data.

| Data/context | Source | Purpose | Freshness | Sensitivity | User visibility/control | Retention | Failure if absent |
|---|---|---|---|---|---|---|---|

### Tool/action contract

| Tool/action | Read/write | Scope | Preconditions | Preview | Confirmation | Verification | Undo/compensation | Audit event |
|---|---|---|---|---|---|---|---|---|

Apply least privilege. Bind permission to purpose, object scope, duration, and action type. Distinguish permission to read, prepare, execute, publish, purchase, delete, communicate, or monitor.

Show the user what context and permissions materially affect an action. Define behavior for expired authorization, partial tool failure, conflicting records, rate limits, and changed external state.

## 6. Failure and operations design

Create a failure matrix:

| Failure | Detection | User impact | Automatic response | User/human action | Preserved progress | Recovery/compensation | Escalation owner |
|---|---|---|---|---|---|---|---|

Cover plausible and material failures. Do not enumerate low-impact theoretical cases that would not change the design. Consider:

- Missing, stale, contradictory, or unauthorized context
- Low-confidence or structurally invalid output
- Tool timeout, partial execution, duplicate action, or changed target
- Incorrect commitment or downstream rejection
- User correction, policy exception, and unavailable human reviewer
- Cost, latency, rate-limit, or service degradation

Define operational ownership for policy updates, exception queues, incidents, model/tool changes, quality review, appeals, and user support. An AI-native experience is not build-ready if it silently relies on unspecified human labor.

## 7. Delivery slices

Plan vertical slices that deliver a testable user outcome, not horizontal layers such as “build the AI” and “build the UI.”

Possible progression; start with the smallest slice that tests the riskiest assumption and stop escalating when a simpler level meets the outcome and guardrails:

1. **Concierge or manual-backed test:** validate the goal and workflow before complex automation.
2. **Read-only context + suggestion:** test relevance and mental model without external action.
3. **Editable preparation:** stage a real action and test correction, control, and quality.
4. **Bounded execution with approval:** integrate tools and verify commitment/recovery.
5. **Policy-bound execution:** automate representative low-risk cases with monitoring.
6. **Persistent monitoring and exceptions:** add R4 continuity only after evidence and operations are adequate.

For each selected slice specify user outcome, included/excluded cases, interaction, capabilities, data/tools, guardrails, instrumentation, test, owner, dependencies, and exit criteria. Do not plan later slices before their need is supported.

## 8. Readiness gates

### G3 Solution integrity

- End-to-end target flow is coherent
- Human and AI responsibilities are explicit
- Commitment, correction, and recovery are designed
- North Star changes the operating model or is rejected with a reason

### G4 Build readiness

- Capability contracts and deterministic enforcement are defined
- Context, data, tools, and permissions are mapped
- Critical states and failure paths are specified
- Human operations and cost assumptions are visible
- First vertical slice and evaluation instrumentation are defined

### G5 Pilot readiness

- Representative cases have passed the prior test level
- Primary metric and guardrails have precommitted thresholds
- Monitoring, support, escalation, and rollback owners are assigned
- Cohort and action scope are bounded
- Security, privacy, accessibility, and policy checks match the risk

Mark a gate `Pass`, `Conditional`, or `Fail`. List conditions explicitly. Do not declare build or pilot readiness from a polished prototype alone.
