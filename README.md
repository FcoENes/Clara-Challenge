# Clara — Data Analyst Challenge (Conversion Funnel)
By: Francisco Esquivel
## Overview
This project analyzes an e-commerce conversion funnel (Home → Search → Payment → Confirmation) to identify where users drop off and to propose actionable, data-driven recommendations to improve conversion, with a focus on new-user performance.

## Contents
- `Clara_Francisco Esquivel_Challenge.ipynb`: end-to-end analysis with funnel metrics, segment breakdowns, visualizations, findings, and recommendations.
- `data/`: input CSV files provided in the challenge.
- `README.md`: project summary and run instructions.

## Requirements
- Python 3.9+
- pandas, numpy, matplotlib

## How to run
1. Place the provided CSV files inside the `data/` folder.
2. Open `Clara_DA_Challenge_Notebook.ipynb`.
3. Run all cells from top to bottom (Kernel → Restart & Run All).

## Key results (summary)
- Overall conversion (Home→Confirmation) drops sharply after February, falling from ~0.8% in Jan–Feb to ~0.2% in Mar–Apr (≈75% decline), indicating a structural breakpoint rather than a gradual trend.
- The funnel degradation differs by device:
  - **Mobile:** Home→Search conversion drops from ~80% to ~20% starting in March, suggesting an early-funnel UX or technical issue.
  - **Desktop:** Search→Payment conversion drops from ~15–16% to ~4% starting in March, pointing to issues in product selection or routing to payment.
- Payment→Confirmation conversion remains relatively stable, indicating that the main revenue loss occurs upstream in the funnel.

## Recommendations
- Prioritize immediate QA and debugging around the identified funnel transitions (by device), focusing on regressions introduced near the breakpoint period.
- Run device-specific product experiments to reduce friction (search UX on mobile, product click-through and routing to payment on desktop).
- Implement ongoing funnel monitoring segmented by device and time, with alerts on significant conversion deviations from baseline.

## Assumptions / notes
- Funnel metrics are computed using unique users (`user_id`) at each stage.
- The analysis assumes the `date` field in `user_table.csv` can be used for cohorting users over time.

## Final note
This analysis provides a clear, production-ready diagnosis of the funnel degradation,
pinpointing when the issue started, which funnel steps are affected, and how the impact differs by device.

