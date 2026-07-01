# 🚀 Accelerate Strategy – 10-Year Product Board

A single-file, browser-based strategy dashboard for long-term product portfolio planning across multiple product lines and time horizons. Built for product managers who need to map, prioritise, and communicate a multi-year roadmap — without installing anything.

---

## Board structure

Swimlane layout: product lines (rows) × time columns, with four planning horizons:

| Horizon | Columns | Focus |
|---|---|---|
| Short Term | 2026, 2027 | Committed roadmap |
| Mid Term | 2028, 2029, 2030 | Strategic planning |
| Long Term | 2031–33, 2034–35 | Vision direction |
| BU Vision | 2036+ | Moonshots |

- Product lines are reorderable by drag & drop
- Effort and cost summaries per column and product line, updated live
- Editable board name in the header — used as the filename for all exports

---

## Card types

The board supports four distinct tile types, each serving a different purpose.

### 🃏 Project cards
The standard unit of work. Each card carries:
- Title, description, user persona
- Status: Idea / Planned / Active / Done / Blocked — colour-coded stripe on the card
- Effort and cost sizing: XS · S · M · L · XL
- Competition status: 🥇 Pioneer / 🥈 Fast Follower / 🥉 Me-Too (shown as medal next to radars in full view; in the badge row in compact view)
- Strategic Score (0–100) — see [Scoring](#strategic-score) below
- Two mini spider-radars: Customer Benefit (4 dimensions) + 10 Types of Innovation
- Full modal with description, persona, sizing, radars, roadmap, and connections

Cards can be dragged between cells and swapped with each other by dropping one on top of another. Cells with 4+ cards auto-switch to a two-column grid layout.

### 🎯 Strategic Goal cards
A customer pain-point / north-star card. Visually distinct: dark background, circular avatar icon overlapping the left edge.
- **Collapsed:** headline + 2-line description preview. No status or score.
- **Expanded (click):** editable goal title and full description field with "Value Proposition / Description" label.
- Has a connection point at the bottom of the avatar for linking to project cards.
- Excluded from status and score filters; included in text search.

### 📦 Bundles
A named release scope that groups related project cards.
- Drag any project card onto a bundle to add it — the card disappears from the board and is listed inside the bundle.
- The bundle face shows an **aggregated average score** across all contained cards.
- Click to open the management modal: add cards (dropdown), remove (×), reorder (drag with grip handles).
- Opening a card from the bundle modal returns you to the bundle modal after saving.
- Export the full bundle as a print-ready **A4 PNG** directly from the modal.

### 🔲 Sub-boards
A full nested planning board attached to any project card — one level deep.
- Click the grey tab on the **right edge** of any project card to attach a sub-board (confirmation required).
- The tab turns **Getinge Blue** once a sub-board is attached.
- Clicking the active tab opens a side panel showing the sub-board's line and card count, plus an **"Open board →"** button.
- Clicking "Open board →" swaps the entire board into the sub-board. A breadcrumb bar at the top shows the path back.
- Leaving the sub-board auto-saves all changes back into the parent card.
- Sub-board data lives inside the parent card — it exports, imports, duplicates, and merges automatically.

---

## Pre-Study add-on

Each project card can have an optional Pre-Study attached via the orange left tab:
- Own status, effort, cost estimate, and a short note
- Visible at a glance without opening the card modal

---

## Connections

- **Blocking** (Berry red, dashed line): must finish before the target
- **Informational / Related** (Clay grey, solid line)

Activate Connection Mode from the toolbar, then click source → target. Click any line to edit its type or label. Delete individually or all at once via toolbar.

---

## Filters & views

- **Search** by title, description, or user persona — also highlights bundles whose cards match
- **Score filter:** High / Medium / Low chips
- **Status filter:** multi-select per lifecycle state
- **Full view:** all card detail visible (radars, timeline, competition medal, pre-study tab)
- **Compact view:** smaller cards, radars hidden, medal shown in badge row

---

## Save & share

| Action | Result |
|---|---|
| **Export JSON** | Full board state — filename uses the board name |
| **Import JSON** | Restores any saved board |
| **Export PNG (board)** | High-resolution 2× PNG of the full board |
| **Export PNG (card)** | A4-format PNG of a single project card |
| **Export PNG (bundle)** | A4-format PNG listing all cards in a bundle |
| **Chase Merge** | Password-protected merge of a colleague's JSON into the master board |

### Chase Merge rules
1. Existing product lines (same name) → ignored completely, including their cards
2. New product lines → added on top, including all cards, bundles, goals, and sub-boards
3. Connections within new product lines → transferred
4. Cross-line connections → dropped (re-create manually)

---

## Strategic Score

The strategic score (0–100) evaluates value delivered relative to effort and cost required. It rewards focused innovation and clear customer benefit while penalising over-scoped projects.

**Formula (simplified):**

```
Score = ( BenefitAvg × 0.5 + InnovationAvg × 0.5 )^0.72 × 15.81
        ──────────────────────────────────────────────────────────
                    √Effort × 0.5 + Cost × 0.03 + 0.3
```

- Customer Benefit: 4 sliders (0–10). Top 2 count double.
- Innovation: 10 sliders (0–10). Top 4 count double.
- Effort and cost each sized XS–XL; applied non-linearly so large-but-valuable projects aren't over-penalised.

| Level | Range | Meaning |
|---|---|---|
| **High** | ≥ 45 | Strong value relative to effort — prioritise |
| **Medium** | 25–44 | Solid project — review scope or ambition |
| **Low** | < 25 | Low impact or high cost — reconsider |

---

## How to use

Open the HTML file in any modern browser — no server, no install, no dependencies.

1. **New project** — start from the welcome screen, add product lines, create cards
2. **Import** — load any previously exported JSON to restore a board
3. **Demo** — load the built-in demo board to explore all features
4. **Share** — export as JSON and send it alongside the HTML. Recipients import with one click.
5. **Team collaboration** — each person works on their own copy; the Board Owner merges JSONs via Chase Merge.

---

## Tech

Pure HTML, CSS, and vanilla JavaScript. No framework, no build step, no external dependencies except:
- **Google Fonts** (Source Sans 3, loaded from CDN)
- **html2canvas** (loaded from cdnjs, used only for PNG export)

Everything else runs client-side. One file, ~245 KB.

---

## Branding

Built with official Getinge brand colours.  
Built by Daniel Röckl.
