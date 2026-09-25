# ARYNTH Autopilot V1 — Workflow Entry & Scope

Status: Draft  
Specification Layer: Functional Map  
Current Stage: Stage 2  
Functional Area: 0001  
Source of Truth: `../global/product-definition.md`  
Stage Map: `0000-functional-map.md`

## 1.1 Purpose & Authority

**1.1.1 Ownership.** This document owns the Functional Map behavior for:

- workflow entry;
- goal sufficiency;
- supporting materials at entry;
- V1 scope classification;
- scope enforcement at entry;
- the one-target-outcome rule;
- the multiple-workflow policy;
- routing between a new workflow and an existing workflow;
- the handoff to 0002 Workflow Orchestration & Progress.

**1.1.2 Authority.** This document derives its authority from:

- the Final Global Spec, sections 1.1–1.9;
- the verified Stage Map;
- the following founder-approved Stage 2 decisions:
  - Decision 0001-A — multiple-workflow policy, applied in §1.9;
  - Decision 0001-B — long-form non-video source material, applied in §1.5 and §1.6;
  - Decision 0001-C — one target outcome, applied in §1.8;
  - Decision 0001-D — non-video companion deliverables, applied in §1.6, §1.7 and §1.8.

**1.1.3 Precedence.** The Global Spec prevails over this document. A rule in this document that conflicts with the Global Spec is a defect in this document and does not apply. Founder decisions refine the Global Spec within its boundaries and do not override it.

**1.1.4 Not owned.** This document does not define execution and progress (0002), approval and intervention behavior (0003), general visibility and attention (0004), confirmation and completion (0005), continuity, stopping and continuation (0006), spending control (0007), or review, revision and export (0008). Where this document relies on those areas, it states only the entry or scope rule and names the owning area (§1.13). Details deferred to later specification layers are listed in §1.14.

**1.1.5 Conventions.**

- "Must", "must not" and "may" state requirements, prohibitions and permissions.
- "GS 1.x" refers to a Global Spec section. "§1.x" refers to a section of this document. Four-digit numbers refer to Functional Map areas.
- Each rule in §1.3–§1.12 states its basis:
  - [GS 1.x] — established by the Global Spec;
  - [0001-A], [0001-B], [0001-C], [0001-D] — founder-approved Stage 2 decision;
  - [Derived: …] — a Functional Map rule that follows from the cited sources without adding product policy.

## 1.2 Functional Definitions

These definitions apply throughout this document. They describe functional meaning only.

- **Workflow** — the unit of V1 work through which ARYNTH carries one sufficient content production goal toward one target outcome. Revisions (GS 1.9) and changes made while the workflow is in progress (0003) occur within the same workflow.
- **Content production goal** — the user's statement of the short-form video result they want ARYNTH to produce (GS 1.1, GS 1.4). It may refer to supporting materials.
- **Minimum goal intent** — enough goal intent for ARYNTH to identify one V1 target outcome and to distinguish the user's intended result from an unspecified request.
- **Sufficient goal** — a content production goal for which the user has provided or explicitly delegated the minimum goal intent.
- **Explicit delegation** — an express statement by the user that ARYNTH may make a choice that would otherwise form part of the minimum goal intent. Omission is not explicit delegation.
- **Supporting material** — material the user supplies to inform the execution of a goal (GS 1.4).
- **Supported input** — supporting material that falls within V1's supported input types, as defined by later specification work (GS 1.4).
- **Excluded input** — supporting material outside V1 input scope: long-form source video and bulk raw footage (GS 1.4), and long-form audio source material (Decision 0001-B).
- **Unsupported material** — supporting material that is not an excluded input but does not fall within V1's supported input types.
- **Target outcome** — the one final production-ready video deliverable toward which a workflow is carried (Decision 0001-C; GS 1.1, GS 1.4). "Production-ready" has the meaning given in GS 1.1 and GS 1.9.
- **Final video deliverable** — a completed video that is to be retained as a separate completed result.
- **Non-video companion deliverable** — a separate user-facing deliverable other than the final video, such as a thumbnail, post caption, hashtags, title, standalone script, standalone image or other publishing asset (Decision 0001-D).
- **Intermediate option** or **working alternative** — content produced within a workflow as a candidate, draft or option on the way to the target outcome.
- **In-progress workflow** — a workflow that is actively progressing, waiting for required user approval, waiting for necessary information, currently unable to continue, or undergoing a revision (Decision 0001-A).
- **Stopped workflow** — a workflow the user has stopped under GS 1.7. **Completed workflow** — a workflow that has reached its production-ready outcome and is not undergoing a revision. Neither is an in-progress workflow (Decision 0001-A).
- **Material part** and **incidental part** — a part of a goal is a material part when omitting it would materially change the user's content production goal within the meaning of GS 1.5; otherwise it is an incidental part. The criteria for this judgment are deferred (§1.14).
- **Material narrowing** — pursuing a goal from which a material part of the user's goal has been removed.
- **Scope-compliant goal** — a sufficient goal whose target outcome, required inputs and required capabilities all fall within V1 scope under §1.6: as stated by the user, after an approved material narrowing or a user redefinition under §1.7.3, or after an incidental out-of-scope part or incidental material has been set aside under §1.7.4 or §1.7.6.

## 1.3 Workflow Entry Condition

**1.3.1 User-initiated entry.** A workflow begins only from a content production goal defined by the user. ARYNTH must not begin a workflow on its own initiative, including when another workflow stops or completes. [GS 1.1, GS 1.4; 0001-A]

**1.3.2 Entry conditions.** A workflow begins only when all of the following hold:

1. the goal is sufficient (§1.4);
2. the goal is scope-compliant and has one target outcome (§1.7, §1.8);
3. no other workflow is in progress (§1.9).

When these conditions hold, the workflow begins and responsibility passes to 0002 (§1.12). [Derived: GS 1.4; 0001-A, 0001-C]

**1.3.3 Materials without a goal.** Supporting materials do not begin a workflow on their own. A goal may express its intent by reference to supporting materials, but materials supplied without any user statement of goal intent are not a content production goal. [GS 1.4]

**1.3.4 Instructions carried forward.** A goal may be accompanied by user instructions that concern later functional areas, including:

- requests for approval points, carried forward to 0003 (GS 1.5);
- spending instructions, or approval of a budget or paid-resource allowance, carried forward to 0007 (GS 1.8).

Such instructions do not by themselves affect goal sufficiency or scope classification. [Derived: GS 1.5, GS 1.8]

**1.3.5 No entry approval.** ARYNTH must not require the user to approve its interpretation of a sufficient goal, or a plan for pursuing it, before the workflow begins, unless the user has explicitly requested such an approval point. The only approvals that may arise at entry are those permitted by GS 1.5, such as approval of a material narrowing under §1.7.3. [GS 1.5]

**1.3.6 Spending and workflow creation.** Creating or entering a workflow does not itself require separate spending approval merely because the workflow is created. Any paid action, whenever it occurs, remains governed by GS 1.8 and 0007. [Derived: GS 1.8]

**1.3.7 Before entry.** Until a workflow begins, no workflow exists for the goal. A goal awaiting minimum goal intent (§1.4.3), or awaiting approval of a material narrowing or a user redefinition (§1.7.3), is not an in-progress workflow for §1.9. Likewise, a request awaiting clarification of its route under §1.10.6 does not begin a new workflow until the user clarifies which existing workflow or new goal it refers to; that clarification is not an approval point. Visibility before entry is governed by §1.11. [Derived: GS 1.1; 0001-A]

## 1.4 Goal Sufficiency

**1.4.1 Sufficient goal.** A goal is sufficient for workflow entry when the user has provided or explicitly delegated enough goal intent for ARYNTH to identify one V1 target outcome and distinguish the user's intended result from an unspecified request. [Derived: GS 1.1, GS 1.4]

**1.4.2 Functional test, not a field schema.** Sufficiency is judged against §1.4.1 as a whole. No individual element of a goal, such as topic, audience, platform, style or length, is mandatory in itself. Goal intent may be stated directly or by reference to supporting materials. [Derived: GS 1.1, GS 1.5]

**1.4.3 Insufficient goal.** When the minimum goal intent is genuinely absent and has not been explicitly delegated, no workflow begins. ARYNTH may ask the user to supply or explicitly delegate the missing intent. Such a request must be limited to the minimum goal intent and must not be used to obtain decisions that would belong to ARYNTH once the goal is sufficient. [Derived: GS 1.1, GS 1.5, GS 1.6]

**1.4.4 Explicit delegation.** The user may explicitly delegate creative choices to ARYNTH, including choices that would otherwise form part of the minimum goal intent. An explicitly delegated choice is an ARYNTH decision under GS 1.5. A goal whose minimum goal intent is met through explicit delegation is sufficient. [Derived: GS 1.5]

**1.4.5 Missing execution information.** Once a goal is sufficient, the absence of information necessary to execute it does not prevent entry. The workflow begins. ARYNTH may request the information when it becomes necessary, and progress that depends on it waits until it is provided. Such a request must not be used to shift a workflow decision to the user when GS 1.5 assigns that decision to ARYNTH. Waiting behavior is owned by 0006. [GS 1.6, GS 1.7]

**1.4.6 Details left open.** Once a goal is sufficient, every detail the user has left open is an ARYNTH decision, unless another Global Spec rule requires user involvement: a material change to the goal or an override of a prior user-approved decision (GS 1.5), an approval point the user requested (GS 1.5), or spending that is not already authorized (GS 1.8). ARYNTH must not turn such details into user questions or approval points. [GS 1.5, GS 1.6]

**1.4.7 Ambiguous goals.** When a goal admits more than one reasonable reading:

1. if the ambiguity prevents ARYNTH from identifying one V1 target outcome or distinguishing the intended result, the minimum goal intent is missing (§1.4.3);
2. if the ambiguity concerns information necessary for execution that ARYNTH cannot determine, §1.4.5 applies;
3. otherwise, choosing between the readings is an ARYNTH decision (§1.4.6).

[Derived: GS 1.5, GS 1.6]

## 1.5 Supporting Materials

**1.5.1 Materials are optional.** A workflow may begin without supporting materials. Entry never requires an existing source video or a pre-assembled edit. Material that the goal depends on but that the user has not yet supplied is missing execution information under §1.4.5, not an entry condition. [GS 1.4; Derived: GS 1.6]

**1.5.2 Category is not support.** GS 1.4 names text, images, short video clips and reference materials as possible supporting-material categories. Belonging to one of these categories does not make a particular material a supported input. A material is a supported input only when it falls within V1's supported input types as defined by later specification work. A material or use that is not expressly excluded is not thereby supported. [GS 1.4]

**1.5.3 Long text and reference documents.** Long text and reference documents are not categorically excluded from V1. They may be supported inputs, subject to supported-input rules and limits defined in later specification work. [0001-B]

**1.5.4 Short video material.** Short video clips are a possible supporting-material category. This document defines the functional role of supported short-video material (§1.5.5). It does not establish which short-video materials, or which uses of them, are supported, including a workflow in which an existing short video serves as the main material. Those are determined by later supported-input specifications. [GS 1.4]

**1.5.5 Role of supported materials.** Supported materials inform the execution of the goal and do not redefine it. How supported materials are used is an ARYNTH decision, unless the goal requires a particular material or use (§1.5.6). [Derived: GS 1.4, GS 1.5]

**1.5.6 Goal-required materials.** When the goal expressly requires a material or a particular use of it, that requirement is part of the goal. Proceeding without honoring it requires user approval under GS 1.5 where doing so would materially change the goal or would override a prior user-approved decision. These are independent triggers; where neither applies, no approval is required. If the required material is an excluded input or unsupported material, the material itself must not be used in any case, and proceeding without it follows §1.7.5 or §1.7.6 according to §1.5.9. [GS 1.5]

**1.5.7 Excluded inputs.** Long-form source video and bulk raw footage are outside V1 input scope. Long-form audio source material, such as a long podcast episode or another long audio recording supplied for extraction or repurposing into a Short, is outside V1. ARYNTH must not use an excluded input in a V1 workflow. [GS 1.4; 0001-B]

**1.5.8 Unsupported materials.** ARYNTH must not use unsupported material in a V1 workflow. At entry, unsupported material is handled in the same way as an excluded input (§1.7.5, §1.7.6). [Derived: GS 1.4]

**1.5.9 Essential and incidental materials.** An excluded input or unsupported material is essential when the goal cannot be pursued without it except by materially changing the goal. Otherwise it is incidental. Enforcement follows §1.7.5 and §1.7.6. [Derived: GS 1.5]

**1.5.10 Conflicting materials.** Where a supported material conflicts with the goal, the goal governs. If the conflict prevents identifying the intended result, §1.4.7 applies. Otherwise, whether and how to use the conflicting material is an ARYNTH decision, subject to §1.5.6. [Derived: GS 1.4, GS 1.5]

**1.5.11 Materials supplied after entry.** Materials supplied after a workflow begins are received through the areas that own that interaction: information requests and waiting (0004, 0006) and user intervention (0003). §1.5.2–§1.5.9 apply to them. [Derived: 0000]

## 1.6 V1 Scope Classification

**1.6.1 Single scope reference.** This section is the Functional Map's V1 scope classification. Other areas that apply scope, including to materials supplied after entry (§1.5.11), goal changes while a workflow is in progress (0003) and revisions (0008), apply this classification and do not restate it. [Derived: 0000]

**1.6.2 Target outcome scope.** A goal is within V1 outcome scope when its target outcome is one final production-ready short-form video deliverable. A goal whose intended final result is not a short-form video is outside V1. Separate non-video companion deliverables are not part of the V1 production-ready outcome, and V1 does not promise them. Text, imagery, captions, titles, graphics or other content incorporated into the final video may be used in producing that video; user-supplied material used this way remains subject to §1.5. [GS 1.1, GS 1.4; 0001-C, 0001-D]

**1.6.3 Input scope.**

- Long-form source video and bulk raw footage are excluded inputs. [GS 1.4]
- Long-form audio source material is an excluded input. [0001-B]
- Long text and reference documents are not categorically excluded and are subject to later supported-input rules. [0001-B]
- Any other supporting material is within input scope only as a supported input (§1.5.2). [GS 1.4]

**1.6.4 Capability scope.**

- V1 does not provide a general-purpose video editing environment. [GS 1.4]
- Publishing or distributing the completed video to external platforms is outside V1. [GS 1.1]

**1.6.5 No inference in either direction.** This document does not treat a capability, material or result as supported because it is not excluded, nor as excluded because it is not named. Anything this section does not classify remains subject to the Global Spec and to later specification layers. [Derived: GS 1.4; 0000 §0.1]

## 1.7 Scope Enforcement at Entry

**1.7.1 Classification before entry.** Before a workflow begins, ARYNTH classifies the goal and any supporting materials under §1.5 and §1.6. [Derived: GS 1.4]

**1.7.2 Wholly out-of-scope goals.** When every material part of the intended result falls outside V1, no workflow begins. ARYNTH must not substitute a different goal on its own initiative. The user may define a scope-compliant goal. [Derived: GS 1.1, GS 1.4, GS 1.5]

**1.7.3 Partly out-of-scope goals where the excluded part is material.** When a material part of the goal falls outside V1 and another material part falls within it, the workflow begins only after either:

1. the user approves a material narrowing of the goal to its scope-compliant part, which is an approval of a material change under GS 1.5; or
2. the user redefines the goal so that it is scope-compliant.

ARYNTH may identify the scope-compliant part of the goal for the user's consideration. [GS 1.5; Derived: GS 1.4]

**1.7.4 Partly out-of-scope goals where the excluded part is incidental.** When the part of the goal outside V1 is an incidental part and setting it aside does not override a prior user-approved decision, the workflow may begin with the scope-compliant goal without user approval. If setting it aside would override a prior user-approved decision, user approval is required under GS 1.5 before proceeding with the narrowed execution. In either case, the excluded part remains outside V1: it will not be performed, and ARYNTH must not represent it as performed or pending. [Derived: GS 1.5, GS 1.7]

**1.7.5 Essential excluded or unsupported material.** When an excluded input or unsupported material is essential (§1.5.9), the parts of the goal that depend on it are outside V1. §1.7.2 applies if no material part of the intended result remains within V1. Otherwise §1.7.3 applies. [Derived: GS 1.4, GS 1.5]

**1.7.6 Incidental excluded or unsupported material.** When an excluded input or unsupported material is incidental and omitting it does not override a prior user-approved decision, the workflow may begin without it and no user approval is required. If omitting it would override a prior user-approved decision, user approval is required under GS 1.5 before proceeding without it. In either case, ARYNTH must not use the material (§1.5.7, §1.5.8); approval permits proceeding without the material, not using it. [Derived: GS 1.4, GS 1.5]

**1.7.7 No silent material narrowing.** ARYNTH must not pursue a goal that is materially narrower than, or materially different from, the user's goal unless the user has approved the material narrowing or redefined the goal. Incidental omissions under §1.7.4 and §1.7.6 must be understandable to the user (§1.11). [GS 1.5]

**1.7.8 Requests that include non-video companion deliverables.** When a goal requests a separate non-video companion deliverable in addition to the video, that part of the request is outside V1 (§1.6.2) and is handled as an out-of-scope part of the goal: under §1.7.3 where it is a material part, and under §1.7.4 where it is an incidental part. A goal whose only requested result is a non-video companion deliverable is wholly out of scope (§1.7.2). [0001-D; Derived: GS 1.5]

## 1.8 One-Target-Outcome Rule

**1.8.1 One target outcome.** Each V1 workflow has exactly one target outcome: one final production-ready video deliverable. [0001-C; GS 1.4]

**1.8.2 Intermediate options and working alternatives.** Intermediate options and working alternatives produced within a workflow do not become additional target outcomes merely because they differ in content, framing, length, language or presentation. Internal or intermediate artifacts produced where needed to make the video are likewise not separate target outcomes and are not separately promised user-facing deliverables. [0001-C, 0001-D]

**1.8.3 User-requested choice among options.** When the user asks to choose among options during a workflow, that choice is an approval point requested by the user and is owned by 0003. The options remain intermediate options, and the workflow keeps one target outcome. [GS 1.5; 0001-C]

**1.8.4 Revisions.** A revision remains inside the same workflow. A revised result replaces the current production-ready outcome only as provided by GS 1.9 and does not become an additional target outcome. Revision behavior is owned by 0008. [GS 1.9; 0001-C]

**1.8.5 Multiple final video deliverables.** When the user requests multiple final video deliverables to be retained as separate completed results, those are multiple target outcomes and cannot belong to one V1 workflow. Accordingly:

1. no workflow begins for the request as stated;
2. ARYNTH must not reduce the request to one final video deliverable without the user's approval of that material narrowing or the user's redefinition (§1.7.3, §1.7.7);
3. the request cannot be satisfied by beginning several workflows, because only one workflow may be in progress (§1.9);
4. the user may pursue each final video deliverable as a separate workflow, one at a time.

[0001-C; Derived: 0001-A, GS 1.5]

**1.8.6 Platform-oriented and language-oriented requests.** Whether a request has one target outcome depends on whether the user requests more than one final video deliverable to be retained as a separate completed result, not on whether content differs:

- one video intended for use on more than one platform, or one video that incorporates more than one language, has one target outcome;
- separate final video deliverables for different platforms or different languages are multiple target outcomes (§1.8.5).

This classification determines only whether a request asks for one target outcome or multiple target outcomes. It does not establish that V1 supports any particular language, platform-specific production capability or variant type. Supported capabilities remain subject to later supported-input and capability specifications and to §1.6.5.

[0001-C; Derived: GS 1.4]

**1.8.7 Series requests.** Each installment of a series that the user wants retained as a separate completed result is a separate target outcome. A workflow may target one installment. A request for several installments is governed by §1.8.5. [0001-C]

**1.8.8 Export-only differences.** Providing the target outcome in an export form does not create an additional target outcome. Export forms are defined by 0008 and later specification layers consistently with this section. Export must not be used to deliver multiple final video deliverables, or separate non-video companion deliverables (§1.6.2), within one workflow. [0001-C, 0001-D; GS 1.1]

## 1.9 Multiple-Workflow Policy

**1.9.1 One in-progress workflow.** At most one workflow may be in progress at a time. V1 has no parallel in-progress workflows. [0001-A]

**1.9.2 What counts as in progress.** A workflow is in progress while it is:

- actively progressing;
- waiting for required user approval;
- waiting for necessary information;
- currently unable to continue;
- undergoing a revision.

[0001-A]

**1.9.3 What does not count.** Stopped workflows and completed workflows are not in progress and do not prevent a new workflow from beginning. This policy places no limit on how many stopped or completed workflows may exist. [0001-A]

**1.9.4 Beginning another workflow.** A new workflow must not begin while another workflow is in progress. To begin another workflow, the user must first stop the in-progress workflow. Stopping is governed by GS 1.7, is owned by 0006, and preserves confirmed progress. [0001-A; GS 1.7]

**1.9.5 No automatic handling.** ARYNTH must not stop or set aside an in-progress workflow on its own to allow another workflow to begin. A goal that cannot begin because another workflow is in progress is not held for later automatic start. This policy does not introduce deletion or discarding of workflows, queuing, parallel execution, or automatic switching between workflows. [0001-A]

**1.9.6 Continuing a stopped workflow.** Continuing a stopped workflow makes it in progress. A stopped workflow may therefore be continued only when no other workflow is in progress. Continuation behavior is owned by 0006. [Derived: 0001-A, GS 1.7]

**1.9.7 Revisions.** A workflow undergoing a revision is in progress. A revision may therefore begin only when no other workflow is in progress. Revision behavior is owned by 0008. [Derived: 0001-A, GS 1.9]

**1.9.8 Review and export.** Reviewing or exporting the production-ready outcome of a completed workflow does not make that workflow in progress and is not restricted by this policy. [Derived: 0001-A, GS 1.9]

## 1.10 New Workflow vs Existing Workflow

**1.10.1 Kinds of request.** A user request concerning a content production goal is one of:

1. a new independent content production goal;
2. a revision of an existing production-ready outcome;
3. a change to the goal of an in-progress workflow;
4. a new content production goal that reuses a previous production-ready outcome as supporting material;
5. a request to continue a stopped workflow, including a request that also changes its goal.

[Derived: GS 1.1, GS 1.5, GS 1.7, GS 1.9]

**1.10.2 New independent goal.** A new independent goal is handled as workflow entry under §1.3 and is subject to §1.9. [GS 1.1; 0001-A]

**1.10.3 Revision.** A request to revise an existing production-ready outcome belongs to the workflow that produced it. It does not begin a new workflow or create an additional target outcome (§1.8.4). Its behavior is owned by 0008. §1.6 and §1.8 apply to what it asks for, and §1.9.7 applies to when it may begin. [GS 1.9; 0001-A, 0001-C]

**1.10.4 Change while a workflow is in progress.** A change to the goal of an in-progress workflow, including a material change, belongs to that workflow as user intervention. It does not begin a new workflow. Its behavior is owned by 0003. §1.6 and §1.8 apply to what it asks for. [GS 1.5; Derived: 0001-C]

**1.10.5 Reuse of a previous outcome.** A previous production-ready outcome may serve as supporting material for a new workflow only where it falls within V1's supported input types (§1.5.2, §1.5.4). The new workflow has its own target outcome. The previous workflow and its production-ready outcome are not changed by this reuse. [Derived: GS 1.4, GS 1.9]

**1.10.6 Meaning-preserving routing.** ARYNTH must not route a request in a way that changes its meaning. It must not, on its own initiative, treat a new independent goal as a revision of or change to an existing workflow, or treat a revision or change as a new workflow. Where the intended route cannot be determined and the possible routes would lead to materially different results, ARYNTH must obtain the user's intent before acting on the request. This is a clarification of the user's intent, not an approval point. [Derived: GS 1.1, GS 1.5, GS 1.9]

**1.10.7 Stopped workflow.** A request to continue a stopped workflow, including a request that also changes its goal, belongs to that stopped workflow. It does not begin a new workflow, and routing must not silently convert the stopped workflow into a new workflow. Continuation behavior is owned by 0006 and remains subject to §1.9.6. Where the request also changes the goal, that change is owned by 0003 once continuation is being handled. Where the request asks for a revision of the stopped workflow's production-ready outcome, the revision is governed by §1.10.3 once continuation is being handled. [Derived: GS 1.5, GS 1.7, GS 1.9; 0001-A]

## 1.11 Entry Visibility Duties

**1.11.1 Entry-specific understanding.** The user must be able to understand when:

1. a goal cannot begin because the minimum goal intent is missing, and that the user may supply or explicitly delegate it (§1.4.3);
2. a goal, or a material essential to it, is outside V1 scope or unsupported, and which scope boundary applies (§1.7.2, §1.7.5);
3. a material narrowing of the goal requires the user's approval before a workflow can begin, and what would not be performed (§1.7.3);
4. an incidental part of the goal will not be performed, or an incidental material will not be used (§1.7.4, §1.7.6);
5. a new workflow cannot begin, a stopped workflow cannot be continued, or a revision cannot begin because another workflow is in progress and must first be stopped (§1.9).

[Derived: GS 1.6, GS 1.7]

**1.11.2 No presentation defined.** These duties do not define presentation, wording, timing or notification mechanisms (§1.14). [Derived: GS 1.6]

**1.11.3 After entry.** Apart from §1.11.1 item 5, which applies whenever §1.9 prevents an action, visibility after a workflow begins is governed by GS 1.6 and owned by 0004. [GS 1.6; Derived: 0000]

## 1.12 Handoff to 0002

**1.12.1 Handoff point.** Responsibility passes from 0001 to 0002 Workflow Orchestration & Progress at the moment a workflow begins under §1.3.2. [Derived: 0000]

**1.12.2 State at handoff.** At handoff, all of the following are established:

1. a sufficient goal, with its minimum goal intent provided or explicitly delegated by the user (§1.4);
2. one V1 target outcome (§1.8);
3. a scope classification resolved sufficiently for work to proceed: the goal is scope-compliant as stated, after an approved material narrowing, or after a user redefinition, and any incidental out-of-scope part or material has been set aside (§1.7);
4. the relevant supported materials associated with the workflow, with no excluded input or unsupported material associated (§1.5);
5. no other workflow in progress (§1.9);
6. user instructions relevant to later functional areas carried forward (§1.3.4).

[Derived: GS 1.4, GS 1.5; 0001-A, 0001-B, 0001-C, 0001-D]

**1.12.3 Not required at handoff.** Handoff does not require every execution detail to be known. Information that later becomes necessary may be requested after handoff, and progress that depends on it waits until it is provided. Details left open remain ARYNTH decisions (§1.4.6). [GS 1.6, GS 1.7]

**1.12.4 After handoff.** 0002 must not re-apply the entry conditions to a workflow that has begun. Later changes to the goal or to its materials are handled by their owning areas (0003, 0006, 0008), which apply §1.5, §1.6 and §1.8 and the policy in §1.9. [Derived: 0000]

## 1.13 Ownership Boundaries & Cross-References

This document does not define the detailed behavior of other areas. Where their rules concern entry or scope, they apply this document rather than restating it.

| Area | Owns | Relationship to 0001 |
|---|---|---|
| 0002 — Workflow Orchestration & Progress | Carrying a begun workflow toward its target outcome, including how associated materials are used during the work | Receives the workflow at handoff (§1.12). |
| 0003 — Autonomy, Approval & Intervention | How approvals and user intervention work | Handles the approvals and interventions that 0001 identifies: material narrowing at entry (§1.7.3), requested approval points (§1.3.4), user-requested choice among options (§1.8.3) and goal changes while a workflow is in progress (§1.10.4). 0001 defines when they arise; 0003 defines how they work. |
| 0004 — Workflow Visibility & Attention | General visibility and attention for active and completed workflows | 0001 owns only the entry-specific duties in §1.11. |
| 0005 — Quality, Confirmation & Completion | Required checks, confirmation, final quality checks and production-ready completion | Applies completion to the one target outcome fixed by §1.8. |
| 0006 — Continuity, Failure, Stop & Resume | Waiting for necessary information after entry, stopping and continuation | Handles waiting under §1.4.5 and stopping under §1.9.4, and applies §1.9.6 when a stopped workflow is continued. |
| 0007 — Cost & Spending Control | Spending authorization and spending visibility | Receives spending instructions carried forward (§1.3.4). Governs any paid action, whenever it occurs (§1.3.6). |
| 0008 — Review, Revision & Export | Review, revision and export | Applies §1.6 and §1.8 to revision requests and §1.9.7 when a revision begins, and defines export forms consistently with §1.8.8. |

## 1.14 Deferred to Later Layers

The following are deferred to later specification layers and must not be inferred from this document:

- supported input types, including which short-video materials and uses are supported (§1.5.2, §1.5.4);
- exact supported formats and file types;
- exact file sizes;
- exact duration thresholds, including what counts as short or long-form video or audio;
- exact text and document limits;
- criteria for judging whether a part of a goal is a material part or an incidental part;
- upload mechanics;
- UI design, navigation and interaction design, including how goals and materials are captured;
- detailed error copy and message wording;
- technical validation of inputs;
- storage;
- authentication;
- architecture and implementation;
- model and provider selection;
- export forms and formats (0008);
- exact quality criteria (0005);
- billing implementation (0007).
