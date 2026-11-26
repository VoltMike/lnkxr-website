# LNKXR Website – Project Context for Claude Code

Owner: Michael Lengenfelder (Founder & CTO, LNKXR)
Communicate with Michael in **German**. Brand/website copy is **English**.

## What this repo is
Static public website for **LNKXR** at https://lnkxr.com, hosted on **GitHub Pages** (deploy from branch `main`, `/` root).
Separate from the private `mvpzer0` repo (technical PoC). MVPzer0 proves the idea; this site explains why it matters.
The site must never claim capabilities MVPzer0 does not actually have.

## Files
```
index.html        # v0.3 "Technical Motion" – preferred visual baseline, keep it
lnkxr-logo.png
impressum.html
datenschutz.html
CNAME             # must contain: lnkxr.com — never delete
README.md
```

## Hard rules (do not reopen without new evidence)
- Name stays **LNKXR**. No naming brainstorms.
- Claim stays **Validation without LOCK-IN.** (exact casing, trailing period)
- Purple X identity stays. v0.3 stays the visual baseline.
- Plain HTML/CSS, minimal JS. No frameworks (React/Next/etc.), no WordPress, no build step.
- No tracking: no analytics, no Meta Pixel, no cookies banner, no newsletter, no contact form, no external fonts/embeds. Contact via `mailto:hello@lnkxr.com`.
- Do not call LNKXR a GmbH/UG or any legal entity — none exists yet.
- AI is a product layer, not the company identity.
- Small, meaningful commits. One issue/section at a time.

## Design system (CSS variables in index.html)
| Role | Hex |
|---|---|
| Background | #030305 |
| Surface | #08080D |
| Primary text | #F5F5F7 |
| Muted text | #8D8D9C |
| Purple | #9D22FF |
| Bright purple (`--purple2`) | #C04CFF |
| Deep purple (`--purple3`) | #5F0AA8 |
| Surface 2 | #0C0B12 |
| Lines/borders (`--line`) | #20202B |

Font stack: `Inter, ui-sans-serif, system-ui, -apple-system, …` (no external font loading).
Max content width: 1180px.

Dark, sparse, large geometric sans, generous whitespace. Purple only as signal/connection accent.
Technical grid, nodes, lines, subtle glow. Motion must express engineering flow, not decorative "AI particles".
Responsive; respect `prefers-reduced-motion`.

## Brand copy
- Claim: Validation without LOCK-IN.
- Vision: Let engineering flow.
- Principle: Hardware is replaceable. Validation knowledge is not.
- Value: Your validation knowledge should outlive your toolchain.
- AI: Engineering knowledge shouldn't end in documents. / Make engineering knowledge executable.
- Hero (current): One validation flow. Any tool. Any hardware.
- Positioning: Vendor-neutral validation for power electronics and embedded systems.
- Contact: Validation should move with engineering.

Tone: short sentences, technically credible. No "revolutionary / game-changing / world-leading",
no fake customers, testimonials or team. "Currently in development" is fine.

## Roadmap
```
v0.1 ✅ Initial prototype
v0.2 ✅ Hero & flow
v0.3 ✅ Technical motion (+ legal pages already added)
v0.4 ⏭ Content polishing   ← current
v0.6 → LinkedIn + contact
v1.0 → Public launch
```

### v0.4 order (one section at a time: discuss → agree → issue → commit → next)
1. Hero  2. Problem  3. Vision/Flow  4. SIL/CHIL/HIL/Lab  5. Platform
6. LNKXR AI (align with MVPzer0)  7. Why LNKXR  8. Development status  9. Contact

### Key content question for v0.4
Current flow is linear: `KNOWLEDGE → SIMULATION → SIL → CHIL → HIL → HARDWARE`.
Likely more accurate model (validation intent mapped to interchangeable targets):
```
ENGINEERING KNOWLEDGE
        ↓
VALIDATION INTENT
        ↓
[ SIM | SIL | CHIL | HIL | LAB/HW ]
        ↓
EVIDENCE
```

## Open backlog
HTTPS enforce · www.lnkxr.com · redirect lnkxr.de/.ai → .com · LinkedIn link in footer ·
favicon from purple X · OpenGraph/social image · v0.4 copy · v1.0 launch checklist

## MVPzer0 reality (for honest copy)
Engineering PDFs → text → local Qwen 2.5 32B (vLLM on DGX Spark, OpenClaw) → structured knowledge → validation targets/test cases.
Manual extraction works; reproducible baseline (MVPZ-011) and schema-enforced JSON extraction are next.
Execution on SIL/CHIL/HIL hardware is **future** — describe it as vision, not as shipped.
