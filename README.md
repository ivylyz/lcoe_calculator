# Onshore Wind & Solar vs Nuclear LCOE Comparison

A Python tool comparing the Levelised Cost of Energy (LCOE) of UK energy onshore wind and solar against nuclear, using published government data.

## Why I built this
Having already gained research experience in the nuclear energy industry, I wanted to explore its economic side. I built this tool to compare nuclear against onshore wind and solar - the UK's two largest renewable sources - to see whether levelised cost is a contributing factor to their dominance.

## What it does
- Loads onshore wind and solar LCOE cost components (pre-development, construction, fixed O&M, variable O&M) for projects commissioning in 2025, 2030, 2035 and 2040
- Compares both against nuclear's Hinkley Point C Contract for Difference strike price, used as a proxy given no comparable modelled nuclear LCOE is publically available
- Plots all three as a chart, showing wind and solar's cost trends over time against nuclear's fixed reference cost

## Output
<img width="792" height="596" alt="image" src="https://github.com/user-attachments/assets/27126a47-b66f-42fb-9542-ca61cc7d83df" />

## Methodology
Levelised Cost of Energy (LCOE) represents the average cost per MWh of electricity generated over plant's lifetime, including construction, operating, and fuel costs. Onshore wind and solar figures are DESNZ's own published, already-levelised cost estimates, broken down by component. No equivalent modelled LCOE is publicly available for nuclear due to commercial confidentiality, so Hinkley Point C's Contract for Difference strike price (£92.50/MWh, 2012 prices) is used as a proxy. Strike prices and LCOE are not directly equivalent — strike prices reflect additional market and revenue considerations not captured in levelised cost — so this comparison should be read as illustrative rather than a precise like-for-like.

## Findings
Onshore wind and solar both remain well below nuclear's strike price across the entire 2025–2040 period. Onshore wind falls from £39/MWh in 2025 to £36/MWh from 2030 onward, while solar falls more steadily, from £41/MWh in 2025 to £30/MWh by 2040 — overtaking wind as the cheaper option by 2035. Nuclear remains fixed at £92.50/MWh throughout, roughly 2.5x the cost of either renewable. This supports the hypothesis that cost is a significant factor behind wind and solar's growth as the UK's leading renewable energy sources.
This comparison has an important limitation: LCOE only measures cost, not reliability. Wind and solar are intermittent generators, while nuclear provides consistent baseload power — a lower LCOE does not mean either renewable can simply substitute for nuclear's role in the grid. A fuller comparison would need to account for the cost of backup capacity or storage needed to manage intermittency, which is outside the scope of this project.

## Data sources
- DESNZ, *Electricity Generation Costs 2023*, Tables 10, 12, 14 and 16 (Onshore Wind & Large-Scale Solar, 2025–2040, 2021 real prices). https://www.gov.uk/government/publications/electricity-generation-costs-2023
- Hinkley Point C CfD strike price (£92.50/MWh, 2012 prices), UK Government Contracts for Difference records.

## Limitations
- Summing individual cost components for 2025 onshore wind gives £39/MWh,£1 above DESNZ's published total of £38/MWh, due to rounding in the source table.
- Nuclear is represented by a single fixed value rather than a modelled projection, since no comparable time series is publicly available.
- Strike prices and LCOE are conceptually different metrics; this comparison is illustrative, not a precise economic equivalence.
- LCOE does not account for intermittency, dispatchability, or the system costs of integrating variable renewable generation.

## Possible extensions
- Include CCGT (gas) for a fuller generation-mix comparison
- Adjust Hinkley's strike price to 2021 prices for closer alignment with the DESNZ figures, which are already in 2021 real prices

## Usage
pip install -r requirements.txt
python lcoe_calculator.py
