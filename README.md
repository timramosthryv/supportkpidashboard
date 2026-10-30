# Support KPI Scorecard · TSS & Keap

One dashboard for the Q4 agent KPI: Productivity (33.3%), QA (33.3%) and CSAT (33.3%).

## Setup on GitHub Pages

1. Create a new repo (for example `cs-agent-kpi`).
2. Add these files:
   - `index.html`, from this folder
   - `thryv-logo.png`, copied from one of your existing dashboard repos
   - a `data` folder for the CSAT and roster files (see below)
3. Turn on GitHub Pages: Settings > Pages > Deploy from branch `main`, root folder.

## Where each pillar gets its data

| Source | Location | Who maintains it |
|---|---|---|
| TSS Agent Time | `tss-agent-time/data` (read live) | Same daily 8x8 uploads you do today |
| Thryv Support QA | `thryv-support-evaluations/evals.csv` (read live) | Same as today |
| Keap Support QA | `keap-support-qa-evaluations/evals.csv` (read live) | Same as today |
| Intercom CSAT | `data/intercom.csv` in this repo | Export from the Intercom report drill-in |
| Qualtrics | `data/qualtrics.csv` in this repo | Qualtrics response export |
| Roster | `data/roster.csv` in this repo | Built from the template on the Data & Settings tab |

Excel files work too. Save them under the names above.

## Roster columns

`Agent, Brand, Coach, Location, Training End, Aliases`

- **Agent:** the full name exactly as it appears in 8x8.
- **Aliases:** every other spelling, separated by `;`. For example: `George C; George Castro`.

The roster takes priority over everything the dashboard works out automatically.

## Changing targets or sources

Open `index.html` and edit the `CONFIG` block near the top of the script. When the data moves to SharePoint, update the URLs in `CONFIG.sources`; nothing else in the page needs to change.
