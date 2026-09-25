# ARYNTH Autopilot V1 — Autonomy, Approval & Intervention

Status: Draft  
Specification Layer: Functional Map  
Current Stage: Stage 2  
Functional Area: 0003  
Source of Truth: `../global/product-definition.md`  
Stage Map: `0000-functional-map.md`

## 3.1 Purpose & Authority

**3.1.1 Purpose.** This document defines:

- the functional boundary between the decisions ARYNTH makes autonomously and the decisions that require user approval;
- how approval works when it is required;
- how user intervention is received and resolved while a workflow is in progress.

Its aim is maximum autonomous workflow ownership by ARYNTH inside explicit user-control boundaries. The user controls the decisions that GS 1.5 reserves to the user without becoming the manual workflow manager (GS 1.3). This document does not define technical architecture, approval records, permission systems or user interface.

**3.1.2 Ownership.** This document owns the Functional Map behavior for:

- the autonomy boundary;
- the closed set of approval authorities;
- the distinction between goal content, explicit delegation, user-requested approval points and prior user-approved decisions;
- the scope of an approval;
- user-requested approval points, including user-requested choice among options;
- the decision facts an approval request must make knowable;
- approval outcomes, and whether approval requests and approvals are still current;
- approvals that arise before workflow entry;
- recognition, interpretation and routing of user intervention;
- the effect of an unresolved intervention on active work;
- goal changes while a workflow is in progress, and their consequences for prior user-approved decisions;
- explicit delegation during a workflow;
- the approval-fatigue guard.

**3.1.3 Authority.** This document derives its authority from:

- the Final Global Spec, sections 1.1–1.9;
- the Stage Map (0000);
- 0001 Workflow Entry & Scope and 0002 Workflow Orchestration & Progress, including the founder decisions applied there;
- the following founder-approved Stage 2 decisions:
  - Decision 0003-A — user direction versus user-approved decisions, applied in §3.5;
  - Decision 0003-B — what an approval authorizes, applied in §3.6;
  - Decision 0003-C — rework resulting from the user's own change, applied in §3.12;
  - Decision 0003-D — lifetime of user-requested approval points, applied in §3.7;
  - Decision 0003-E — keeping requests and approvals current, applied in §3.9;
  - Decision 0003-F — alternatives in an approval request, applied in §3.8.

**3.1.4 Global Spec sources.** The Stage Map names GS 1.5 as the primary source of this area. This document also applies:

- GS 1.1, for the confirmed state and the role of approval in it;
- GS 1.3, for the manual-coordination problem;
- GS 1.6, for the visibility of approval needs and the limit on information requests;
- GS 1.7, for waiting, stop and continuation;
- GS 1.8, for spending approval as a separate authority;
- GS 1.9, for revision within the same workflow.

It applies those sections and does not redefine them.

**3.1.5 Precedence.** The Global Spec prevails over this document. The Stage Map, 0001 and 0002 prevail over this document where they establish a rule. A rule in this document that conflicts with any of them is a defect in this document and does not apply. Founder decisions refine the Global Spec within its boundaries and do not override it.

**3.1.6 Not owned.** This document does not define the following, which belong to other areas:

- entry, scope classification and scope enforcement (0001);
- orchestration, holding, sequencing, reassessment, reopening and corrective work (0002);
- visibility, wording, attention and presentation (0004);
- required checks, confirmation and completion (0005);
- waiting, interruption, inability to continue, stop and continuation (0006);
- spending authorization and cost information (0007);
- review, revision intake, revision scope, outcome replacement and export (0008).

Where this document relies on those areas, it states only the autonomy, approval or intervention rule and names the owning area (§3.16). Details deferred to later specification layers are listed in §3.17.

**3.1.7 Conventions.**

- "Must", "must not" and "may" state requirements, prohibitions and permissions.
- "GS 1.x" refers to a Global Spec section, and "¶n" to its nth paragraph. "§3.x" refers to a section of this document. "0001 §1.x" and "0002 §2.x" refer to sections of those documents, and "0000 §0.x" to a section of the Stage Map. Four-digit numbers refer to Functional Map areas.
- Each rule in §3.3–§3.15 states its basis:
  - [GS 1.x] — established by the Global Spec;
  - [0000 §0.x], [0001 §1.x] or [0002 §2.x] — established by an earlier Functional Map document;
  - [0002-C] and similar — a founder-approved Stage 2 decision applied in an earlier document;
  - [0003-A], [0003-B], [0003-C], [0003-D], [0003-E], [0003-F] — a founder-approved Stage 2 decision applied in this document;
  - [Derived: …] — a Functional Map rule that follows from the cited sources without adding product policy.

## 3.2 Functional Definitions

The definitions in 0001 §1.2 and 0002 §2.2 apply in this document. They include workflow, content production goal, explicit delegation, target outcome, intermediate option, in-progress workflow, stopped workflow, completed workflow, material part, incidental part, material narrowing, meaningful work, remaining work, confirmed work, pending item, dependency on a pending item, held work, reopening, reassessment, revision work and legitimate user touchpoint. The following definitions also apply. They describe functional meaning only.

- **ARYNTH decision** — a decision ARYNTH makes without user approval (§3.3).
- **Approval authority** — one of the grounds in §3.4.1 on which a decision requires user approval.
- **Approval-requiring decision** — a decision to which an approval authority applies.
- **Material change** — a decision that would materially change the user's defined content production goal within the meaning of GS 1.5. The criteria of materiality are deferred (§3.17).
- **Override** — a decision that would depart from, reverse or replace a prior user-approved decision, or would be inconsistent with it (§3.5.8).
- **Goal content** — the user's content production goal together with the user's other statements about the desired result, including instructions and preferences, whether given at entry or through intervention. It comprises result direction and explicit process constraints. It does not include advisory process preferences (§3.5.4).
- **Result direction** — user direction that defines, constrains or changes the intended outcome or its required characteristics (§3.5.4).
- **Explicit process constraint** — user direction that clearly requires or prohibits a specific production or workflow behavior (§3.5.4).
- **Advisory process preference** — user direction that expresses a desired approach to producing the result without clearly requiring it (§3.5.4, §3.5.6).
- **Prior user-approved decision** — a decision the user has made through an approval event or at a user-requested approval point, and that is in effect under §3.5.2.
- **Approval event** — the user's approval, at a current approval request, of a proposal or alternative presented for approval (§3.9.2), or the user's complete user decision in response to that request (§3.9.5).
- **Complete user decision** — a response to an approval request that itself fully settles the decision presented, so that no further ARYNTH decision is needed to determine what that decision is (§3.9.5).
- **User-requested approval point** — an approval point the user has explicitly requested under GS 1.5 ¶3 for a decision scope the user names, including a user-requested choice among options (0001 §1.8.3) (§3.7).
- **Covered decision** — a decision within the decision scope of an active user-requested approval point.
- **User direction** — goal content, advisory process preferences, explicit delegations and user-requested approval points: the standing statements by which the user directs the workflow other than by approval. Spending instructions are user direction owned by 0007.
- **Incidental departure** — ARYNTH's not following an incidental part of goal content because reaching the target outcome requires it (§3.5.5).
- **Approval request** — ARYNTH's putting an approval-requiring decision to the user for approval, or its presenting options at a user-requested choice among options (§3.8). It is a functional act, not a message or an interface element.
- **Proposal** — the decision ARYNTH recommends and puts forward for approval in an approval request.
- **Alternative** — a materially distinct decision presented for approval alongside the proposal under §3.8.5.
- **Current request** — an approval request whose proposal is still the decision ARYNTH would take under the current workflow state (§3.9.7).
- **Withdrawn request** — an approval request that ARYNTH has withdrawn under §3.9.8.
- **Lapsed approval** — an approval that became stale before ARYNTH acted on it (§3.9.10).
- **Acting on an approved decision** — ARYNTH's beginning to carry out the approved decision in the workflow. This includes beginning meaningful work on its basis or, before entry, beginning the workflow on its basis.
- **Intervention** — a user action concerning an existing workflow that may affect that workflow (§3.10.2).
- **Unresolved intervention** — an intervention whose effect has not yet been determined and applied (§3.11.1).
- **Clarification of intent** — ARYNTH's request to the user to establish what an ambiguous intervention means (§3.10.8). It is not an approval point.
- **User change** — an intervention by which the user explicitly changes goal content or other user direction (§3.12).
- **Necessary consequence** — a change to a prior user-approved decision that is required to carry out a user change consistently and is attributable to that change (§3.12.5, §3.12.8).

## 3.3 Autonomy Boundary

**3.3.1 Autonomy by default.** ARYNTH makes every decision in a workflow autonomously unless an approval authority in §3.4 applies to that decision. [GS 1.5 ¶1, ¶2, ¶3]

**3.3.2 Single boundary.** §3.3 and §3.4 together are the Functional Map's single autonomy boundary. Other areas apply them and do not restate or extend them. The following are ARYNTH decisions under §3.3.1, and this document does not list them again:

- the workflow decisions in 0002 §2.3.5;
- the details left open in 0001 §1.4.6;
- explicitly delegated choices (§3.13).

[Derived: GS 1.5; 0000 §0.4; 0001 §1.4.6; 0002 §2.3.5]

**3.3.3 Authority must be identified.** Any request by ARYNTH for a user decision, approval or input must rest on an identified authority:

1. for an approval, an approval authority in §3.4;
2. for any other request, a legitimate user touchpoint under 0002 §2.14.2.

A request that cannot identify its authority is invalid. ARYNTH must not make it, and makes the decision itself. [GS 1.5 ¶3, GS 1.6 ¶3; 0002 §2.14.2, §2.14.8]

**3.3.4 Autonomy within user direction.** Autonomy does not permit ARYNTH to disregard user direction. ARYNTH makes its decisions within whichever of the following apply:

- goal content (§3.5);
- explicit delegations (§3.13);
- user-requested approval points (§3.7);
- prior user-approved decisions (§3.5).

Advisory process preferences inform those decisions as provided in §3.5.6. A detail that goal content specifies is not a detail left open under 0001 §1.4.6. [GS 1.1 ¶2, GS 1.5; 0001 §1.4.6]

**3.3.5 Autonomy within spending authorization.** Autonomy does not authorize spending. Every ARYNTH decision remains subject to GS 1.8 and 0007. [GS 1.8]

**3.3.6 Materiality used, not defined.** This document applies materiality as GS 1.5 uses it. It does not define the criteria for judging whether a decision is a material change, or whether a part of goal content is material or incidental. Those criteria are deferred (§3.17). [0001 §1.2, §1.14; 0000 §0.1]

## 3.4 Approval Authorities

**3.4.1 Closed set.** A decision requires user approval only when:

1. ARYNTH would materially change the user's defined content production goal;
2. ARYNTH would override a prior user-approved decision;
3. the decision is a covered decision of a user-requested approval point;
4. another section of the Global Spec explicitly requires approval.

[GS 1.5 ¶2, ¶3]

**3.4.2 Other Global Spec approvals.** The only approval that another Global Spec section explicitly requires in V1 is spending approval under GS 1.8. Spending approval is owned by 0007.

GS 1.1 describes a confirmed state as one that has passed ARYNTH's required checks and, where required, user approval. That description does not itself create an approval requirement. Whether approval is required for any work is determined by §3.4.1 (0002 §2.5.4). GS 1.9 requires no user acceptance of a production-ready outcome.

[GS 1.1 ¶3, GS 1.8, GS 1.9 ¶1; 0002 §2.5.4]

**3.4.3 No other authority.** This document introduces no approval authority, and no later rule may introduce one. In particular, none of the following is an approval authority or creates one:

- uncertainty;
- the existence of several valid approaches;
- a failed required check;
- a wish for reassurance or confirmation;
- the possible usefulness of a retry, redo or rewrite;
- a change to an execution detail or to the execution strategy;
- the difficulty of a workflow decision.

[GS 1.5 ¶3; 0002 §2.14.4]

**3.4.4 Independent authorities.** Each approval authority applies independently. One decision may be subject to more than one authority. Each authority that applies must be satisfied before ARYNTH acts on the decision (§3.14.3). [GS 1.5 ¶2, ¶3, GS 1.8]

**3.4.5 Before acting.** ARYNTH must not make or act on an approval-requiring decision before the required approval has been given. Until then, the matter is a pending item, and 0002 §2.7 determines which work is held. [GS 1.5 ¶2; 0002 §2.7, §2.13.1]

**3.4.6 No authority, no approval.** Where no approval authority applies to a decision, ARYNTH must not seek approval for it, and makes the decision itself. [GS 1.5 ¶1, ¶3; 0002 §2.14.4]

**3.4.7 No circumvention.** ARYNTH must not avoid an approval requirement by describing, dividing or sequencing a decision so that the requirement appears not to apply. Whether a decision is a material change or an override is judged by its effect on the goal or on the prior user-approved decision, however the decision is described. [GS 1.5 ¶2; 0002 §2.6.7]

## 3.5 Prior User-Approved Decisions & Goal Direction

**3.5.1 Four distinct kinds.** The following are distinct and must not be treated as one another.

| Kind | Arises from | Effect |
|---|---|---|
| Goal content | The user's statements of the desired result, including instructions and preferences, at entry or through intervention. It comprises result direction and explicit process constraints, and not advisory process preferences, which §3.5.6 governs (§3.5.4). | Honored. A departure from a material part requires approval as a material change. A departure from an incidental part is permitted only under §3.5.5. |
| Explicit delegation | An express statement that ARYNTH may make an identified choice | The delegated choice is an ARYNTH decision (§3.13). |
| User-requested approval point | An explicit user request to approve decisions within a named scope | Covered decisions require approval each time they are made or remade (§3.7). |
| Prior user-approved decision | A decision the user made through an approval event or at a user-requested approval point | May not be overridden without approval under GS 1.5, except as a necessary consequence of a user change (§3.12). |

[0003-A; GS 1.5; 0001 §1.4.4]

**3.5.2 Prior user-approved decisions.** A prior user-approved decision exists only where the user has made a decision through an approval event or at a user-requested approval point. Examples:

1. approving a material narrowing, before entry (0001 §1.7.3) or during progression (0002 §2.10.7);
2. approving any other material change, or an override;
3. choosing among options at a user-requested choice among options;
4. approving a plan or sequence at a user-requested approval point;
5. approving a covered decision at any other user-requested approval point;
6. settling the decision presented in an approval request by a complete user decision, including at a user-requested approval point (§3.9.5 item 1).

An approved decision becomes a prior user-approved decision when ARYNTH acts on it. An approval that lapses before then does not (§3.9.10). A choice the user makes at a user-requested choice among options is the user's decision from the moment it is made. For a complete user decision, §3.9.11 determines when each part becomes a prior user-approved decision. [0003-A, 0003-E; GS 1.5 ¶2]

**3.5.3 Goal content is not an approval.** Goal content, including instructions and preferences given at entry or through intervention, is not a prior user-approved decision merely because the user stated it. The same applies to a statement the user makes about existing work other than at an approval event or a user-requested approval point, such as an instruction to keep that work: it is goal content to the extent that it expresses what the user wants. It is not a prior user-approved decision. [0003-A]

**3.5.4 Result direction, process constraints and process preferences.** User direction about the result, and about how it is produced, is one of the following:

1. **Result direction** defines, constrains or changes the intended outcome or its required characteristics. It is goal content.
2. **An explicit process constraint** clearly requires or prohibits a specific production or workflow behavior, such as "do not use stock footage", "use this supplied recording" or "do not generate new images". It is goal content, and it is honored according to its actual meaning, subject to the applicable approval and scope rules. Where it requires a particular material or use, 0001 §1.5.6 applies. Where it requires the user's approval of a decision, such as "the script must be approved before narration", it is a user-requested approval point under §3.7.
3. **An advisory process preference** expresses a desired approach without clearly requiring it, such as "I prefer drafting the script before looking for visuals", "ideally use model X" or "if possible, work on the voice first". It is not goal content, and §3.5.6 governs it.

Whether a direction clearly requires or prohibits a behavior is judged by what the user asks for, not by its wording alone. Where that cannot be determined, 0001 §1.4.7 applies at entry and §3.10.8 applies during a workflow.

ARYNTH must honor goal content. Honoring goal content does not turn the workflow decisions around it into user decisions. [0003-A; GS 1.5; 0001 §1.4.6, §1.4.7, §1.5.6; 0002 §2.6.9]

**3.5.5 Departure from goal content.** A departure from goal content, including from an explicit process constraint, is governed as follows:

1. a departure from a material part of goal content is a material change and requires approval under GS 1.5;
2. ARYNTH may depart from an incidental part of goal content only when reaching the target outcome requires that departure;
3. an incidental departure requires no approval, unless it would also override a prior user-approved decision or is a covered decision, in which case §3.4 applies;
4. an incidental departure must remain understandable to the user through 0004.

ARYNTH must not depart from goal content merely because it prefers another result, approach or execution. [0003-A; GS 1.5 ¶2, GS 1.6; 0001 §1.7.4, §1.7.7]

**3.5.6 Advisory process preferences and no approval locks.** An advisory process preference informs ARYNTH's decisions. It does not remove ARYNTH's ownership under 0002 of any of the following:

- sequencing;
- execution strategy;
- tools and models;
- corrective paths;
- other ordinary execution decisions.

ARYNTH takes the preference into account. It may depart from the preference when another valid execution choice better serves the target outcome, reliability, cost or progression. Such a departure is an ARYNTH decision and creates no approval point. §3.4 applies only where the departure would also:

- materially change the goal;
- override a prior user-approved decision;
- be a covered decision of an active user-requested approval point; or
- require approval under another Global Spec authority.

Whether a departure from an advisory process preference is made understandable is owned by 0004.

Goal content does not require approval for a necessary incidental departure (§3.5.5). Neither goal content nor an advisory process preference is a prior user-approved decision. Neither creates a user-requested approval point, except where the user explicitly requires approval of a decision (§3.5.4 item 2, §3.7.1). ARYNTH must not treat ordinary instructions or preferences as approval locks. [0003-A; GS 1.5 ¶1, ¶3; Derived: 0002 §2.3.5, §2.6.5, §2.6.6, §2.9.4]

**3.5.7 What a prior user-approved decision protects.** ARYNTH must not override a prior user-approved decision without approval under GS 1.5, except to the extent that §3.12.5 authorizes a necessary consequence of a user change.

- The protection covers the decision as approved under §3.6. It does not cover details that were not presented for approval.
- The protection does not depend on whether work that embodies the decision is confirmed (§3.14.1).

[GS 1.5 ¶2; 0003-B, 0003-C]

**3.5.8 Overrides.** ARYNTH overrides a prior user-approved decision when a decision it would take would depart from, reverse or replace that decision, or would be inconsistent with it. This includes reopening, replacing or discarding work that embodies the decision where that would have one of those effects. Carrying out an approved decision with details that were not presented for approval is not an override. [GS 1.5 ¶2; 0003-B; 0002 §2.8.4]

**3.5.9 ARYNTH's own reasons.** Sometimes ARYNTH's own workflow reasons, such as a failed required check, would require a decision that overrides a prior user-approved decision. That decision requires approval under GS 1.5. A user change supplies authority only under §3.12.5. [GS 1.5 ¶2; 0002 §2.8.4, §2.9.4]

**3.5.10 Spending approvals.** An approval given solely under GS 1.8 approves spending, and 0007 owns its scope and effect. It does not make the workflow decision whose spending it authorized a prior user-approved decision for the purposes of GS 1.5. [0003-B; GS 1.8; Derived: GS 1.5]

**3.5.11 Delegated choices and approval points.** A choice ARYNTH makes under explicit delegation is an ARYNTH decision, not a prior user-approved decision (§3.13.6). A user-requested approval point is user direction, not a prior user-approved decision. A decision approved, chosen or settled by a complete user decision at a user-requested approval point becomes one under §3.5.2. [0003-A, 0003-D; 0001 §1.4.4]

## 3.6 Approval Scope

**3.6.1 What an approval authorizes.** An approval authorizes:

1. the specific decision as presented for approval;
2. the consequences explicitly identified in the approval request.

[0003-B]

**3.6.2 What an approval does not authorize.** An approval does not authorize:

1. unrelated decisions;
2. later decisions of the same kind;
3. consequences that were not identified in the approval request and that would independently require approval;
4. any standing or blanket authority for the future.

ARYNTH must not treat an earlier approval as permission for a later decision because the later decision is similar, or because the user approved a similar decision before. [0003-B; GS 1.5 ¶2]

**3.6.3 Narrower interpretation.** Where the scope of an approval is ambiguous, the narrower interpretation applies. [0003-B]

**3.6.4 What is presented for approval.** Information that an approval request gives to explain the proposal, its consequences or its alternatives does not become part of the approved decision unless it is presented for approval. Details not presented for approval remain ARYNTH decisions, unless another rule requires user involvement. An approved plan or sequence therefore binds only as presented. It does not freeze workflow details that were not presented for approval. [0003-B; GS 1.5 ¶1]

**3.6.5 Unidentified consequences.** Carrying out an approved decision may have a consequence that was not identified in the approval request and that would independently require approval. That consequence requires its own approval. Until that approval is given, the consequence is a pending item, and 0002 §2.7 determines which work is held. This applies equally to the accepted portion of a mixed response: a user modification in the same response does not authorize the consequence (§3.12.8). [0003-B; GS 1.5 ¶2; 0002 §2.7]

**3.6.6 Approval does not compel obsolete execution.** An approval authorizes a decision. It does not require ARYNTH to carry out a decision that has become obsolete (§3.9.10). [0003-E]

## 3.7 User-Requested Approval Points

**3.7.1 Established only by the user.** A user-requested approval point exists only where the user has explicitly requested it. The user may do so at entry, where the request is carried forward under 0001 §1.3.4, or through intervention. Adding, changing or removing an approval point is itself an intervention. [GS 1.5 ¶3; 0003-D; 0001 §1.3.4]

**3.7.2 No approval points on ARYNTH's initiative.** ARYNTH must not create, propose, suggest or offer an approval point on its own initiative. This includes doing so to reduce its own uncertainty, to seek reassurance or to share responsibility for a workflow decision. [GS 1.5 ¶3; 0003-D; 0002 §2.7.12, §2.14.4]

**3.7.3 Decision scope.** An approval point covers the decisions the user names and never extends beyond them. Where the named scope is ambiguous, §3.10.8 applies.

Preparing what is to be presented for approval, such as a proposed version of covered content, may or may not itself be within the covered decision. That depends on the scope the user named. [0003-D; GS 1.5 ¶3]

**3.7.4 Application each time.** An active approval point applies each time a covered decision is made or remade within the workflow, unless the user has scoped it more narrowly. This includes decisions made or remade through:

- corrective work;
- reopening;
- reassessment after a user change;
- revision work.

For example, a request to be asked before every script change applies to every later script change.

A covered decision that the user has settled personally at the approval point, by a choice among options or by a complete user decision (§3.9.5 item 1), is not presented again for approval. Carrying it out is not remaking it. Where part of it lapses before ARYNTH acts on it, §3.9.11 governs. Where the user's response leaves ARYNTH to create or choose a new covered proposal, the approval point applies to that proposal (§3.9.5 item 2). [0003-A, 0003-D]

**3.7.5 Lifetime.** An approval point remains active until:

1. the user removes it;
2. the user changes it, in which case the changed approval point applies from then on;
3. a limit the user set on its lifetime is reached, as with a request to be shown only the first script;
4. the workflow no longer involves the covered decision (§3.7.6).

An approval point does not end:

- because the covered decision has been made once;
- because production-ready completion has been reached;
- because a revision begins;
- because the workflow is stopped and later continued;
- because applying it is inconvenient to ARYNTH.

[0003-D; GS 1.7 ¶5, GS 1.9 ¶3]

**3.7.6 No longer involved.** An approval point stops applying when the workflow no longer involves the covered decision. This happens when, under the goal as it then stands, the covered decision no longer arises in the workflow, for example because a user change has removed the part of the goal to which it relates.

It does not stop applying while the covered decision may still arise in the workflow, including in revision work. If a later change brings the covered decision back into the workflow, the approval point applies to it again, unless the user has removed it or the user's limit has been reached. [0003-D; Derived: GS 1.5 ¶3]

**3.7.7 Taking effect.** A newly added or broadened approval point applies to covered decisions made after it is established. It also applies to a covered decision whose resulting work has not yet been completed. It does not require retrospective approval of completed work. The user may change completed work through intervention or revision. [0003-D; Derived: GS 1.5 ¶3, ¶4]

**3.7.8 Removal and narrowing.** When the user removes or narrows an approval point:

1. a pending approval request that rested only on that approval point, and that no longer falls within it, is withdrawn under §3.9.8;
2. the decision returns to ARYNTH, unless another approval authority applies;
3. work held only on account of that approval point is released, and 0002 reassesses remaining work (0002 §2.7.10).

[0003-D, 0003-E; GS 1.5 ¶1]

**3.7.9 Held work.** Which work is held while a covered decision awaits approval, and which independent work continues, is determined by 0002 §2.7, including §2.7.4 item 2 and §2.7.8. [0002-C; 0002 §2.7.4, §2.7.8]

**3.7.10 Bounded involvement.** Approval at an approval point authorizes the covered decision as presented. It does not open further user decisions beyond the named scope. [0003-B; 0002 §2.14.6]

**3.7.11 Approval versus choice among options.** A user-requested approval point and a user-requested choice among options are distinct.

1. **Approval point.** At a user-requested approval point, ARYNTH selects and develops the covered proposal under its normal workflow authority, including its selection among working alternatives (0002 §2.6.10). It then obtains the requested approval before using that decision. An approval point does not permit ARYNTH to present several working candidates for the user to choose among. For example, "let me approve the script before narration" means that ARYNTH presents its script for approval, not three scripts to choose from.
2. **Choice among options.** Where the user has separately asked to choose among options, the approval point is a user-requested choice among options (0001 §1.8.3):
   - ARYNTH presents the options the user's request calls for, together with its recommendation;
   - the options remain intermediate options, and the workflow keeps one target outcome;
   - §3.8.5 does not limit the options the user asked to choose among;
   - the user's choice is governed by §3.9.11.

[0001 §1.8.3; 0002 §2.6.10; 0003-D, 0003-E, 0003-F]

**3.7.12 Approval points and workflow entry.** A user-requested approval point does not become a workflow-entry condition unless the user explicitly scopes it to occur before the workflow begins.

1. **Default.** An approval point that applies to decisions made during the workflow does not delay entry. This includes one requested at entry that covers ARYNTH's plan for pursuing the goal. The approval point applies once the workflow begins, and work that depends on the covered decision is then held under 0002 §2.7 until the decision is approved.
2. **Explicitly before entry.** The user may explicitly ask to approve something before the workflow begins. Examples are "before the workflow begins, let me approve your interpretation of my goal" and "show me the initial plan before you start the workflow". That boundary is honored (0001 §1.3.5):
   - the approval occurs before the workflow is in progress, and the workflow begins only once the requested approval has been given and the entry conditions in 0001 §1.3.2 hold;
   - until then, no workflow exists, and §3.9.12 items 1, 4 and 5 apply;
   - the request follows §3.8 and its outcomes follow §3.9;
   - on decline, no workflow begins on the declined basis, and ARYNTH may present a different proposal, subject to §3.9.4, or the user may redefine the goal;
   - an approved decision becomes a prior user-approved decision when the workflow begins on its basis;
   - once the workflow begins, the approval point has no further effect, unless the user also scoped it to decisions made during the workflow.
3. ARYNTH must not treat an approval point as applying before entry unless the user has explicitly scoped it that way.

[0001 §1.3.2, §1.3.4, §1.3.5, §1.3.7; 0002 §2.3.2; 0003-D]

**3.7.13 Approval points and spending.** A user direction that concerns spending, including a request to be asked before paid actions, is a spending instruction governed by 0007. To the extent that it is also a request to approve identified workflow decisions, §3.7 applies to that part. [GS 1.5 ¶3, GS 1.8; 0001 §1.3.4]

## 3.8 Approval Requests

**3.8.1 When a request is made.** ARYNTH makes an approval request only:

- for an approval-requiring decision that it would take under the current workflow state; or
- to present options at a user-requested choice among options.

[GS 1.5 ¶2, ¶3; 0003-E]

**3.8.2 Required decision facts.** Where applicable, an approval request must make the following knowable to the user:

1. the proposal: what ARYNTH recommends, and exactly what is presented for approval (§3.6.4);
2. the authority that makes approval necessary, and each authority where more than one applies (§3.4);
3. for a material change or an override, why ARYNTH would take the decision;
4. for a material change, what would materially change in the goal;
5. for an override, which prior user-approved decision would be overridden, and how;
6. for a covered decision, which user-requested approval point applies;
7. any part of the goal that would no longer be performed;
8. known consequences for other prior user-approved decisions, and any other known consequence that would independently require approval (§3.8.3);
9. any materially distinct alternatives presented under §3.8.5;
10. cost impact, where 0007 requires it;
11. where already known, that declining would leave no valid path to the target outcome.

[GS 1.5, GS 1.6 ¶2, GS 1.8 ¶3; 0003-B, 0003-F]

**3.8.3 Known consequences.** ARYNTH must identify in the request every consequence it knows of that would independently require approval. A consequence that is not identified is not authorized by the approval (§3.6.5). [0003-B]

**3.8.4 Recommendation.** Where approval is required, ARYNTH presents its recommended decision as the proposal. [0003-F]

**3.8.5 Alternatives.** ARYNTH may also present alternatives, but only where all of the following hold:

1. each alternative is materially different from the proposal and from every other alternative;
2. each would validly resolve the same approval-requiring issue;
3. each would itself require user approval.

Alternatives are materially distinct ways of resolving the approval-requiring boundary itself. An example is a material narrowing that could validly be resolved by removing either of two materially different goal requirements, where each resolution would require approval. A candidate for a covered decision is not such an alternative merely because a user-requested approval point covers the decision. It is a working alternative: 0002 §2.6.10 governs it, and ARYNTH selects among such candidates itself (§3.7.11 item 1).

ARYNTH must not present variants that differ only in workflow details ARYNTH owns. ARYNTH is not required to find or manufacture alternatives where one clear proposal is sufficient. Presenting alternatives creates no approval trigger. [0003-F; GS 1.5 ¶3; 0002 §2.6.10]

**3.8.6 No disguised decisions.** An approval request must not:

- include an ARYNTH decision for the user to decide;
- be used to seek reassurance;
- ask the user to approve work in general, such as whether ARYNTH should continue.

[GS 1.5 ¶3, GS 1.6 ¶3; 0002 §2.14.5]

**3.8.7 Requests before entry.** An approval request can arise before a workflow begins. Examples are a request to approve a material narrowing under 0001 §1.7.3, and a request at an approval point the user has explicitly scoped to occur before entry (§3.7.12). §3.8.2 applies to it as far as its facts apply, including what would not be performed (0001 §1.11.1). [0001 §1.7.3, §1.11.1]

**3.8.8 Facts, not presentation.** This section defines the decision facts an approval request must make knowable. Presentation, wording, layout, grouping, timing and notification are owned by 0004. The content of cost information and the rules for it are owned by 0007. [GS 1.6, GS 1.8; 0000 §0.2]

## 3.9 Approval Outcomes & Currency

**3.9.1 Outcomes.** A current approval request is resolved in one of these ways:

- the user approves;
- the user declines;
- the user gives a modified response;
- ARYNTH withdraws the request.

The absence of a response resolves nothing. [GS 1.5; 0003-E]

**3.9.2 Approve.** When the user approves the proposal, or a presented alternative, as presented:

1. the approval authorizes what §3.6.1 provides, and nothing more;
2. the approved decision is released to orchestration, and 0002 reassesses the work that depended on it (0002 §2.7.10);
3. the approved decision becomes a prior user-approved decision when ARYNTH acts on it (§3.5.2).

[0003-B, 0003-E; 0002 §2.7.10]

**3.9.3 Clear approval only.** A response approves only where it clearly approves the proposal, or a presented alternative, as presented. A response whose meaning is unclear is not approval, and §3.10.8 applies to it. [0003-B; GS 1.5 ¶2]

**3.9.4 Decline.** When the user declines:

1. the declined proposal and any declined alternative are not authorized, and ARYNTH must not carry them out while they require approval;
2. the goal and prior user-approved decisions that the proposal concerned remain as they stood, and remain protected under §3.4;
3. 0002 reassesses remaining work for another valid path that ARYNTH may take autonomously (0002 §2.7.10, §2.9);
4. ARYNTH must not present the same proposal again, or one substantially equivalent to it, unless circumstances have materially changed since the decline;
5. where another approval-requiring decision is then the decision ARYNTH would take, ARYNTH makes a new request for it under §3.8;
6. where no valid path remains, the workflow cannot currently continue, as governed by 0002 §2.13.8 and 0006, and ARYNTH must not substitute a different goal on its own initiative.

[GS 1.5, GS 1.7 ¶4; 0002 §2.10.8, §2.13.8; Derived: 0003-E]

**3.9.5 Modified response.** A modified response alters the decision presented, rather than approving the proposal or a presented alternative as presented or simply declining it. Examples are an approval that adds changes or conditions, and a different decision stated by the user. The proposal as a whole is not approved or carried out as presented. Any portion of it that the user accepts unchanged is approved as presented (§3.12.8 item 1). A modified response is an intervention, and §3.11 applies to it until it is resolved. It is one of the following:

1. **Complete user decision.** The response itself fully settles the decision presented, so that no further ARYNTH decision is needed to determine what that decision is. An example is "Approved with one change: replace 'today' with 'this week'; everything else stays."
   - The decision the user specified is the resolved decision at that approval request, or at the user-requested approval point concerned.
   - ARYNTH must not ask the user to approve it again.
   - It is a decision the user made at an approval event or a user-requested approval point (§3.5.2). §3.9.11 governs when each of its parts is current and when each is protected as a prior user-approved decision.
   - The part the user specified is the user's own change, and §3.12.4 governs its scope. Any portion of ARYNTH's proposal that the response accepts remains approved only under §3.6. §3.12.8 determines which consequences belong to each part, and which of them §3.12.5 authorizes. Any spending the decision requires remains subject to 0007.
2. **Direction requiring a new proposal.** The response gives direction but leaves ARYNTH to create or choose a materially new proposal, as with "make the opening much stronger and show me again".
   - The direction is user direction under §3.5 and is resolved as an intervention under §3.10–§3.12.
   - ARYNTH carries out the necessary work.
   - Where the resulting decision still requires approval, including because it is a covered decision of the user-requested approval point, ARYNTH makes a new request for it.
3. **Unclear response.** It cannot be determined whether the response settles the decision or asks ARYNTH for a new proposal. The response is resolved under §3.10.8. That resolution must not be used to create a repeated request for a decision the user has settled.

Apart from item 1, what the user states in a modified response is user direction under §3.5. It is not a prior user-approved decision merely because it was given in response to an approval request.

A response may approve or decline as presented and also contain a separate intervention. In that case the approval or decline takes effect under §3.9.2 or §3.9.4, and the separate intervention is handled under §3.10. [0003-A, 0003-D, 0003-E; GS 1.5 ¶4]

**3.9.6 No response.** The absence of a response is never approval, decline or delegation.

- While a current request awaits a response, work that depends on it is held under 0002 §2.7, and independent work continues.
- The absence of a response does not by itself make a request stale.
- Waiting, attention and any consequence of a prolonged absence of response are owned by 0006 and 0004. None of them may treat silence as approval.

[GS 1.5 ¶2, GS 1.7 ¶3; 0002-C; 0003-E]

**3.9.7 Currency.** An approval request remains valid only while its proposal is still the decision ARYNTH would take under the current workflow state. [0003-E]

**3.9.8 Withdrawal.** ARYNTH withdraws an approval request when its proposal:

1. becomes unnecessary;
2. becomes obsolete;
3. is superseded; or
4. is no longer the decision ARYNTH would take, including because the approval authority on which the request rested no longer applies.

On withdrawal:

- a response to the withdrawn request authorizes nothing;
- where approval is still required for a different decision, ARYNTH makes a new request for that current decision;
- the pending item that the request created is resolved, and 0002 releases and reassesses the affected work (0002 §2.7.10).

[0003-E; 0002 §2.7.10]

**3.9.9 Choice requests.** §3.9.7 and §3.9.8 apply to a request at a user-requested choice among options until the user chooses. Where the options become obsolete, ARYNTH withdraws the request. If the approval point still applies, ARYNTH presents current options. [0003-D, 0003-E]

**3.9.10 Lapse.** An approval that becomes stale before ARYNTH acts on it lapses. This includes the accepted portion of ARYNTH's proposal within a complete user decision (§3.9.11). A lapsed approval does not become a prior user-approved decision, and ARYNTH does not carry out the obsolete decision. Where approval is still required for a different decision, ARYNTH makes a new request for that current decision. [0003-E]

**3.9.11 Currency of approvals, user choices and complete user decisions.** This rule is the single authority for when an approved or user-made decision is current and when it becomes a prior user-approved decision.

1. **Acted-on approvals.** Once ARYNTH acts on an approved decision, the decision is a prior user-approved decision and can no longer lapse. Any later change to it is governed by §3.5.7 and §3.12.
2. **User choices.** A choice the user has made at a user-requested choice among options is the user's decision from the moment it is made. It does not lapse merely because ARYNTH has not yet acted on it.
3. **Complete user decisions.** A complete user decision (§3.9.5 item 1) settles what the user decided. It does not give all of its parts the same currency. Before ARYNTH acts:
   - **Accepted portion.** Any portion of ARYNTH's proposal that the user accepted remains an approval of that proposal. It is subject to §3.9.7–§3.9.10, and it becomes a prior user-approved decision only when ARYNTH acts on it. If it becomes stale before then, it lapses under §3.9.10. It does not become a prior user-approved decision because the user also specified a modification in the same response, and ARYNTH needs no override approval to stop following it.
   - **User-specified part.** The part the user specified is the user's own decision, and it is a prior user-approved decision from the moment it is made. It is protected according to its actual meaning and scope, subject to the dependence rule below. It does not lapse merely because ARYNTH has not yet acted on it.
   - **Proposal-dependent user direction.** A user-specified part that has meaning only within the accepted proposal falls with that proposal if the proposal lapses. An example is title B specified in place of title A in a proposal that has since lapsed. It does not require ARYNTH to recreate or continue the obsolete proposal, and abandoning the proposal is not an override merely because the user specified part of it.
   - **Independent continuing direction.** Some user direction applies independently of the proposal, whether it is a user-specified part or a separate direction in the same response (§3.9.5). An example is "do not use stock footage anywhere in this workflow". Such direction continues to apply according to its own meaning and scope as user direction under §3.5, even if the proposal lapses, and ARYNTH must not discard it because the proposal changed.
   - **Unclear dependence.** Where it is unclear whether a user-specified part depends on the proposal, §3.10.8 applies.
4. **After a lapse.** Reassessment follows §3.9.10 and 0002 (0002 §2.7.10, §2.9). Where a current decision then requires approval, including a covered decision that ARYNTH must remake, ARYNTH makes a new request for that decision. Determining which parts remain current is not a request to approve them again. A user-specified part that remains current is not presented for approval again (§3.9.5 item 1).

The authority for the consequences of each part is determined separately, by §3.12.8. [0003-A, 0003-B, 0003-E; GS 1.5 ¶2; 0002 §2.7.10]

**3.9.12 Before entry.** An approval may arise before a workflow begins, such as approval of a material narrowing under 0001 §1.7.3 or §1.8.5. This section applies to it, with the following differences:

1. no workflow exists, so the holding, waiting and orchestration rules of 0002 do not apply (0001 §1.3.7);
2. on approval, the workflow may begin on the narrowed basis if the other entry conditions in 0001 §1.3.2 hold, and the approved narrowing becomes a prior user-approved decision when the workflow begins on that basis;
3. on decline, no workflow begins on the narrowed basis, and the user may redefine the goal (0001 §1.7.3);
4. without a response, no workflow begins, and a goal awaiting such approval is not an in-progress workflow (0001 §1.3.7);
5. a user redefinition of the goal before entry is handled by 0001, and it may make a pending request obsolete under §3.9.8.

Approval at a user-requested approval point that the user has explicitly scoped to occur before entry is governed by §3.7.12, which applies items 1, 4 and 5. Visibility before entry is governed by 0001 §1.11. [GS 1.5 ¶2; 0001 §1.3.7, §1.7.3, §1.8.5, §1.11]

## 3.10 User Intervention

**3.10.1 Right to intervene.** The user may intervene at any time while a workflow is in progress. This includes while the workflow is actively progressing, waiting for approval or information, currently unable to continue, or undergoing a revision. ARYNTH must not require the user to wait for a particular point in progression before intervening. [GS 1.5 ¶4; 0001 §1.9.2]

**3.10.2 What an intervention is.** An intervention is a user action concerning an existing workflow that may affect any of the following:

- goal content, including instructions and preferences;
- advisory process preferences;
- explicit delegation;
- approval decisions, including responses to approval requests;
- user-requested approval points;
- materials or information;
- spending instructions;
- stopping or continuing the workflow;
- revision of the workflow's production-ready outcome;
- the user's understanding of the workflow, through a question or a request for explanation.

[GS 1.5 ¶4; Derived: GS 1.6, GS 1.7, GS 1.8, GS 1.9]

**3.10.3 Intervention is optional.** Intervention is the user's option, not a duty. Progression must not depend on the user intervening. [GS 1.3, GS 1.5 ¶1; 0002 §2.6.3]

**3.10.4 Routing.** ARYNTH recognizes each intervention and routes it by what it asks for.

| Intervention | Routed to |
|---|---|
| Stop | 0006 (GS 1.7 ¶5). |
| Continue a stopped workflow | 0006 first. Any change made in the same request is then handled under this document (0001 §1.10.7). |
| Revision request | 0008 for intake and scope. Revision work then progresses under 0002 §2.11, and interventions during it follow this document (§3.14.4). |
| Spending instruction, including a budget or allowance | 0007. |
| Materials, or information given in response to a request for necessary information | Classification under 0001 §1.5 and use under 0002 §2.10.3. Information requests fall under 0002 §2.13.2 and 0006. An instruction to use a material in a particular way is goal content (0001 §1.5.6; §3.12). |
| Response to an approval request | §3.9. |
| Adding, changing or removing a user-requested approval point | §3.7. |
| Explicit delegation, or a change to or withdrawal of one | §3.13. |
| Change to goal content, including result direction and explicit process constraints | §3.12. |
| Change to an advisory process preference | §3.5.6. The preference informs ARYNTH's decisions from then on. |
| Request for explanation only | 0004. The workflow does not change. |

[GS 1.5 ¶4, GS 1.7, GS 1.8, GS 1.9; 0001 §1.5.6, §1.5.11, §1.10.7; 0002 §2.10.1]

**3.10.5 Composite interventions.** One intervention may contain several elements. Each element is routed to its owner, and ARYNTH must not disregard any element. [Derived: GS 1.5 ¶4]

**3.10.6 Interpretation belongs to 0003.** This document determines what an intervention changes. That includes whether it changes goal content, whether it responds to an approval request, and whether a decision that results from it requires approval. An intervention is interpreted by what the user asks for, not by its form. [GS 1.5; 0001 §1.10.4; 0002 §2.10.1]

**3.10.7 Explanation requests.** A request for explanation only does not change the workflow and does not hold work. It is answered as owned by 0004. ARYNTH must not treat such a request as an instruction to change the workflow. Where it is unclear whether a user statement asks only for an explanation or also for a change, §3.10.8 applies. [GS 1.6; Derived: GS 1.5 ¶4]

**3.10.8 Ambiguous interventions.** Where an intervention admits more than one reading:

1. where ARYNTH can resolve the ambiguity within its autonomy boundary, including from the goal content, the workflow's context or other user direction, it does so;
2. where the ambiguity prevents ARYNTH from determining what the user is changing, and plausible readings would lead to materially different results, ARYNTH may request clarification of intent;
3. otherwise, choosing between the readings is an ARYNTH decision, made within the goal content and the other user direction that applies.

A clarification of intent is not an approval point. It is a request for information necessary to carry out the user's direction, and it is handled as such for waiting and attention purposes (0002 §2.13.2; 0006). It must be limited to what the user is changing. It must not be used to hand an ARYNTH decision back to the user. [GS 1.5 ¶3, GS 1.6 ¶3; 0001 §1.4.7, §1.10.6; 0002 §2.14.5]

**3.10.9 The user's own change needs no approval.** An explicit user change is the user's own direction. It takes effect once resolved, whether or not it is material, and ARYNTH must not ask the user to approve it. This includes a change to something the user previously approved, and the part the user specified in a complete user decision given in response to an approval request (§3.9.5 item 1, §3.12.8). Where a user change leaves ARYNTH to create or choose a decision, that ARYNTH decision remains subject to §3.4, including any active user-requested approval point (§3.9.5 item 2, §3.12.5 item 4). [GS 1.5 ¶2; 0003-A, 0003-C; 0001 §1.7.3]

**3.10.10 Stopped workflows.** An intervention concerning a stopped workflow does not continue that workflow unless the user chooses to continue it. Continuation is handled by 0006 first and remains subject to 0001 §1.9.6. [GS 1.7 ¶5; 0001 §1.9.6, §1.10.7]

**3.10.11 Completed workflows.** For a workflow that has reached production-ready completion and has no revision underway:

- a request to change its outcome is a revision request, routed to 0008;
- a request for explanation is routed to 0004;
- review and export are owned by 0008;
- a change to user direction takes effect for any revision work that later begins.

[GS 1.9; 0001 §1.10.3; 0002 §2.13.5]

**3.10.12 Which workflow.** Whether a user request concerns an existing workflow or is a new goal is determined by 0001 §1.10. [0001 §1.10]

## 3.11 Intervention During Active Work

**3.11.1 Unresolved intervention.** An intervention is unresolved from the moment it is received until its effect has been determined and applied. This document determines and applies the effect of the elements it owns. For elements routed elsewhere, the owning area does so.

An intervention that awaits a clarification of intent remains unresolved. Once any approval required by an intervention has become a pending item under 0002 §2.7, the intervention is resolved, and the pending item governs the work that depends on it. [Derived: GS 1.5 ¶4; 0002 §2.13.3]

**3.11.2 Dependency-scoped holding.** While an intervention is unresolved, work that it could change is held in the same way as work that depends on a pending item (0002 §2.7.5–§2.7.7). The intervention could change work if it could change whether that work is needed or what that work must be. Where ARYNTH cannot determine whether the intervention could change a piece of work, that work is held. [0002-C; 0002 §2.7.4–§2.7.7]

**3.11.3 No knowingly invalidated work.** ARYNTH must not knowingly continue producing work that an unresolved intervention could invalidate. If the intervention could change the active meaningful work item, that item stops being active. Partial progress on it is not confirmed work (0002 §2.7.7). [GS 1.5 ¶4; 0002 §2.7.7]

**3.11.4 Independent work continues.** Work that the unresolved intervention could not change may continue. An intervention does not by itself hold the whole workflow. Where resolution awaits the user, the whole workflow waits only when no independent work that may validly progress remains (0002 §2.7.9). [0002-C; 0002 §2.7.8, §2.7.9]

**3.11.5 Stop is different.** A stop is not dependency-scoped. It halts further execution as provided by GS 1.7 and 0006. [GS 1.7 ¶5; 0002 §2.13.6]

**3.11.6 Explanation requests do not hold.** A request for explanation only holds no work (§3.10.7). [Derived: GS 1.6]

**3.11.7 Prompt resolution by ARYNTH.** ARYNTH resolves an intervention itself, without waiting for the user, unless clarification of intent (§3.10.8) or approval (§3.4) is required. ARYNTH must not leave an intervention unresolved in order to avoid a decision. [GS 1.5 ¶1; Derived: GS 1.3]

**3.11.8 On resolution.** When an intervention is resolved:

- progression continues on the goal and user direction as they then stand;
- 0002 re-engages and reassesses remaining work (0002 §2.9.8, §2.13.12);
- any approval that the resolution requires is a pending item under 0002 §2.7.

[0002 §2.9.8, §2.10.1, §2.13.12]

**3.11.9 Several interventions.** Where the user makes several interventions, they are interpreted together, in the order they were made. Where they conflict, the later one governs to the extent of the conflict. Where it is unclear whether the user meant to change the earlier direction, §3.10.8 applies. [Derived: GS 1.5 ¶4]

**3.11.10 Effect on pending requests.** An intervention may make stale a pending approval request, or an approval that ARYNTH has not yet acted on. §3.9.7–§3.9.10 then apply. [0003-E]

**3.11.11 Completion does not overtake an unresolved intervention.** An unresolved intervention may be able to change or invalidate work on which a production-ready determination would depend. In that case, the workflow must not be treated as having reached production-ready completion on the basis of that work until:

1. the intervention is resolved; and
2. 0002 has reassessed progression, including routing any affected result to the required checks owned by 0005.

This applies equally to revision work: a revised result must not be treated as production-ready on that basis while the intervention is unresolved. This rule concerns interventions received before production-ready completion is reached; after it, §3.10.11 applies. This rule does not:

- hold the whole workflow, or independent work and checks that the intervention could not affect;
- make this document the owner of required checks, final quality checks or production-ready criteria;
- create a separate pause state.

0005 owns checks, quality, confirmation and the production-ready determination. 0002 owns progression, reassessment and reopening. 0008 owns replacement of the current production-ready outcome. [GS 1.1 ¶4, GS 1.5 ¶4, GS 1.9 ¶5; Derived: 0002 §2.9.7, §2.13.5]

**3.11.12 Mechanics not defined.** This section defines only which work may be selected or continued, and the completion boundary in §3.11.11. It does not define how execution below the meaningful-work level is halted, cancelled or rolled back, and it defines no concurrency mechanism (§3.17). [0000 §0.5; 0002 §2.7.2]

## 3.12 Goal Changes & Consequential Rework

**3.12.1 Goal changes belong to the workflow.** A change to the goal of an in-progress workflow, including a material change, belongs to that workflow as an intervention and does not begin a new workflow. This document determines whether an intervention changes goal content. [0001 §1.10.4; 0002 §2.10.1]

**3.12.2 No approval of the user's own change.** §3.10.9 applies to every user change to goal content, including a material change. [GS 1.5 ¶2; 0003-C]

**3.12.3 Resolving a goal change.** ARYNTH resolves a user change to goal content as follows:

1. determine what the change asks for (§3.10.6, §3.10.8);
2. classify what it asks for under 0001 §1.6, and handle any out-of-scope part under §3.12.4;
3. apply the one-target-outcome rule (0001 §1.8) to what it asks for;
4. determine its consequences for prior user-approved decisions under §3.12.5;
5. determine whether any decision ARYNTH would take as a result requires approval under §3.4;
6. hand progression back to 0002, which reassesses remaining work and reopens confirmed work only under 0002 §2.8.

[0001 §1.6.1, §1.8, §1.10.4; 0002 §2.8.2, §2.10.1, §2.10.2; 0003-C]

**3.12.4 Scope of a change.** 0001 §1.6 remains the only V1 scope classification. ARYNTH must not silently adopt a change, or any part of one, that falls outside V1.

An out-of-scope part of what a change asks for is handled under 0001 §1.7, as applied during progression by 0002 §2.10.6–§2.10.8. Those rules govern:

- setting aside an incidental part, including the approval required where setting it aside would override a prior user-approved decision;
- the user approval or user redefinition required before a materially narrowed basis is pursued, and the pending item that arises until then;
- the case where no valid in-scope path remains.

ARYNTH must not substitute a different change on its own initiative (0001 §1.7.2; 0002 §2.10.8). A change that asks for more than one final video deliverable is handled under 0001 §1.8.5. A change that asks for a separate non-video companion deliverable is handled under 0001 §1.7.8. [0001 §1.6.1, §1.7, §1.7.8, §1.8.5; 0002 §2.10.5–§2.10.8]

**3.12.5 Consequences for prior user-approved decisions.** A user change authorizes changes to prior user-approved decisions only as far as necessary to carry the change out consistently, and only for consequences attributable to that change under §3.12.8:

1. prior user-approved decisions that remain compatible with the change must be preserved;
2. where ARYNTH can carry out the change while preserving a prior user-approved decision, it must preserve it;
3. a prior user-approved decision that the change makes necessarily obsolete or inconsistent may be changed without separate approval, solely to the extent necessary to carry out the change;
4. what replaces obsolete work is an ARYNTH decision. The replacement requires approval under §3.4 only where it:
   - materially changes the goal beyond the user's own change;
   - overrides another prior user-approved decision that the change did not require changing;
   - is a covered decision of an active user-requested approval point; or
   - requires approval under another Global Spec authority, including GS 1.8 through 0007;
5. the resulting consequential changes must be understandable to the user through 0004.

[0003-C; GS 1.5, GS 1.6, GS 1.8]

**3.12.6 Earlier goal content.** Where a user change is inconsistent with earlier goal content, the change governs to the extent of the inconsistency. Earlier goal content that remains compatible with the change continues to be honored under §3.5.4. [0003-A, 0003-C; Derived: GS 1.5 ¶4]

**3.12.7 No mechanical re-approval.** ARYNTH must not require the user to approve the necessary consequences of the user's own change, whether one by one or together. §3.12.5 items 1, 2 and 4 govern the protection of compatible prior user-approved decisions and the approval required for a replacement. [0003-C; GS 1.5]

**3.12.8 Attributing consequences to approvals and user changes.** §3.12.5 applies only to changes the user makes. It does not apply to:

- the consequences of an ARYNTH proposal that the user has approved, which are governed by §3.6;
- decisions ARYNTH takes for its own workflow reasons, which are governed by §3.5.9.

A single response may both accept all or part of ARYNTH's presented proposal and add a precise user-specified modification. An example is "Approved, but use 'Discover more' instead. Everything else stays." This rule is the single authority for the consequences of such a mixed response:

1. **Accepted portion.** Any portion of the proposal that the user accepts is approved under §3.6: as presented, together with the consequences identified in the approval request. A consequence of that portion that was not identified, and that independently requires approval, requires its own approval (§3.6.5). It does not become authorized because the same response also contains a user modification.
2. **User modification.** The user's exact modification is the user's own change. Only the consequences necessary to carry out that modification consistently receive authority under §3.12.5. The modification does not authorize consequences that the accepted portion would have had without it.
3. **Attribution.** For each consequential change, ARYNTH determines which part of the response makes it necessary:
   - if it would still be necessary with the user's modification removed and the accepted portion unchanged, it belongs to the accepted portion, and item 1 applies;
   - if it becomes necessary specifically because of the user's modification, §3.12.5 may apply to it;
   - if it is attributable to neither, the approval authorities in §3.4 apply to it as they would to any other decision;
   - if its attribution cannot be clearly determined, the broader authority is not inferred. The narrower existing authority applies, together with any independently required approval. A consequence that was not identified in the approval request and that independently requires approval therefore requires its own approval.

   ARYNTH makes this determination itself from the known decision and consequences. The difficulty of attribution is not a reason to involve the user (§3.4.3).
4. **No re-approval.** Where the response fully settles the decision presented, it remains a complete user decision under §3.9.5 item 1 and is not presented again for approval. This rule governs only the authority for its consequences.
5. **Independent authorities.** A mixed response does not waive any of the following:
   - any other prior user-approved decision;
   - any other active user-requested approval point;
   - the scope rules of 0001;
   - spending authorization under GS 1.8 and 0007;
   - any other Global Spec approval authority.

[0003-B, 0003-C; GS 1.5, GS 1.8; 0001 §1.6]

**3.12.9 Resolution of the 0002 dependency.** For 0002 §2.8.5 and §2.10.2: a goal change resolved through this document authorizes reopening, changing or discarding work that embodies a prior user-approved decision, whether confirmed or not, to the extent §3.12.5 permits. To that extent, no further approval is required. Beyond that extent, approval under GS 1.5 is required, and the matter is a pending item under 0002 §2.8.4. [0003-C; 0002 §2.8.4, §2.8.5, §2.15.2]

**3.12.10 Revision requests.** A revision request that 0008 admits is a user change for the purposes of §3.12.5, in respect of what it asks to change. 0008 determines what a revision may ask for and the boundaries of revision. [GS 1.9; 0003-C; 0000 §0.2]

**3.12.11 Confirmation and reopening not defined here.** This document determines only whether changing work that embodies a prior user-approved decision requires approval, or is authorized by a user change. Whether work is or remains confirmed is owned by 0005. Reopening, dropping, discarding and reassessment are owned by 0002. [0000 §0.2; 0002 §2.8, §2.9]

**3.12.12 Continuation with a change.** Where a request to continue a stopped workflow also changes its goal, 0006 handles continuation first, and the change is then resolved under this section. [0001 §1.10.7; GS 1.7 ¶5]

## 3.13 Delegation

**3.13.1 Delegation during a workflow.** The user may explicitly delegate identified decisions to ARYNTH, at entry or through intervention. An explicitly delegated decision is an ARYNTH decision. [0001 §1.4.4; GS 1.5 ¶1]

**3.13.2 Delegation must be explicit.** Delegation is never inferred from any of the following:

- silence or omission;
- the absence of a response to an approval request;
- the user's general satisfaction with the workflow.

[0001 §1.2; GS 1.5]

**3.13.3 Effect on approval points.** Delegating a covered decision removes or narrows the user-requested approval point to the extent of the delegation (§3.7.8). [0003-D; GS 1.5 ¶3]

**3.13.4 Bounded relaxation of user direction.** A bounded instruction such as "you may drop X if necessary" is not a general approval waiver. Where the user may validly give it, it is a bounded user change that relaxes the relevant goal content or prior user-approved decision within its stated terms:

- given at entry, it forms part of the goal content as defined;
- given through intervention, it is a user change under §3.10.9 and §3.12.

Within those terms, ARYNTH may then take the identified decision without further approval, because the direction the decision would otherwise depart from no longer requires what the relaxation releases.

A bounded relaxation does not:

- pre-approve any other decision;
- authorize an override of a prior user-approved decision that it does not name;
- waive approval of unidentified future material changes;
- waive GS 1.5 or GS 1.8 (§3.13.5).

Where it is unclear whether such an instruction extends to a decision that would otherwise require approval under GS 1.5, it does not extend to that decision. [GS 1.5; 0003-B, 0003-C; Derived: 0001 §1.4.4]

**3.13.5 No waiver of GS 1.5.** Delegation does not waive the approval requirements of GS 1.5 for unidentified future material changes or overrides. A general statement such as "never ask me anything" or "decide everything yourself" is interpreted only as:

1. delegation of the choices the user may validly delegate;
2. removal of the user's own requested approval points, where applicable.

Such a statement does not waive:

- approval of material changes or overrides under GS 1.5;
- spending approval under GS 1.8;
- the need for necessary information that ARYNTH cannot determine.

A full waiver of GS 1.5 would require a change to the Global Spec and is outside this document. [GS 1.5 ¶2, GS 1.6 ¶3, GS 1.8; 0001 §1.4.4]

**3.13.6 Delegated choices remain ARYNTH's.** A choice ARYNTH makes under delegation is not a prior user-approved decision. ARYNTH may later change it as a workflow decision, subject to §3.4. [0003-A; GS 1.5 ¶1]

**3.13.7 Changing a delegation.** The user may narrow or withdraw a delegation through intervention. Withdrawing a delegation does not by itself create an approval point. Where the user withdraws a delegation in order to make the choice personally, that is goal content or a user-requested approval point, according to how the user expresses it. [GS 1.5 ¶3, ¶4; 0003-A, 0003-D]

**3.13.8 No solicitation of delegation.** ARYNTH does not need delegation for decisions it already owns, and it must not ask the user to delegate them. [GS 1.5 ¶1; 0002 §2.14.5]

## 3.14 Cross-Area Approval Interaction

**3.14.1 Confirmation.** Approval is not a routine step of confirmation. Only §3.4 determines whether a result requires approval, and 0005 owns confirmation. The protection of a prior user-approved decision does not depend on whether work that embodies it is confirmed. [GS 1.1 ¶3, GS 1.5; 0002 §2.5.4, §2.8.10]

**3.14.2 Reopening.** Whether reopening confirmed work requires approval is determined by §3.4, §3.5.9 and §3.12.9. How reopening is carried out is owned by 0002 §2.8. [0002 §2.8.4, §2.8.5]

**3.14.3 Decisions needing both GS 1.5 and GS 1.8 authority.** Where a decision requires both approval under GS 1.5 and spending approval under GS 1.8:

1. both authorities must be satisfied before ARYNTH acts on the decision;
2. spending approval authorizes spending only, and does not authorize a material change, an override or a covered decision;
3. approval under GS 1.5 does not authorize spending that is not already authorized;
4. where both approvals are sought together, the request must make it determinable that approval is sought under each authority (§3.8.2);
5. where either approval is not given, the decision is not carried out.

Spending authorization, cost information and cost uncertainty are owned by 0007. [GS 1.5, GS 1.8; 0002 §2.6.7]

**3.14.4 Revision.** 0008 owns revision intake, revision scope and boundaries, the preservation and replacement of the current production-ready outcome, review and export. Once revision work is underway:

1. interventions during it follow this document;
2. active user-requested approval points continue to apply to covered decisions made or remade in revision work, unless the user scoped them otherwise (§3.7.4);
3. prior user-approved decisions remain protected, subject to §3.12.10;
4. no approval or intervention alters the current production-ready outcome, which remains current until it is replaced under 0008 (0002 §2.11.4).

[GS 1.9; 0003-D; 0002 §2.11]

**3.14.5 Stop and continuation.** A stop is not a response to an approval request: it neither approves nor declines a pending request. A stop does not remove user-requested approval points, explicit delegations or prior user-approved decisions. How pending requests are treated while a workflow is stopped is owned by 0006. On continuation, any request or approval that ARYNTH has not yet acted on is subject to §3.9.7–§3.9.10, applied to the workflow as continued. [GS 1.7 ¶5; 0003-D, 0003-E]

**3.14.6 Waiting and inability to continue.** 0006 and 0004 own the waiting for an approval or clarification, any reminders, attention, and any consequence of a prolonged wait. Inability to continue after a decline, or after a required narrowing is not approved, is owned by 0006. [GS 1.7 ¶3, ¶4]

**3.14.7 Necessary information.** A request for necessary information is not an approval request, and an approval request is not a request for information. Each must rest on its own authority (§3.3.3). [GS 1.5, GS 1.6 ¶3; 0002 §2.13.2]

**3.14.8 Determinable decision facts.** Where applicable, the following must be determinable at any time, so that 0004 can make them understandable under GS 1.6:

1. each pending approval request, its authority, its proposal and any alternatives;
2. the prior user-approved decision that any request would affect, and the request's known consequential changes;
3. the outcome of each request, including withdrawal and supersession, and any lapsed approval;
4. unresolved interventions, and any pending clarification of intent;
5. active user-requested approval points, and any that have stopped applying under §3.7.6;
6. explicit delegations in effect;
7. incidental departures from goal content;
8. consequential changes made under §3.12.5.

This rule requires the facts to be determinable. What is presented, and how, is owned by 0004. [GS 1.6; 0003-A, 0003-C, 0003-D, 0003-E, 0003-F]

## 3.15 Manual-Coordination & Approval-Fatigue Guard

**3.15.1 Principle.** The objective is maximum autonomous workflow ownership by ARYNTH inside explicit user-control boundaries, not maximum autonomy. The user controls the boundaries that GS 1.5 reserves to the user without becoming the manual workflow manager. [GS 1.1 ¶6, GS 1.3, GS 1.5]

**3.15.2 No approval creep.** None of the following becomes an approval point or a user decision merely because it is difficult or uncertain:

- the normal next step;
- tools or models;
- whether to retry, redo or rewrite;
- corrective paths;
- ordinary creative alternatives;
- sequencing;
- execution strategy;
- internal reassessment.

This list applies §3.4.3 and 0002 §2.14.3 and does not narrow them. Where the list and those rules differ, the broader protection applies. [GS 1.5 ¶1, ¶3; 0002 §2.14.3, §2.14.4]

**3.15.3 Invalid questions.** The following are not valid user questions unless an authority under §3.3.3 genuinely requires user involvement:

- "Would you like me to review this with you first?"
- "Should I retry?"
- "Which approach should I use?"
- "Should I continue?"

[GS 1.5 ¶3; 0002 §2.14.4]

**3.15.4 Friendliness is not authority.** Courtesy, check-ins, offers to review work with the user and confirmations of understanding are not approval requests, and they must not hold work. Informing the user is owned by 0004. It must not be framed as a user decision, and it must not wait for one. [GS 1.5 ¶3, GS 1.6; 0002 §2.14.5]

**3.15.5 No self-initiated user checkpoints.** ARYNTH must not propose, offer or create, on its own initiative, a point at which the user is asked to approve or review work before ARYNTH proceeds (§3.7.2).

This prohibition does not concern points that do not ask the user to approve or review. These include:

- internal checks;
- the required checks and confirmation owned by 0005;
- confirmed progress;
- other workflow points owned elsewhere.

It also does not limit the user's ability to request approval points or to intervene, or the visibility owned by 0004. [GS 1.5 ¶3, ¶4; 0003-D; 0002 §2.14.7]

**3.15.6 Known fatigue risks.** This document closes the following risks.

| Risk | Closed by |
|---|---|
| Treating every user statement as a prior user-approved decision | §3.5.3, §3.5.6 |
| Turning advisory process preferences into binding workflow locks | §3.5.4, §3.5.6 |
| Asking the user to re-approve a complete user decision | §3.9.5, §3.10.9 |
| Requiring re-approval of every consequence of a user change | §3.12.5, §3.12.7 |
| Keeping obsolete requests or approvals binding | §3.9.7–§3.9.10 |
| Freezing every detail of an approved plan | §3.6.4 |
| ARYNTH offering user approval or review checkpoints on its own initiative | §3.7.2, §3.15.5 |
| Using a user-requested approval point to present several working candidates | §3.7.11, §3.8.5 |
| Asking again about a declined proposal | §3.9.4 |
| Manufacturing alternatives or trivial variants | §3.8.5 |
| Using clarification to hand decisions back to the user | §3.10.8 |

[0003-A, 0003-B, 0003-C, 0003-D, 0003-E, 0003-F]

**3.15.7 Audit rule for later layers.** Every approval rule, at this or any later specification layer, must be tested against one question: could it produce repeated user confirmation where ARYNTH could validly decide itself? A rule that could must be rejected or narrowed. A later rule that would route a decision to the user must identify its authority under §3.3.3, or it does not apply. [GS 1.5 ¶3; 0002 §2.14.8]

**3.15.8 User control unaffected.** This guard does not limit any of the following:

- approvals that §3.4 requires;
- user-requested approval points;
- the user's ability to intervene;
- the visibility owned by 0004.

[GS 1.5 ¶2, ¶3, ¶4, GS 1.6]

## 3.16 Ownership Boundaries & Open Dependencies

**3.16.1 Ownership.** This document does not define the detailed behavior of other areas. Where their rules concern autonomy, approval or intervention, they apply this document rather than restating it.

| Area | Owns | Relationship to 0003 |
|---|---|---|
| 0001 — Workflow Entry & Scope | Entry, goal sufficiency, V1 scope classification and enforcement, the one-target-outcome rule, the multiple-workflow policy and routing | Identifies the following, which 0003 defines how to handle: approvals at entry (0001 §1.7.3); requested approval points and spending instructions carried forward (0001 §1.3.4); user-requested choice among options (0001 §1.8.3); goal changes (0001 §1.10.4). See §3.7, §3.9.12 and §3.12. 0003 applies 0001 §1.6–§1.8 to changes without restating them (§3.12.4). |
| 0002 — Workflow Orchestration & Progress | Orchestration, dependency-scoped holding, sequencing, reassessment, reopening mechanics and corrective work | Holds work that depends on pending approvals (§3.4.5), holds work affected by unresolved interventions (§3.11.2), and re-engages when an intervention is resolved (§3.11.8). 0003 resolves the open dependency in 0002 §2.15.2 (§3.12.9). |
| 0004 — Workflow Visibility & Attention | Visibility, wording, attention and presentation | Presents approval requests and the decision facts in §3.8.2 and §3.14.8. Answers explanation requests. Makes incidental departures and consequential changes understandable. |
| 0005 — Quality, Confirmation & Completion | Checks, confirmation, quality and production-ready completion | Owns the confirmation status of work affected by approvals or user changes (§3.12.11, §3.14.1). Makes the production-ready determination, which must not rest on work that an unresolved intervention could change or invalidate (§3.11.11). |
| 0006 — Continuity, Failure, Stop & Resume | Waiting, interruption, inability to continue, stop and continuation | Owns waiting on approvals and clarifications, the consequences of no response, inability to continue after a decline, and stop and continuation (§3.9.6, §3.14.5, §3.14.6). |
| 0007 — Cost & Spending Control | Cost authorization, spending approval, cost uncertainty and cost information | Receives spending instructions (§3.7.13, §3.10.4). Supplies cost information for approval requests (§3.8.2). Governs spending approval where a decision needs both authorities (§3.14.3). |
| 0008 — Review, Revision & Export | Review, revision intake and scope, outcome replacement and export | Admits revision requests, to which §3.12.10 applies. Revision work is subject to this document (§3.14.4). |

**3.16.2 Dependency resolved.** 0002 §2.15.2 left one question to 0003: whether a goal change resolved through 0003 itself authorizes the resulting rework involving prior user-approved decisions. §3.12.5 and §3.12.9 answer it.

**3.16.3 Open dependencies.** This document depends on the following rules. They must be defined by their owning areas and are not defined here.

| Dependency | Owner | Relied on in |
|---|---|---|
| Presentation of approval requests, decision facts, incidental departures and consequential changes, and whether departures from advisory process preferences are made understandable | 0004 | §3.5.5, §3.5.6, §3.8.8, §3.12.5, §3.14.8 |
| Waiting while an approval or clarification is awaited, and any consequence of a prolonged absence of response | 0006 | §3.9.6, §3.14.6 |
| Treatment of pending requests while a workflow is stopped | 0006 | §3.14.5 |
| Cost information required in approval requests, and the scope and effect of spending approvals and spending instructions | 0007 | §3.5.10, §3.7.13, §3.8.2, §3.14.3 |
| What a revision request may ask for, and its admission | 0008 | §3.12.10, §3.14.4 |
| Whether work affected by an approval or a user change is or remains confirmed | 0005 | §3.12.11, §3.14.1 |

## 3.17 Deferred to Later Layers

The following are deferred to later specification layers and must not be inferred from this document:

- criteria for judging whether a decision is a material change, whether a part of goal content is material or incidental, and how doubt about materiality is resolved (0001 §1.14);
- criteria for judging when alternatives are materially distinct (§3.8.5) and when circumstances have materially changed after a decline (§3.9.4);
- UI design, dialogs, buttons, forms, approval cards and interaction design;
- presentation, wording, notifications and reminder timing (0004);
- timers or deadlines for responses (0006);
- approval records, storage, audit logs and history;
- API design and event types;
- authentication, approver identity and permission roles;
- technical cancellation, rollback and concurrency mechanisms;
- workflow-engine and orchestration implementation;
- cost information content and billing implementation (0007);
- revision controls, revision limits and version history (0008).
