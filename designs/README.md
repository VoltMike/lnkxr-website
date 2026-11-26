# LNKXR website – final designs (v0.4)

Status: **2026-11-26** · live on https://lnkxr.com · source of truth is always `../index.html`.

This folder archives the final designs of the v0.4 work as **renders** (PNG/JPG) and as **standalone component pages** (HTML).
It is excluded from the published site via `_config.yml`.

## Renders

| File | Shows |
|---|---|
| `renders/00_full-page_desktop.jpg` | Whole page, 1440 px wide |
| `renders/07_full-page_mobile.jpg` | Whole page, 390 px wide (2×) |
| `renders/01_hero.png` | Hero: logo, headline, SIL/CHIL/HIL/AI tags |
| `renders/02_architecture-flow.png` | Architecture flow, deployment tile "On-site" active |
| `renders/02b_architecture-flow_hosted.png` | Same, deployment tile "Hosted · HaaS" active |
| `renders/03_haas-node.png` | LNKXR HaaS NODE section: headline, function blocks, 19" demonstrator render |
| `renders/04a_rack-journey_bench.png` | Journey scene: node on the workbench ("Today · Demonstrator") |
| `renders/04b_rack-journey_travel.png` | Journey scene: node travelling to the rack |
| `renders/04c_rack-journey_in-rack-drawer-open.png` | Journey scene: node in the rack, LEDs on, DUT drawer open |
| `renders/05_build-progress.png` | Build progress: Architecture ✓ · Demonstrator build · Bring-up · First remote session |
| `renders/06_haas-console_running.png` | HaaS console during a run with phase-loss derate |
| `renders/06b_haas-console_power-path.png` | Console power path with circuit symbols |
| `renders/08_sequencer_fault-run.png` | Sequencer after a run with injected fault (PWR-004 FAIL, PWR-005 SKIP) |
| `renders/08b_sequencer_mobile.png` | Sequencer on a phone (390 px) |

## Standalone components

Open directly in a browser; each file contains the full site CSS and one section.

| File | Section | Notes |
|---|---|---|
| `components/architecture-flow.html` | `#flow` | Knowledge → LNKXR core (+ on-prem AI compute) → SIL / CHIL / HIL / LAB/HW → Evidence; deployment On-site / Hosted · HaaS |
| `components/haas-node-and-rack.html` | `#node` | HaaS NODE demonstrator + "From demonstrator to HIL rack" animation + build progress |
| `components/haas-console.html` | `#haas` | Interactive glass console (OBC 11 kW / 800 V, simulated data) |
| `components/sequencer.html` | `#sequencer` | Clickable sequencer run demo (power_up_smoke.json, simulated data) |

## Design decisions (2026-11-26)

1. **No simulation (SIM) as an offering.** Execution targets are SIL, CHIL, HIL and LAB/HW only.
2. **Two deployment models:** on-site at the customer, or hosted by LNKXR as Hardware-as-a-Service.
3. **Architecture instead of a linear chain:** validation intent is defined once and mapped to interchangeable targets via adapters.
4. **Technology is shown, brands are not:** on-prem GPU node, racks, controller board, lab supply – generic, no vendor look-alikes.
5. **HaaS console** uses a glass style (translucent panels, blur) over purple light fields; status colours ok `#5FE3A1`, warn `#FFB547`, bad `#FF4D6D` are limited to this section.
6. **Power path symbols:** grid (3 phases), diode bridge (PFC), capacitor (DC link, glows with voltage), resonant tank + transformer with isolation barrier (CLLC), battery with SOC fill.
7. **HaaS NODE** is built natively in HTML/CSS from the public promo slide (`mvpzer0/HaaS_demonstrator/images/03_HaaS_NODE_website_promo_PUBLIC.png`), not embedded as an image.
8. **First demonstrator rack holds exactly one HaaS NODE**, plus network uplink, I/O · fault injection, source · load, vent panel and a DUT drawer that opens to show the DUT.
9. **Honesty labels:** "Concept preview · simulated data", "Under development", "Architecture overview · currently in development".
10. **Disclosure:** no component names, channel counts, storage size, connectors or network topology of the HaaS NODE on the public site.

## Animation reference

| Element | Technique | Cycle |
|---|---|---|
| Architecture pulses | SVG `<animateMotion>` | 1–2 s per wire |
| Deployment tiles | CSS opacity keyframes | 8 s |
| Rack journey | CSS `transform` keyframes on an SVG group | 10 s (bench → lift → slot in → LEDs → drawer open/close → reset) |
| Console values | Inline vanilla JS at 10 Hz | continuous |

All motion stops under `prefers-reduced-motion`; the journey then shows the node already in the rack.
