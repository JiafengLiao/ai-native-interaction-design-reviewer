# Review Framework

Use this reference for a full or deep interaction review. Tailor the depth to the evidence available; do not fabricate research findings or technical capabilities.

## Table of contents

1. Review setup
2. Goal definition
3. Current flow reconstruction
4. Friction map
5. AI opportunity map
6. Target flow
7. Interaction specification
8. Evaluation dimensions and scoring
9. Design decision summary

## 1. Review setup

State the frame before critiquing screens.

### Required fields

- **Refactor Ambition:** R1, R2, R3, R4, or Dual-track
- **Design Constraints:** technical, regulatory, organizational, timeline, platform, data, or adoption limits
- **Allowed Changes:** what can change now
- **North Star:** what can change in the unconstrained direction
- **Assumptions:** only material assumptions
- **Frequency:** one-off, frequent, recurring, or continuous
- **Risk:** low, medium, or high, with the reason
- **Current Autonomy:** L0–L5

If the user gives no ambition, use Dual-track. If constraints are unclear, infer a plausible practical boundary and label it.

## 2. Goal definition

Do not describe a UI action as the goal.

### Template

- **Primary User Goal:** one sentence describing the outcome the user cares about
- **Trigger:** the situation that creates the need
- **Desired Outcome:** the state the user wants to reach
- **Success Criteria:** observable signals of completion or quality
- **Frequency:** one-off, frequent, recurring, or continuous
- **Risk Drivers:** external action, money, communication, deletion, publication, privacy, business impact, or another domain-specific concern

Bad:

> The user wants to click Generate to create an email.

Better:

> The user wants to follow up with important customers at the right time with an accurate, relationship-aware message.

## 3. Current flow reconstruction

Compress the current workflow into the smallest meaningful task chain.

### Flow format

```text
Trigger → Step → Step → Decision → Action → Outcome
```

### Actor annotation

Label each step as:

- User
- AI
- Product/System
- External Tool

### Action type

Use when it clarifies burden:

- Think
- Search
- Input
- Configure
- Decide
- Confirm
- Execute
- Wait
- Review
- Recover

### User burden

Count or estimate:

- User inputs
- Explicit decisions
- App or surface switches
- Confirmations
- Repeated context entry
- Manual execution steps
- Wait states
- Recovery restarts

Do not treat every click equally. Emphasize cognitive, coordination, commitment, and recovery costs.

## 4. Friction map

Prioritize 3–7 issues. Diagnose workflow before aesthetics.

### Friction categories

#### Cognitive load

The user must understand internal structure, select complex parameters, design a solution, decompose the task, or write a sophisticated prompt.

#### Context burden

The user must copy, paste, upload, re-explain, or manually identify information the system could already know or retrieve with permission.

#### Coordination burden

The user must sequence work, manage dependencies, move between tools, or act as the router between systems.

#### Execution burden

The system knows the intended next action but still makes the user transfer, apply, submit, publish, or repeat it manually.

#### Confirmation cost

The design asks for approval on low-risk, reversible, or obvious actions, creating confirmation fatigue.

#### Visibility gap

The user cannot distinguish understanding, planning, acting, waiting, reviewing, and completion—or suggestion, draft, prepared action, and committed action.

#### Recovery cost

Failure destroys progress, requires a full restart, hides partial completion, or makes correction harder than regeneration.

#### Dead end

AI produces an output but offers only copy, close, or regenerate instead of edit, compare, apply, continue, execute, or automate.

#### Continuity gap

Recurring work resets to zero. The system does not remember bounded preferences, monitor relevant changes, or carry a goal forward.

### Issue template

For each issue, provide:

- **Location**
- **Problem**
- **User Cost**
- **Why It Is Not AI-Native**
- **Severity:** High, Medium, or Low
- **Design Implication:** the responsibility or interaction change required

Use [ai-native-smells.md](ai-native-smells.md) to name recurring anti-patterns.

## 5. AI opportunity map

For each meaningful step, ask: **Does the user actually need to do this?**

### AI roles

- **Keep manual:** preserve user responsibility
- **Infer:** derive information from available context
- **Suggest:** recommend a next step or option
- **Prefill:** prepare likely structured inputs
- **Generate:** create content, options, or a draft
- **Prepare:** stage a concrete action without committing it
- **Execute:** perform an authorized action
- **Monitor:** watch for a condition over time
- **Escalate:** involve the user when risk, ambiguity, policy, or exception requires judgment

### Opportunity table

| Current Step | Current Owner | Proposed AI Role | Required Context or Capability | User Role | Risk |
|---|---|---|---|---|---|
| Example | User | Prepare | Customer history + email tool | Review draft | Medium |

Then summarize:

- **Steps to Remove**
- **Steps to Automate**
- **Steps to Preserve**
- **New Capabilities Required:** context, integrations, permissions, memory, policies, evaluation, or monitoring

Keep judgment-heavy choices with the user when values, accountability, or ambiguous tradeoffs dominate. Automate mechanical coordination when the context and authority are clear.

## 6. Target flow

This is the central output. Replace the current chain with a coherent operating model.

### Practical target

Use R1/R2. Respect near-term constraints. Show a complete path from trigger to outcome.

```text
Trigger → Context acquired → AI suggestion/preparation → User steering or approval →
Bounded action → Result → Next action or recovery
```

### AI-Native North Star

Use R3 and add R4 only when persistence is useful and safe.

```text
Goal and boundaries → Context interpretation → Plan or preview → User correction →
AI action → Visible result → Continuous improvement, monitoring, or escalation
```

### Required annotations

- Owner of each step
- Where the user participates and why
- Steps removed
- Steps automated
- Steps newly added
- Context and permissions required
- Estimated user-effort reduction, stated as directional when precise data is unavailable
- Failure and correction path

### Dual-track comparison

| Dimension | Current | Practical | AI-Native North Star |
|---|---|---|---|
| User input |  |  |  |
| Context handling |  |  |  |
| AI responsibility |  |  |  |
| Confirmation |  |  |  |
| Recovery |  |  |  |
| Continuity |  |  |  |

The North Star must alter at least one paradigm dimension: interaction, responsibility, context, execution, confirmation, recovery, or continuity.

## 7. Interaction specification

Specify the critical moments, not every pixel.

### Template

| Moment | Pattern | User Sees | AI Does | User Can Do | State/Recovery |
|---|---|---|---|---|---|
| Draft review | Editable preview + diff | Proposed content and sources | Generates and highlights changes | Edit, accept part, reject, refine | Preserve edits on retry |

### Candidate patterns

- Intent-first input
- Contextual suggestion
- Structured natural-language input
- Smart defaults and prefill
- Editable AI preview
- Inline edit or direct manipulation
- Suggest → Apply
- Plan → Execute
- Diff or compare
- Partial approval
- Agent activity panel
- Permission and scope control
- Progressive disclosure
- Exception inbox
- Reversible automation
- Human-on-the-loop monitoring

### State model

Use meaningful states such as:

```text
Understanding → Preparing → Awaiting input → Acting → Verifying → Done
```

Show action-relevant summaries and progress. Do not expose private chain-of-thought.

## 8. Evaluation dimensions and scoring

Score current and target from 1–5 on each dimension. Explain the evidence briefly.

| Dimension | Review question |
|---|---|
| Intent-first | Can users express the outcome instead of translating it into system operations? |
| Context awareness | Does AI use authorized existing context without unnecessary transport or repetition? |
| AI initiative | Does the system proactively infer, prepare, execute, or monitor where appropriate? |
| Visibility | Can users understand status, scope, inputs, and whether anything was committed? |
| User control | Can users steer, edit, stop, partially apply, approve, or undo? |
| Recovery | Can the flow preserve progress, explain failure, accept correction, and resume? |
| Trust | Are sources, assumptions, permissions, uncertainty, and impact appropriately visible? |
| Iteration | Can users refine, compare, continue, reuse context, and improve the goal over time? |

### Interpretation

- **8–16:** Traditional UX with an AI feature
- **17–24:** AI-assisted
- **25–32:** AI-native
- **33–40:** Agent-native

Treat bands as diagnostic shorthand, not targets. High-risk products may intentionally keep autonomy low while scoring well on control, trust, and recovery.

## 9. Design decision summary

End with:

- **Current Score:** `/40`
- **Target Score:** `/40`
- **Autonomy Shift:** current L0–L5 → recommended L0–L5
- **Top Three Design Changes**
- **Biggest UX Gain**
- **Biggest Risk**
- **Recommended Next Prototype**
- **What to Test With Users**
- **Feasibility Dependencies:** data, integration, permissions, model quality, evaluation, or operations

Prefer one decisive prototype that tests the riskiest assumption over a broad list of disconnected improvements.
