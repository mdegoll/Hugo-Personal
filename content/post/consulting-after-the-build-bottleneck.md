---
title: "Consulting after the build bottleneck"
date: 2026-05-18
description: "AI agents can handle much of the build. Consultants now compete on judgment, architecture, and operational trust."
summary: "AI agents compress build work. The consultancy edge shifts to decision quality, system design, and sustained adoption."
tags: ["consulting", "ai agents", "architecture", "business tools"]
ShowToc: true
TocOpen: false
---

A lot of what consultancies billed for in 2023 (screen setup, boilerplate, ticket churn, status reporting) is work an agent now does in an afternoon, with review. Agents still need context and business judgment, but enough has shifted that a consultancy whose main product is implementation hours has a problem: a three-person team with good tooling can often ship the same thing faster than a twenty-person team organized around tickets.

Consultants still matter. What changes is what they're for. The useful one decides what should exist, what should be removed, what to change next, what risk to accept, and how to make the outcome something the business can trust.

> AI agents can carry much of the build. Consultants carry the judgment of what should become production software.

## The build bottleneck is breaking

The practical blocker used to be build capacity. Businesses described the same pain over and over:

- The CRM is hard to use.
- The approval process is spread across email.
- Dashboards are stale or wrong.
- Integrations break and data trust collapses.
- The team wants automation but can't spare cycles to build it.
- A platform was bought for one workflow and then became the home for many unrelated processes.

The usual response was expensive: admins, developers, architects, QA, PMs, release managers, training, and a ticket queue measured in months.

Agents cut most of that. They read code, modify software, generate tests, explain unfamiliar systems, and draft migrations, scripts, docs, UI states, and integration glue, and they're especially good at the repetitive middle work where human attention used to be the expensive part. Implementation is still necessary; it's just no longer the thing everything else waits on.

What's scarce now is selection. Which work is worth doing this month, and which should wait?

## The consultant as diagnostician

Many requests are labeled as "software" but describe a process problem.

"Need a Salesforce dashboard" can mean leadership doesn't trust pipeline stages.

"Need an integration" can mean two teams disagree on handoff ownership.

"Need AI" can mean support is repeating the same questions too often.

"Need CRM customization" can mean the underlying process was never designed for this outcome.

A consultant can still turn requirements into work. What changes is what gets built first, and how quickly the team retires work that doesn't add anything.

The questions worth asking before anything gets built:

- What decision is blocked?
- What process is duplicated?
- Where does trust fail?
- Which team is compensating for bad workflows?
- What process exists only because the current system forced it?
- What would disappear if the team stopped protecting sunk cost?

The consultant translates across operators, executives, admins, developers, finance, security, and customers, and points to the operating decision behind the request.

Discovery only matters when it closes a decision. A two-day prototype can invalidate a long planning cycle. The standard now is diagnosis plus an execution plan the team can start on Monday.

## Architecture decisions matter more

Agents can build pieces quickly. They don't decide system ownership.

The right questions become:

- Should this remain in Salesforce?
- Can Salesforce be simplified instead?
- Can one workflow move out first?
- Is Salesforce still the source of truth for this process?
- Is this process generic enough for a system of record?
- Is a purpose-built tool the better fit?
- Which data moves, and which data can be archived?
- Which dependencies should retire first?

Consulting value moves from preserving current implementation patterns to shaping the architecture and migration path.

That can mean staying in Salesforce, cleaning object models, removing unused automation, tightening permissions, and improving operating discipline in the existing platform.

It can also mean removing one high-friction workflow into a smaller tool, or planning a staged migration off Salesforce entirely.

What counts is whether the business got simpler and faster without losing control. How much platform extension got delivered is a vendor's metric.

Platform loyalties bias recommendations, and not subtly. If a team is paid only to extend one platform, there's a built-in pull toward whatever is easy on that platform rather than what's right for the business. The advisor worth trusting is the one who can say "don't solve this here" and give up the work.

## Trust as the review layer

The faster output gets, the more the review layer matters.

Wrong code is only part of the risk. Plausible output that's weak on evidence does just as much damage, and that risk now lands across code, configuration, migrations, recommendations, support responses, documentation, and automation.

Teams adopting agents need owners for:

- Evals and regression sets
- Permission checks
- Audit trails
- Tool-call logging
- Human approval gates
- Security review
- Data quality checks
- Exception handling
- Rollback plans
- Clear ownership after launch

That list is what keeps a demo from quietly becoming a process risk, and the consultant who owns it's a lot harder to replace than the one who runs tickets. They define:

- What the agent may do
- What requires approval
- How to verify evidence
- How to detect regressions
- What happens when the model is uncertain
- Who owns the workflow after launch
- What gets logged and how to troubleshoot

Once that's written down, trust stops depending on who happens to be in the room.

## Durable systems over one-off builds

Code and configuration move fast. Systems don't. What keeps the value around after the build:

- Tested change paths
- Up-to-date documentation
- Clear permissions and boundaries
- Known failure modes
- Deployment process
- Support ownership
- Shared understanding of why the system exists

Consultants now have to make the output repeatable after the first proof works, which means packaging the boring operational parts:

- Repo-native build and test commands
- Smoke tests on key workflows
- AI behavior evals
- Validation-heavy migration scripts
- Operator runbooks
- Architecture notes and decision records
- Permission and approval models
- Feedback loops after launch

The demo proves a path. The durable system proves adoption. Most of the consulting work now is getting from the first to the second before the team overbuilds.

## Economics of consulting change

If agents reduce build labor, pricing by the implementation hour gets hard to defend. Projects still cost money; what changes is that the bill gets justified by outcomes instead of headcount. What clients increasingly look at:

- How quickly teams understand the problem
- How much risk is removed
- How much waste is retired
- How quickly teams can continue without handholding
- Whether complexity stays controlled
- How much of the solution is maintainable by the team

Delivery models built on large implementation benches need a stronger differentiator or a narrower specialty than they used to. The pitch moves from "more builders" to faster clarity, safer decisions, and a cleaner migration path, and a small, technically strong team can beat a large, coordination-heavy one when it brings judgment, clear methods, and proof from live operations.

## What happens to junior consultants?

This is a training problem as much as a delivery problem. Junior consultants have usually learned by doing the lower-level work: tickets, configuration, QA, data cleanup, reporting, meeting notes. If that work is automated, the apprenticeship has to shift earlier, toward structured decision work. Removing the apprenticeship entirely doesn't work, and skipping straight to strategy doesn't either. People still need to learn how systems fail and how a decision made in a workshop turns into an edge case in production.

The new skill set for junior consultants includes:

- Structured discovery
- Reviewing agent output
- Writing practical eval cases
- Workflow mapping
- Real scenario testing
- Decision recording
- Migration validation
- Comparing build, buy, simplify, and retire options
- Post-launch operator behavior analysis

That path needs tighter coaching than the old one. Without it you get people who can prompt a tool but can't diagnose an operational problem.

## The risk of overbuilding

When agents get better, demos get easier, and that creates a predictable failure mode: a polished demo lets everyone skip the hard questions.

- Where does this data come from?
- Who is allowed to see it?
- What happens when the answer is wrong?
- Which system owns the record?
- What happens when tools fail?
- How is cost managed?
- What is logged?
- Who approves actions?
- What should be retired after this lands?

The point is safer operations. A better demo is a side effect at best. A rollout that holds up usually looks like this:

1. Pick one workflow with clear pain and measurable outcomes.
2. Map current behavior and manual workarounds.
3. Choose what to keep, simplify, replace, or retire.
4. Build the smallest useful slice.
5. Add evals, permissions, logs, and approvals.
6. Pilot with real operators.
7. Iterate from feedback, or stop if risk is unresolved.
8. Retire the old process only after trust is proven.

Good consulting includes a better exit option: stopping work that's no longer needed.

## What the job looks like now

Judgment becomes the durable consulting role. In practice that means five things:

- Diagnose the business behind the surface request, and separate the operating problem from the software ask.
- Own architecture and migration: stay in Salesforce, simplify it, replace one workflow, migrate data, or build a purpose-built tool.
- Design the trust layer: evals, permissions, audit, security, quality checks, exception handling, and ownership handoffs.
- Turn agent output into tested, documented systems the team can support without you.
- Lead the transition from large implementation plans to smaller decision cycles.

The consultants who do well here stay close to operators, are comfortable evaluating technical work, and are willing to say "we shouldn't build this" when it adds risk.

Build capacity keeps rising. Judgment is what gets scarce, and picking the right work and shipping it safely is where the fee gets earned.
