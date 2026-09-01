# Autonomy and Guardrail Framework

Use this reference to decide what AI may suggest, prepare, execute, monitor, or escalate. Apply the framework action by action; one product can contain several autonomy levels.

## Table of contents

1. Autonomy levels
2. Decision factors
3. Confirmation model
4. Guardrail matrix
5. Core principles
6. Failure and recovery
7. Progressive delegation

## 1. Autonomy levels

### L0 — Manual

The user performs the work. AI is absent or limited to passive information.

Use when automation offers little value or authority, context, reliability, or safety is insufficient.

### L1 — Assist

AI explains, recommends, or highlights. The user performs the action.

Use for judgment support, unfamiliar domains, or early trust building.

### L2 — Copilot

AI drafts, prefills, compares, or prepares. The user reviews and commits the action.

Use when preparation is valuable but commitment requires human judgment.

### L3 — Delegation

The user defines the goal and scope. AI executes a bounded task, with confirmation at meaningful checkpoints.

Use when authority, context, evaluation, and recovery are adequate.

### L4 — Agent

AI plans and completes multiple steps across time or tools, maintains state, and escalates exceptions.

Use for repeatable workflows with explicit policies, permissions, activity history, verification, and rollback or compensating controls.

### L5 — Autonomous

AI continuously monitors conditions and acts within standing authority, involving the user mainly for policy exceptions or material uncertainty.

Use only when outcomes are measurable, actions are sufficiently safe or recoverable, boundaries are explicit, and oversight is effective.

## 2. Decision factors

Assess each proposed action on:

- **Impact:** local draft, internal system, external party, public audience, financial or legal consequence
- **Reversibility:** easy undo, compensating action, costly recovery, or irreversible
- **Confidence:** quality of context and action selection, not just model confidence language
- **Ambiguity:** whether reasonable users would choose different outcomes
- **Authorization:** explicit permission, role, data access, tool scope, and policy
- **Observability:** ability to verify the action and outcome
- **Frequency:** one-off, repeated, recurring, or continuous
- **Time sensitivity:** cost of waiting for confirmation
- **Failure containment:** size of the blast radius and ability to limit scope
- **User expectation:** whether the action matches the delegation the user reasonably believes they granted

### Default direction

| Conditions | Recommended behavior |
|---|---|
| Low impact + reversible + high confidence | Prepare or execute; notify and allow undo |
| Medium impact or meaningful ambiguity | Preview; support edit and partial approval |
| High impact, external, irreversible, financial, privacy-sensitive, or reputation-sensitive | Require explicit confirmation at commitment |
| Insufficient authority or policy conflict | Do not execute; explain the boundary and request appropriate authorization |
| Low confidence with material consequences | Escalate with specific alternatives and evidence |

## 3. Confirmation model

Confirmation is a design control, not a universal safety ritual.

### No confirmation

Usually appropriate for:

- Generating local drafts
- Retrieving authorized context
- Creating reversible previews
- Reordering or formatting a local working copy
- Monitoring without external action, when users can see and stop it

### Notify with undo

Usually appropriate for:

- Reversible local changes
- Low-risk categorization, tagging, or organization
- Bounded updates with a clear history and reliable rollback

### Preview and approve

Usually appropriate for:

- Material edits
- Multi-object changes
- Medium-risk internal actions
- Actions with meaningful ambiguity
- First-time delegation of a repeated workflow

### Explicit confirmation at commitment

Usually required for:

- Sending external communication
- Publishing publicly
- Spending or transferring money
- Deleting or overwriting valuable data
- Changing permissions or access
- Disclosing sensitive information
- Entering legal, employment, medical, or other high-impact commitments

### Prohibit or escalate

Use when the action exceeds authority, violates policy, has unacceptable risk, or cannot be made adequately observable and recoverable.

Avoid confirmation spam. Bundle related changes into a reviewable plan or diff and place approval at the actual commitment boundary.

## 4. Guardrail matrix

Complete one row per consequential AI action.

| AI Action | Level | Scope | Preview | Confirmation | Undo/Rollback | Provenance | Permission | Verification | Failure Recovery |
|---|---:|---|---|---|---|---|---|---|---|
| Example: draft email | L2 | One customer | Yes | Before send, not before draft | Version history | Customer records used | Read CRM | User review | Preserve edits and regenerate section |

Also answer explicitly:

- What AI may do directly
- What AI may do and then notify with undo
- What AI must prepare for approval
- What AI must never execute automatically under the proposed policy

## 5. Core guardrail principles

### Scope

Define objects, time window, audience, amount, tools, and data sources. Prefer the smallest useful authority.

### Permission

Separate the ability to access context from the ability to act. Make current permissions inspectable and revocable.

### Preview

Show the actual proposed change, target, audience, and material assumptions—not a vague summary.

### Provenance

Expose sources or data lineage when they affect correctness, trust, or accountability. Distinguish facts, inferences, and generated content.

### Reversibility

Provide undo, rollback, version history, compensating action, or a safe staged state in proportion to autonomy.

### Visibility

Show what is planned, in progress, completed, blocked, and committed. Do not reveal private chain-of-thought; show concise action-relevant rationale.

### Limits

Set thresholds for volume, spend, time, audience, confidence, and repeated failures. Stop or escalate when a limit is reached.

### Verification

Check the result after tool execution. A successful tool call is not always a successful user outcome.

### Accountability

Maintain an activity history of consequential actions, approvals, policy decisions, and outcomes.

## 6. Failure and recovery

Treat misunderstanding and tool failure as normal states.

### Recovery sequence

1. Stop further propagation when needed.
2. State what succeeded, failed, and remains pending.
3. Preserve completed work and user edits.
4. Explain the actionable cause without exposing hidden reasoning.
5. Offer specific alternatives or a correction point.
6. Resume from the current state instead of restarting.
7. Roll back or use a compensating action when appropriate.
8. Escalate repeated or high-impact failures.

### Design for partial completion

For multi-step actions, track per-step state and distinguish:

- Not started
- In progress
- Completed and verified
- Completed but unverified
- Failed
- Rolled back
- Needs user decision

## 7. Progressive delegation

Do not jump from manual operation to standing autonomy without evidence.

```text
Suggest → Prepare → Execute with approval → Execute and notify → Monitor and escalate
```

Advance autonomy when:

- The user has seen representative previews
- Outcomes are measurable and repeatedly acceptable
- Preferences or policies are explicit
- Permissions remain bounded
- Activity is visible
- Stop, correction, and recovery work reliably

Reduce autonomy when context changes, failure rates rise, risk increases, or user trust is not established. Let users inspect and revise the policy, not merely toggle “autopilot.”
