# AI-Native Smell Tests

Use these smells to diagnose structural problems. A smell is evidence to investigate, not an automatic verdict.

## Table of contents

1. Prompt Box Everywhere
2. AI as a Button
3. Chat for Everything
4. User as API Router
5. Confirmation Spam
6. AI Dead End
7. Context Amnesia
8. Manual Orchestrator
9. Black-Box Action
10. Perfect-Prompt Dependency
11. Regenerate-from-Zero
12. One-Off Agent
13. Autonomy Theater
14. Invisible Commitment Boundary

## 1. Prompt Box Everywhere

**Signal:** Every AI capability begins with an empty prompt box.

**Why it fails:** The user must discover what is possible, design the solution, translate the goal into instructions, and supply context manually.

**Better direction:** Contextual actions, examples, structured intent capture, suggestions, direct manipulation, and editable previews. Keep open-ended prompting as an escape hatch.

## 2. AI as a Button

**Signal:** The user completes most of the traditional workflow and clicks an AI button for one generation step.

**Why it fails:** AI decorates the feature instead of changing responsibility allocation.

**Better direction:** Ask which upstream inputs AI can infer and which downstream actions it can prepare, execute, or monitor.

## 3. Chat for Everything

**Signal:** Parameter tuning, multi-object selection, comparison, batch editing, state inspection, and spatial manipulation all happen through chat.

**Why it fails:** Conversation is inefficient for precise, parallel, visual, or stateful control.

**Better direction:** Combine conversation with chips, forms, tables, inline controls, canvas interaction, diffs, editable previews, or activity views.

## 4. User as API Router

**Signal:** The user copies from one tool, opens another, pastes, invokes AI, then transfers the result elsewhere.

**Why it fails:** The user bears context transport and system coordination.

**Better direction:** With permission, acquire context and use tools directly. If integration is unavailable, prepare an explicit handoff that preserves structure and provenance.

## 5. Confirmation Spam

**Signal:** AI asks for approval before every low-risk or reversible action.

**Why it fails:** Repeated confirmation becomes habitual and reduces attention at genuinely consequential moments.

**Better direction:** Confirm at meaningful commitment boundaries. Let local, reversible preparation happen without interruption.

## 6. AI Dead End

**Signal:** After generation, the only actions are Copy, Close, or Regenerate.

**Why it fails:** AI output is disconnected from the user's actual workflow.

**Better direction:** Offer Edit, Compare, Apply, Apply Selected, Continue, Execute, Save as Rule, or Monitor where appropriate.

## 7. Context Amnesia

**Signal:** AI repeatedly asks for information visible on the current page, already supplied in the session, or stored in an authorized project source.

**Why it fails:** The user becomes the system's memory layer.

**Better direction:** Inherit relevant context, show what was used, let users remove or correct it, and define retention boundaries.

## 8. Manual Orchestrator

**Signal:** The user decomposes the goal, sequences every subtask, waits for each completion, and decides the next obvious step.

**Why it fails:** The user does project management that AI could handle under bounded delegation.

**Better direction:** Let AI propose a concise plan, execute authorized steps, surface blockers, and request judgment only for exceptions.

## 9. Black-Box Action

**Signal:** The interface says “Working…” and later reports success without showing scope, tool use, partial results, or committed changes.

**Why it fails:** Users cannot assess status, impact, or whether intervention is needed.

**Better direction:** Show actionable progress, affected objects, tool status, commitment state, and a verifiable result.

## 10. Perfect-Prompt Dependency

**Signal:** Good results require users to anticipate every constraint and produce a long, exact prompt.

**Why it fails:** Error prevention is pushed onto the user.

**Better direction:** Support incomplete intent, make assumptions visible, ask targeted questions only when material, and make correction cheaper than re-prompting.

## 11. Regenerate-from-Zero

**Signal:** Any correction discards the useful parts of the previous result.

**Why it fails:** Iteration destroys progress and user edits.

**Better direction:** Preserve accepted sections, support partial regeneration, diff changes, version history, and resumable recovery.

## 12. One-Off Agent

**Signal:** A recurring goal is treated as a new task every time, with repeated setup and no bounded learning.

**Why it fails:** The product never develops continuity.

**Better direction:** Consider persistent goals, saved policies, remembered preferences, monitoring, and exception-based escalation.

## 13. Autonomy Theater

**Signal:** The product is described as an agent but only generates recommendations that users must manually implement step by step.

**Why it fails:** Naming changes without a real execution model.

**Better direction:** Be honest about L1/L2 assistance, or add tool execution, permissions, activity history, verification, and recovery required for L3+ delegation.

## 14. Invisible Commitment Boundary

**Signal:** Drafting and sending, previewing and publishing, or proposing and deleting look nearly identical.

**Why it fails:** Users cannot tell when an action becomes externally consequential or irreversible.

**Better direction:** Visually and behaviorally distinguish suggestion, draft, prepared action, execution, and committed action. Place confirmation at the transition that matters.

## Diagnostic format

For every smell used in a review, state:

- **Evidence:** what in the flow triggered the smell
- **User Cost:** what burden or risk it creates
- **Root Cause:** which responsibility or interaction model is wrong
- **Replacement Pattern:** the concrete alternative
- **Severity:** High, Medium, or Low

Do not produce a smell checklist without redesign implications.
