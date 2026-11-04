# Entro Data Analysis 

Tushar Shandilya · Data & Reporting Lead assignment · November 2026

Power BI dashboard and written notes analysing Entro's proposal pipeline and billing: won value, book-to-burn, proposal volume, win rates and writer performance.

## Files

| File | What it is |
|------|------------|
| `Tushar_Shandilya_Entro_Dashboard.pbix` | Power BI report (principal and writer pages) |
| `Tushar_Shandilya_Entro_Assignment_Notes.pdf` | Answers, assumptions, sensitivity checks and data issues |
| `Entro Take-Home_ Assumptions, Answers and Data Issues.pdf` | Same notes document |
| `Entro Projects Dataset.xlsx` | Source dataset (proposals and invoices) |
| `*.png` | Dashboard backgrounds and logo |

## Headline findings

- **FY26 book-to-burn is 1.01** — $15.41M won vs $15.26M billed, so backlog held flat.
- That rests on one deal: without the $1.63M Airports win (May 2026) FY26 would be **0.90**. Rolling 12-month ratio was below 1.0 every month from Jul 2025 to Apr 2026.
- Counting internal account 9999 as billing drops FY26 to **0.87**; it is excluded as intercompany.
- **FY26 win % is 49.0%**, blending original commissions (32.9%) and additional services (94.4%). Both rose vs FY25; the headline dipped only due to mix.
- Monthly book-to-burn swings 0.26–2.26, so the rolling 12-month line is the recommended headline.

## Answer sheet

| # | Question | Answer |
|---|----------|--------|
| 1 | Won value, June 2026 | $1,487,320 |
| 2 | Book-to-burn, June 2026 | 1.12 |
| 3 | Book-to-burn, FY26 | 1.01 |
| 4 | Proposals submitted, March 2026 | 47 |
| 5 | Win % by count, FY26 | 49.0% |
| 6 | Average proposal value, FY26 | $161,087 (median $75,250) |
| 7 | Writer B, Jan–Jun 2026: proposals submitted | 52 |
| 8 | Writer B, Jan–Jun 2026: win % by count | 39.1% (9 / 23 decided) |
| 9 | Writer B, Jan–Jun 2026: average proposal value | $219,775 |

## Key assumptions

- **A1** — Co-written proposals give full credit to each writer; company totals count each proposal once.
- **A2** — "Submitted" = has a Submitted Date and is not No Go / In Pursuit. Win % = Won / (Won + Lost), submission-month cohort.
- **A3** — Internal account 9999 excluded from billing; credit notes netted.
- **A4** — Work is won on the Decision Date; 15 undated wins ($10.66M) listed separately.
- **A5** — Win % shown only once ≥10 proposals are decided. Monthly refresh.
- Fiscal year runs July–June (FY26 = Jul 2025 – Jun 2026).

## Data model

`Fact_Proposals`, `Fact_Invoices`, a fiscal `Dim_Date` (Jul–Jun), and a writer bridge to `Dim_Writer`. Won Value uses Decision Date and proposal measures use Submitted Date (via `USERELATIONSHIP`); Billed Value uses Invoice Date.

See the notes PDF for the full sensitivity table, data issues and next-step priorities.
