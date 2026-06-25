🚀 Accelerate Strategy – 10-Year Product Board

A single-file, browser-based strategy dashboard for long-term product portfolio planning across multiple product lines and time horizons. Built for product managers who need to map, prioritize, and communicate a multi-year roadmap — without installing anything.

### What it does

### Board structure
Swimlane board: product lines (rows) × time columns
8 year-based columns with decreasing granularity: 2026 · 2027 · 2028 · 2029 · 2030 · 2031–33 · 2034–35 · 2036+
Grouped under four horizons: Short Term / Mid Term / Long Term / BU Vision
Product lines can be reordered by drag & drop
Effort summaries per column and product line, updated live


### Project cards
Title, status (Idea / Planned / Active / Done / Blocked), effort and cost sizing (XS–XL)
Strategic Score (0–100): calculated from benefit and innovation ratings vs. effort and cost
Two mini spider-radars per card: Customer Benefit (4 dimensions) + 10 Types of Innovation
Full detail view in modal: project description, user persona, sizing, radars, roadmap, connections


### Pre-Study add-on
Each card can have an optional Pre-Study attached (orange left tab)
Pre-Study has its own status, effort, cost, and a short note
Visible at a glance on the board without opening the card


### Project Roadmap
Milestones per project with quarter + year
Grouped by quarter in the modal, sorted chronologically


### Connections
Blocking connections (Berry red, dashed) and informational/related connections (Clay gray)
Draw connections by clicking the dot on any card
Labels on connection lines, editable by clicking the line
Delete individual connections or all at once


### Filters
Search by name, status, and strategic score level (High / Medium / Low)
All filters combinable; filtered cards including Pre-Study tabs disappear cleanly


### Views
Full view (with radars) and compact view (smaller cards, no radars)


### Save & share
Export full board state as JSON (cards, positions, connections, product lines)
Import JSON to restore any saved state
No server needed — share the JSON file alongside the HTML


### Strategic Score
The strategic score (0–100) evaluates how much value a project delivers relative to the effort and cost required. It is designed to reward focused innovation and clear customer benefit, while accounting for realistic project sizing.

### How it is calculated
**Step 1 — Customer Benefit (weighted average)**
The four benefit dimensions are rated 0–10. The top two scores count double, the other two count once. This rewards projects with one or two genuinely strong customer benefits rather than mediocre scores across all dimensions.
```
Benefit avg = (top1×2 + top2×2 + 3rd + 4th) / 6
```
**Step 2 — Innovation Score (weighted average)**
All ten innovation types are rated 0–10. The top four scores count double, the remaining six count once. Based on research showing that highly innovative companies (e.g. Apple) typically excel in 3–4 innovation types — not all ten simultaneously. Every additional strong innovation type still raises the score, but with diminishing returns.
```
Innovation avg = (top1×2 + top2×2 + top3×2 + top4×2 + 5th + 6th + 7th + 8th + 9th + 10th) / 14
```
**Step 3 — Combined value**
```
Combined = Benefit avg × 0.5 + Innovation avg × 0.5
```
**Step 4 — Effort and cost adjustment**
Effort (team capacity) is the primary constraint and is penalised more strongly than cost. A non-linear (square root) function ensures that large projects are not disproportionately disadvantaged — a genuine L project with strong impact can still score well.
```
Divisor = √Effort weight × 0.5 + Cost weight × 0.03 + 0.3
```
Effort and cost weights: XS = 1 · S = 2 · M = 3 · L = 4 · XL = 5

**Step 5 — Final score**
```
Score = Combined^0.72 × 15.81 / Divisor   (capped at 100)
```
The exponent 0.72 compresses the upper range and stretches the middle — giving more differentiation between medium-quality projects, which is where most real planning decisions happen.
### Score levels
| Level | Range | Meaning |
|-------|-------|---------|
| **High** | ≥ 45 | Strong value relative to effort — prioritise |
| **Medium** | 25–44 | Solid project — review scope or ambition |
| **Low** | < 25 | Low impact or high cost — reconsider |

### Reference points
| Scenario | Score |
|----------|-------|
| XS/XS effort+cost, all dimensions maxed | 100 |
| S/S, all dimensions maxed | 78 |
| M/M (standard), all dimensions maxed | 66 |
| M/M, 2 strong benefits + 4 strong innovations | ~47 |
| M/M, 2 strong benefits + 3 strong innovations | ~43 |
| L/L, all dimensions maxed | 58 |
| XL/XL, all dimensions maxed | 53 |

### How to use Dashboard
Open index.html in any modern browser — no server, no install, no dependencies.
To share a saved state, export as JSON and send it alongside the HTML file. Recipients import it with one click.

### Example data
The board loads with a Closed Loop Patient Monitoring example showing:
Clear the example by deleting the product line and starting fresh.

### Tech
Pure HTML, CSS, and vanilla JavaScript. No frameworks, no build step, no external dependencies (except Google Fonts for Source Sans 3 as fallback for Adelle Sans). Everything runs client-side. One file, ~130 KB.

### Branding
Built with official Getinge brand colors 

Built by Daniel Röckl 
