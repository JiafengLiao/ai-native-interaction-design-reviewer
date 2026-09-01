# AI-Native Interaction Design Reviewer

An installable Skill for reviewing and redesigning product interactions across four levels of ambition: R1 Optimize, R2 Recompose, R3 AI-Native, and R4 Agent-Native.

The default is **Dual-track**: a practical R1/R2 redesign for the next iteration plus an R3/R4 North Star unconstrained by the current workflow.

## What it reviews

- Whether the flow starts from the user's goal or from software operations
- Whether AI uses available context instead of making users transport it
- Whether responsibilities are assigned appropriately across user, AI, system, and tools
- Whether confirmation, control, visibility, trust, and recovery match the action risk
- Whether the design is truly AI-native rather than traditional software with an AI surface
- Whether recurring work should become persistent, policy-bound agent delegation

## Package structure

```text
ai-native-interaction-design-reviewer/
├── SKILL.md
├── README.md
├── agents/
│   └── openai.yaml
└── references/
    ├── review-framework.md
    ├── ai-native-smells.md
    ├── autonomy-framework.md
    └── examples.md
```

`SKILL.md` contains the concise operating instructions. The reference files hold the detailed framework, diagnostic patterns, autonomy guidance, and worked examples. `agents/openai.yaml` provides optional UI metadata for compatible Codex environments.

## Install

Use the ZIP bundle where skill ZIP uploads are supported, or extract it and add the complete `ai-native-interaction-design-reviewer` folder to the skills directory used by your agent environment. Keep the folder structure unchanged so the relative reference links continue to work.

For API-based skill management, OpenAI's Skills API accepts either a directory upload or a single ZIP file. Product availability and UI installation steps can vary by account or workspace, so follow the skill-management surface available in your environment.

## Invoke

Use the skill by name:

```text
Use $ai-native-interaction-design-reviewer to review this flow.
```

You can provide a screenshot, prototype, Figma flow, PRD, feature description, user journey, or plain task chain.

## Starter commands

```text
Review this flow
```

Runs the default Dual-track review.

```text
Optimize this flow
```

Uses R1 and preserves the current product model.

```text
Recompose this workflow
```

Uses R2 and redesigns the human/AI division of labor.

```text
Make this AI-native
```

Uses R3 and redesigns from the user's underlying goal.

```text
Make this agent-native
```

Uses R4 and explores persistent goals, monitoring, policies, and exception handling.

```text
Compare practical vs North Star
```

Compares a realistic R2 direction with an R3/R4 North Star.

```text
Review autonomy and guardrails
```

Focuses on execution boundaries, confirmation, undo, provenance, permissions, and recovery.

```text
Run a quick AI-native review
```

Returns a compressed review.

## Example input

```text
Use $ai-native-interaction-design-reviewer in Dual-track mode.

Current flow:
Select a customer in the CRM → click “Write follow-up” → enter a prompt →
generate an email → copy it → open Gmail → paste → send.

Constraint: The next release cannot replace the CRM or email provider.
```

## Expected full-review output

1. Review Setup
2. Goal Definition
3. Current Flow
4. Friction Map
5. AI Opportunity Map
6. Target Flow
7. Interaction Specification
8. Autonomy & Guardrail Matrix
9. Design Decision Summary

## Design principle

> User-goal-first, AI-enabled, human-controlled.

The North Star must change the operating model—not merely add a prompt box, chat panel, or AI button.
