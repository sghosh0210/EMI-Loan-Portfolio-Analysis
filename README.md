# EMI Loan Portfolio — Delinquency & Default Risk Analytics

A finance-domain data analytics portfolio project built on a 116,058-row EMI (Equated Monthly Installment) loan dataset. It reverse-engineers a real-world business context from a raw, undocumented file, then delivers cleaning, EDA, and an interactive Power BI dashboard on top of it.

## Why this project stands out
The dataset arrived with **no data dictionary and no business requirements** — exactly like many real analyst jobs. This project demonstrates the full workflow: inferring business meaning from data patterns, documenting assumptions transparently, cleaning with a rationale, and translating findings into a stakeholder-ready BI tool.

## Project Structure
```
project/
├── README.md                          <- you are here
├── data/
│   ├── EMI_raw.csv                    <- original source file
│   └── EMI_cleaned.csv                <- cleaned, feature-engineered, BI-ready dataset
├── docs/
│   ├── Business_Requirements_Document.docx   <- BRD: objectives, stakeholders, business questions, scope
│   ├── Data_Dictionary.xlsx                  <- column definitions + assumptions log
│   └── PowerBI_Build_Guide.docx               <- data model, DAX measures, page-by-page layout
├── charts/                            <- exported EDA chart images (01-07)
└── EDA_Data_Cleaning.ipynb            <- full data cleaning + EDA notebook (executed, with outputs)
```

## Suggested read order
1. **Business_Requirements_Document.docx** — the "why": business problem, stakeholders, 8 key questions the analysis answers.
2. **Data_Dictionary.xlsx** — the "what": every column explained, plus an Assumptions Log documenting how ambiguous fields were interpreted.
3. **EDA_Data_Cleaning.ipynb** — the "how": data quality issues found, cleaning steps with rationale, and EDA answering each business question with charts.
4. **PowerBI_Build_Guide.docx** — build the dashboard: star schema, DAX measures, and a 5-page layout (Portfolio Overview, Risk Drivers, Originator Scorecard, Delinquency & Early Warning, Loan Detail).

## Key findings (see notebook for full detail)
- Default risk rises sharply as credit score drops and DTI/LTV increase — classic credit-risk behavior.
- Delinquency builds progressively over the 12-month performance window rather than appearing immediately, supporting an early-warning monitoring dashboard page.
- A small subset of originators contribute a disproportionate share of defaults relative to their loan volume.
- `candidate_id` was found to be an unreliable, non-unique key — a data quality issue documented rather than silently ignored.

## How to build the Power BI dashboard
1. Open Power BI Desktop → Get Data → `data/EMI_cleaned.csv`.
2. Follow `PowerBI_Build_Guide.docx` for the star-schema dimension tables, DAX measures, and page layouts.
3. Publish to Power BI Service or export as `.pbix` for your portfolio.

## Tech stack
Python (pandas, matplotlib, seaborn) for cleaning/EDA · Excel for documentation · Power BI for the dashboard.
