🚀 Accelerate Strategy – 10-Year Product Board

A single-file, browser-based strategy dashboard for long-term product portfolio planning across multiple product lines and time horizons. Built for product managers who need to map, prioritize, and communicate a multi-year roadmap — without installing anything.

What it does

Board structure
Swimlane board: product lines (rows) × time columns
8 year-based columns with decreasing granularity: 2026 · 2027 · 2028 · 2029 · 2030 · 2031–33 · 2034–35 · 2036+
Grouped under four horizons: Short Term / Mid Term / Long Term / BU Vision
Product lines can be reordered by drag & drop
Effort summaries per column and product line, updated live


Project cards
Title, status (Idea / Planned / Active / Done / Blocked), effort and cost sizing (XS–XL)
Strategic Score (0–100): calculated from benefit and innovation ratings vs. effort and cost
Two mini spider-radars per card: Customer Benefit (4 dimensions) + 10 Types of Innovation
Full detail view in modal: project description, user persona, sizing, radars, roadmap, connections


Pre-Study add-on
Each card can have an optional Pre-Study attached (orange left tab)
Pre-Study has its own status, effort, cost, and a short note
Visible at a glance on the board without opening the card


Project Roadmap
Milestones per project with quarter + year
Grouped by quarter in the modal, sorted chronologically


Connections
Blocking connections (Berry red, dashed) and informational/related connections (Clay gray)
Draw connections by clicking the dot on any card
Labels on connection lines, editable by clicking the line
Delete individual connections or all at once


Filters
Search by name, status, and strategic score level (High / Medium / Low)
All filters combinable; filtered cards including Pre-Study tabs disappear cleanly


Views
Full view (with radars) and compact view (smaller cards, no radars)


Save & share
Export full board state as JSON (cards, positions, connections, product lines)
Import JSON to restore any saved state
No server needed — share the JSON file alongside the HTML


Strategic Score
Score = (Customer Benefit avg × 0.5 + Innovation avg × 0.5) × 10 ÷ ((Effort weight + Cost weight) / 2)
High (≥ 60, green): high value relative to effort — prioritize
Medium (30–59, yellow): review effort/cost or increase ambition
Low (< 30, gray): low value or high cost — deprioritize or revisit scope
Effort/cost weights: XS = 1 · S = 2 · M = 3 · L = 4 · XL = 5

How to use
Open index.html in any modern browser — no server, no install, no dependencies.
To share a saved state, export as JSON and send it alongside the HTML file. Recipients import it with one click.

Example data
The board loads with a Closed Loop Patient Monitoring example showing:
Clear the example by deleting the product line and starting fresh.

Tech
Pure HTML, CSS, and vanilla JavaScript. No frameworks, no build step, no external dependencies (except Google Fonts for Source Sans 3 as fallback for Adelle Sans). Everything runs client-side. One file, ~130 KB.

Branding
Built with official Getinge brand colors 

Built by Daniel Röckl 
