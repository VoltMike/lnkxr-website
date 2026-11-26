# lnkxr-website

Official website of **LNKXR** – *Validation without LOCK-IN.*

Live: **https://lnkxr.com** · Hosting: GitHub Pages (branch `main`, root) · Contact: hello@lnkxr.com

LNKXR is building a vendor-neutral validation platform for power electronics and embedded systems.
Validation intent is defined once and executed on **SIL, CHIL, HIL and lab hardware** through adapters,
either **on-site** at the customer or **hosted by LNKXR as Hardware-as-a-Service (HaaS)**.

---

## Repository structure

| File | Purpose |
|---|---|
| `index.html` | The whole site: markup, CSS and the small demo script, in one file |
| `lnkxr-logo.png` | Wordmark (white LNKXR, purple X, claim) |
| `impressum.html` | Legal notice (Impressum) |
| `datenschutz.html` | Privacy notice |
| `CNAME` | Custom domain `lnkxr.com` – **do not delete** |
| `CLAUDE.md` | Project rules and context for Claude Code |
| `CHANGELOG.md` | Version history and decisions |

No build step, no framework, no dependencies. Edit `index.html`, commit, push – GitHub Pages deploys automatically.

## Page sections

| # | Section | Anchor | Notes |
|---|---|---|---|
| 1 | Hero | `#top` | Logo, headline, SIL/CHIL/HIL/AI tags, grid + scanline |
| 2 | Problem | `#vision` | "Engineering validation is fragmented." |
| 3 | Let engineering flow | `#flow` | **Animated architecture** (see below), tech cards, terminal |
| 4 | Hardware-as-a-Service | `#haas` | **HaaS console demo** (see below) |
| 5 | Platform | `#platform` | Knowledge · Validation · Connect |
| 6 | LNKXR AI | `#ai` | Extract → Structure → Validate |
| 7 | Why LNKXR | – | "Your validation knowledge should outlive your toolchain." |
| 8 | Status | `#status` | Currently in development |
| 9 | Contact | `#contact` | `mailto:hello@lnkxr.com` |

## Components

### Architecture flow (`#flow`, CSS scoped to `.arch`)
Inline SVG, no JavaScript.

```
01 KNOWLEDGE        02 LNKXR CORE              03 EXECUTION                 04 EVIDENCE
Requirements   ──▶  LNKXR AI · Extract    ──▶  SIL      (terminal icon)  ──▶  Results
Schematics          Knowledge model            CHIL     (controller board)    Traceability
Manuals             Validation intent          HIL      (rack, LEDs)          Report
                    ▲ On-prem AI compute       LAB / HW (supply + waveform)
                                               Deployment: ON-SITE | HOSTED · HaaS
```

- Pulses run along the wires with SVG `<animateMotion>`; rack LEDs, waveform and the deployment tiles use CSS keyframes.
- Four KPI tiles below: Validation intent · Execution · Deployment · Status.
- Mobile: the diagram scrolls horizontally ("Swipe to explore →").

### HaaS console (`#haas`, CSS scoped to `#haas`)
A **concept preview with simulated data** of how a customer monitors and controls a hosted HIL bench.
Example DUT: **on-board charger (OBC), 11 kW, 800 V**.

| Panel | Content |
|---|---|
| Top bar | Bench HIL-02 · DUT · hosted location · session clock · **E-STOP** |
| Power path | Grid 3~ → PFC (SiC) → DC link 850 V → CLLC (isolated) → emulated HV battery, each with an animated circuit symbol |
| DUT state | State machine, AC/HV contactors, control pilot (26.7 % / 16 A), insulation monitor |
| Live values | P_out, V_out, I_out, efficiency, T_max + 60 s trend |
| Bench control | Power limit 1–11 kW, battery emulator 550–920 V |
| Fault injection | Grid sag −15 %, phase loss L3, coolant +20 °C, CAN timeout |
| AC phase currents / thermal | Live 3-phase waveform, PFC/DC-DC SiC and transformer temperatures |
| Test sequence | `OBC-PWR-012`: insulation check → precharge → CP handshake → ramp → hold → grid sag ride-through → safe shutdown |
| Event log | Timestamped, traceable events |

- ~100 lines of inline vanilla JS (10 Hz simulation), no libraries, no network requests.
- Values are physically plausible (≈16.6 A per phase and ≈13.8 A DC at 11 kW / 800 V, η ≈ 95–96 %).
- Labelled **"Concept preview · simulated data · hosted benches in development"** – keep it that way.
- `prefers-reduced-motion` stops all decorative animation.

## Design system

| Token | Value |
|---|---|
| `--bg` | `#030305` |
| `--surface` / `--surface2` | `#08080D` / `#0C0B12` |
| `--text` / `--muted` | `#F5F5F7` / `#8D8D9C` |
| `--line` | `#20202B` |
| `--purple` / `--purple2` / `--purple3` | `#9D22FF` / `#C04CFF` / `#5F0AA8` |
| Status (HaaS only) | ok `#5FE3A1` · warn `#FFB547` · bad `#FF4D6D` |

Font: `Inter, ui-sans-serif, system-ui, …` (no external font loading). Max width 1180px.
Purple is an accent for signal and connection, not a fill colour.

## Content rules

- English copy, short sentences, technically credible. No hype words, no fake customers, team or testimonials.
- Offering focus: **SIL · CHIL · HIL · LAB/HW**. Pure simulation is not an offered execution target.
- Deployment: **on-site** or **hosted (HaaS)**.
- Anything not yet built is described as vision / in development.
- No tracking, no cookies, no external embeds.

## Editing and deploying

```bash
git checkout -b feature/my-change
# edit index.html
git commit -am "Describe the change"
git push -u origin feature/my-change   # open a pull request, merge to main
```

GitHub Pages publishes `main` within a minute or two. If the old version still shows, hard-refresh (Cmd + Shift + R).
