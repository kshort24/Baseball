# Philadelphia Phillies — Statcast Analysis

I've been pulling pitch-level data from Baseball Savant and turning it into Phillies analysis since 2023. This repo is where that work lives — part running journal, part scouting notebook, part data infrastructure.

I am a passionate fan of the Philadelphia Phillies. My professional background is in data. This is the intersection of my personal and professional interests. Following them closely through data is how I engage with the game — and this is what that looks like.

---

## How the Notebooks Work

Most of the work here is organized by month. Each monthly notebook covers what happened on the field and what the numbers say about it — pitch mix shifts, a starter who's losing a tick off the fastball, a reliever who found his slider, a stretch where the lineup went cold against same-handed arms. I try to answer the questions I actually have while watching games, not just report the box score in chart form.

Beyond the monthlies, there are deeper dives when something specific earns one:

- When Gage Wood showed up in Clearwater throwing a curveball that looked like it belonged three levels higher, I pulled his minor league Statcast data and compared the pitch shape against every right-handed MLB curve in the dataset. That's what the **Gage Wood Comps** notebook is.
- Before the Rockies series in May 2026 I put together a full opponent breakdown — their tendencies against left/right-handers, where they hit the ball, what the Phillies bullpen matchups looked like. That's the **Phillies vs. Rockies Preview**.
- The **2023 Playoffs** notebook goes deep on the NLCS run against Arizona — how the Phillies approached their pitching, what the Diamondbacks did well, and what actually broke the series open.

There's also a full function library (`baseball_functions.py`) that handles all the Statcast math — wOBA, whiff rates, pitch movement — so each notebook stays focused on the analysis, not the plumbing.

---

## What's In Here

### Season Journals

| Season | Notebooks |
|---|---|
| 2023 | Full season analysis, NLDS/NLCS playoff breakdown |
| 2024 | March/April through October + AI-assisted season review |
| 2025 | March through December — complete |
| 2026 | January onward — updated as the season goes |

### Scouting & Feature Work

- **Gage Wood Comps** — Minor league pitch shape analysis for a 2026 Phillies pitching prospect
- **Phillies vs. Rockies May 2026 Preview** — Series opponent breakdown
- **Phillies Spring Training 2025** — Early camp pitch data from the spring roster
- **Phillies Offseason 2024 / Offseason Videos 2024-25** — Acquisition analysis and video review
- **Bullpen Functions** — Dedicated bullpen tracking
- **2024 Season Preview** — Preseason outlook using multi-year trends

### Infrastructure

- **Baseball Functions** — The core function library. Everything else runs off this.
- **mlb_data.py** — Data loading utilities

---

## The Data

Everything runs off [Baseball Savant](https://baseballsavant.mlb.com/) Statcast exports — pitch-level data going back to 2015 for the Phillies, plus targeted pulls on opponents and prospects. Raw data files aren't committed here (they're large), but the notebooks document what I'm looking at and why.

---

## AI Collaboration

Through 2023 and most of 2024 the work here was entirely my own Python and my own analysis. In late summer 2024 I started using ChatGPT — some code in the 2024 notebooks came from it, though the questions being asked, the data choices, and what the outputs mean have always been mine.

In 2026 I started using Claude more heavily, and the collaboration got more sophisticated. Rather than one-off code help, I've been building custom agents and skills tuned specifically to this work. The `.claude/` directory in this repo is published on purpose — it's part of the project:

- **`phillies-analyst` agent** — a domain-tuned assistant that understands the Statcast data layer, the standard Phillies metrics I track, and how the notebooks are structured, the goal is for this agent to be able to reproduce my style of analysis in my voice in the future
- **`graph-builder` agent** — handles visualization requests with awareness of what the data looks like
- **`phillies-pitchmix-analysis` skill** — a structured workflow for pitch mix scouting, including scripts and reference material
- **`wheeler-scouting-report` skill** — a repeatable scouting report workflow built around Zack Wheeler specifically

The notebooks are still primarily driven by what I want to know while watching games. The AI gets me to answers faster and handles more of the mechanical work. The curiosity is mine.

---

## Tools

Python · pandas · Plotly · Jupyter · Claude
