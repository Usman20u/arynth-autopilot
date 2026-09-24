# ARYNTH Autopilot V1 — Product Definition

Status: Final  
Specification Layer: Global Spec  
Current Stage: Stage 2  
Last Confirmed Section: 1.9

## 1.1 What ARYNTH Autopilot V1 Does

ARYNTH Autopilot V1 is an AI work operator for short-form content production.

The user defines a content production goal. ARYNTH coordinates the workflow, preserves its state, uses approved AI tools and models, checks important intermediate results, and continues from the latest confirmed state until a production-ready outcome is reached.

A confirmed state is a saved point in the workflow where completed work has passed ARYNTH's required checks and, where required, user approval.

A production-ready outcome is a completed short-form video that has passed ARYNTH's required final quality checks and is ready for user review and export. Publishing or distributing the completed video to external platforms is outside the scope of V1.

The purpose of V1 is not to become a universal AI assistant or a complete personal operating system.

V1 exists to prove that ARYNTH can reliably carry one content production goal from intent to a production-ready outcome without requiring the user to manually coordinate every step of the workflow.

## 1.2 Primary User

ARYNTH Autopilot V1 is built first for solo creators and creator-operators who regularly produce short-form content.

The primary user typically:

- regularly produces Shorts, TikTok videos, Reels, or similar short-form content;
- already uses, or is willing to use, AI tools as part of the production process;
- currently has to coordinate multiple tools, files, revisions, and production steps manually;
- loses time and context when moving between research, scripting, generation, editing preparation, files, and revisions;
- wants to define the desired outcome without manually managing every intermediate step;
- needs visibility and control over important decisions.

The V1 primary user is intentionally NOT defined as:

- an enterprise organization;
- a large production team;
- a marketing agency with complex team permissions;
- a general-purpose AI user;
- every possible type of creator.

These may become future markets, but they must not expand the scope of V1.

## 1.3 The One Real Problem

Solo creators and creator-operators can already use AI tools for individual content production tasks, but they still have to manually coordinate the workflow required to carry a content production goal from intent to a production-ready outcome.

They remain responsible for keeping track of what has been completed, what needs review, what has changed, and what must happen next.

This manual coordination creates unnecessary tool switching, increases the risk of losing workflow context, and makes reliable progress harder to maintain.

The core problem ARYNTH Autopilot V1 addresses is that they still have to act as the manual workflow manager for short-form content production.

## 1.4 V1 Content Scope

ARYNTH Autopilot V1 begins with a content production goal.

The user may also provide optional supporting materials, such as text, images, short video clips, or reference materials that fall within V1's supported input types. An existing source video or pre-assembled edit is not required.

Each V1 workflow produces one production-ready outcome from the defined goal and any supported optional materials.

Long-form source videos and bulk raw footage are outside the supported content input scope of V1.

V1 does not provide a general-purpose video editing environment.

These excluded capabilities may be considered in future versions, but they must not expand the scope of V1.

## 1.5 User Control & Autonomy Boundary

ARYNTH Autopilot V1 proceeds autonomously with workflow decisions by default.

User approval is required before ARYNTH makes a decision that would materially change the user's defined content production goal or override a prior user-approved decision.

Outside these cases, additional approval points may exist only when explicitly requested by the user or explicitly required by another section of this Global Spec. Later specification layers must not introduce any other approval requirement.

The user must be able to intervene while the workflow is in progress.

## 1.6 Workflow Visibility Boundary

ARYNTH Autopilot V1 must make meaningful workflow state understandable to the user without requiring the user to manually manage the workflow.

For an active or completed workflow, the user must be able to understand:

- what meaningful work is currently in progress;
- what meaningful work has been completed;
- what meaningful changes have been made to completed work since it was last confirmed;
- whether user approval is required;
- whether the workflow is blocked or has encountered a problem that requires the user's attention;
- whether the production-ready outcome has been reached.

If the workflow cannot continue without user approval, or because information necessary to execute the user's existing content production goal is missing, ARYNTH must clearly indicate that the user's attention is required. When missing information is the cause, ARYNTH may request that information, but such a request must not be used to shift a workflow decision to the user when section 1.5 assigns that decision to ARYNTH.

Workflow visibility does not require ARYNTH to expose every internal model call, technical event, internal reasoning step, or other low-level execution detail.

## 1.7 Workflow Continuity & Failure Boundary

ARYNTH Autopilot V1 must preserve confirmed progress through temporary interruptions and recoverable problems so that the user does not have to restart work that has already reached a confirmed state.

When a recoverable problem no longer prevents continuation, ARYNTH must continue autonomously from the latest confirmed state unless continuation requires user approval or necessary information under the established V1 boundaries.

If the workflow cannot continue without required user approval or necessary information, further progress must wait until that requirement is resolved, and the need for user attention must remain visible.

If ARYNTH cannot continue the workflow to a production-ready outcome, it must not report the workflow as successfully completed. The user must be able to understand that the outcome has not been reached and why the workflow cannot currently continue.

If the user stops the workflow, ARYNTH must stop further execution and preserve any confirmed progress that exists. A user-stopped workflow must not resume automatically. If the user later chooses to continue it, ARYNTH must continue from the latest confirmed state.

## 1.8 Cost Transparency & Budget Boundary

ARYNTH Autopilot V1 may use AI tools and paid resources autonomously when their use remains within the user's approved budget, included usage, or approved paid-resource allowance.

For this section, a paid charge is already authorized when it remains within the user's approved budget or approved paid-resource allowance. Such a charge does not require separate approval merely because it is newly incurred.

Before an action would create a paid charge that is not already authorized under this section, exceed the remaining approved budget, or consume usage beyond an approved paid-resource allowance, ARYNTH must clearly explain the expected cost impact and obtain user approval.

An approved budget or approved paid-resource allowance is a hard spending authorization boundary. Based on the cost information available before execution, ARYNTH must not initiate or authorize an action that would exceed that boundary without additional user approval.

When the exact cost of an action cannot be known before execution, ARYNTH must obtain user approval if the available cost information indicates that the action could reasonably create a paid charge that is not already authorized under this section, exceed the remaining approved budget, or consume usage beyond an approved paid-resource allowance. ARYNTH must explain the relevant cost uncertainty and must not present an estimate as a guaranteed final charge.

The user must be able to understand current spending or consumption against any approved budget, included usage, or approved paid-resource allowance in terms that are meaningful to them. The user must not be required to understand model tokens, provider billing units, or other internal AI cost mechanics in order to control spending.

ARYNTH must not intentionally create or authorize an unexpected paid charge.

Exact prices, subscription limits, usage allowances, metering rules, model-selection economics, and billing implementation are intentionally deferred to later specification work.

## 1.9 Post-Outcome Review & Revision Boundary

Reaching a production-ready outcome does not require separate user acceptance. Once ARYNTH's required final quality checks have passed, the outcome satisfies V1's production-ready completion condition and is available for user review and export.

After review, the user may request revisions to that outcome within the same workflow. A revision request does not create a new V1 workflow or a second target outcome.

When revisions are requested, ARYNTH must continue the existing workflow using its preserved confirmed progress, subject to the existing autonomy, approval, visibility, continuity, and cost rules.

While revisions are in progress, the most recent production-ready outcome remains the workflow's current production-ready outcome and remains available for user review and export.

A revised result must pass ARYNTH's required final quality checks before it can replace the previous production-ready outcome and be treated as the current production-ready outcome for that workflow.

Exact revision controls, revision limits, version history, and interaction design are intentionally deferred to later specification work.
