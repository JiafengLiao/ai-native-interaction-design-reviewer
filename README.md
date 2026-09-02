# AI-Native Interaction Design Reviewer

An installable Codex skill that helps anyone—from a first-time builder to an experienced product team—turn a rough idea, existing workflow, PRD, screenshot, or prototype into an evidence-backed, user-friendly, implementation-ready AI-native system.

The skill does more than review screens. It guides the work from user goal and baseline through workflow redesign, human/AI responsibility, interaction states, system requirements, evaluation, and pilot planning.

## What makes it different

- **Works at any experience level:** automatically adapts to Beginner, Standard, or Expert mode without lowering the final quality bar.
- **Does not require existing analytics:** starts with a lightweight task walkthrough and clearly labels unproven benefits.
- **Supports existing flows and 0-to-1 products:** compares against the current workflow, workaround, substitute, or analogue.
- **Separates design quality from evidence:** no false-precision maturity total or unsupported ROI claim.
- **Produces a buildable package:** includes interaction, AI capability, data, tool, permission, failure, operations, delivery, and measurement specifications.
- **Balances efficiency with human outcomes:** speed must improve without unacceptable regressions in quality, safety, control, recovery, trust, or accessibility.
- **Treats “no AI” as valid:** recommends deterministic software or process change when AI is not justified.

## Method

The skill uses a stage-gated loop:

```text
Goal → Evidence → Baseline → Diagnosis → Responsibility →
System Design → Implementation Blueprint → Evaluation → Pilot & Learning
                         ↖──────── evidence-driven return ────────↙
```

Evidence is tracked from E0 (stated) through E4 (tested). Missing metrics do not stop the work, but E0/E1 evidence cannot be presented as proven efficiency.

The default design view is Dual-track:

- **Practical:** an implementable R1/R2 next iteration.
- **AI-Native North Star:** an R3 redesign of the operating model, with R4 persistent delegation only when useful and safe.

## Install

Clone the repository into the skills directory used by Codex:

```bash
git clone https://github.com/JiafengLiao/ai-native-interaction-design-reviewer.git \
  "${CODEX_HOME:-$HOME/.codex}/skills/ai-native-interaction-design-reviewer"
```

If the destination already exists, update it from the repository instead of cloning over it. Keep the folder structure unchanged so the reference links continue to work.

## Use

Invoke the skill by name:

```text
Use $ai-native-interaction-design-reviewer to help me turn this rough idea into
an AI-native system. I have no product design experience.
```

The skill follows the language used in the request.

### Beginner examples

```text
Use $ai-native-interaction-design-reviewer in Beginner mode. Our team spends
too long making weekly reports and I think AI might help. I don't have metrics.
```

```text
Use $ai-native-interaction-design-reviewer. I have an idea but don't know where
to start: help parents understand messages from their child's school.
```

The skill asks only a few plain-language questions at a time, translates the answers into professional artifacts, and shows what has been completed and what comes next.

### Standard and expert examples

```text
Use $ai-native-interaction-design-reviewer to review this workflow and compare
a practical next release with an AI-native North Star.
```

```text
Use $ai-native-interaction-design-reviewer in Expert mode. Build an
implementation-ready blueprint from this PRD, research report, event taxonomy,
and architecture. Preserve evidence IDs and identify unresolved gate conditions.
```

### Focused commands

- `Review this flow`
- `Optimize this flow` — R1
- `Recompose this workflow` — R2
- `Make this AI-native` — R3
- `Make this agent-native` — R4
- `Prove whether this actually saves time`
- `Create the evaluation kit`
- `Review autonomy and guardrails`
- `Beginner mode`, `Standard mode`, or `Expert mode`

## Full delivery package

1. Decision Brief
2. Evidence & Baseline Pack
3. Target Experience Blueprint
4. Interaction & Autonomy Specification
5. System Implementation Blueprint
6. Delivery Roadmap
7. Evaluation Kit

The main decision is kept concise; detailed evidence, specifications, and test materials live in modular appendices.

## Package structure

```text
ai-native-interaction-design-reviewer/
├── SKILL.md
├── README.md
├── agents/
│   └── openai.yaml
└── references/
    ├── adaptive-guidance.md
    ├── review-framework.md
    ├── evidence-and-evaluation.md
    ├── implementation-blueprint.md
    ├── method-foundations.md
    ├── ai-native-smells.md
    ├── autonomy-framework.md
    └── examples.md
```

`SKILL.md` is the concise orchestration layer. References are loaded only when the task needs their detail.

## Method foundations

The skill operationalizes stable principles from:

- [Microsoft Guidelines for Human-AI Interaction](https://www.microsoft.com/en-us/research/publication/guidelines-for-human-ai-interaction/)
- [Google People + AI Guidebook](https://pair.withgoogle.com/guidebook-v2/chapters)
- [NIST AI Risk Management Framework](https://www.nist.gov/itl/ai-risk-management-framework)
- [ISO 9241-11 usability concepts](https://www.iso.org/standard/63500.html)

These sources support the method. Project-specific claims still require project-specific evidence.

## Core principle

> User-goal-first, evidence-led, AI-enabled, human-controlled, measurably better.
