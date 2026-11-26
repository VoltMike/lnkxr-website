# LNKXR Website – Project Context for Claude Code

Owner: Michael Lengenfelder (Founder & CTO, LNKXR)
Communicate with Michael in **German**. Brand/website copy is **English**.

## What this repo is
Static public website for **LNKXR** at https://lnkxr.com, hosted on **GitHub Pages** (deploy from branch `main`, `/` root).
Separate from the private `mvpzer0` repo (technical PoC). MVPzer0 proves the idea; this site explains why it matters.
The site must never claim capabilities MVPzer0 does not actually have.

## Files
```
index.html        # single-page site (v0.4): v0.3 visual baseline + architecture flow + HaaS console
lnkxr-logo.png
impressum.html
datenschutz.html
CNAME             # must contain: lnkxr.com — never delete
README.md         # structure, sections, components, how to edit/deploy
CHANGELOG.md      # version history and decisions
designs/          # archive of final designs (renders + standalone components) – update after design changes
_config.yml       # excludes docs/designs from GitHub Pages
```

## Hard rules (do not reopen without new evidence)
- Name stays **LNKXR**. No naming brainstorms.
- Claim stays **Validation without LOCK-IN.** (exact casing, trailing period)
- Purple X identity stays. v0.3 stays the visual baseline.
- Plain HTML/CSS, minimal JS. No frameworks (React/Next/etc.), no WordPress, no build step.
  Exception: the HaaS console demo uses ~100 lines of inline vanilla JS for its simulation (no libraries, no network).
- No tracking: no analytics, no Meta Pixel, no cookies banner, no newsletter, no contact form, no external fonts/embeds. Contact via `mailto:hello@lnkxr.com`.
- Do not call LNKXR a GmbH/UG or any legal entity — none exists yet.
- AI is a product layer, not the company identity.
- Small, meaningful commits. One issue/section at a time.
- **Offering focus: SIL, CHIL, HIL and LAB/HW. Pure simulation (SIM) is NOT part of the offering** — too much competition from established vendors. Do not reintroduce "simulation" as an execution target.
- **Deployment model: on-site at the customer, or hosted by LNKXR as Hardware-as-a-Service (HaaS).**
- Demos must be labelled honestly (e.g. "Concept preview · simulated data"). Never present the HaaS console as a live service.

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

Status colours (HaaS console only, scoped to `#haas`): ok #5FE3A1 · warn #FFB547 · bad #FF4D6D.
Glass panels: translucent white gradient + 1px white/10% border + `backdrop-filter: blur(18px)`.

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
- HaaS: Your DUT. Our bench. Full control.
- Positioning: Vendor-neutral validation for power electronics and embedded systems.
- Contact: Validation should move with engineering.

Tone: short sentences, technically credible. No "revolutionary / game-changing / world-leading",
no fake customers, testimonials or team. "Currently in development" is fine.

## Roadmap
```
v0.1 ✅ Initial prototype
v0.2 ✅ Hero & flow
v0.3 ✅ Technical motion (+ legal pages already added)
v0.4 ⏭ Content polishing   ← current (architecture flow ✅, HaaS console ✅)
v0.6 → LinkedIn + contact
v1.0 → Public launch
```

### v0.4 order (one section at a time: discuss → agree → issue → commit → next)
1. Hero  2. Problem  3. Vision/Flow  4. SIL/CHIL/HIL/Lab  5. Platform
6. LNKXR AI (align with MVPzer0)  7. Why LNKXR  8. Development status  9. Contact

## Page sections (index.html)
1. Hero · 2. Problem (`#vision`) · 3. Let engineering flow (`#flow`) – animated architecture SVG
3b. HaaS NODE (`#node`) – demonstrator hardware, under development · 4. HaaS (`#haas`) – glass console demo · 5. Platform (`#platform`) · 6. LNKXR AI (`#ai`)
7. Why LNKXR · 8. Status (`#status`) · 9. Contact (`#contact`)

Architecture model shown on the site (decided 2026-11-26):
```
KNOWLEDGE → LNKXR CORE (AI extract → knowledge model → validation intent)
          → SIL | CHIL | HIL | LAB/HW  (via adapters; deployed on-site or hosted/HaaS)
          → EVIDENCE (results · traceability · report)
```
CSS of new components is scoped: architecture under `.arch`, node under `#node`, console under `#haas`.

**HaaS NODE disclosure (from mvpzer0/HaaS_demonstrator):** public = function blocks, flow, API types (REST, MQTT, web UI).
Never public = component/board names, channel counts, storage size, connector types, rack height details, network topology/VLANs.

## Open backlog
HTTPS enforce · www.lnkxr.com · redirect lnkxr.de/.ai → .com · LinkedIn link in footer ·
favicon from purple X · OpenGraph/social image · v0.4 copy · v1.0 launch checklist

## MVPzer0 reality (for honest copy)
This repo is public: keep internal tooling details out of it.
- Working: AI-assisted extraction of engineering documents with a local LLM on on-prem GPU compute (manual baseline).
- Working: hardware-neutral test sequencer with adapter interface (simulator adapter only).
- Future: execution on real SIL/CHIL/HIL/LAB hardware and hosted HaaS benches — describe as vision, not as shipped.
