# Changelog

## v0.4 – Content polishing (in progress)

### 2026-11-26 · Sequencer demo
- New section **LNKXR Sequencer** (`#sequencer`): "Define the test once. Run it anywhere."
- Clickable run demo of the MVPzer0 test sequencer with the real example sequence `power_up_smoke.json`:
  RUN/PAUSE/STOP, fault injection, live step status, PASS/FAIL/SKIP, DC bus gauge, event log.
- Labelled "Concept preview · simulated data"; targets shown honestly (simulator active, HaaS NODE in development, HIL rack planned).
- Navigation: added `SEQUENCER`. Anchor `#sequencer` (not `#seq`, which the HaaS console already uses).

### 2026-11-26 · Design archive
- `designs/` with renders (full page desktop/mobile, every new section, journey key frames, running console)
  and standalone component pages; design decisions and animation reference in `designs/README.md`.
- `_config.yml` excludes `designs/`, `prototypes/` and the Markdown docs from the published site.

### 2026-11-26 · First demonstrator rack: one node
- HIL rack in the journey scene now holds exactly **one HaaS NODE** (the one from the workbench) plus network,
  I/O · fault injection, source · load and a larger DUT drawer. Additional node slots removed.

### 2026-11-26 · HIL rack journey
- New animated scene in `#node`: the HaaS NODE demonstrator moves from the workbench into a full HIL rack
  with network, node slots, I/O · fault injection, source · load and a DUT drawer that opens.
- Framed as vision ("One node today … in one rack next"), no internal specs.

### 2026-11-26 · HaaS NODE demonstrator
- New section **LNKXR HaaS NODE** (`#node`): "Test hardware as a service. Without LOCK-IN."
- Native HTML/CSS version of the public promo slide: animated 19" unit, public function blocks,
  build progress (architecture done · demonstrator in build · bring-up · first remote session).
- Marked **under development**; no component names or internal specs (per HaaS_demonstrator disclosure rules).
- Navigation: added `NODE`.

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
