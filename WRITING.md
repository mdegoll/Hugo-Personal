# Michael DeGoll writing

This site should make complicated work easy to understand and show how I think through it. A reader should leave with a clearer decision, a practical move, or a question worth asking.

Write for capable people who are responsible for an outcome. They may own the company, the operation, the budget, the architecture, or the implementation. They do not need an AI pitch or a generic lesson in software. They need to see the real constraint, understand the tradeoff, and decide what to do next.

## The voice

Michael sounds like a builder with one foot in business operations and the other in implementation.

The voice:

- says what it thinks and explains the reasoning
- is technically curious without turning every topic into a technical lecture
- notices cost, risk, timing, ownership, and operating reality
- respects existing systems when they still earn their keep
- recommends smaller working moves before large programs
- distinguishes firsthand experience, verified evidence, inference, and proposed direction
- looks for the exception that could break the model
- changes direction plainly when new evidence changes the problem
- treats AI as a useful tool that still needs boundaries, review, and proof
- sounds like one person, not an agency, a product company, or a content team

Use first person singular for Michael's experience and judgment. Use `we` only when a real team or collaboration is in view. Use `you` when the reader has a clear action or decision, not as a constant sales device.

Personal voice is not permission to invent personal history. Do not write `I saw`, `I learned`, `I built`, or `in my work` unless the source material supports the claim or Michael has confirmed it. Recast unsupported experience as a hypothesis, recommendation, or open question.

Michael shows expertise through judgment and proof.

## The point of view

The writing should reinforce a few durable beliefs:

- Useful systems should get easier to understand, operate, and improve.
- An existing platform should stay when it still creates more value than drag.
- When a platform becomes expensive, rigid, or hard to trust, replace the smallest painful workflow first.
- Important workflows should fit the people doing the work.
- Recurring cost is only part of platform drag. Slow change, workarounds, vendor limits, and lost operating knowledge matter too.
- AI agents compress build work. Selection, architecture, review, and operational trust become more valuable as output gets cheaper.
- Local AI is useful when privacy, control, offline work, or fast experimentation matters. Important workflows still need a reliable operating path.
- A working slice creates more confidence than a polished promise.
- A prototype should help close a decision. A production system should survive real use.
- Reliability is an operating outcome. People need to know what happened, correct mistakes, and recover when something fails.
- Design should start with evidence of how the work happens, including the exceptions and manual workarounds.
- The amount of process and protection should match the consequence of failure.
- Build with the likely next step in mind without making the first release carry all of it.
- Sometimes the right answer is to simplify, buy, keep, or stop. Building is one option.

Treat these as positions. Explain the conditions that make each one true instead of repeating them as slogans.

## How Michael explains something

Start with the claim, tension, decision, or operating consequence. Skip broad market setup unless the market change is the subject.

Then:

1. Explain what is happening in plain language.
2. Show the operating moment or evidence behind the claim.
3. Name the tradeoff, risk, or exception.
4. Give a recommendation or practical next move.

If the answer is uncertain, explain what would resolve it. Do not hide behind vague caution.

Useful questions include:

- What work is someone actually trying to complete?
- What decision is blocked?
- Where does trust fail?
- What is the current workaround costing?
- Which part of the existing system still earns its keep?
- What is the smallest useful version?
- What could make this unsafe or unreliable?
- Who owns the workflow after launch?
- What evidence would prove the change worked?

Use the questions to shape the piece. Do not print them all unless the reader needs a diagnostic checklist.

When an explanation becomes abstract, return to a concrete operating moment. Show what a person is trying to do, where the friction appears, how the system responds, and what remains under human control.

Before recommending an approach, understand the scale. How often does the problem occur? What is at stake? What does the workaround require? What changes at higher volume? The right answer for a rare exception may be wrong for a daily workflow.

Ask which edge case is most likely to break the proposed model. Explain whether it changes the normal path or deserves a separate path. Do not make every rare possibility part of the headline.

Weak:

> Artificial intelligence is transforming the way modern businesses operate.

Michael:

> AI agents can now handle much of the build. The harder question is deciding what should become production software.

## Make it readable

- Put the answer before the background.
- Give each sentence one main job.
- Prefer concrete nouns and active verbs.
- Use the words operators use for the work.
- Explain a technical term when it changes the decision or helps the reader use the artifact.
- Keep most paragraphs to one to three sentences.
- Use a list when the reader needs to compare, choose, verify, or act.
- Keep the condition close to the claim it qualifies.
- Make pronouns unambiguous. The reader should know who owns the action.
- Cut sentences that only announce the next sentence.
- Use headings to expose the argument, not to decorate the page.

Length should follow the idea. A simple answer can be one line. A meaningful tradeoff deserves enough detail to make the choice clear. A playbook can be long when the reader can navigate it and use it.

## Make it worth reading

Clear prose helps the reader follow. Specific judgment gives them a reason to care.

Any substantial piece should contain at least one of these:

- a constraint the reader recognizes
- a consequence they can feel or measure
- a specific observation about how the work happens
- a useful distinction
- an honest tradeoff
- a recommendation the reader can test
- a practical artifact or next move

Use numbers when they sharpen the decision. Use examples when they shorten the explanation or reveal a hidden edge case. Do not add a story merely to manufacture emotion.

A reader should be able to repeat the central idea after one pass.

## Keep it personal

The site should feel like a field notebook from a working builder. Keep the polish, but lose the detached publication voice.

- Use `I` when stating a real choice, practice, opinion, or lesson.
- Let the reader see the reasoning behind a recommendation.
- Admit when a tool, assumption, or early direction did not hold up.
- Name what remains unresolved instead of polishing away the uncertainty.
- Include details from the workbench when they teach something useful.
- Keep anecdotes short and attached to the point.
- Prefer a clear opinion over a survey of every possible view.

Do not perform intimacy. Avoid diary filler, manufactured vulnerability, and claims about what `we all` feel. Personal writing still needs to earn the reader's time.

Weak:

> As someone deeply passionate about innovation, I have always believed in the transformative power of technology.

Michael:

> I use local models when privacy, control, or fast experimentation matters. If the workflow becomes important, it needs tests, logs, and an owner.

## Make the work visible

Proof does not have to look finished. A narrow working example can be more persuasive than a polished concept when the reader can see what it changes.

Be precise about:

- what exists and works today
- what was personally verified
- what is intentionally rough
- what the example proves
- what remains assumed or proposed
- what could fail
- what happens next
- what was designed for later but intentionally left disabled

Translate hidden technical work into an operating consequence: fewer expensive mistakes, a clear record of what happened, an earlier warning, a safer migration, or a workflow that keeps moving under pressure.

Never present a mockup, reference architecture, planned feature, or AI-generated example as a live capability. A polished artifact does not prove that the underlying system exists.

## Make the judgment clear

Strong writing can say:

- keep this part of the platform
- remove this dependency first
- this option is simpler to operate
- this will take more work the first time
- test this before changing production
- the recurring cost does not justify the dependency
- the evidence is incomplete
- I changed my view after seeing the real workflow
- this is probably not worth building

Do not turn every capability into a promise. State the conditions that make a claim true.

## Make uncertainty useful

When the answer is unsettled, state:

- what is known
- what remains unverified
- what changed the current understanding
- what can be decided now
- the sensible default for the moment
- what input could change that decision
- what work can continue without waiting

Treat reversible choices as reversible. Irreversible decisions need more care. Before recommending a destructive migration or permanent change, explain what will happen, what can still be recovered, and what fallback remains.

For proof-heavy work, use evidence labels where they help:

- **Verified:** supported by an inspected source, command, test, or observed result.
- **Inferred:** a conclusion drawn from evidence, with the reasoning made visible.
- **Proposed:** a recommended future state that has not been implemented or proven.

Do not sprinkle labels through ordinary prose when a plain sentence is clearer.

## Make control concrete

Words such as `flexible`, `configurable`, `agentic`, and `automated` are not benefits by themselves. Explain how control works:

- what happens by default
- who can change the rule
- when an exception is allowed
- whether another person must approve it
- what is recorded for later review
- how a person can correct or stop the action
- what can change later without starting over

Good automation removes repeated work while preserving useful judgment. Expensive mistakes deserve stronger review, clearer logs, and a tested recovery path.

Weak:

> Our robust automation framework empowers teams to unlock efficiency at scale.

Michael:

> Map the ordinary path, automate the repeated handoff, and keep an approval step where a mistake would be expensive.

## Evidence, attribution, and confidentiality

- Cite consequential, current, or non-obvious external claims.
- Prefer primary sources, official documentation, and direct evidence.
- Date facts that can drift, especially product behavior, pricing, and platform capabilities.
- Link to the specific source that supports the sentence.
- Separate what the source says from what Michael concludes.
- Do not use a client name, internal detail, result, or quote without permission.
- Anonymize real work without inventing facts. Label a composite example if several cases were combined.
- Do not manufacture metrics, customer stories, implementation details, or firsthand experience.

Technical credibility comes from accurate boundaries as much as detailed mechanisms.

## Vocabulary

Prefer words such as:

- work
- workflow
- operator
- system
- tool
- useful
- cost
- control
- ownership
- evidence
- constraint
- decision
- exception
- working slice
- migration path
- test
- verify
- review
- retire
- improve
- earn its keep

Use these only when the sentence makes them concrete:

- AI
- agent
- platform
- architecture
- automation
- operating system
- custom
- transformation
- scale

Avoid empty language such as:

- cutting-edge
- seamless
- robust
- world-class
- innovative
- best-in-class
- future-proof
- unlock value
- empower teams
- digital transformation
- end-to-end solution
- tailored to your unique needs
- revolutionize
- game-changing

Use `leverage` as a noun when it describes a real advantage. Do not use it as a decorative verb.

Use vendor and product names when the choice matters. Do not make a tool the hero of a piece that is really about an operating problem.

## Rhythm and punctuation

- Use contractions when they sound natural.
- Mix short decisive sentences with longer explanations.
- Avoid a page full of sentences with the same length or structure.
- Use periods, commas, and colons. Do not use em dashes or double hyphens in public copy.
- Do not force every idea into a group of three.
- Avoid stacked fragments written only for emphasis.
- Use normal capitalization. Preserve official capitalization for names and tools.
- Use a short run of questions when the questions help diagnose a decision.
- Read important passages aloud. If the sentence is hard to say, it is probably hard to read.

Use spoken sources for decision rhythm. Remove filler, repetition, fragments, profanity, casual typos, and shorthand. Preserve the directness, then edit the material into clean prose.

## AI writing patterns to remove

Review every public draft manually. Rewrite the sentence instead of mechanically replacing a word.

Remove:

- `it's not X, it's Y` framing
- `here's why` and `here's why it matters`
- `at its core`, `fundamentally`, and `in today's landscape`
- forced enthusiasm such as `I'm excited to share`
- empty setup such as `in this guide, we will explore`
- repeated rhetorical questions
- suspiciously balanced paragraphs and repeated three-part lists
- conclusions that merely restate the opening
- generic claims that could describe any consultant, software company, or AI site
- technical vocabulary that makes the reader translate the sentence into practical value
- inflated transitions such as `moreover`, `delve`, `navigate the complexities`, and `a testament to`
- fake quotations, invented anecdotes, and unsupported first-person claims

Do not remove useful structure, necessary detail, or honest qualifications simply because they look less conversational.

## Site format rules

### Home and About

- Make the point of view obvious before listing capabilities.
- Use first person and sound like one working builder.
- Lead with the operating problem, not the tool stack.
- Keep each section focused on one claim.
- Use a real project or artifact before adding another broad promise.
- Keep biography relevant to the work the reader is evaluating.
- Write action labels that name the next useful step.

### Essays and posts

- Put the thesis in the opening paragraphs.
- Develop one central argument rather than assembling a trend report.
- Move between operating reality, technical consequence, and judgment.
- Include the strongest relevant exception or counterargument.
- Use headings that let a reader follow the reasoning at a glance.
- End by advancing the idea, naming a decision, or giving a practical move. Do not summarize the introduction.
- Keep the title specific enough that a reader knows what tension the piece will resolve.

### Playbooks

- State the audience, goal, scope, and expected artifact near the top.
- Make prerequisites, boundaries, and safety assumptions explicit.
- Separate reference architecture from implemented capability.
- Give commands, examples, schemas, or checklists that the reader can actually use.
- Keep code and prose consistent with each other.
- Label verified, inferred, and proposed conclusions where the distinction matters.
- Explain failure modes, approval points, and rollback paths.
- Link official references for behavior that can change.
- Finish with a proof package or completion criteria. Skip the motivational conclusion.

### Project and case notes

- Start with the real constraint.
- Explain what was kept, changed, retired, or deferred.
- Show the choice and the evidence behind it.
- State what the work proved and what remains unresolved.
- Protect client confidentiality and avoid claiming results that were not measured.

### Technical explanations

- Answer the practical question first.
- Explain the mechanism only as far as accuracy and reuse require.
- Keep examples runnable or label them as illustrative.
- Separate current behavior from a recommended design.
- Surface risk without dramatizing it.
- End with the safest useful next step.

## Hugo content rules

- Keep front matter valid and consistent with the content type.
- Posts should include `title`, `date`, `description`, `summary`, `tags`, `ShowToc`, and `TocOpen` when appropriate.
- Playbooks should include `title`, `description`, `date`, `draft`, `layout: playbook`, table-of-contents settings, `playbookMeta`, and `tags`. Add `mermaid: true` only when the page contains Mermaid.
- Write descriptions for the reader scanning a list or search result. Do not repeat the title with filler.
- Use one H1 supplied by the page template, then follow heading levels in order.
- Give links meaningful labels. Avoid `click here`.
- Add alt text that explains the useful content of an image.
- Use diagrams when they make a workflow, boundary, or system easier to understand than prose.
- Preview the rendered page before publishing. Check narrow screens, code blocks, lists, links, diagrams, and the table of contents.

## Lines that set the standard

- "Move past bloated platforms. Build tools around the work."
- "Keep what works."
- "Sunset what doesn't."
- "A plan only matters if it turns into something real."
- "No tool should be treated like magic."
- "The demo proves a path. The durable system proves adoption."
- "Good consulting includes a better exit option: stopping work that is no longer needed."
- "AI agents can carry much of the build. Consultants carry the judgment of what should become production software."

These lines are useful because they are direct, specific to the site's point of view, and attached to a decision. Do not repeat them everywhere or copy their sentence shape into every headline.

## Final review

Before publishing, read the complete piece once as an operator and once as a skeptical builder.

Ask:

1. Can the intended reader understand the central point on the first pass?
2. Does the opening give them a reason to continue?
3. Is there a real observation, decision, or artifact beneath the piece?
4. Did I make a useful judgment or merely describe the topic?
5. Are personal claims true and supported by the available source material?
6. Are external claims cited or appropriately qualified?
7. Can the reader distinguish what is verified, inferred, and proposed?
8. Does each paragraph earn its place?
9. Is the important exception or failure mode visible?
10. Is control concrete, or did I merely call the system flexible?
11. Did I show evidence of the outcome or only promise it?
12. Does the ending add a decision, implication, or next move?
13. Could this have appeared on any generic AI consultant site? If so, rewrite it.
14. Does it sound like a thoughtful person who has stayed close to the work?

Most final edits should make the writing shorter, clearer, more accurate, or more specific.
