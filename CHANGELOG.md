# Changelog

## v0.4 – Content polishing (in progress)

### 2026-11-26 · HaaS console
- New section **Hardware-as-a-Service** (`#haas`): "Your DUT. Our bench. Full control."
- Glass-style console demo for a hosted HIL bench with an **11 kW / 800 V on-board charger** as example DUT:
  power path with animated circuit symbols, DUT state, live values + trend, bench control,
  fault injection, AC phase currents, thermal, test sequence `OBC-PWR-012`, event log, E-STOP.
- Simulated data, clearly labelled as concept preview. Inline vanilla JS, no dependencies.
- Navigation: added `HAAS`.

### 2026-11-26 · Architecture flow
- Replaced the linear `KNOWLEDGE → SIMULATION → SIL → CHIL → HIL → HARDWARE` chain with an
  animated architecture: Knowledge → LNKXR core → SIL / CHIL / HIL / LAB → Evidence.
- Added on-prem AI compute node, hardware illustrations and the deployment model (on-site / hosted HaaS).
- Hero subline and platform copy no longer mention simulation.

### Decisions
- **Simulation (SIM) is not part of the offering** – too much competition from established vendors.
  Focus on SIL, CHIL, HIL and lab/power hardware.
- **Two deployment models:** on-site at the customer, or hosted by LNKXR as HaaS.
- Demos stay honest: simulated data and "in development" are stated on the page.

### 2026-11-26 · Project context
- Added `CLAUDE.md` with brand rules, design tokens and roadmap for Claude Code.

## v0.3 – Technical motion
- Engineering grid, scanline, SIL/CHIL/HIL/AI tags, animated flow, tech cards, terminal block.
- Impressum and privacy pages, footer links.
- Custom domain `lnkxr.com` via GitHub Pages.

## v0.2 – Hero & flow
- Stronger hero, purple glow, headline "One validation flow. Any tool. Any hardware."

## v0.1 – Initial prototype
- First dark one-pager: hero, problem, vision, platform, AI, status, contact.
