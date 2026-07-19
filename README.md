# Sales Funnel Analysis

Synthetic B2B sales-funnel dataset (10,000 leads) generated in Python, analyzed with Excel pivot tables, and visualized in Tableau.

## Workflow

| Step | Tool | Artifact |
|------|------|----------|
| Data generation | Python (`pandas`, `faker`) | [`Generate_Funnel_Data.ipynb`](Generate_Funnel_Data.ipynb) → `sales_funnel_data.xlsx` |
| KPI analysis | Excel pivot tables | `Sales_Funnel_Data_Cleaned.xlsx` (Analysis sheet) |
| Dashboard | Tableau | `Sales Funnel Dash.twb` |

Each lead gets a source, industry, and signup date, then moves through a six-stage funnel (Awareness → Interest → Consideration → Demo → Proposal → Closed) with a 75% chance of progressing at each stage; leads reaching Closed convert 60% of the time with revenue of $200–$2,000.

## Key findings

- **Overall conversion: 13.9%** — 1,393 of 10,000 leads closed and converted, generating **$1.53M total revenue** at an **average deal size of $1,101**.
- **The biggest funnel drop-off is at the top**: 25.4% of leads (2,535) never move past Awareness — the largest single loss in the funnel. Of leads that reach Closed, 60% convert, so late-stage execution is not the bottleneck.
- **Email Campaign is the strongest lead source** on both conversion rate (15.2%, vs. 13.3% for the weakest sources, Referral and Direct) and revenue ($344K — 14% ahead of the next source).
- **Revenue is evenly spread across industries** ($292K–$318K), with Finance on top — no industry concentration in this dataset.

| Funnel stage reached | Leads | % of total |
|----------------------|-------|-----------|
| Awareness | 10,000 | 100% |
| Interest | 7,465 | 75% |
| Consideration | 5,621 | 56% |
| Demo | 4,256 | 43% |
| Proposal | 3,131 | 31% |
| Closed | 2,318 | 23% |

*(Since the data is synthetic, these findings validate the generation logic and demonstrate the analysis workflow rather than real market behavior.)*

<!-- TODO: export the Tableau dashboard as an image (Dashboard > Export Image) and embed it here:
![Sales funnel dashboard](images/dashboard.png)
-->

## Reproducing

1. `pip install -r requirements.txt`
2. Run `Generate_Funnel_Data.ipynb` (note: no fixed random seed, so regenerated data will differ from the committed `sales_funnel_data.xlsx`).
