# 70% by 2030: Sri Lanka's Renewable Electricity Reality Check

An evidence-led Streamlit investigation of whether Sri Lanka can reach 70% renewable electricity generation by 2030. It separates historical actuals, regulator quarterly evidence, CEB planning scenarios, project development stages, approvals, applications, storage and grid constraints.

## Run locally

1. Install Python 3.10 or later.
2. Open a terminal in this folder.
3. Create and activate a virtual environment (recommended).
4. Install dependencies and launch:

```bash
python -m venv .venv
# Windows PowerShell: .venv\\Scripts\\Activate.ps1
# macOS/Linux: source .venv/bin/activate
pip install -r requirements.txt
streamlit run app.py
```

## Dashboard pages

1. **The verdict** — direct answer, historical actuals, CEB 2030 scenario and the narrow scenario cushion.
2. **Generation reality** — historical generation and capacity by source.
3. **The 2026 pulse** — PUCSL Q2 2026 generation comparisons and June 2026 renewable capacity snapshot.
4. **The 2030 maths** — adjustable demand denominator, target and renewable delivery-rate sensitivity.
5. **Project delivery tracker** — all 27 rows in `Project_Tables.xlsx`, source-stage labels, selected independently verified updates and separate additional commissioned projects.
6. **Approvals & applications** — approved projects, PPA approval records, applications and historical CEB tender/installed-capacity snapshots.
7. **Grid readiness** — storage, curtailment, planned additions and demand peaks.
8. **Sources & methodology** — source register, calculations and limitations.

## Included datasets

- `data/Sri_Lanka_Electricity_Actuals_and_CEB_Plan_Combined.xlsx`
- `data/Project_Tables.xlsx`
- `data/Project_and_PPA_Approvals.xlsx`
- `data/Renewable_Energy_Applications.xlsx`
- `data/CEB_NCRE_and_Installed_Capacity_v3.xlsx`
- `data/ceb new.xlsx`
- `evidence/PUCSL_Q2_2026_generation.csv`
- `evidence/PUCSL_H1_2026_renewables.csv`
- `evidence/PUCSL_2026_installed_capacity.csv`
- `evidence/CEB_Aug2024_pipeline_snapshot.csv`
- `evidence/CEB_Nov2024_installed_capacity.csv`
- `evidence/project_updates.csv`
- `evidence/source_register.csv`

## Key findings built into the dashboard

- PUCSL Annual Report 2025 reports net generation of 18,054 GWh, of which 10,966 GWh was renewable (60.7%). The supplied historical workbook's recorded-generation basis gives 60.2% for 2025. The two bases are not merged.
- CEB's 2030 average renewable generation scenario is approximately 16,560 GWh and its scenario total generation is 22,997 GWh (about 72.0%). CEB's demand forecast separately lists 22,927 GWh net generation; using that denominator yields about 72.2%.
- On 22,927 GWh net generation, 70% requires about 16,049 GWh renewable generation. The CEB average renewable output has only about 511 GWh of headroom (roughly 3.2% above the target requirement), assuming the denominator is fixed.
- PUCSL's Q2 2026 report shows renewable generation of 2,485.9 GWh, 16.2% below Q2 2025. Major hydro fell 37%; mini-hydro fell 25%; rooftop solar rose 42%; IPP solar rose 124%.
- The PUCSL Q2 2026 report contains an apparent inconsistency between the Q1-vs-Q2 chart and its accompanying sentence (and the Q1 technology table does not reconcile to the chart total). The dashboard flags this and does not use the disputed quarter-on-quarter comparison.
- The 27-project register totals 2,756 MW. This is a project list, not committed or commissioned capacity. The latest WindForce interim statement reports Rividhanavi/Siyabalanduwa commissioning in August 2027, later than the 2026 expected year in the original project workbook.
- Approval, PPA and application registers may overlap with the 27-project pipeline. Their capacities are not summed together.
- BESS is shown in MW and MWh separately and is not counted as renewable generation capacity.

## Important limitations

- This is an analytical dashboard, not an official government assessment or a dispatch model.
- Project updates are a limited set of recent, source-linked milestones. Projects without an update are not assumed inactive; their latest progress was not independently verified in this build.
- The source table groupings in `Project_Tables.xlsx` are preserved as source labels. They are not current status confirmations for every project.
- The application file contains application records but no subsequent regulatory outcomes. Diya Janani is separately reported commissioned; reconcile its identity by licence/application number before deduplicating.
- The CEB NCRE workbook includes historical snapshots dated August and November 2024. They are not live data.
- The `ceb new.xlsx` division-by-year numeric series has no clear unit/metric label in the supplied workbook and is intentionally not used as a named metric.
- Update the CSV files in `evidence/` as new official data and project disclosures become available. Evidence dates and source links should be maintained.

## Core interpretation

**Sri Lanka can technically reach 70% under the CEB average planning scenario, but the target is not yet securely on track.** The result depends on timely project commissioning, adequate renewable output, hydro conditions, grid transmission, storage, system flexibility and demand growth. The modelled generation margin is narrow enough that delivery slippage can matter.
