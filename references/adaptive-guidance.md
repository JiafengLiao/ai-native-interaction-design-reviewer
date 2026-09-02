# Adaptive Guidance

Use this reference to make the same rigorous method usable by people with different levels of experience. Adapt language and pacing, not the quality standard.

## Table of contents

1. Detect the working mode
2. Run beginner guidance
3. Ask high-value questions
4. Translate terminology
5. Handle uncertainty
6. Show progress
7. Compress for experts

## 1. Detect the working mode

Infer a mode without testing or labeling the user.

### Beginner signals

- One-sentence idea, personal story, or desired feature
- “I don't know where to start” or uncertainty about users and metrics
- No artifacts and little domain language
- A request for examples, explanation, or step-by-step help

### Standard signals

- A recognizable user, workflow, pain point, or constraint
- Some product terminology or screenshots, but incomplete evidence
- A request to improve, review, or compare directions

### Expert signals

- Structured PRD, research report, journey, architecture, event data, or experiment plan
- Explicit hypotheses, metrics, risk classification, or autonomy requirements
- A narrowly scoped request with sufficient context

Do not infer expertise from writing style, job title, language fluency, or brevity alone. Start with the least burdensome suitable mode. Let the user say `Beginner mode`, `Standard mode`, or `Expert mode` at any time.

## 2. Run beginner guidance

Ask only 1–3 questions per turn. Use this sequence:

1. **Why this matters:** one sentence tied to the user's outcome.
2. **Plain question:** ask about a concrete event or behavior.
3. **Example:** show one short example only when it reduces ambiguity.
4. **Professional translation:** after the answer, convert it into the relevant goal, flow, evidence, risk, or requirement.
5. **Visible progress:** say what is now known and what comes next.

Good:

> To know where AI would actually help, I first need the moment this problem begins. What happened the last time someone had this problem, from the first trigger to the result? For example: “A customer asked for a refund, I checked three systems, then waited for finance.”

Avoid:

> Define the primary persona, JTBD, autonomy level, North Star metric, and service blueprint.

Do not front-load the full method. Produce useful partial artifacts after each small answer.

## 3. Ask high-value questions

Ask only questions whose answers would change the goal, design, autonomy, risk, or test. Prefer recent concrete behavior over opinions.

### Goal

- What is the person trying to finish or make true?
- What causes them to start?
- How do they know they are done?

### Current or analogous behavior

- What happened the last time this was done?
- Which part took the most effort, waiting, or backtracking?
- What do people use instead today if the product does not exist?

### Consequences

- What goes wrong when the result is late or incorrect?
- Does anything get sent, published, purchased, deleted, or changed for someone else?
- Which decision must remain with a person, and why?

### Evidence

- What have you directly seen or measured?
- What is currently a belief rather than a fact?
- What is the cheapest real case we could observe?

### Feasibility

- What information would the system need?
- Which tools or people must it coordinate with?
- What may not change in the first release?

### Success

- What should become faster or easier?
- What must not become worse?
- What result would make the team stop or roll back?

## 4. Translate terminology

Use plain language first. Introduce the professional term in parentheses only when it helps handoff.

| Professional concept | Plain-language question |
|---|---|
| Primary user goal | What is the person really trying to get done? |
| Trigger | What happens that makes them start? |
| Baseline | How does it work today, and what does it currently cost? |
| Cognitive load | What must the person remember, figure out, or compare? |
| Context burden | What information do they repeatedly find, explain, copy, or upload? |
| Autonomy | What may the system do by itself, and what needs a person first? |
| Commitment boundary | At what point does something affect the outside world or become hard to reverse? |
| Guardrail | What limit prevents an unacceptable outcome? |
| Recovery | If it fails halfway, how does the person continue without starting over? |
| Evidence confidence | How sure are we, and what have we actually seen? |
| Success threshold | What result counts as good enough to continue? |

## 5. Handle uncertainty

When the user says “I don't know”:

1. Do not repeat the same question with jargon.
2. Offer 2–3 materially different possibilities when a choice is needed.
3. State a reversible default when the impact is low.
4. Label the assumption in the Evidence Ledger.
5. Give the lowest-cost way to replace the assumption with evidence.

Use four labels consistently:

- **Known:** supplied or observed evidence supports it.
- **Inferred:** derived from evidence but not directly observed.
- **Assumed:** selected so work can continue.
- **Unknown:** material and not yet safely inferable.

Never silently turn an assumption into a fact later in the work.

## 6. Show progress

At the end of a guided stage, use a compact update:

```text
What we know
- ...

What is still uncertain
- ...

What this produced
- Goal statement / baseline / target flow / blueprint section

Next step
- One concrete action or 1–3 questions
```

For beginners, add a short action checklist with owner and expected result. Avoid dumping every appendix before the user needs it.

## 7. Compress for experts

- Do not ask for information already present in artifacts.
- State mapped assumptions and gaps in one block.
- Use tables, IDs, state names, metric definitions, and dependency lists directly.
- Allow focused entry at any stage, but preserve upstream assumptions and downstream validation.
- Keep evidence, guardrails, failure modes, and measurement even when the rest is compressed.
- Do not mistake confidence or sophisticated language for strong evidence.
