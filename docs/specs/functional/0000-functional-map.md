# ARYNTH Autopilot V1 — Functional Map

Status: Draft  
Specification Layer: Functional Map  
Current Stage: Stage 2  
Source of Truth: `../global/product-definition.md`

## 0.1 Purpose

This Functional Map translates the Final Global Spec into the functional areas that ARYNTH Autopilot V1 must support.

It defines the functional decomposition and dependency order for Stage 2.

It does not define detailed feature behavior, user-interface design, technical architecture, implementation mechanisms, provider selection, or code.

If a Functional Map decision would introduce product policy that is not established by the Final Global Spec, that decision must be treated as a gap rather than invented here.

## 0.2 Functional Areas

ARYNTH Autopilot V1 is divided into the following Stage 2 functional areas.

### 0001 — Workflow Entry & Scope

Defines the functional responsibilities for starting one V1 workflow from a user-defined content production goal and supported optional materials.

Covers the functional enforcement of V1 content boundaries and the one-target-outcome rule.

Primary Global Spec sources: 1.1, 1.4.

Planned file:

`0001-workflow-entry-and-scope.md`

### 0002 — Workflow Orchestration & Progress

Defines how ARYNTH functionally carries the defined goal through meaningful work toward the production-ready outcome without requiring the user to manually coordinate every intermediate step.

Covers meaningful progress, completed work, confirmed progress, and the relationship between current work and the target outcome.

It does not define technical orchestration architecture.

Primary Global Spec sources: 1.1, 1.3, 1.6, 1.7.

Planned file:

`0002-workflow-orchestration-and-progress.md`

### 0003 — Autonomy, Approval & Intervention

Defines the functional boundary between decisions ARYNTH may make autonomously and decisions that require user approval.

Also defines the functional responsibility to support user intervention while work is in progress.

It must not introduce approval requirements that are not permitted by the Global Spec.

Primary Global Spec source: 1.5.

Planned file:

`0003-autonomy-approval-and-intervention.md`

### 0004 — Workflow Visibility & Attention

Defines the meaningful workflow information that must remain understandable to the user.

Covers work in progress, completed work, meaningful changes, approval needs, blocking problems, required user attention, and production-ready outcome visibility.

It does not require exposure of low-level technical events or internal reasoning.

Primary Global Spec source: 1.6.

Planned file:

`0004-workflow-visibility-and-attention.md`

### 0005 — Quality, Confirmation & Completion

Defines the functional responsibilities around required checks, confirmed progress, final quality checks, and production-ready completion.

It defines when functional work may be treated as confirmed or production-ready without specifying detailed quality algorithms or scoring criteria.

Primary Global Spec sources: 1.1, 1.7, 1.9.

Planned file:

`0005-quality-confirmation-and-completion.md`

### 0006 — Continuity, Failure, Stop & Resume

Defines functional behavior for temporary interruptions, recoverable problems, waiting for user approval or necessary information, inability to continue, user stops, and user-directed continuation.

It preserves confirmed progress and truthful completion behavior without defining technical recovery mechanisms.

Primary Global Spec sources: 1.6, 1.7.

Planned file:

`0006-continuity-failure-stop-and-resume.md`

### 0007 — Cost & Spending Control

Defines the functional responsibilities for approved budgets, included usage, approved paid-resource allowances, spending authorization, cost uncertainty, approval before unauthorized spending, and meaningful spending visibility.

It does not define prices, plans, metering formulas, provider billing implementation, or model-routing economics.

Primary Global Spec source: 1.8.

Planned file:

`0007-cost-and-spending-control.md`

### 0008 — Review, Revision & Export

Defines the functional responsibilities after a production-ready outcome is reached.

Covers user review, export readiness, optional same-workflow revision, preservation of the current production-ready outcome during revision, repeated final quality checks, and replacement of the current outcome by a verified revised result.

Publishing or external distribution remains outside V1.

Primary Global Spec sources: 1.1, 1.4, 1.9.

Planned file:

`0008-review-revision-and-export.md`

## 0.3 Dependency Order

The default Stage 2 specification order is:

`0001 Workflow Entry & Scope`
→ `0002 Workflow Orchestration & Progress`
→ `0003 Autonomy, Approval & Intervention`
→ `0004 Workflow Visibility & Attention`
→ `0005 Quality, Confirmation & Completion`
→ `0006 Continuity, Failure, Stop & Resume`
→ `0007 Cost & Spending Control`
→ `0008 Review, Revision & Export`

This order represents specification dependency, not necessarily runtime execution order.

Later Functional Map files may reference earlier areas where necessary, but they must not redefine product policy already established by the Global Spec.

## 0.4 Cross-Cutting Rules

All Stage 2 functional areas must preserve the following Global Spec constraints:

- one V1 workflow begins from one content production goal;
- one workflow has one target production-ready outcome;
- ARYNTH proceeds autonomously by default within established boundaries;
- user approval is required only where the Global Spec permits or requires it;
- meaningful workflow state must remain understandable;
- confirmed progress must be preserved according to the continuity rules;
- incomplete work must not be represented as successful completion;
- spending must remain within the established authorization boundaries;
- revisions remain inside the same workflow;
- the current production-ready outcome remains valid until a verified revision replaces it;
- publishing and external distribution remain outside V1.

## 0.5 Stage 2 Boundaries

The Functional Map may define:

- functional responsibilities;
- functional flows;
- functional states where needed to explain behavior;
- user-visible functional obligations;
- functional dependencies;
- entry and exit conditions between functional areas;
- behavior required by Global Spec rules.

The Functional Map must not define:

- implementation architecture;
- databases;
- storage design;
- API design;
- authentication implementation;
- infrastructure;
- deployment;
- framework or programming-language choices;
- model-provider architecture;
- detailed retry or timeout mechanisms;
- detailed billing implementation;
- visual design;
- user stories;
- work plans;
- code.

Exact supported formats, detailed limits, exact quality criteria, revision limits, version-history mechanics, export formats, pricing details, and technical enforcement remain deferred to their appropriate later specification layers.

## 0.6 Stage 2 Completion Standard

Stage 2 is complete only when:

- every required V1 functional responsibility from the Final Global Spec has a clear place in the Functional Map;
- no material product policy has been invented outside the Global Spec;
- functional areas do not contradict or unnecessarily duplicate one another;
- entry, progress, approval, visibility, completion, continuity, spending, revision, and export responsibilities are functionally connected;
- later Feature Specs can be derived from the Functional Map without inventing missing functional behavior;
- a final cross-document Functional Map audit finds no remaining Stage 2 blocker.

Until those conditions are met, Stage 2 remains Draft.
