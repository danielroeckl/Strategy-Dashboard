# 🚀 Accelerate Strategy – 10-Year Product Board

A single-file, browser-based strategy dashboard for long-term product portfolio planning across multiple lanes and time horizons. Built for product managers who need to map, prioritise, and communicate a multi-year roadmap — without installing anything.

---

## Board structure

Swimlane layout: **lanes** (rows) × time columns, with four planning horizons:

| Horizon | Columns | Focus |
|---|---|---|
| Short Term | 2026, 2027 | Committed roadmap |
| Mid Term | 2028, 2029, 2030 | Strategic planning |
| Long Term | 2031–33, 2034–35 | Vision direction |
| BU Vision | 2036+ | Moonshots |

- A **lane** is one board row. It can represent a product line, a topic, or a theme — the neutral name keeps it open. New lanes are auto-named "Lane 1", "Lane 2", … and can be renamed inline.
- Lanes are reorderable by drag & drop; titles wrap automatically for long names.
- Effort and cost summaries per column and lane, updated live.
- Editable board name in the header — used as the filename for all exports.

---

## Card types

The board supports four distinct tile types, each serving a different purpose.

### 🃏 Project cards
The standard unit of work. Each card carries:
- Title, description, user persona
- **User Needs** — why we are tackling it (see [User Needs](#user-needs))
- Status: Idea / Planned / Active / Done / Blocked — colour-coded stripe on the card
- Effort and cost sizing: XS · S · M · L · XL
- Competition status: 🥇 Pioneer / 🥈 Fast Follower / 🥉 Me-Too
- Strategic Score (0–100) — see [Scoring](#strategic-score) below
- Two mini spider-radars: Customer Benefit (4 dimensions) + 10 Types of Innovation
- Full modal with description, persona, User Needs, sizing, radars, roadmap, and connections

Cards can be dragged between cells and swapped by dropping one on top of another. Cells with 4+ cards auto-switch to a two-column grid layout.

### 🎯 Strategic Goal cards
A customer pain-point / north-star card. Visually distinct: dark background, circular avatar icon.
- **Collapsed:** headline + 2-line description preview. No status or score.
- **Expanded (click):** editable goal title and full description field.
- Has a connection point for linking to project cards, bundles, and goals.
- Excluded from status and score filters; included in title search.

### 📦 Bundles
A named release scope that groups related project cards.
- Drag any project card onto a bundle to add it — the card moves inside the bundle.
- The bundle face shows an **effort-weighted strategic quality score** — see [Bundle Score](#bundle-score).
- Click to open the management modal: add cards, remove (×), reorder (drag handles).
- Export the full bundle as a print-ready **A4 PNG** directly from the modal.
- Bundles respond to the User Needs filter: a bundle stays visible when at least one contained card matches the active filter.

### 🔲 Sub-boards
A full nested planning board attached to any project card — one level deep.
- Click the **grey tab on the right edge** of any project card to attach a sub-board.
- The tab turns **Getinge Blue** once attached; the side panel offers an **"Open board →"** button.
- A breadcrumb bar shows the path back to the parent.
- Sub-board data lives inside the parent card — it exports, imports, duplicates, and merges automatically.

---

## User Needs

User Needs answer **why** we tackle an initiative — the purpose it serves. This is deliberately separate from **Customer Benefit** (Revenue, Cost savings, Convenience, Clinical benefit), which measures **how strongly** it pays off and feeds the strategic score. Purpose vs. impact — two different lenses.

Eight categories (short filter label in brackets):

| Category | Covers |
|---|---|
| Clinical Value *(Clinical)* | Outcomes, clinical confidence, diagnostic accuracy, decision support, early detection |
| Patient Safety *(Safety)* | Error prevention, alarming, guideline adherence, risk reduction, therapy safety |
| Workflow & Usability *(Workflow)* | Workflow efficiency, ease of use, time savings, automation, documentation |
| Connectivity *(Connectivity)* | EMR/PDMS/HIS integration, device connectivity, data exchange, remote access |
| Economic Value *(Economic)* | Cost savings, total cost of ownership, resource utilisation, length-of-stay reduction |
| Compliance & Trust *(Compliance)* | MDR/FDA compliance, cybersecurity, data privacy, reliability, auditability |
| Operational Excellence *(Operations)* | Serviceability, installation, fleet management, remote service, scalability |
| Evidence & Innovation *(Evidence)* | Clinical evidence, health economics, AI support, research, data analytics |

- Assigned per card in the card modal (multi-select chips); shown as neutral tags on the card face in both Full and Compact view.
- An info (i) button in the card modal explains each category's sub-topics.
- Categories are neutral grey — no colour — so they don't clash with status and score signals.

---

## Pre-Study add-on

Each project card can have an optional Pre-Study attached via the **orange left tab**: own status, effort, cost estimate, and a short note — visible without opening the card modal.

---

## Connections

- **Blocking** (Berry red, dashed line): must finish before the target.
- **Informational / Related** (Clay grey, solid line).
- **Directional arrowheads** point toward the dependent card; arrow colour matches the line state (blocking, related, or the active Focus / Critical-path highlight).

Activate connection mode from the toolbar. A step banner guides you: click the **source** dot, then the **target** dot. Click any line to edit its type or label. Connections can be drawn to and from any card type.

### Focus mode & Critical path
- **Focus mode:** click a card to see only its direct dependencies; everything else dims.
- **Critical path:** click a card to trace the longest dependency chain leading to it.
- **Hover highlight:** hovering a card outlines its connected neighbours and dims the rest.
- **Hide connections:** toggle all lines off for clean screenshots.

---

## Filters & views

The filter bar follows a deliberate priority order: **Score → User Needs → Status**.

- **Search** — matches card titles only.
- **Score:** High / Medium / Low.
- **User Needs:** the 8 categories, multi-select — combine several to see any card matching one of them.
- **Status:** multi-select per lifecycle state.
- **Master toggle (Filters):** *All on* resets everything to visible; *All off* hides everything so you can reveal the board layer by layer (e.g. first High score, then one User Need, then a status).
- **View:** Full / Compact segmented toggle.

All three filter groups share the same model — every chip active means everything is visible — so the master toggle behaves consistently across them.

### Toolbar hierarchy
The **Add to board** group leads with **New lane** (the entry point), followed by New project card, New bundle, and New strategic goal — all in one unified dark-navy button style. Connections and Save & Load use a quieter grey style so the primary "add" actions stand out.

---

## Save & share

| Action | Result |
|---|---|
| **Export JSON** | Full board state including all sub-boards and User Needs — filename uses the board name |
| **Import JSON** | Restores any saved board including all sub-board data |
| **Export PNG (board)** | High-resolution 2× PNG; in a sub-board the filename is `[card-name]-subboard.png` |
| **Export PNG (card)** | A4-format PNG of a single project card |
| **Export PNG (bundle)** | A4-format PNG listing all contained cards with scores |
| **Chase Merge** | Password-protected merge of a colleague's JSON into the current board |

### Chase Merge rules
1. Existing lanes (same name) → ignored completely, including their cards.
2. New lanes → added, including all cards, bundles, goals, and sub-boards.
3. Connections within new lanes → transferred.
4. Cross-line connections → dropped (re-create manually).

---

## Strategic Score

The strategic score (0–100) evaluates value delivered relative to effort and cost required. It rewards focused innovation and clear customer benefit while penalising over-scoped projects.

**Formula:**

```
Quality  =  BenefitAvg × 0.5  +  InnovationAvg × 0.5

Score    =       Quality ^ 0.72  ×  15.81
          ─────────────────────────────────────────
            √Effort × 0.5  +  Cost × 0.03  +  0.3
```

- **Customer Benefit:** 4 sliders (0–10). Top 2 count double.
- **Innovation:** 10 sliders (0–10). Top 4 count double.
- **Effort / Cost:** sized XS–XL, applied via a non-linear divisor.

| Level | Range | Meaning |
|---|---|---|
| **High** | ≥ 45 | Strong value relative to effort — prioritise |
| **Medium** | 25–44 | Solid project — review scope or ambition |
| **Low** | < 25 | Low impact or high cost — reconsider |

---

## Bundle Score

The bundle score (0–100) reflects the collective strategic quality of a release scope, weighted so that larger projects have more influence — without penalising them twice for their size.

**Formula:**

```
Quality_i  =  BenefitAvg_i × 0.5  +  InnovationAvg_i × 0.5   (0–10, no effort penalty)

Weight_i   =  Effort weight of card i   (XS=1 · S=2 · M=3 · L=4 · XL=5)

BundleScore  =  Σ( Quality_i × Weight_i )  ×  10
                ─────────────────────────────────
                         Σ( Weight_i )
```

Larger projects (XL) count five times as much as the smallest (XS); a strong XL contributes fully on content, not reduced by its size. Score is colour-coded using the same High / Medium / Low thresholds as individual cards.

---

## How to use

Open the HTML file in any modern browser — no server, no install, no dependencies to set up.

1. **New project** — start from the welcome screen, add lanes, create cards.
2. **Import** — load any previously exported JSON to restore a board including all sub-boards.
3. **Demo** — load the built-in demo board to explore all four card types and the sub-board feature.
4. **Share** — export as JSON and send it alongside the HTML. Recipients import with one click.
5. **Team collaboration** — each person works on their own copy; the Board Owner merges JSONs via Chase Merge.

---

## Tech

Pure HTML, CSS, and vanilla JavaScript. No framework, no build step, no external dependencies except:
- **Google Fonts** (Source Sans 3, loaded from CDN)
- **html2canvas** (loaded from cdnjs, used only for PNG export)

Everything else runs client-side. One file.

---

## Branding

Built with official Getinge brand colours.  
Built by Daniel Röckl.
