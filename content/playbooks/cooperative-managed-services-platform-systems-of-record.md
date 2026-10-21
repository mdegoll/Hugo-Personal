---
title: "Keep it working after release, with humans and agents"
description: "Turn operator feedback into scoped work, verified changes, and better instructions for the next request."
summary: "Carry an operator report through diagnosis, assignment, review, release, and verification. Includes a work-order template and guidance for recovering stalled work and learning from corrections."
weight: 3
date: 2026-05-19
lastmod: 2026-09-11
draft: false
layout: playbook
stage: "Support it after release"
ShowToc: true
TocOpen: true
playbookMeta:
  - "Managed services, for delivery leads and platform builders"
tags:
  - Cooperative Systems
  - Managed Services
  - Systems of Record
  - Support Automation
  - OpenAI
  - Agents
  - Internal Tools
---

## Follow a request until the user can finish

An operator reports that a shipment can't be completed. The problem might be missing information, an uncleared balance, a failed provider call, or a defect. Someone has to establish which one it's before changing the screen or retrying the action.

That's the work I want a managed-services system to support. It should carry the request from the user's observation through diagnosis, implementation, and verification, with enough context that each person or agent can take the next step.

My recent work on order-management workflows, Salesforce migration, and remote agent delivery has pushed this design toward the handoffs. Building a component is only part of the job. The next role must be able to use it, the running environment must contain it, and the team needs a way to recover when an effect is uncertain.

This playbook describes the way of working I'm aiming for, drawing on those projects and the managed-services direction in Kicksights. The sections below are design guidance; each capability needs verification against its implementation and deployment.

## Capture the request where the work happens

Start with the intake source the team already uses. A ticket, an in-app report, or an approved walkthrough can all supply useful evidence. The first improvement is giving that evidence a durable home and an owner.

For an in-app report, capture the intended action, the observed result, the route, and the application release. Resolve the reporter's role and organization through the authenticated server context. Collect only the additional information needed to investigate; screenshots and logs can contain customer data and credentials.

Let the operator describe the interruption in their own words. They shouldn't need to know the component name or guess the cause. The system can attach permitted technical context and ask for missing details later.

An intake agent can group duplicates, locate related incidents, and draft the next question. It should preserve the original report and its source. Instructions inside an attachment or ticket don't authorize the agent to change scope, reveal information, or contact anyone.

## Turn the report into a work order

The request becomes actionable when it has a reproducible problem or a clearly defined discovery step. Attach the relevant system baseline, inspect the current implementation, and identify any unresolved business rule. The [discovery playbook](/playbooks/claude-org-scan-and-migration-readiness-playbook/) describes that inspection.

Keep the work order short enough that a reviewer can understand the change without reading the entire conversation:

```text
Outcome: the shipping operator can resume an interrupted package.
Evidence: report reference, affected release, and reproduced behavior.
Scope: package persistence and the existing shipping workspace.
Preserve: allocation, clearance, permissions, and audit history.
Acceptance: save, reload, resume, and verify the next role's view.
Owner: assigned builder; named reviewer and workflow owner.
Authority: allowed actions and any approval still required.
Recovery: how to stop, reconcile, or reverse the change.
```

The request ID should lead to the source baseline, work order, change, checks, and release result. These can remain in existing systems. A GitHub diff belongs in GitHub; the request needs its reference and status, not a second copy of the code review.

That separation also keeps authority clear. The work queue records the assignment. The source repository establishes the implementation. The deployed application and its domain records establish what actually ran and changed.

## Make the next action easy to find

A status is useful when it explains who can move the work forward. “Blocked” needs a reason, an owner, and the next action that could resolve it. “Ready” needs to say ready for review, deployment, or operator verification.

I'd start with a small lifecycle and keep the details on the request:

| State | What happens next |
| --- | --- |
| Needs evidence | The assigned investigator collects a specific missing observation or decision. |
| Ready to build | Scope, ownership, dependencies, and acceptance are established. |
| In progress | One owner is responsible for the current attempt. |
| In review | The reviewer checks the candidate revision and its evidence. |
| Ready to release | Required checks and approvals cover the candidate and target environment. |
| Verifying | The release is being checked against the requested outcome. |
| Done | The agreed outcome is verified and the result is attached. |

Blocked and canceled work retain their reason and history. Reopening a request should preserve the previous attempt so the team can tell a failed repair from a new problem.

Give agents compact answers to practical questions: what is assigned, which source is current, what action is permitted, and what proves completion? Link to deeper context on demand. A generated inventory of commands or dependencies is easier to keep current than a second manually maintained map.

## Coordinate workers through durable state

With a usable request and lifecycle, agent workers have something specific to do. Start with bounded jobs such as reproducing an issue, comparing metadata, preparing a change, or checking a release. Add specialists when the work can be divided without competing ownership.

The delivery work on a shared VPS has made one requirement clear: a running process is weak evidence of progress. A worker can be active while its claim is stale, its dependency is unresolved, or its output has no path to review.

Track claims, attempt IDs, dependencies, and review state in the coordination system. Use leases or the project's equivalent to recover abandoned work, and recheck the current attempt before accepting a result. An old worker must not be able to finalize a task that has been reassigned.

Keep monitors quiet while the state is unchanged. Notify the responsible person when work completes, fails, loses its owner, or needs a decision. If the coordinator is unhealthy, restore a trustworthy queue before increasing the workload.

## Keep business operations in the application

The queue can coordinate a repair, but business state still belongs to the system of record. A shipment, payment, allocation, or approval should change through its owning service. Screens and agent tools should share that operation's authorization, validation, concurrency, and audit rules.

Authorize each action against the authenticated actor and organization on the server. Bind approvals to the actual scope, candidate, and environment; a materially changed action needs a new decision. Once an action is covered, carry that authorization forward rather than asking the same question at every step.

External effects need their own status. A database commit can succeed while a notification or provider request remains pending. Record the operation and its pending effect together where the architecture supports it, then track delivery and reconciliation. If the caller loses the response, look up the existing attempt before retrying.

This is especially relevant to migration and fulfillment. A source read doesn't authorize a source write. A carrier label doesn't establish physical dispatch. A preview doesn't reserve inventory or guarantee a price. The system should return enough evidence for the next actor to tell which state has actually been reached.

## Close the request against the deployed workflow

Review and CI establish that a candidate is ready to move through the release process. Completion depends on the outcome promised in the work order. For a deployed workflow change, record the running revision and test with the appropriate authenticated role.

Follow the handoff far enough to catch the original interruption: save the work, reload it, resume as the next operator, and inspect the persisted result. Include relevant refusal and recovery cases. When a provider effect is in scope, reconcile its result too.

Record partial success precisely. “Code merged; deployment pending” tells the release owner what remains. “Shipping save verified; finance handoff untested” tells the workflow owner where to continue. Neither should silently become “done.”

The [implementation playbook](/playbooks/codex-openai-implementation-playbook-business-tools/) covers the checks and publication sequence. The managed-services system's job is to keep that evidence attached to the request and route any unfinished step to its owner.

## Use corrections to improve the next attempt

When a reviewer rejects an answer or an operator reopens a request, capture the reason. Stale source context, a missing tool, an incorrect business rule, and a failed external effect call for different repairs.

Put the lesson in its existing home. A reproducible defect becomes a regression test. An ambiguous rule becomes a clarified contract. A repeated investigation becomes a short runbook or a bounded tool. Generate facts that can be derived from source, and refresh live state when a decision depends on it.

Keep attempt history for audit and investigation, while editing current guidance in place. An agent starting tomorrow should be able to find the corrected instruction without reading months of contradictory summaries. Durable policy changes still need their owner's review; one successful workaround doesn't make a rule.

## Pilot one queue before expanding

For a managed-services pilot, I'd choose one customer workflow with recurring requests and a reviewer who knows it well. Begin with diagnosis and work-order preparation, then add implementation and release steps as the checks become reliable. Kicksights is one place I'm exploring this pattern for Salesforce work; Rebase infrastructure offers another starting point through failed-build investigation and environment setup.

Use completed historical cases to test the first version. Include missing evidence, a denied action, an uncertain write result, and a request that should be escalated. Measure whether the next person can act on the output and how much correction it requires.

Once the pilot is running, review time from report to verified outcome, time waiting for review, reopened requests, and cost per accepted result. Read a few failed attempts alongside the numbers. That shows whether the next improvement belongs in the agent, its tools, the documentation, or the team's handoff process.

Expand when the first workflow can be repeated and recovered by someone other than its original builder. The next queue should inherit the contracts and tests that worked and a clearer way to run things.
