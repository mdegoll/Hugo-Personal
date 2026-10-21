---
title: "Change one workflow and prove it works where it runs"
description: "Take a workflow from source inspection through a scoped change, review, and verification on the release that matters. Codex does the implementation; the checks are yours."
summary: "Define a checkable outcome, implement the full workflow, and verify it on the intended release. Covers task scope, shared ownership, recovery, and when to add a runtime agent."
weight: 2
date: 2026-05-18
lastmod: 2026-09-11
draft: false
layout: playbook
stage: "Change it"
ShowToc: true
TocOpen: true
playbookMeta:
  - "Business tools, with Codex as the builder"
tags:
  - Codex
  - OpenAI
  - Business Tools
  - Agents
  - Salesforce
  - Data Migration
---

## Begin with the outcome you can check

A build can pass while an operator still can't finish the job. A provider adapter can exist while its connection is disabled. A migration can be committed while the target database has never applied it.

Those gaps have shaped how I use Codex. Recent work has included Salesforce migration tooling, order-management workflows, infrastructure setup, and repairs that had to survive a real deployment. Each needed a different kind of verification. “The tests pass” was useful evidence, but it didn't answer every question.

I start by defining the result and where it must work. For an org scan, that might be four reports traceable to approved metadata. For a business tool, it might be a shipping operator resuming a saved transaction and completing the next permitted step. That outcome determines the implementation scope and the checks.

## Establish the starting point

Before editing, find the repository instructions, current branch, working changes, and checkout that owns delivery. In a shared project, the local machine may be useful for inspection while a remote checkout owns commits and releases. Read that arrangement before assuming where work belongs.

These commands give an initial Git picture:

```bash
git status --short --branch
git log -5 --oneline
git worktree list
```

Then locate the requested workflow's screen, service, data owner, and tests. Read the relevant architecture decision and deployment configuration. Refresh remote state when publication depends on it. A broad scan of every document usually costs more than following the references from a maintained project entry point.

Keep `AGENTS.md` useful for that navigation. It should name real commands, ownership rules, access limits, and completion criteria. Link to detailed runbooks instead of copying them. Check that the commands work before asking an agent to rely on them.

With the baseline established, write a task the agent can finish:

```text
Outcome: the shipping operator can resume a saved package after reload.
Starting point: identify the current source revision and reproduce the loss.
Scope: package persistence, its API path, and the existing workspace.
Preserve: permissions, allocation rules, and financial release checks.
Verify: save, reload, resume, and attempt an unauthorized update.
Delivery: implement and run local checks; report deployment status separately.
```

If deployment is part of the assignment, include it and its acceptance check. Carry existing authorization through the work; ask again only when the action exceeds that scope or needs a decision the user hasn't made.

## Build a complete, narrow workflow

A useful slice follows one action through the system. For package persistence, that means the screen sends the right input, the service validates it, the data survives reload, and the next operator sees the correct state. A UI-only fix would leave the original problem unresolved.

Use the existing domain operation where possible. A screen, CLI, and agent tool should reach the same service rules. A second implementation for agents creates another place for permissions, eligibility, and business logic to drift.

The operation should make its preconditions and result clear: who may act, which record version is expected, what changes, and how the caller can look up the outcome. If it triggers an external effect, distinguish the committed state from the pending delivery of that effect.

This matters during recovery. A timeout leaves the outcome uncertain. Before retrying a write, look up its durable result or reconcile it with the provider. Use the operation's idempotency contract rather than creating a new request that might repeat a successful effect.

## Add parallel work only when ownership is clear

Some tasks split naturally. One agent can trace a service while another reviews an independent API contract. Implementation can run in parallel when the files and interfaces have clear owners. Work that depends on the same changing contract is often faster in sequence.

Give each worker a bounded assignment, the relevant baseline, and a required result. Use the project's reservation or coordination mechanism when it has one. Preserve unrelated changes and have one owner integrate the results.

In the remote delivery work I've been doing, active terminal panes were a poor measure of progress. The useful checks were whether a task was claimed, its dependencies were satisfied, the coordinator was healthy, and reviewed work was reaching the shared branch. If that machinery is unhealthy, repair it before assigning more work.

Judge parallelism by accepted changes and review effort. More concurrent activity is only helpful when it gets the requested result delivered sooner.

## Choose checks that can catch the defect

Verification should follow the failure. A persistence defect needs a save-and-reload check. An authorization defect needs a direct server request from the wrong role. A concurrency defect needs overlapping operations. A copy edit generally needs a build and rendered review, without a new test that merely repeats the wording.

Keep broader repository gates where they are required. When a check fails, reproduce the cause and repair it without weakening the assertion. Separate a failure introduced by the change from an existing environment problem, and state any check that remains unavailable.

For browser workflows, follow the operator through the handoff, refusal, correction, and reload. Test at the screen sizes they use. Hiding an unauthorized button is insufficient if the server still accepts the action. An expected login screen proves an access gate; it doesn't prove the authenticated workflow works.

The same care applies to migrations. Bind the rehearsal to its migration files, target baseline, and input artifact. Follow the failed step into the actual ledger and database state. The [discovery and migration playbook](/playbooks/claude-org-scan-and-migration-readiness-playbook/#treat-migration-as-a-separate-proof-problem) covers the evidence needed before choosing a recovery path.

## Verify the release at the level you claim

Once the change passes review, publish within the authorized scope. On a dirty tree, stage explicit paths and inspect the staged diff. Before merging or cleaning up branches, check current remote state, ancestry, and ownership. After pushing, confirm the remote revision contains the intended change.

Deployment introduces another set of facts. Keep them separate in the report:

| Claim | Evidence needed |
| --- | --- |
| Implemented | Source revision and checks of the changed behavior. |
| Deployed | The running environment's release identity. |
| Configured | Required settings are present, verified without exposing secrets. |
| Connected and enabled | A permitted provider check and the current activation state. |
| Usable by this operator | An authenticated workflow on that release with the expected persisted result. |

For an external action, also verify the provider result when the assignment permits it. An accepted request may still be waiting in an outbox. A local fixture proves behavior against that fixture.

Pre-production is a place for reversible rehearsal and fast correction, but its financial, inventory, and audit records still need integrity. Keep provider activation and live routing explicit. A working demo doesn't grant authority to send a real trade, charge, shipment, or customer message.

## Choose an API only when the product needs an agent

So far, Codex has been doing development work. The resulting product may run entirely on ordinary services, forms, and jobs. Add runtime reasoning when a specific interaction benefits from it.

When it does, choose who owns the execution loop:

| Option | Where I would use it |
| --- | --- |
| Responses API | A product feature whose model calls and tool execution the application controls directly. |
| Agents SDK | Application-owned workflows that benefit from a reusable agent loop, tools, and handoffs. |
| Agents API | Background tasks where OpenAI manages the Codex harness and persistent session, using configured tools and an optional execution environment. |

The runtime distinctions are documented in OpenAI's [Agents guide](https://developers.openai.com/api/docs/guides/agents). Keep application state and business authorization in the owning system regardless of runtime.

For Responses function calling, defining a tool only describes a callable operation. The application must validate the request, execute the handler, return its output, and continue the conversation. Use the complete [function-calling flow](https://developers.openai.com/api/docs/guides/function-calling#the-tool-calling-flow) when implementing it.

For Rebase infrastructure, I'd pilot failed-build investigation: capture the run and revision, reproduce the error in an isolated checkout, attempt a bounded repair, and return a tested draft PR or a concrete blocker. I'd replay known failures and measure diagnosis quality, review time, and cost before enabling automatic triggers.

Choose the environment with its data policy in mind. As checked on September 11, 2026, the Agents API retains session state, supports US data residency, and isn't eligible for Zero Data Retention, including with a self-hosted sandbox. See the [Agents API overview](https://developers.openai.com/api/docs/guides/agents-api/overview) before connecting client material.

For any runtime, narrow tools to the job, enforce authorization in the handler, and treat retrieved text as evidence rather than instructions. Log identifiers, outcomes, and timings with an allowlist; raw arguments and payloads may contain sensitive data. Evaluate wrong-tool choices, unavailable evidence, denied actions, and failed effects alongside successful answers.

## Leave a result the next person can use

The final report should say what changed, what was checked, which revision and environment were verified, and what remains incomplete. Link the diff and the relevant evidence. A release task also needs the deployed result and a recovery path.

Then put the useful lesson where the next task will find it: a regression test for a defect, a corrected contract for an ambiguity, or a runbook step for an operational failure. Update the existing source instead of adding another competing summary. The [managed-services playbook](/playbooks/cooperative-managed-services-platform-systems-of-record/) describes how that verified result feeds back into the next request.
