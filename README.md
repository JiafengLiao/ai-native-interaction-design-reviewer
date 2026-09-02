# AI-Native Interaction Design Reviewer

**Design AI products that do less—and work better.**

Turn a rough idea, workflow, screenshot, PRD, or prototype into the smallest evidence-backed AI system worth building: useful to people, clear about what AI should and should not do, safe to operate, and ready to test.

This Codex skill is for first-time builders and experienced product teams alike. It explains unfamiliar concepts before using professional terminology and adapts its depth to the material you bring.

> AI-native does not mean adding chat everywhere. It means starting from the user's real goal, removing unnecessary work, and giving people and AI the responsibilities each can handle best.

## Why use it

AI product work often starts too late in the process—with a feature, model, prompt, or screen already chosen. This skill helps you step back before expensive decisions harden.

It helps you:

- find the real user outcome behind a feature request;
- see where time, attention, coordination, and trust are being lost;
- remove, simplify, combine, or reuse before adding new machinery;
- decide what stays human and what AI may suggest, prepare, execute, or monitor;
- turn the direction into a buildable first slice with safeguards and a real test;
- reject AI when ordinary software or process change is the better answer.

No analytics? No polished PRD? No product-design vocabulary? You can still start.

## Try it in one prompt

```text
Use $ai-native-interaction-design-reviewer to help me improve this idea.
First explain in plain language how you can help, then guide me toward the
simplest useful solution. I have no product design experience.

[Describe the idea or paste the workflow here]
```

The skill will not bury you in a framework. It starts with a few concrete questions, shows what it has learned, and makes useful progress at each step.

## What you get

| The question you need answered | What the skill produces |
|---|---|
| What problem are we really solving? | A clear user goal, trigger, outcome, constraints, and non-goals |
| Is this a real problem or only a belief? | An evidence map that separates facts, observations, assumptions, and unknowns |
| Where should AI help? | A simpler target workflow with explicit human, AI, system, and operational responsibilities |
| How do we keep people in control? | Interaction states, permissions, confirmations, correction, recovery, and fallback |
| What should we build first? | The smallest coherent delivery slice, dependencies, risks, and evaluation plan |
| How will we know it is better? | Efficiency measures plus quality, safety, trust, accessibility, and rollback guardrails |

## The design philosophy

1. **Outcome before feature** — start with what the person needs to make true.
2. **Remove before automate** — delete, simplify, combine, and reuse before adding AI.
3. **Evidence before confidence** — label what is known and what is still a hypothesis.
4. **Minimum sufficient autonomy** — give the system no more initiative or permission than the outcome requires.
5. **Recovery is part of the product** — design how people inspect, correct, stop, undo, and continue.

When two solutions work equally well, the skill prefers the one with fewer screens, roles, agents, integrations, data sources, permissions, handoffs, and operating burdens.

## Choose the depth you need

- **Step-by-step guidance:** best for a rough idea or an unfamiliar domain.
- **Quick review:** a compact judgment on the goal, evidence, friction, direction, risk, and next test.
- **Full blueprint:** an end-to-end package for product, design, engineering, data, research, risk, and operations.
- **Focused review:** only autonomy, evaluation, interaction, implementation, evidence, or another requested section.

The rigor stays the same; only the pacing, terminology, and amount of detail change.

## Useful prompts

```text
Review this flow and tell me what should be removed before we add AI.
```

```text
Rethink this product from the user's real goal, but keep the solution as simple as possible.
```

```text
Decide what people should control and what AI may safely prepare or execute.
```

```text
Build the smallest test that can show whether this actually saves time.
```

```text
Turn this PRD into an implementation-ready AI product blueprint. Keep assumptions explicit.
```

## How the method works

```text
Goal → Evidence → Current reality → Root friction → Responsibility →
Target system → First build → Evaluation → Pilot and learning
                         ↖──── learn and simplify ────↙
```

The method uses three sets of shorthand in formal work, but explains them before use:

- **Evidence strength (E0–E4):** from something merely stated to something tested.
- **Degree of change (R1–R4):** from improving today's flow to safe ongoing delegation.
- **Decision readiness (G1–G5):** from a coherent direction to a real-world pilot that is ready to run.

You do not need to learn these codes to use the skill.

## Install

Clone the repository into the skills directory used by Codex:

```bash
git clone https://github.com/JiafengLiao/ai-native-interaction-design-reviewer.git \
  "${CODEX_HOME:-$HOME/.codex}/skills/ai-native-interaction-design-reviewer"
```

If the destination already exists, update that repository instead of cloning over it. Keep the folder structure unchanged so the reference links continue to work.

## What a full blueprint can include

Only the modules needed for the decision, handoff, or risk are produced:

1. Decision Brief
2. Evidence & Baseline Pack
3. Target Experience Blueprint
4. Interaction & Autonomy Specification
5. System Implementation Blueprint
6. Delivery Roadmap
7. Evaluation Kit

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

`SKILL.md` is the concise orchestration layer. Detailed references are loaded only when the task needs them.

## Method foundations

The skill operationalizes stable principles from:

- [Microsoft Guidelines for Human-AI Interaction](https://www.microsoft.com/en-us/research/publication/guidelines-for-human-ai-interaction/)
- [Google People + AI Guidebook](https://pair.withgoogle.com/guidebook-v2/chapters)
- [NIST AI Risk Management Framework](https://www.nist.gov/itl/ai-risk-management-framework)
- [ISO 9241-11 usability concepts](https://www.iso.org/standard/63500.html)

These sources support the method. Project-specific claims still require project-specific evidence.

## Core principle

> User-goal-first, evidence-led, minimum-sufficient, AI-enabled, human-controlled, measurably better.
