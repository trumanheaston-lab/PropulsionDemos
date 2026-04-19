# 🚀 Rocket Equation Calculator

**An interactive, browser-based tool that visualizes the Tsiolkovsky Rocket Equation — built to deepen my understanding of the physics behind real propulsion systems.**

---

## Live Demo

> 🔗 [**Launch Calculator**](https://trumanheaston-lab.github.io/PropulsionDemos/rocket-equation)  
> *(GitHub Pages link — will go live once Pages is enabled on the repo)*

---

## Why This Project Matters

The Tsiolkovsky Rocket Equation is the foundation of every propulsion budget ever written — from a Rocket Lab Electron first stage to a SpaceX Starship upper stage separation. Before you can talk mass fractions, specific impulse optimization, or staging logic in an engineering interview, you need this equation in your bones.

Building a calculator that *visualizes* how changing propellant mass, structural mass, or exhaust velocity shifts your delta-v forced me to stop treating the equation as a formula I could look up and start treating it as an intuition I own. That's the goal.

---

## How It Works

The calculator is built around the **Tsiolkovsky Rocket Equation**:

```
Δv = ve × ln(m₀ / mf)
```

| Variable | Meaning |
|---|---|
| `Δv` | Change in velocity (m/s) — your "propulsion budget" |
| `ve` | Effective exhaust velocity (m/s) — linked to specific impulse via `ve = Isp × g₀` |
| `m₀` | Initial (wet) mass — structure + propellant + payload |
| `mf` | Final (dry) mass — structure + payload after burnout |
| `ln(m₀/mf)` | The natural log of the **mass ratio** — this is where propellant efficiency lives |

The user inputs wet mass, dry mass, and exhaust velocity (or Isp). The calculator returns delta-v instantly and displays a dynamic bar showing how much of the total mass is propellant — making the mass ratio tangible rather than abstract.

---

## Key Learnings

- **Mass ratio dominates everything.** A small increase in dry mass (e.g., heavier tank walls) eats delta-v far more aggressively than intuition suggests — the natural log relationship is unforgiving at high mass fractions.
- **Specific impulse is the "fuel efficiency" number that engineers actually argue about.** The difference between kerosene (Isp ~300s) and liquid hydrogen (Isp ~450s) is enormous when you propagate it through a staging calculation.
- **Staging exists because of this equation.** Dropping an empty stage resets `mf`, letting you take a fresh ln() of a better mass ratio. The math makes staging feel inevitable, not clever.
- **This is a design constraint tool, not just a formula.** Real propulsion engineers use it to back-calculate allowable structural mass given a target Δv — building this made that flow feel natural.

---

## Calculator Preview

The interface features:

- **Three input fields** — wet mass (kg), dry mass (kg), and specific impulse (s)
- **Live delta-v output** in m/s and km/s, updating on every keystroke
- **Mass fraction bar** — a visual breakdown showing propellant vs. dry mass as a proportion of total vehicle mass
- **Preset buttons** for real-world reference points (Falcon 9 first stage, Electron, generic solid rocket) so you can immediately see what "good" numbers look like
- Clean, minimal UI — no clutter, just the physics

*(Screenshot folder: `/rocket-equation/assets/screenshots/`)*

---

## Technologies Used

- **HTML5** — semantic structure, accessible form inputs
- **CSS3** — responsive layout, animated mass fraction bar, clean typography
- **Vanilla JavaScript** — real-time calculation logic, DOM updates, no dependencies

No frameworks or libraries. The goal was to keep the stack as transparent as the physics.

---

## File Structure

```
rocket-equation/
├── index.html          # Main calculator page
├── style.css           # Styling and layout
├── calculator.js       # Rocket equation logic + DOM bindings
├── presets.js          # Real-world vehicle reference data
└── assets/
    └── screenshots/    # UI screenshots for documentation
```

---

## Future Improvements

- [ ] **Multi-stage calculator** — chain two or three stages, each with independent Isp and mass inputs, to compute total mission delta-v
- [ ] **Isp ↔ exhaust velocity toggle** — let users work in either unit system naturally
- [ ] **Delta-v budget comparison** — overlay common mission requirements (LEO ~9.4 km/s, TLI ~3.1 km/s) so users can see how close a given design comes to mission capability
- [ ] **Propellant type selector** — pre-fill exhaust velocity based on common propellant combinations (LOX/RP-1, LOX/LH2, N2O4/UDMH, solid)
- [ ] **Mobile-responsive layout** — currently optimized for desktop

---

## About

This project is part of [PropulsionDemos](https://github.com/trumanheaston-lab/PropulsionDemos) — a collection of propulsion engineering projects I'm building in high school as I work toward an aerospace engineering career focused on propulsion system design.

I'm particularly interested in liquid rocket engine development and hope to contribute to programs at companies like SpaceX or Rocket Lab. These projects are how I close the gap between classroom physics and real engineering practice.

---

*Built by [Truman Heaston](https://github.com/trumanheaston-lab)*
