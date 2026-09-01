# Worked Examples

Use these examples as patterns, not fixed answers. Adapt autonomy, guardrails, and interaction patterns to the domain and evidence.

## Table of contents

1. CRM follow-up
2. Research search
3. Long-form writing
4. Cross-tool workflow automation

## 1. CRM follow-up

### Input

```text
Select a customer → click “Write follow-up” → enter a prompt → generate →
copy → open email → paste → send.
```

### Review setup

- **Ambition:** Dual-track
- **Constraint:** Keep the CRM and email provider for the next release
- **Frequency:** Frequent
- **Risk:** Medium; external communication and reputation
- **Current Autonomy:** L1

### Goal

Follow up with the right customer at the right time using an accurate, relationship-aware message.

### Key friction

1. **Prompt Box Everywhere — High:** The CRM already has the customer context, but the user must translate it into a prompt.
2. **User as API Router — High:** The user moves content between CRM and email.
3. **AI as a Button — High:** AI generates text but does not help identify timing, prepare the action, or track the outcome.
4. **AI Dead End — Medium:** The draft is detached from sending, editing, and follow-up monitoring.

### Opportunity map

| Current Step | Proposed AI Role | Required Context | User Role | Risk |
|---|---|---|---|---|
| Choose whom to follow up | Suggest | Relationship stage, last contact, tasks | Confirm priority | Medium |
| Write prompt | Remove/Infer | Customer and account history | Correct assumptions | Low |
| Draft email | Generate/Prepare | Tone, purpose, prior messages | Edit or approve | Medium |
| Copy and paste | Remove/Execute | Email integration | None | Low |
| Send | Execute after approval | Recipient and final draft | Confirm commitment | Medium |
| Check for reply | Monitor | Inbox permission and policy | Handle exception | Medium |

### Practical target

```text
CRM highlights “Follow up recommended” → User opens suggestion →
AI shows an editable draft with customer context used → User edits/approves →
AI sends through the connected provider → CRM logs the action
```

### North Star

```text
User defines follow-up policy and tone → AI monitors relationship signals →
AI prepares prioritized drafts → User reviews an exception/approval inbox →
AI sends approved messages → AI monitors replies and updates the relationship plan
```

### Key interaction

- Contextual suggestion in the customer record
- Editable draft with source context and missing-data warnings
- Clear Send commitment boundary
- Activity history and cancel window where supported
- Exception inbox for ambiguous or sensitive accounts

### Guardrails

- Generate without confirmation
- Require approval before first external send and for sensitive accounts
- Never invent customer facts; show missing context
- Restrict recipients to the selected account
- Log sent content and source context
- Escalate uncertain tone, legal claims, or conflicting contact policies

### Decision

Move from L1 to L3 for individual follow-ups, then consider bounded L4 monitoring after policy and quality validation.

## 2. Research search

### Input

```text
Enter query → scan results → open many tabs → copy passages →
paste into notes → ask AI to summarize → manually add citations.
```

### Goal

Build a trustworthy answer to a research question with clear evidence, coverage, and uncertainty.

### Key friction

- The user translates the research goal into many separate searches.
- Context and evidence are manually transported between browser and notes.
- Summarization happens after source collection, so gaps are found late.
- Citations and claim-to-source links are reconstructed manually.
- A chat-only output makes comparison and evidence inspection difficult.

### Practical target

```text
User states question and constraints → AI proposes research facets →
User adjusts scope → AI searches and builds an evidence table →
User inspects sources and gaps → AI drafts a cited synthesis →
User edits claims or requests deeper coverage
```

### North Star

```text
User defines an evidence standard and decision deadline →
AI maintains a living evidence map across approved sources →
AI flags new evidence, contradictions, and stale claims →
User decides on contested interpretations →
AI updates the synthesis and provenance graph
```

### Interaction specification

- Use a structured evidence table beside the narrative, not chat alone.
- Let users filter by claim, source type, date, and confidence.
- Mark fact, inference, and unresolved disagreement distinctly.
- Support accept/reject at the claim level and preserve manual edits.
- Show coverage gaps and failed searches as first-class states.

### Guardrails

- Keep source links and claim provenance.
- Do not silently upgrade inference to fact.
- Ask before using restricted or sensitive sources.
- Use L2/L3 for synthesis; keep interpretation and consequential decisions with the user.

## 3. Long-form writing

### Input

```text
Choose template → fill many fields → write prompt → generate entire document →
regenerate repeatedly → copy final text into the editor.
```

### Goal

Develop a coherent document that reflects the author's intent, evidence, voice, and constraints while preserving control over important choices.

### Key friction

- The user must know the document structure before exploring the idea.
- Required context is fragmented across fields and prompts.
- Whole-document regeneration destroys accepted content and manual edits.
- AI output is separated from the actual editing surface.

### Practical target

```text
User states audience, outcome, and source material → AI proposes an editable outline →
User steers the argument → AI drafts section by section in the editor →
User accepts, edits, or compares changes → AI checks coherence and unresolved claims
```

### North Star

```text
User maintains an evolving brief and evidence set →
AI acts as a context-aware coauthor inside the document →
AI proposes targeted changes with diffs and rationale →
User retains authorship decisions →
AI learns bounded style preferences and checks consistency over time
```

### Interaction specification

- Direct manipulation and inline suggestions for local edits
- Outline canvas for structure
- Diff/compare for revisions
- “Keep this section” and partial regeneration
- Source panel for factual claims
- Version history and explicit publication boundary

### Guardrails

- Never overwrite user edits silently.
- Separate style suggestions from factual corrections.
- Require provenance for important factual claims.
- Keep publication or external sharing as an explicit commitment.
- Use L2 by default; use L3 only for bounded transformations the user can review and undo.

## 4. Cross-tool workflow automation

### Input

```text
Read a support ticket → check account data → ask engineering for status →
update the ticket → message the customer → create a follow-up task.
```

### Goal

Resolve customer issues accurately and quickly while coordinating the necessary systems and people.

### Key friction

- The user manually orchestrates several tools and dependencies.
- Each system has partial context, so the user reconciles identities and status.
- The flow restarts whenever another team replies.
- Sending an update and creating follow-up tasks are repetitive but consequential.

### Practical target

```text
Agent opens ticket with unified authorized context → AI suggests issue classification and plan →
User corrects scope → AI prepares internal query, customer draft, and follow-up task →
User approves selected actions → AI executes and records results →
Ticket shows pending dependencies and recovery options
```

### North Star

```text
Team defines resolution policies, permission boundaries, and service goals →
AI monitors incoming tickets and relevant system changes →
AI resolves routine cases within policy →
AI escalates ambiguity, high impact, or policy exceptions with a concise evidence packet →
AI verifies outcomes, updates records, and learns from reviewed exceptions
```

### Autonomy progression

```text
L1 classification → L2 prepared actions → L3 bounded resolution →
L4 monitoring and exception handling
```

### Guardrails

- Resolve identity across tools before acting.
- Limit data access and action scope to the ticket and account.
- Require approval for refunds, sensitive disclosures, or commitments outside policy.
- Show every external message before first use of a policy.
- Maintain per-step status, activity history, and compensating actions.
- Stop after repeated tool failures or conflicting records; escalate with evidence.

### What to prototype

Prototype the unified ticket view, selected-action approval, and partial-failure recovery. Test whether agents understand what will be committed, can correct AI assumptions quickly, and can recover without restarting the case.
