---
target: home page
total_score: 23
max_score: 32
na_heuristics: 7,10
p0_count: 0
p1_count: 2
target_identity: "file:/Users/Michael/Projects/Hugo-Personal/content/_index.md"
target_fingerprint: "sha256:aa009ce33e4100d7fad89b2fb757be3b3f5a824882de523515f4f5b0eac940f3"
target_path: /Users/Michael/Projects/Hugo-Personal/content/_index.md
timestamp: 2026-10-21T17-30-59Z
slug: content-index-md
---
Method: dual-agent (A: design review · B: detector/browser evidence)

## Design Health Score: 23/32 (Good)

| # | Heuristic | Score | Key Issue |
|---|---|---|---|
| 1 | Visibility of System Status | 3 | No active nav state on /. mailto: gives no feedback without a mail client. |
| 2 | Match System / Real World | 3 | Strong operator language; "working slice", "Codex" assume an insider. |
| 3 | User Control and Freedom | 3 | Only conversion path is mailto:; plain address only in 11px footer mono. |
| 4 | Consistency and Standards | 2 | Primary/secondary buttons render 46px vs 62px tall (theme .button margin leak). Hero rule 860px vs section rules 1040px. First playbook is Salesforce-first. |
| 5 | Error Prevention | 3 | mailto: has no subject. |
| 6 | Recognition Rather Than Recall | 3 | Whole card darkens on hover; only the title is a link. |
| 7 | Flexibility and Efficiency | n/a | Persuade surface. |
| 8 | Aesthetic and Minimalist Design | 3 | Restrained; "How I work" is a prose wall; left column dead space. |
| 9 | Error Recovery | 3 | Failed mailto: strands the visitor. |
| 10 | Help and Documentation | n/a | Persuade surface. |

## Design Specificity Verdict

Copy is authored for this product. Visual layer is a rebase.team-derived skin (big serif hero, cool-gray paper, lime button, left-heading rows, white cards) that an unrelated consultant could reuse unchanged. Nothing visual is about the work. Deterministic scan: 2 findings on public/index.html, both overused-font: geist, explained by the brief. No overlay injected (no mutable browser tab); evidence from Playwright measurements. Contrast clean (lede 5.27:1, panel text 6.14:1, ink on lime 10.1:1), 13/13 focusable elements show the 2px lime-deep ring, headings in order, no horizontal overflow at 390.

## Priority Issues

- [P1] Theme button rule breaks the primary CTA. themes/PaperMod/assets/css/common/profile-mode.css:29 .button { margin: 8px } and :active transform leak into site .button. Desktop primary inset 8px, secondary stretched to 62px; mobile widths 342 vs 358. Fix: .button { margin: 0; transform: none }, .page-actions { align-items: center }. Command: polish.
- [P1] No proof on the persuasion surface. Kicksights, Rebase, GitHub, LinkedIn only on /about/. Fix: "Current work" page-section on home between Where AI fits and Playbooks; GitHub/LinkedIn secondary buttons in page-closing. Command: layout.
- [P2] First artifact contradicts the Salesforce-first anti-reference; playbook titles read as tool tutorials ("Using X for..."). Fix: retitle around the operating problem; move tool/platform into dek or chip. Command: clarify.
- [P2] Visuals carry no product idea; three identical cards for "three stages of one job". Fix: sequenced stage strip with stage name primary, or a small keep/fix/move/retire diagram. Flat, one accent. Command: bolder.
- [P2] No reassurance or fallback at contact. Bare mailto:, no subject, no next-step line, address only in footer. Fix: ?subject=, a reply-time/what-to-include line under the closing button, selectable plain address. Command: clarify.

## Persona Red Flags

- Jordan: hero never says who Michael is or that he is for hire; "Start with the one you are in" requires self-diagnosis before the stages are explained.
- Riley: card hover implies whole card is clickable; section-note link loops to the same three items; single post dated May reads as unmaintained.
- Casey (390): CTAs visible by y=595, then 614px of unbroken prose; next email CTA at y=3000/3214; nav links 19px tall.
- AI platform evaluator: tests/logs/owner claim links to nothing; no GitHub on home; no og:image.

## Minor Observations

Hero rule stops at 860px vs 1040px section rules. section-note orphans "in." at 1280. Left h2 grid cells stretch to 505px. Lime underline on paper 1.6:1. Secondary button border 1.49:1 on paper. Both CTAs labelled "Send me an email". Footer email uppercase mono.

## Questions

- Should the first screen say "I build at Rebase", or should the skin diverge from rebase.team?
- What would it take to show one real redacted log or diff instead of a paragraph of "How I work"?
- What single artifact should an Anthropic/OpenAI evaluator leave remembering, and is it on the page?

Note: copy was revised (Dan Luu pass) after the assessments ran; copy-specific findings are partly stale, structural/measured findings hold.
