# Method Foundations

Use this reference to understand the stable foundations behind the method and to cite primary sources when a formal or contested recommendation requires support. Apply the principles to the project; do not treat a framework citation as evidence that the project outcome will improve.

## Table of contents

1. Foundation map
2. Human-AI interaction
3. Usability and human-centered quality
4. Risk and lifecycle governance
5. Evidence use and citation rules

## 1. Foundation map

| Method component | Foundation | How this skill operationalizes it |
|---|---|---|
| Goal before feature | Human-centered design and user-needs framing | Start with trigger, outcome, users, context, and success |
| Effectiveness and efficiency | ISO 9241-11 usability concepts | Measure task outcome, resources used, and experience in context |
| AI timing and correction | Microsoft Guidelines for Human-AI Interaction | Define initial behavior, interaction-time behavior, error handling, and adaptation |
| Mental models, control, feedback, failure | Google People + AI Guidebook | Specify capability framing, feedback effects, controls, explanations, and graceful failure |
| Risk throughout the lifecycle | NIST AI Risk Management Framework | Govern, map, measure, and manage risk from concept through monitoring |
| Progressive autonomy | Human oversight and risk-based control | Increase initiative only with evidence, bounded authority, visibility, and recovery |
| Evidence-gated delivery | Product discovery, usability evaluation, and experimental reasoning | Separate claims from evidence, test the riskiest assumption, and predefine thresholds |

## 2. Human-AI interaction

Use the Microsoft *Guidelines for Human-AI Interaction* as a stable checklist across four moments:

- **Initially:** make clear what the system can do and how well it can do it.
- **During interaction:** act in context, support efficient invocation and dismissal, and avoid unnecessary disruption.
- **When wrong:** support correction, scoped recovery, and appropriate fallback.
- **Over time:** learn or adapt within disclosed boundaries, provide controls, and communicate changes.

Primary source:

- Saleema Amershi et al., “Guidelines for Human-AI Interaction,” CHI 2019: https://www.microsoft.com/en-us/research/publication/guidelines-for-human-ai-interaction/

Use the Google People + AI Guidebook for applied questions about user needs, defining success, data and evaluation, mental models, explainability and trust, feedback and control, and graceful failure.

Primary source:

- Google People + AI Guidebook: https://pair.withgoogle.com/guidebook-v2/chapters

Do not mechanically apply every guideline. Test relevance against the use context, user population, capability, error profile, and consequences.

## 3. Usability and human-centered quality

Use ISO 9241-11 as the foundation for treating usability as an outcome in a specified context of use, rather than as visual polish or satisfaction alone. Evaluate:

- **Effectiveness:** whether intended outcomes are achieved accurately and completely.
- **Efficiency:** the resources used in relation to achieved results.
- **Satisfaction:** the user's responses resulting from use.
- **Context of use:** users, goals, tasks, resources, and environment.

This skill extends the practical evaluation for AI systems with comprehensibility, cognitive load, control, recovery, trust calibration, accessibility, and AI-specific risks. Keep these extensions separate enough to diagnose tradeoffs.

Primary source:

- ISO 9241-11:2018 overview: https://www.iso.org/standard/63500.html

Do not cite ISO 9241-11 as prescribing this skill's exact process; the standard provides definitions and concepts, not the complete implementation method used here.

## 4. Risk and lifecycle governance

Use the NIST AI Risk Management Framework to keep risk work continuous and cross-functional:

- **Govern:** establish policies, roles, accountability, and risk tolerance.
- **Map:** understand context, users, intended use, impacts, and dependencies.
- **Measure:** assess system performance, trustworthiness characteristics, and uncertainty.
- **Manage:** prioritize, respond, monitor, and improve.

Translate this into the skill's stage gates, action-level autonomy decisions, evidence requirements, pilot boundaries, monitoring, and rollback.

Primary sources:

- NIST AI RMF overview: https://www.nist.gov/itl/ai-risk-management-framework
- NIST AI RMF 1.0: https://nvlpubs.nist.gov/nistpubs/ai/nist.ai.100-1.pdf
- NIST AI RMF Playbook: https://airc.nist.gov/airmf-resources/playbook/

Treat this as a risk-management foundation, not a claim of regulatory compliance. Identify applicable law, policy, accessibility, security, privacy, or sector standards separately when the project requires them.

## 5. Evidence use and citation rules

### Internalize by default

Use the stable principles without inserting citations into every routine design response. Keep the user's decision and evidence central.

### Cite when needed

Retrieve and cite primary sources when:

- The user requests formal rationale, literature, or citations
- A recommendation is disputed or high stakes
- The work will enter governance, procurement, policy, or executive review
- A current law, regulation, standard, or product-specific rule matters
- The exact scope or wording of a framework affects the decision

### Separate three forms of support

1. **Method support:** an external framework supports why a dimension should be considered.
2. **Project evidence:** observations, data, or tests support what is true in this project.
3. **Design reasoning:** an explicit inference connects project evidence to a proposed change.

Never use method support as a substitute for project evidence. Never imply that following a guideline proves efficiency, usability, safety, or compliance.

### Source quality

- Prefer standards bodies, original research, official framework owners, and project-primary evidence.
- Verify current versions when the information may have changed.
- Label inference and avoid unsupported universality.
- Keep quoted text brief; paraphrase operational implications.
