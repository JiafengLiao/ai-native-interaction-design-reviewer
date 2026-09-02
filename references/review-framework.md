# End-to-End Review and Design Framework

Use this reference for a full review, guided design, or implementation-ready blueprint. Tailor the pacing to the user and the depth to the evidence. Apply the minimum-sufficient-system principle throughout; treat sections and templates as conditional tools, not required output. Do not fabricate research, metrics, capabilities, or feasibility.

## Table of contents

1. Stage 1 — Understand the goal
2. Stage 2 — Establish evidence
3. Stage 3 — Reconstruct the baseline
4. Stage 4 — Diagnose the workflow
5. Stage 5 — Reallocate responsibility
6. Stage 6 — Design the system
7. Stage 7 — Build the implementation blueprint
8. Stage 8 — Define evaluation
9. Stage 9 — Plan pilot and learning
10. Stage gates and final decisions

## 1. Stage 1 — Understand the goal

Do not describe a screen action as the goal.

Capture:

- **Primary user or actor:** who experiences the need and who is affected
- **Trigger:** the event that creates the need
- **Underlying goal:** the outcome the person cares about
- **Desired result:** the observable end state
- **Success conditions:** what must be true, not a metric target yet
- **Frequency:** one-off, occasional, frequent, recurring, or continuous
- **Consequences:** what happens when the result is late, wrong, missing, or unauthorized
- **Constraints and non-goals:** what may not change now and what is intentionally excluded

For 0-to-1 work, identify the current substitute, workaround, avoidance, or unmet behavior. Test whether AI has a distinctive advantage over deterministic software, process change, content, or service design.

### Value hypothesis

Write:

```text
For [user/context], when [trigger], the system helps achieve [outcome]
by [change in responsibility or capability], expected to improve [benefit]
without worsening [guardrails]. Current evidence: [claim IDs and level].
```

Pass G1 only when the user, goal, value mechanism, risk, and non-goals are coherent enough to guide evidence collection.

## 2. Stage 2 — Establish evidence

Create an Evidence Ledger using [evidence-and-evaluation.md](evidence-and-evaluation.md). Separate:

- What has been directly observed or measured
- What stakeholders or users report
- What is inferred from artifacts or behavior
- What is assumed so work can continue
- What is a desired target
- What remains materially unknown

Link every major friction, design choice, expected benefit, and risk to claim IDs. Record contradictions and limitations.

Choose the next evidence action by decision value, not by research completeness: ask which unknown could most plausibly reverse the direction or make it unsafe.

## 3. Stage 3 — Reconstruct the baseline

Compress the current, substitute, or analogous workflow:

```text
Trigger → Step → Decision → Handoff/Wait → Commitment → Outcome → Recovery
```

For each step record:

| Step | Actor | Action type | Input/context | Decision | Tool/handoff | Time/wait | Failure/rework | Evidence |
|---|---|---|---|---|---|---|---|---|

Use actor labels such as User, AI, Product/System, External Tool, and Human Operations. Use action types such as Think, Search, Input, Configure, Decide, Confirm, Execute, Wait, Review, Verify, and Recover.

Do not treat every click equally. Emphasize:

- Cognitive work and judgment
- Context finding and transport
- Coordination and handoffs
- Explicit decisions and commitment
- Active time and elapsed waiting
- Quality checks and correction
- Failure, lost work, and restart cost

When analytics are missing, run the lightweight baseline sprint. Pass G2 when the baseline is sufficient to choose the riskiest test—not when every metric exists. Keep benefit claims hypothetical until evidence supports them.

## 4. Stage 4 — Diagnose the workflow

Prioritize the smallest set of structural frictions that explains the important burden—usually 1–3, expanding only when distinct problems would otherwise be hidden. Use [ai-native-smells.md](ai-native-smells.md) for recurring patterns.

For each friction provide:

- Location and affected user or actor
- Concrete problem and evidence claim IDs
- User, quality, coordination, or recovery cost
- Root responsibility or capability mismatch
- Severity and frequency confidence
- Design implication
- What evidence would change the judgment

Cover cognitive, context, coordination, execution, waiting, confirmation, visibility, handoff, recovery, continuity, and accessibility costs when relevant.

Do not diagnose “lack of AI” as a friction. Diagnose unmet outcomes and burdens first.

## 5. Stage 5 — Reallocate responsibility

For every meaningful step, ask whether a person actually needs to do it.

Evaluate each step in this order: remove it, simplify it, combine it with another step, reuse known context or an existing capability, apply deterministic automation, then consider bounded AI. Consider autonomous execution only when the recurring value exceeds its added permissions, monitoring, recovery, and operational burden.

| Current step | Current owner | Proposed role | Required context/capability | User role | Risk | Evidence dependency |
|---|---|---|---|---|---|---|

Use these proposed roles:

- **Keep manual:** preserve human responsibility
- **Infer:** derive information from authorized context
- **Suggest:** recommend an option or next step
- **Prefill:** prepare likely structured inputs
- **Generate:** create content or alternatives
- **Prepare:** stage a concrete action without committing it
- **Execute:** perform an authorized action
- **Monitor:** watch for a condition over time
- **Escalate:** involve a person for ambiguity, policy, risk, or exception

Summarize work to Remove, Simplify or Combine, Reuse, Automate, Preserve, and Add. Name only the context, integrations, policies, memory, operations, and evaluation required by the chosen direction.

Apply [autonomy-framework.md](autonomy-framework.md) action by action. One workflow may contain multiple autonomy levels.

## 6. Stage 6 — Design the system

Honor an explicit R1–R4 ambition. Otherwise create two tracks:

### Practical track

Use R1/R2. Respect near-term technical, regulatory, operational, platform, and adoption constraints. Deliver a complete path from trigger to verified outcome and recovery.

### AI-Native North Star

Use R3 and add R4 only when persistent delegation is valuable and supportable. Change the operating model rather than decorating the current flow.

Compare:

| Dimension | Current/Analogue | Practical | North Star |
|---|---|---|---|
| Intent expression |  |  |  |
| Context acquisition |  |  |  |
| User work |  |  |  |
| AI/system work |  |  |  |
| Human operations |  |  |  |
| Confirmation/commitment |  |  |  |
| Recovery |  |  |  |
| Continuity |  |  |  |
| Expected benefit and evidence |  |  |  |

For each track show actor ownership, removed and new work, required capabilities, user checkpoints, failure path, and evidence gaps. For each new entity, name the problem it solves and why reuse or a simpler mechanism is insufficient. Reject the North Star when the added complexity, cost, risk, or loss of control is not justified.

## 7. Stage 7 — Build the implementation blueprint

Use [implementation-blueprint.md](implementation-blueprint.md) as a menu. Produce only what the first coherent outcome and its material risks require:

- Target Experience Blueprint
- Critical interaction and state specification
- Action-level autonomy and guardrails
- AI capability contracts
- Context, data, tools, and permission maps
- Failure and human-operations design
- Instrumentation requirements
- Testable vertical delivery slices

Do not call a design build-ready when it omits material dependencies, failure paths, evaluation, or hidden manual work. Do not add speculative components merely to make the blueprint look complete.

Pass G3 when the operating model is coherent. Pass G4 only when the first delivery slice can be implemented and evaluated without material product decisions left to the implementer.

## 8. Stage 8 — Define evaluation

Use [evidence-and-evaluation.md](evidence-and-evaluation.md) to create the smallest metric and evidence set that can detect the intended benefit and material regressions:

- Metric tree linked to the user outcome
- Primary efficiency measure
- Outcome/quality, safety, control/recovery, accessibility, and cost guardrails
- Baseline source and current evidence level
- Test tasks and realistic failure scenarios
- Observation sheet and interview guide
- Event instrumentation and privacy constraints
- Precommitted continue, revise, pause, and rollback thresholds

Assess design readiness separately from evidence confidence and measured outcome. Never use one total score.

## 9. Stage 9 — Plan pilot and learning

Choose the smallest reversible exposure that tests the riskiest system assumption.

Specify:

- Cohort, case scope, and excluded cases
- Current comparison or control condition
- Model, prompt, tool, policy, and interface version
- Training, onboarding, support, and manual fallback
- Live monitoring and review cadence
- Escalation and incident owners
- Stop and rollback triggers
- Decision date and evidence review
- How accepted findings change the next slice

Do not progress from prepared actions to standing autonomy merely because a prototype is appealing. Require representative outcomes, bounded policies, reliable permissions, monitoring, and recovery.

## 10. Stage gates and final decisions

Use `Pass`, `Conditional`, or `Fail` for each gate:

| Gate | Decision question |
|---|---|
| G1 Direction | Is the problem and value mechanism worth investigating? |
| G2 Evidence | Is there enough baseline evidence to choose and interpret the next test? |
| G3 Solution integrity | Does the proposed system form a coherent, controllable operating model? |
| G4 Build readiness | Can a team implement the first slice without unresolved material decisions? |
| G5 Pilot readiness | Are thresholds, guardrails, monitoring, ownership, and rollback ready? |

End a full engagement with:

- Recommendation and current gate
- Evidence level and most important unknown
- Practical and North Star decisions
- Largest expected gain and largest risk
- First vertical slice
- Evaluation and pilot decision rule
- Named next action and owner

For guided work, expose only the current decision and next step while retaining the complete artifact structure internally.
