---
title: "Using Claude for Salesforce Discovery and Migration Planning"
description: "Read the configuration, watch the work, and turn the gaps into changes a team can test."
summary: "Compare Salesforce configuration with operator walkthroughs, resolve the gaps, and define a tested path for repair or migration. Includes an evidence-note template and migration rehearsal guidance."
weight: 1
date: 2026-05-18
lastmod: 2026-09-11
draft: false
layout: playbook
ShowToc: true
TocOpen: true
aliases:
  - /playbooks/claude-deployment-playbook-salesforce-heavy-enterprises/
playbookMeta:
  - "For Salesforce teams, consultants, and workflow owners"
  - "Updated September 11, 2026"
tags:
  - Claude
  - Salesforce
  - Enterprise AI
  - Evaluation
  - Data Migration
  - Integration Discovery
---

## Start with the workflow someone needs to finish

A shipping screen can produce a carrier label while the invoice still has an outstanding balance. Both events can be valid. The mistake is treating either one as proof that the order is complete.

Recent order-management work has made me more careful about these distinctions. A selected status, a saved record, a printed document, and a physical handoff each tell us something different. Before changing the software, I want to know what happened, what should happen next, and who owns that step.

I use Claude to compare Salesforce metadata, workflow notes, source code, and migration plans. It helps find contradictions and organize the questions. I still need evidence for the answer, especially when the question involves money, inventory, permissions, or a customer commitment.

The process starts with one workflow and follows it far enough to see the outcome. That gives the org scan a purpose and keeps discovery from becoming an inventory nobody uses.

## Establish what the system can tell you

Begin with the checked-out metadata, project configuration, integration documentation, and deployment scripts. Record the source revision, the environment it describes, and the inspection date. If local files differ from that revision, identify the changed files too. A finding needs a baseline another person can inspect.

Use approved describe and metadata inventory calls to fill gaps. Look at the objects and relationships involved in the workflow, then follow their behavior through Flows, Apex, validation rules, permissions, UI components, packages, and external systems. For each handoff, identify the trigger, join key, receiving system, failure path, and owner.

This first pass excludes business records, report results, Salesforce file contents, messages, raw payloads, and debug logs. Constrain what each inspection tool can retrieve and return. Metadata can also contain sensitive values, so credentials and embedded customer details stay out of the analysis artifacts.

That limit affects the conclusions. An unreferenced field is a candidate for investigation; metadata alone does not prove nobody uses it. A configured integration does not establish that it is connected. Permission definitions describe possible access, not a complete history of who exercised it.

I label major findings **Confirmed**, **Inferred**, or **Unknown**. A confirmed finding has direct evidence; an inference explains the reasoning and its limits. For an unknown, I add the specific observation or decision needed to resolve it. If the saved state is unclear, name the permitted state check and the person who can demonstrate the next step.

## Put the operator's account beside the configuration

Once the technical path is visible, watch someone perform the workflow. Include the preparation, the next person's handoff, and a failure or correction. A successful form submission rarely explains the whole job.

In recent walkthrough reviews, packing slips, reference labels, carrier labels, tracking, and invoice completion needed separate treatment. Combining them into one “shipping” step would have hidden both useful shortcuts and controls that had to remain.

Record what the operator entered, which action they took, the response they saw, and where the recording ends. Separate narration from visible behavior. If the review sampled frames, say so; a brief transition may have been missed. Use approved recordings and keep sensitive source material in its designated storage, with sanitized notes for wider use.

A compact finding might read:

```text
Workflow: prepare an order for dispatch
Observed: a carrier label was created; invoice completion was refused
Evidence: recording reference and timestamps, plus inspected source revision
Unknown: whether label creation changed the persisted shipment state
Next check: inspect the permitted state evidence and demonstrate the next handoff
Owner: shipping and finance
```

That finding directs the next inspection without inventing a cause. It also prevents a UI redesign from removing a control simply because the recording did not show its purpose.

## Write the map so someone else can act

The scan and walkthrough should now explain the same workflow, including where they disagree. I keep that explanation in four linked documents. They share source references rather than repeating the inventory.

| Document | What the reader needs |
| --- | --- |
| `01-executive-overview.md` | What the org supports, the main risks, and the next decision. |
| `02-technical-deep-dive.md` | Where the behavior lives, with component paths and integration dependencies. |
| `03-improvement-areas-and-open-questions.md` | Prioritized findings, owners, unresolved rules, and the next check for each. |
| `04-business-process-system-map.md` | The workflow, record states, role handoffs, and failure paths. |

Each document states its baseline and access limits. The process map is usually the best entry point; it should lead a new builder from the user's task to the relevant screen, automation, service, and verification method.

Give Claude a specific review assignment:

> Compare this source baseline with the approved walkthrough notes. Explain the workflow and its handoffs. Cite each major finding, distinguish observed behavior from inferred causes, and identify the next check for anything unresolved. Do not infer business policy from example values or retrieve additional record data.

Review the result against a few cases the team knows well: a normal transaction, a failed handoff, overlapping automation, and something the evidence cannot answer. Check whether the explanation is correct and useful before adding more cases or automating the report.

## Choose the first change from the findings

The next step depends on the kind of gap. A defect needs a reproduction and a fix. An awkward but functioning workflow may need better interaction design. An unresolved business rule needs an owner to decide it before implementation.

Keep those differences visible in the backlog. A recording of a negative balance does not establish an overdraft policy. A missing field in one screen does not establish that the underlying capability is absent. Refresh older findings against current source before assigning work; another change may already have addressed them.

Write acceptance around the user's outcome. For a broker-to-shipping handoff, that could mean the shipping operator can resume the transaction, see the required destination and clearance facts, understand any blocker, and complete the next permitted step. The test should include a refusal and recovery path as well as success.

This is where discovery moves into the [implementation playbook](/playbooks/codex-openai-implementation-playbook-business-tools/). Carry the evidence, unresolved rules, and acceptance criteria into the task so the builder does not have to reconstruct them.

## Treat migration as a separate proof problem

A map can justify moving a workflow out of Salesforce. It cannot establish that the records are ready to move.

Before extraction, agree on which system owns each entity, which identifiers survive, how relationships will be preserved, and what will be archived. Resolve transformations with the business owner, including dates, currencies, quantities, rounding, duplicates, and lifecycle state. Metadata can suggest a mapping; record quality requires separately approved inspection.

For an approved migration, keep the source read-only. Preserve the permitted extract with a manifest, checksums, access controls, and retention rules. Use sanitized or pseudonymized rehearsal data where appropriate; pseudonymized data still needs protection. Record validation results against the exact extract and target revision.

The rehearsal should reconcile counts, relationships, rejected rows, and the totals or balances the business depends on. It should also prove that operators can continue the workflow after the load. A row count cannot show whether an order can be received, allocated, shipped, or closed.

When a rehearsal fails, inspect the failed artifact, the exact migration, the actual target ledger, and the relevant database state before proposing recovery. A recent pre-production investigation traced a failure to a grant for a role that did not exist. The database already had migration history; a reset would have addressed the wrong problem. The diagnosis identified a possible repair, but the repair still needed review and a successful rehearsal.

Check whether a migration has been applied anywhere before amending it. Record partial application explicitly, then choose the recovery path that fits the evidence. Decide the cutover and recovery procedure before the live load, including how to handle new writes after cutover; restoring the old application may not undo their effects.

## Hand over a decision and a way to test it

Discovery is ready for handoff when the team can explain the workflow, locate its implementation, name the unresolved decisions, and test the next change. The recommendation may be to repair Salesforce, move one workflow, retain an archive, or leave a working part alone.

I want the next builder to know where to start and the operator to know what will improve. After the change, update the map with what was verified and what remains unknown. Those updates become the starting point for the next request in the [managed-services workflow](/playbooks/cooperative-managed-services-platform-systems-of-record/).
