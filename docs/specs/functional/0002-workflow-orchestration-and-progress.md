# ARYNTH Autopilot V1 — Workflow Orchestration & Progress

Status: Draft  
Specification Layer: Functional Map  
Current Stage: Stage 2  
Functional Area: 0002  
Source of Truth: `../global/product-definition.md`  
Stage Map: `0000-functional-map.md`

## 2.1 Purpose & Authority

**2.1.1 Purpose.** This document defines how ARYNTH functionally carries a begun V1 workflow through meaningful work toward its one target outcome, so that the user does not have to act as the manual workflow manager (GS 1.3) and V1 can show that one content production goal can be carried reliably from intent to a production-ready outcome without the user manually coordinating every step (GS 1.1). It does not define technical orchestration architecture.

**2.1.2 Ownership.** This document owns the Functional Map behavior for:

- receipt of a begun workflow from 0001;
- meaningful work as the functional unit of progression;
- determination of the next meaningful work;
- sequencing and adaptation of remaining work;
- execution strategy, including the use of associated supported materials during progression;
- the relationship of current work to the one target outcome;
- the functional progress distinctions;
- confirmed progress as the basis for later dependent work;
- reopening confirmed work;
- routing completed work to required checks and selecting corrective work;
- reassessment of remaining work;
- the orchestration consequence of pending approvals, necessary information and cost authorization;
- detection and routing of scope issues discovered during progression;
- progression of revision work;
- detection of handoffs to other functional areas;
- the determinable progress state;
- ending, suspending and re-engaging active progression;
- the manual-coordination guard.

**2.1.3 Authority.** This document derives its authority from:

- the Final Global Spec, sections 1.1–1.9;
- the Stage Map (0000);
- 0001 Workflow Entry & Scope, including the founder decisions applied there;
- the following founder-approved Stage 2 decisions:
  - Decision 0002-A — progression basis, applied in §2.5;
  - Decision 0002-B — reopening confirmed work, applied in §2.8;
  - Decision 0002-C — scope of waiting, applied in §2.7;
  - Decision 0002-D — concurrent meaningful work, applied in §2.7.

**2.1.4 Global Spec sources.** The Stage Map names GS 1.1, 1.3, 1.6 and 1.7 as the primary sources of this area. This document also applies GS 1.5 (ARYNTH's autonomy over workflow decisions and the approval boundary), GS 1.8 (spending authorization as a limit on progression) and GS 1.9 (progression of revisions within the same workflow). It applies those sections and does not redefine them.

**2.1.5 Precedence.** The Global Spec prevails over this document. The Stage Map and 0001 prevail over this document where they establish a rule. A rule in this document that conflicts with any of them is a defect in this document and does not apply. Founder decisions refine the Global Spec within its boundaries and do not override it.

**2.1.6 Not owned.** This document does not define entry or scope classification (0001), approval and intervention behavior (0003), visibility and attention (0004), required checks, confirmation and completion (0005), waiting, interruption, failure, stopping and continuation (0006), spending control (0007), or review, revision intake and export (0008). Where this document relies on those areas, it states only the orchestration rule and names the owning area (§2.15.1). Rules this document depends on that those areas must still define are listed in §2.15.2. Details deferred to later specification layers are listed in §2.16.

**2.1.7 Conventions.**

- "Must", "must not" and "may" state requirements, prohibitions and permissions.
- "GS 1.x" refers to a Global Spec section, and "¶n" to its nth paragraph. "§2.x" refers to a section of this document. "0001 §1.x" refers to a section of 0001, and "0000 §0.x" to a section of the Stage Map. Four-digit numbers refer to Functional Map areas.
- Each rule in §2.3–§2.14 states its basis:
  - [GS 1.x] — established by the Global Spec;
  - [0000 §0.x] or [0001 §1.x] — established by an earlier Functional Map document;
  - [0002-A], [0002-B], [0002-C], [0002-D] — founder-approved Stage 2 decision;
  - [Derived: …] — a Functional Map rule that follows from the cited sources without adding product policy.

## 2.2 Functional Definitions

The definitions in 0001 §1.2 apply in this document, including workflow, content production goal, supporting material, supported input, excluded input, unsupported material, target outcome, intermediate option, working alternative, in-progress workflow, stopped workflow, completed workflow, material part and incidental part. The following definitions also apply. They describe functional meaning only.

- **Progression** — ARYNTH's carrying of an in-progress workflow through meaningful work toward its target outcome, including revision work (§2.11).
- **Meaningful work** — work at the level defined in §2.4.1. A **meaningful work item** is one identifiable unit of meaningful work (§2.4.3).
- **Result** — what a meaningful work item produces toward the target outcome (§2.4.5).
- **Remaining work** — the meaningful work that ARYNTH currently determines is still needed to reach the target outcome and has not been completed. Remaining work is ARYNTH's current determination. It is not a commitment to the user or a plan the user must approve or manage (§2.6.8).
- **Active meaningful work** — the one meaningful work item that ARYNTH is progressing at a given time (§2.7.1).
- **Completed work** — meaningful work whose result has been produced.
- **Completed but unconfirmed work** — completed work that is not confirmed work.
- **Confirmed work** — completed work that 0005 treats as confirmed, so that it forms part of a confirmed state within the meaning of GS 1.1.
- **Changed confirmed work** — confirmed work that has been changed since it was last confirmed and has not yet been treated as confirmed again in its changed form (GS 1.6).
- **Dropped work** — remaining work that ARYNTH has dropped because it is no longer needed (§2.9.10). Dropped work was never completed.
- **Discarded result** — the result of completed work that ARYNTH has discarded from current progress (§2.9.10). The work that produced it remains completed work.
- **Required check** — a check that 0005 requires for a result, including the required final quality checks for the target outcome (GS 1.1). Which results require checks, and the criteria of any check, are owned by 0005.
- **Dependency on a result** — meaningful work depends on a result when it uses, builds on or must be consistent with that result.
- **Pending item** — a matter that progression awaits from another owning area: user approval required under GS 1.5, including approval at a user-requested approval point; necessary information under GS 1.6; or cost authorization under GS 1.8.
- **Dependency on a pending item** — meaningful work depends on a pending item when the pending answer could change whether that work is needed or what that work must be (§2.7.4).
- **Independent work** — meaningful work that does not depend on the result or pending item in question.
- **Held work** — dependent work that is not selected while the pending item it depends on remains unresolved (§2.7.5).
- **Corrective work** — meaningful work that ARYNTH selects because a result did not pass a required check (§2.9).
- **Reopening** — ARYNTH's changing of confirmed work (§2.8).
- **Reassessment** — ARYNTH's redetermination of remaining work and of the next meaningful work (§2.9).
- **Revision work** — meaningful work performed to produce a revised result after a revision has validly begun under 0008 (§2.11).
- **Legitimate user touchpoint** — a path from orchestration to the user that has authority under §2.14.2.

## 2.3 Handoff & Orchestration Ownership

**2.3.1 Receipt of the workflow.** Responsibility for progression passes to this document at the moment a workflow begins under 0001 §1.3.2. [0001 §1.12.1]

**2.3.2 Starting state.** Progression starts from the state established at handoff under 0001 §1.12.2, including the sufficient goal, the one target outcome, a scope classification resolved sufficiently for work to proceed, and the associated supported materials. User instructions carried forward under 0001 §1.3.4 are applied through the areas that own them, such as requested approval points through 0003 and spending instructions through 0007. [0001 §1.3.4, §1.12.2]

**2.3.3 No re-entry.** Progression must not re-apply the entry conditions to a begun workflow. ARYNTH must not require the user to restate or reconfirm the goal, or to approve ARYNTH's interpretation of it or a plan for pursuing it, unless the user has requested such an approval point. [GS 1.5; 0001 §1.3.5, §1.12.4]

**2.3.4 Coordination belongs to ARYNTH.** From handoff, ARYNTH, not the user, keeps track of what meaningful work has been completed, what needs checking, what has changed and what must happen next. [GS 1.1, GS 1.3]

**2.3.5 Workflow decisions belong to ARYNTH.** Determining the next meaningful work, the sequence of meaningful work, the execution strategy, corrective work and the reassessment of remaining work are workflow decisions. ARYNTH makes them autonomously. The user is involved in them only through a legitimate user touchpoint (§2.14). [GS 1.5; 0001 §1.4.6]

**2.3.6 One workflow.** Progression concerns only the workflow being progressed. ARYNTH must not begin, queue, switch to or progress another workflow as part of progression. [0001 §1.3.1, §1.9.1, §1.9.5]

**2.3.7 One target outcome.** All meaningful work must serve the workflow's one target outcome. Intermediate options, working alternatives and internal artifacts produced along the way are means to that outcome. They do not become additional target outcomes or separately promised deliverables. ARYNTH must not perform work toward an out-of-scope part of the goal that has been set aside, toward a separate non-video companion deliverable, or toward any additional target outcome. [0001 §1.6.2, §1.7.4, §1.8.1, §1.8.2]

## 2.4 Meaningful Work

**2.4.1 Definition.** Meaningful work is work at the level the user would otherwise have to coordinate as part of carrying the content production goal toward the target outcome. It is the level of workflow progress described in GS 1.2 and GS 1.3, such as research, scripting, generation and editing preparation. These examples illustrate the level of meaningful work. They are not required stages. [Derived: GS 1.2, GS 1.3, GS 1.6]

**2.4.2 Exclusions.** Individual model or tool calls, technical events, internal reasoning steps, internal retries and other implementation mechanics are not meaningful work. They may be performed within a meaningful work item, but they are not units of progression. [GS 1.6 ¶4]

**2.4.3 Identifiable items.** Each meaningful work item must be identifiable by what it contributes toward the target outcome, so that it can be understood as meaningful work in progress or completed within the meaning of GS 1.6. How items are presented is owned by 0004. [Derived: GS 1.6]

**2.4.4 Granularity.** A meaningful work item must not be so broad that identifying it no longer conveys what ARYNTH is working on, as when the production of the whole video is treated as a single item. It must not be so narrow that it represents internal execution under §2.4.2. Detailed granularity criteria are deferred (§2.16). [Derived: GS 1.6; 0002-D]

**2.4.5 Results.** A completed meaningful work item has a result. A result may be subject to a required check (§2.9), may serve as the basis for dependent work (§2.5) and may become confirmed work. [Derived: GS 1.1]

**2.4.6 No fixed pipeline.** V1 does not define a fixed set or sequence of stages that every workflow must follow. The meaningful work a workflow needs, and its order, are determined for that workflow by ARYNTH (§2.6) and may differ between workflows. [GS 1.5; 0000 §0.1; 0001 §1.4.6, §1.5.5]

**2.4.7 Adaptation.** The meaningful work in a workflow may adapt to:

- the goal;
- the associated supported materials;
- results so far;
- the results of required checks;
- changes resolved through 0003;
- supported material received after entry;
- continuation through 0006;
- revision work under 0008.

[Derived: GS 1.5, GS 1.7, GS 1.9]

**2.4.8 What remains stable.** However the meaningful work adapts, the following remain fixed except as changed through the rules that govern them:

1. the goal, as defined at entry or as changed through 0003;
2. the one target outcome;
3. confirmed work, except as reopened under §2.8;
4. prior user-approved decisions, except as changed under GS 1.5;
5. materials and uses the goal expressly requires;
6. the exclusion of out-of-scope parts that have been set aside.

[GS 1.5; 0001 §1.5.6, §1.7.4, §1.8.1; 0002-B]

## 2.5 Progression Basis

**2.5.1 Confirmed basis.** Meaningful work that depends on a result subject to a required check may begin only after that result is confirmed. [0002-A; GS 1.1]

**2.5.2 Independent work.** Meaningful work that does not depend on such a result is not blocked by that result's pending confirmation. [0002-A]

**2.5.3 No check, no gate.** A result for which 0005 requires no check creates no confirmation gate for work that depends on it. [0002-A]

**2.5.4 Confirmation not defined here.** This document does not define which results require checks, the criteria of any check, or when a result becomes confirmed. Those are owned by 0005. Where confirmation also involves user approval under GS 1.1, whether that approval is required is determined by GS 1.5 and handled by 0003. Progression must not treat user approval as a routine step of confirmation. [GS 1.1, GS 1.5; 0000 §0.2]

**2.5.5 Changed basis.** When confirmed work is reopened and changed (§2.8), and the changed work is subject to a required check, dependent work that has not yet begun may begin only after the changed work is confirmed. Dependent work that already rests on the prior confirmed form is reassessed under §2.9. [0002-A; Derived: GS 1.6]

## 2.6 Selecting & Sequencing Work

**2.6.1 ARYNTH determines the next work.** ARYNTH determines what meaningful work happens next. [GS 1.3, GS 1.5]

**2.6.2 Work that may validly progress.** Meaningful work may validly progress only when all of the following hold:

1. it serves the one target outcome and is within V1 scope as classified under 0001 §1.6 (§2.3.7, §2.10);
2. any confirmed basis required by §2.5 exists;
3. it is not held under §2.7;
4. it does not require a decision, information or paid action for which a handoff is required under §2.13.1 and has not been resolved;
5. it does not use excluded input or unsupported material.

[Derived: GS 1.4, GS 1.5, GS 1.6, GS 1.8; 0001 §1.5.7, §1.5.8, §1.6; 0002-A, 0002-C]

**2.6.3 Continuous progression.** While meaningful work may validly progress, ARYNTH progresses it without waiting for a user instruction to proceed. [GS 1.1, GS 1.3, GS 1.5 ¶1]

**2.6.4 Selection.** ARYNTH selects the next meaningful work from the work that may validly progress, with a view to carrying the workflow reliably to its target outcome within the established spending boundaries. [Derived: GS 1.1, GS 1.8]

**2.6.5 Sequence and remaining work.** ARYNTH determines the sequence of meaningful work and may revise it, and the remaining work, whenever reassessment requires (§2.9). Revising the sequence or remaining work is a workflow decision and requires no user approval, unless the revision would materially change the goal, would override a prior user-approved decision, including a sequence or plan the user approved at an approval point the user requested, or would require spending that is not already authorized. [GS 1.5, GS 1.8; 0001 §1.3.5]

**2.6.6 Execution strategy.** ARYNTH determines how each meaningful work item is performed, including the approach, which of the approved AI tools and models are used, and how associated supported materials are used. Changing the execution strategy is a workflow decision within the same boundary as §2.6.5. Selecting among approved AI tools and models is not a user decision, except at an approval point the user has requested. The composition of the set of approved AI tools and models is deferred (§2.16). [GS 1.1, GS 1.5; 0001 §1.5.5]

**2.6.7 Strategy and the goal.** A change to the execution strategy is a material change to the goal when its effect on the target outcome would materially change the user's content production goal within the meaning of GS 1.5. Such a change requires approval under GS 1.5, handled by 0003, however it is described, including where it would reduce cost or avoid the need for cost authorization. The criteria of materiality are deferred (0001 §1.14). [GS 1.5, GS 1.8; 0001 §1.7.7]

**2.6.8 Remaining work is not a user plan.** Remaining work does not require user approval and is not a list the user must manage or advance. Whether and how remaining work is made understandable is owned by 0004. [GS 1.5, GS 1.6; 0001 §1.3.5]

**2.6.9 Supporting materials.** How associated supported materials are used during progression is an ARYNTH decision, unless the goal expressly requires a particular material or use. A goal-required material or use is honored. Proceeding without honoring it requires approval under GS 1.5 where doing so would materially change the goal or override a prior user-approved decision. ARYNTH must not use excluded input or unsupported material. [0001 §1.5.5–§1.5.8]

**2.6.10 Working alternatives.** ARYNTH may produce intermediate options and working alternatives as means to the target outcome. Choosing among them is an ARYNTH decision. ARYNTH must not present them for the user to choose among unless the user has asked to choose, which is a user-requested approval point owned by 0003. [GS 1.5; 0001 §1.8.2, §1.8.3]

**2.6.11 Spending.** Meaningful work whose paid actions remain within the user's approved budget, included usage or approved paid-resource allowance proceeds without separate approval. Before initiating a paid action that would, or that available cost information indicates reasonably could, create a paid charge not already authorized, exceed the remaining approved budget or consume usage beyond an approved paid-resource allowance, ARYNTH hands the matter off to 0007 under §2.13.1. [GS 1.8]

## 2.7 Active Work & Dependency-Scoped Holding

**2.7.1 One active item.** At the functional level, ARYNTH progresses one active meaningful work item at a time. [0002-D]

**2.7.2 Internal parallelism.** This document does not prohibit parallel execution below the meaningful-work level within the active item. The execution concurrency model is deferred to later technical specification (§2.16). [0002-D; GS 1.6 ¶4]

**2.7.3 Duration of activity.** A meaningful work item remains the active item until its result is completed and any required check of that result has been performed and the check result incorporated under §2.9, unless it stops being active earlier under §2.7.5 or §2.7.7. Where confirmation of the result also awaits user approval, that approval is a pending item and §2.7.4–§2.7.10 apply. [Derived: 0002-A, 0002-D]

**2.7.4 Dependency on a pending item.** While a pending item is unresolved, meaningful work depends on it when the pending answer could change whether that work is needed or what that work must be. The following are always dependent:

1. the work whose decision, information or paid action is the subject of the pending item;
2. work placed behind a user-requested approval point, which depends on that approval.

[0002-C]

**2.7.5 Held work is not selected.** Dependent work is held while the pending item remains unresolved. ARYNTH must not select held work as the active item, make a decision that awaits approval, proceed on information that has not been provided, or initiate a paid action that awaits authorization. If the active item becomes dependent on a pending item, it stops being active. [0002-C; GS 1.5, GS 1.7 ¶3, GS 1.8]

**2.7.6 Doubt about dependency.** Work is independent of a pending item only when the pending answer could not change whether that work is needed or what that work must be. Where ARYNTH cannot determine this, the work is dependent. [Derived: 0002-C]

**2.7.7 Changing the active item.** ARYNTH may change which item is active when the active item becomes held or when reassessment (§2.9) determines that other work should come first. An item that stops being active before completion returns to remaining work or is dropped under §2.9.10. Partial progress on such an item is not confirmed work. [Derived: GS 1.5; 0002-D]

**2.7.8 Independent work continues.** Independent meaningful work that may validly progress (§2.6.2) may continue while a pending item is unresolved. [0002-C]

**2.7.9 Whole-workflow waiting.** The whole workflow waits only when no independent meaningful work remains that may validly progress. [0002-C; GS 1.7 ¶3]

**2.7.10 Release.** When a pending item is resolved through its owning area, whether by approval, refusal, provision of information or authorization, work held on account of that item is no longer held on that account, and ARYNTH reassesses remaining work in light of the resolution (§2.9). [Derived: 0002-C; GS 1.5, GS 1.7]

**2.7.11 Orchestration consequence only.** This section defines only which work is selected while a pending item is unresolved. Approval behavior is owned by 0003. Information requests and attention are owned by 0004 and 0006. Waiting, interruption and continuation are owned by 0006. Cost authorization is owned by 0007. [0000 §0.2; 0002-C]

**2.7.12 No manufactured pending items.** A pending item may arise only from a legitimate user touchpoint (§2.14.2). ARYNTH must not create a pending item in order to hand a workflow decision to the user. [GS 1.5 ¶3, GS 1.6 ¶3]

## 2.8 Confirmed Progress & Reopening

**2.8.1 Confirmed work is the basis.** Progression continues from the latest confirmed state and builds on confirmed work. ARYNTH must not redo, replace or change confirmed work except by reopening it under this section. [GS 1.1, GS 1.7; 0002-B]

**2.8.2 Necessity only.** ARYNTH may reopen confirmed work only when reaching the target outcome requires it, including when:

1. later work cannot pass required checks or reach production-ready completion without changing it; or
2. a goal change resolved through 0003, or a revision under 0008, makes the confirmed work inconsistent with the current goal.

[0002-B]

**2.8.3 No discretionary reopening.** ARYNTH must not reopen confirmed work merely because it believes further discretionary improvement may be possible. [0002-B]

**2.8.4 Approval boundary.** Where reopening would override a prior user-approved decision or materially change the goal, approval is required under GS 1.5 and is handled by 0003. Until approval is given, the reopening is a pending item (§2.7). Where reopening would require a paid action that is not already authorized, §2.6.11 applies. Otherwise reopening is a workflow decision and requires no approval. This document creates no other approval requirement for reopening. [GS 1.5, GS 1.8; 0002-B]

**2.8.5 Rework after a goal change.** Where a goal change resolved through 0003 makes confirmed work that embodies a prior user-approved decision inconsistent with the current goal, whether the goal change itself authorizes the resulting rework, or whether approval under GS 1.5 is still required, is determined by 0003 (§2.15.2). [GS 1.5; 0000 §0.2]

**2.8.6 Changed confirmed work.** Confirmed work that has been reopened and changed is changed confirmed work. It is not treated as confirmed in its changed form until 0005 treats it as confirmed. [GS 1.1, GS 1.6; 0000 §0.2]

**2.8.7 Dependent work after reopening.** When confirmed work is reopened, ARYNTH reassesses the meaningful work that depends on it (§2.9). Whether dependent confirmed work remains confirmed when its basis changes is determined by 0005 (§2.15.2). [0002-A, 0002-B; 0000 §0.2]

**2.8.8 Preservation not defined here.** Reopening does not determine what is preserved or what the latest confirmed state is for continuation. Those are owned by 0006. [GS 1.7; 0000 §0.2]

**2.8.9 Changes must be understandable.** Meaningful changes to completed work since it was last confirmed must be understandable to the user. How they are made understandable is owned by 0004. [GS 1.6]

**2.8.10 Completed but unconfirmed work.** This section does not protect completed but unconfirmed work. ARYNTH may revise or replace it, or discard its result from current progress under §2.9.10, as a workflow decision, subject to GS 1.5 and GS 1.8. [GS 1.5, GS 1.7 ¶1, GS 1.8; Derived: 0002-B]

## 2.9 Checks, Corrective Work & Reassessment

**2.9.1 Routing to checks.** When the result of a meaningful work item is subject to a required check, ARYNTH routes that result to the check. What is checked, and how, is owned by 0005. [GS 1.1; 0000 §0.2]

**2.9.2 Passed.** When 0005 treats the result as confirmed, it becomes confirmed work and may serve as the basis for dependent work (§2.5). [GS 1.1; 0002-A]

**2.9.3 Not passed.** When 0005 reports that a result did not pass a required check, the result does not become confirmed and does not serve as the basis for dependent work (§2.5.1). ARYNTH selects corrective work. [GS 1.1; 0002-A]

**2.9.4 Corrective work belongs to ARYNTH.** Selecting corrective work is a workflow decision. It may include revising the result, redoing the work, changing the approach, tools, models or use of materials, or revising the remaining work or its sequence. It is subject to §2.6.5–§2.6.7, and to §2.8 where it would reopen confirmed work. A failed required check is not by itself a legitimate user touchpoint (§2.14.4). [GS 1.5; 0002-B]

**2.9.5 Corrected results.** A corrected result is routed to required checks under §2.9.1 before it can be confirmed. [GS 1.1]

**2.9.6 Repeated failure.** This document does not define when repeated failure to pass required checks means that ARYNTH cannot continue. That boundary is owned by 0006, subject to 0007 (§2.15.2). Corrective work remains subject to spending authorization at all times (§2.6.11). [GS 1.7, GS 1.8; 0000 §0.2]

**2.9.7 Final checks.** When a result is the completed video intended as the target outcome, it is routed to the required final quality checks. Production-ready completion is determined by 0005, and progression ends under §2.13.5. [GS 1.1, GS 1.9 ¶1]

**2.9.8 Reassessment triggers.** ARYNTH reassesses remaining work after:

1. a result does not pass a required check;
2. an intervention or goal change is resolved through 0003;
3. supported material is received after entry (§2.10.3);
4. confirmed work is reopened;
5. a pending item is resolved (§2.7.10);
6. control returns from 0006;
7. revision work begins under 0008 (§2.11).

ARYNTH may also reassess at any other point in progression. [Derived: GS 1.3, GS 1.5, GS 1.7, GS 1.9]

**2.9.9 Content of reassessment.** Reassessment determines:

1. which remaining work is still needed and what it must be;
2. whether confirmed work must be reopened, which may occur only under §2.8;
3. which results of completed but unconfirmed work remain usable;
4. which work depends on any unresolved pending item (§2.7);
5. the next meaningful work (§2.6).

[Derived: GS 1.3; 0002-A, 0002-B, 0002-C]

**2.9.10 Dropped work and discarded results.** Reassessment distinguishes dropping unperformed remaining work from discarding the result of completed work from current progress:

1. **Dropping unperformed remaining work.** Remaining work that reassessment finds is no longer needed is dropped from remaining work, including an item that stopped being active before completion (§2.7.7). Dropped work was never completed and must not be represented as performed, completed, pending or confirmed.
2. **Discarding the result of completed work.** Where the result of completed work becomes unusable, obsolete or unnecessary, ARYNTH may discard that result from current progress. The result of confirmed work may be discarded only through reopening under §2.8. Discarding a result does not change the fact that the work was performed, and the work remains completed work. The discarded result:
   - does not count as current usable progress;
   - must not be treated or represented as pending;
   - does not acquire confirmed status by being discarded, and is identifiable as confirmed only if it satisfied confirmation under 0005 before it was discarded;
   - must not serve as the basis for later dependent work merely because it once existed (§2.5).

Completed work whose result has been discarded remains distinguishable from completed work whose result forms part of current progress (§2.12.5). This rule does not define how completed work is presented, how long records of it are kept, or how results are stored or versioned. [GS 1.5, GS 1.6, GS 1.7 ¶4; 0002-A, 0002-B; Derived: 0001 §1.7.4]

**2.9.11 Retained work.** Completed work that remains consistent with the current goal may be retained. Retained work that is not confirmed still requires confirmation before it serves as the basis for dependent work under §2.5.1. [0002-A]

**2.9.12 Reassessment belongs to ARYNTH.** Reassessment is a workflow decision. It requires no user approval unless a resulting decision falls within §2.6.5, §2.6.7 or §2.8.4. [GS 1.5]

## 2.10 Changes, New Materials & Scope Discovery

**2.10.1 Changes resolved through 0003.** User interventions and changes to the goal are received and resolved by 0003, including whether an intervention changes the goal and whether any approval is required. After 0003 resolves an intervention or goal change, progression continues on the goal as it then stands, and ARYNTH reassesses remaining work (§2.9). Where resolving it leaves a pending item, §2.7 applies. [GS 1.5; 0001 §1.10.4]

**2.10.2 Work affected by a change.** After a goal change, confirmed work that is inconsistent with the current goal is reopened only under §2.8. Remaining work and completed but unconfirmed work are handled under §2.9.10 and §2.9.11. [0002-B; Derived: GS 1.5]

**2.10.3 Materials received after entry.** Supporting material supplied after a workflow begins is received through the areas that own that interaction (0003, 0004, 0006) and classified under 0001 §1.5. Once supported material is associated with the workflow, its use is an ARYNTH decision under §2.6.9, and ARYNTH reassesses remaining work. Excluded input and unsupported material are not used. [0001 §1.5.11]

**2.10.4 Scope discovery.** If ARYNTH determines during progression that part of the goal requires something outside V1 scope as classified under 0001 §1.6, or that an associated material is excluded input or unsupported material, ARYNTH must identify the issue, must not progress work toward that part or use that material, and must handle it under §2.10.6–§2.10.8. A problem that prevents work for another reason, such as a temporary interruption or a recoverable problem, is not a scope issue and is governed by 0006. [0001 §1.6; Derived: GS 1.4, GS 1.5]

**2.10.5 One scope policy.** 0001 §1.6 remains the only V1 scope classification. This section applies 0001 §1.7 to issues discovered during progression and does not create another scope policy. [0001 §1.6.1]

**2.10.6 Incidental part.** Where the affected part of the goal, or the affected material, is incidental, it is set aside as provided by 0001 §1.7.4 or §1.7.6. Progression continues without it and without user approval, unless setting it aside would override a prior user-approved decision, in which case approval under GS 1.5 is required and is handled by 0003. The set-aside part is not performed and must not be represented as performed or pending. The omission must be understandable to the user, as owned by 0004. [GS 1.5, GS 1.6; 0001 §1.7.4, §1.7.6, §1.7.7]

**2.10.7 Material part.** Where the affected part of the goal is a material part, or the affected material is essential within the meaning of 0001 §1.5.9, ARYNTH must not pursue a materially narrowed goal unless the user approves the material narrowing under GS 1.5 or redefines the goal, through 0003. Until then, the narrowing is a pending item (§2.7). [GS 1.5; 0001 §1.5.9, §1.7.3, §1.7.5, §1.7.7]

**2.10.8 No valid path.** Where no valid in-scope path to the target outcome remains, including where no material part of the goal remains within V1, or where a required narrowing is not approved and no other valid path exists, ARYNTH cannot currently continue (§2.13.8). ARYNTH must not substitute a different goal on its own initiative. [GS 1.5, GS 1.7 ¶4; 0001 §1.7.2]

**2.10.9 Same workflow.** Scope discovery does not re-apply the entry conditions, begin a new workflow or end the existing one. [0001 §1.10.4, §1.12.4]

## 2.11 Revision Progression

**2.11.1 Ownership split.** 0008 owns revision intake, revision scope and boundaries, review and export, and the preservation and replacement of the current production-ready outcome. Once revision work has validly begun under 0008 and 0001 §1.9.7, this document owns how that revision work progresses through meaningful work. 0005 continues to own required checks and production-ready determination. [GS 1.9; 0000 §0.2; 0001 §1.9.7]

**2.11.2 Same orchestration model.** Revision work progresses under the rules of this document. There is no separate orchestration model for revisions. [GS 1.9 ¶3]

**2.11.3 Preserved confirmed progress.** Revision work continues the existing workflow from its preserved confirmed progress. Confirmed work is reopened for a revision only under §2.8. [GS 1.9 ¶3; 0002-B]

**2.11.4 Current outcome untouched.** Revision work must not alter the current production-ready outcome. It remains the current production-ready outcome, available for review and export, until a revised result passes the required final quality checks and replaces it under 0008. [GS 1.9 ¶4, ¶5]

**2.11.5 One target outcome.** Revision work serves the workflow's one target outcome and does not create an additional target outcome. [0001 §1.8.4]

**2.11.6 End of revision progression.** A revised result is routed to the required final quality checks (§2.9.7). Progression of revision work ends under §2.13.5 when 0005 determines that the revised result has reached production-ready completion. Replacement of the current outcome is owned by 0008. [GS 1.9 ¶5; 0000 §0.2]

## 2.12 Progression Cycle & Progress State

**2.12.1 Functional progression cycle.** While a workflow is actively progressing, progression follows this functional cycle:

1. assess the current workflow state: the goal as it stands, the target outcome, confirmed work, completed but unconfirmed work, remaining work and any unresolved pending item;
2. determine the next meaningful work that may validly progress (§2.6);
3. progress that work as the active item (§2.7);
4. route its result through any required check (§2.9);
5. incorporate the result, selecting corrective work where a required check was not passed;
6. reassess remaining work (§2.9);
7. continue, hand off, suspend or end progression (§2.13).

[Derived: GS 1.1, GS 1.3; 0000 §0.5]

**2.12.2 Functional only.** The cycle describes functional responsibilities and their order of dependency. It is not a technical state machine, a set of implementation statuses, a workflow-engine design or an agent design, and it does not prescribe how the steps are executed (§2.16). [0000 §0.5]

**2.12.3 Events from other areas.** A user intervention (0003), a stop, an interruption or a recoverable problem (0006) may occur at any step. Progression then follows §2.13. When progression re-engages, it resumes at step 1. [GS 1.5 ¶4, GS 1.7]

**2.12.4 Progress distinctions.** For the purposes of progression, the workflow's meaningful work is distinguished as:

1. remaining work;
2. active meaningful work;
3. completed but unconfirmed work whose result forms part of current progress;
4. confirmed work whose result forms part of current progress;
5. changed confirmed work;
6. held work, together with the pending item it depends on;
7. completed work whose result has been discarded from current progress (§2.9.10).

These are functional distinctions, not implementation statuses. [Derived: GS 1.1, GS 1.6; 0002-A, 0002-B, 0002-C, 0002-D]

**2.12.5 Determinable progress state.** The progress state must be determinable at any time, so that 0004 can make meaningful workflow state understandable under GS 1.6, including:

1. which meaningful work item is active, or why none is;
2. what meaningful work has been completed, distinguishing completed work whose result forms part of current progress from completed work whose result has been discarded;
3. what completed work has changed since it was last confirmed;
4. whether any work is held, and whether the whole workflow is waiting (§2.7.9);
5. whether progression has ended because production-ready completion has been reached.

This rule requires the state to be determinable. It does not require every distinction to be presented to the user. What is presented, and how, is owned by 0004. [GS 1.6; 0000 §0.2]

## 2.13 Handoffs, Relinquishing & Re-engaging

**2.13.1 Handoff before acting.** Before progressing work that requires any of the following, ARYNTH hands the matter to its owner and does not act on it until it is resolved:

1. a decision that would materially change the goal or override a prior user-approved decision, or a decision at a user-requested approval point: 0003 (GS 1.5);
2. information necessary to execute the goal that ARYNTH cannot determine and that is not an ARYNTH decision: 0004 and 0006 (GS 1.6, GS 1.7);
3. a paid action that is not already authorized, would exceed the remaining approved budget or would consume usage beyond an approved paid-resource allowance, including where available cost information indicates that it reasonably could: 0007 (GS 1.8);
4. a scope issue discovered during progression: §2.10.

A matter handed off under items 1 to 3 is a pending item while it remains unresolved, and §2.7 applies. [GS 1.5, GS 1.6, GS 1.7 ¶3, GS 1.8]

**2.13.2 Necessary information.** Information is necessary only when execution of the goal requires it and ARYNTH cannot determine it. A detail the user has left open is an ARYNTH decision, not missing information. A request for information must not be used to shift a workflow decision to the user. [GS 1.6 ¶3; 0001 §1.4.5–§1.4.7]

**2.13.3 Events owned by other areas.** When the user intervenes or stops the workflow, or when an interruption or recoverable problem occurs, progression follows the rules of the owning area: 0003 for intervention, and 0006 for stops, interruptions and recoverable problems. [GS 1.5 ¶4, GS 1.7; 0000 §0.2]

**2.13.4 When progression is relinquished.** ARYNTH relinquishes active progression only in the cases in §2.13.5–§2.13.9. §2.13.5 and §2.13.6 end progression. §2.13.7–§2.13.9 suspend it. [Derived: GS 1.1, GS 1.7, GS 1.9]

**2.13.5 Production-ready completion.** Active progression ends when 0005 determines that the target outcome has passed the required final quality checks and production-ready completion has been reached. No user acceptance is required. After that point ARYNTH performs no further meaningful work on the workflow, including discretionary improvement, unless a revision validly begins under 0008. Review and export are owned by 0008. [GS 1.1 ¶2, GS 1.9 ¶1, ¶2; 0000 §0.2]

**2.13.6 User stop.** When the user stops the workflow, progression ends and no further meaningful work is selected or progressed. Stop behavior, preservation and continuation are owned by 0006. A user-stopped workflow must not be re-engaged automatically. [GS 1.7 ¶5]

**2.13.7 Whole-workflow waiting.** When the whole workflow waits under §2.7.9, active progression is suspended. Waiting behavior is owned by 0006. [GS 1.7 ¶3; 0002-C]

**2.13.8 Unable to continue.** When no meaningful work may validly progress toward the target outcome, and no unresolved pending item exists whose resolution could allow progression to continue, ARYNTH identifies that it cannot currently continue, and active progression is suspended. This includes the case where no valid in-scope path remains (§2.10.8) and the case where repeated corrective failure reaches the boundary defined by 0006. The consequences, including truthful non-completion, the user's understanding of why the workflow cannot continue, preservation and any later continuation, are owned by 0006. [GS 1.7 ¶4; 0000 §0.2]

**2.13.9 Interruption or recoverable problem.** When a temporary interruption or a recoverable problem prevents progress, active progression is suspended as governed by 0006. [GS 1.7 ¶1, ¶2]

**2.13.10 No false completion.** Only §2.13.5 represents the target outcome as reached. Ending or suspending progression in any other case must not be represented as successful completion. [GS 1.7 ¶4]

**2.13.11 No additional workflow status.** Relinquishing progression adds no workflow status to those in 0001 §1.9.2 and §1.9.3. Progression, including progression of independent work while other work is held, is "actively progressing". Progression of revision work is "undergoing a revision". Whole-workflow waiting is "waiting for required user approval" or "waiting for necessary information", cost authorization being a user approval under GS 1.8. Inability to continue under §2.13.8 is "currently unable to continue". A workflow whose progression is suspended under §2.13.7–§2.13.9 is neither stopped nor completed and remains in progress. [GS 1.7, GS 1.8; 0001 §1.9.2, §1.9.3]

**2.13.12 Re-engagement.** Active progression re-engages, starting at step 1 of §2.12.1, when:

1. a pending item is resolved through its owning area (§2.7.10);
2. 0006 returns control, including after an interruption or recoverable problem no longer prevents continuation;
3. the user continues a stopped workflow, as governed by 0006 and subject to 0001 §1.9.6;
4. 0003 resolves an intervention;
5. revision work validly begins under 0008 (§2.11).

[GS 1.5, GS 1.7, GS 1.9; 0001 §1.9.6]

**2.13.13 Continuation from the confirmed state.** When progression re-engages after an interruption, a recoverable problem or a stop, it continues from the latest confirmed state as provided by 0006, and ARYNTH reassesses remaining work. The user must not be required to restart work that has reached a confirmed state. [GS 1.7 ¶1, ¶2, ¶5]

**2.13.14 No instruction needed to re-engage.** Re-engagement after a pending item is resolved, or after a recoverable problem no longer prevents continuation, requires no user instruction to proceed. A user-stopped workflow re-engages only when the user chooses to continue it. [GS 1.5 ¶1, GS 1.7 ¶2, ¶5]

## 2.14 Manual-Coordination Guard

**2.14.1 Principle.** ARYNTH owns workflow coordination. The user must not become the manual workflow manager or the exception handler for the workflow. [GS 1.1 ¶6, GS 1.3]

**2.14.2 Legitimate user touchpoints.** A path from orchestration to the user for a decision, an approval or input has authority only where one of the following applies:

1. approval required under GS 1.5, including approval at a user-requested approval point and a user-requested choice among options (0001 §1.8.3);
2. necessary information under GS 1.6 (§2.13.2);
3. stop, continuation or inability to continue under GS 1.7;
4. cost authorization under GS 1.8.

[GS 1.5, GS 1.6, GS 1.7, GS 1.8]

**2.14.3 Decisions ARYNTH must not transfer.** Unless §2.14.2 applies, ARYNTH must not require the user to choose or decide:

- the next workflow step;
- a tool;
- a model;
- a stage;
- the sequence of meaningful work;
- a corrective path after a failed required check;
- a working alternative;
- whether to retry, redo or rewrite work;
- whether to reopen confirmed work.

[GS 1.5 ¶1, ¶3; 0001 §1.4.6]

**2.14.4 Uncertainty is not authority.** Uncertainty, difficulty, a failed required check, the existence of several viable options, or a need to change the sequence or execution strategy is not by itself a reason to involve the user. Questions such as "Which option should I choose?", "What should I do next?", "Should I retry?" and "Should I rewrite this?" are not valid user questions unless an authority in §2.14.2 makes them one. Where no such authority applies, ARYNTH makes the workflow decision itself. [GS 1.5 ¶1, ¶3, GS 1.6 ¶3]

**2.14.5 No disguised decisions.** Information requests, indications that the user's attention is required, and approval requests must not be used to transfer a workflow decision that belongs to ARYNTH. [GS 1.5 ¶3, GS 1.6 ¶3]

**2.14.6 Requested involvement is bounded.** Where the user has requested an approval point or a choice among options, the user's involvement is legitimate to the extent of that request and does not authorize further user decisions beyond it. [GS 1.5 ¶3; 0001 §1.8.3]

**2.14.7 Intervention and visibility unaffected.** This section does not limit the user's ability to intervene while the workflow is in progress, which is owned by 0003, or the visibility owned by 0004. [GS 1.5 ¶4, GS 1.6]

**2.14.8 Rule for later layers.** A later rule that would route a workflow decision from orchestration to the user must identify its authority under §2.14.2. A rule that cannot do so is inconsistent with GS 1.5 and does not apply. [GS 1.5 ¶3]

## 2.15 Ownership Boundaries & Cross-References

**2.15.1 Ownership.** This document does not define the detailed behavior of other areas. Where their rules concern progression, they apply this document rather than restating it.

| Area | Owns | Relationship to 0002 |
|---|---|---|
| 0001 — Workflow Entry & Scope | Entry, goal sufficiency, V1 scope classification, the one-target-outcome rule, the multiple-workflow policy and new-versus-existing workflow routing | Hands the workflow to 0002 (0001 §1.12). 0002 applies 0001 §1.5–§1.8 during progression without restating them (§2.3, §2.6.9, §2.10) and never re-applies entry (§2.3.3). |
| 0003 — Autonomy, Approval & Intervention | Approval behavior, requested approval points, user-requested choice among options, intervention handling, goal changes, materiality handling within intervention, and the consequences of user-approved decisions | 0002 hands off decisions that trigger GS 1.5 (§2.13.1), holds dependent work (§2.7), and reassesses once 0003 resolves an intervention or goal change (§2.10.1). |
| 0004 — Workflow Visibility & Attention | User-facing workflow visibility, presentation of progress, attention requirements, and how changes are made understandable | 0002 keeps the progress state determinable (§2.12.5). It defines no presentation. |
| 0005 — Quality, Confirmation & Completion | Which work requires checks, check criteria, when work becomes confirmed, the confirmation status of dependent confirmed work when its basis changes, final quality checks and production-ready determination | 0002 routes results to checks (§2.9), applies the confirmed basis (§2.5), selects corrective work (§2.9.4) and ends progression on 0005's determination (§2.13.5). |
| 0006 — Continuity, Failure, Stop & Resume | The waiting state, interruptions, recoverable problems, inability to continue, the repeated-failure boundary, stop, continuation and preservation | 0002 does not select held work (§2.7), relinquishes progression as provided in §2.13 and re-engages when control returns (§2.13.12). |
| 0007 — Cost & Spending Control | Spending authorization, cost approval, cost uncertainty and budget visibility | 0002 hands off paid actions that are not already authorized (§2.6.11, §2.13.1). Spending boundaries constrain selection, strategy and corrective work. |
| 0008 — Review, Revision & Export | Review, revision intake, revision boundaries, preservation and replacement of the production-ready outcome, and export | 0002 progresses revision work once it has validly begun (§2.11) and hands the workflow to 0008 at production-ready completion (§2.13.5). |

**2.15.2 Open dependencies.** This document depends on the following rules. They must be defined by their owning areas and are not defined here.

| Dependency | Owner | Relied on in |
|---|---|---|
| Whether dependent confirmed work remains confirmed when its confirmed basis changes | 0005 | §2.8.7, §2.9.9 |
| When repeated corrective failure means that ARYNTH cannot continue | 0006, subject to 0007 | §2.9.6, §2.13.8 |
| Whether a goal change resolved through 0003 itself authorizes resulting rework involving prior user-approved decisions | 0003 | §2.8.5, §2.10.2 |

## 2.16 Deferred to Later Layers

The following are deferred to later specification layers and must not be inferred from this document:

- detailed granularity criteria for meaningful work items (§2.4.4);
- criteria for judging whether a change is material (0001 §1.14), including a change of execution strategy (§2.6.7);
- which results require checks, check criteria and confirmation criteria (0005);
- the repeated-failure boundary (0006);
- the composition of the set of approved AI tools and models, and model, tool and provider selection mechanics, including model routing;
- technical orchestration architecture, including state machines, implementation statuses, workflow engines, agents and agent graphs, queues, jobs, background workers and event mechanisms;
- the representation of dependencies between meaningful work items;
- the execution concurrency model below the meaningful-work level (§2.7.2);
- storage and persistence of results and confirmed states;
- retry, backoff and timeout mechanisms;
- API design;
- cost estimation mechanics and billing implementation (0007);
- UI design, presentation, wording and notification mechanisms (0004);
- revision controls, revision limits and version history (0008).
