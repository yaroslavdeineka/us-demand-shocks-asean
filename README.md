# US Demand Shocks & ASEAN Industrial Production

Panel data analysis examining how demand shocks originating in the United States 
transmit to industrial production across four ASEAN economies — and why some 
economies are far more exposed than others.

> MSc Data Analysis individual project · Anglia Ruskin University

## Research Questions
1. How sensitive is each ASEAN economy's industrial production to shifts in US import demand?
2. Does a country's trade openness amplify the transmission of US demand shocks?

## Data
- **912 country-month observations** — four economies (Singapore, Malaysia, Thailand, Philippines) over 1999–2017
- Key variables: industrial production (constant prices, seasonally adjusted), US imports (proxy for US external demand), exports as % of GDP (trade openness), exchange rate vs USD, CPI, GDP per capita (PPP)
- Source data merged from national statistics / IMF series into a single panel (`df_merged.csv`)

## Methodology
- Feature engineering: year-on-year growth rates (12-month % change) for IP and US demand
- Descriptive statistics and distribution profiling by country
- 12-month rolling correlations between US demand and domestic production
- Per-country OLS regressions estimating each economy's sensitivity (β) to US demand
- Split-sample regression: high-dependency vs low-dependency economies, with macro controls (CPI, exchange rate)
- Volatility regression testing whether trade openness raises macroeconomic instability
- Cross-country analysis linking trade openness to US-demand sensitivity
- **Tools:** Python — pandas, NumPy, statsmodels (OLS), SciPy, matplotlib, seaborn

## Key Findings
- **US demand transmits significantly to all four economies** (all correlations significant at p < 0.001, N = 216 each). Malaysia is most correlated (r = 0.69), followed by Singapore (0.54), Thailand (0.46) and the Philippines (0.40).
- **Trade openness is the dominant amplifier.** Across countries, average exports/GDP almost perfectly predicts sensitivity to US demand (r = 0.98).
- **High-dependency economies are ~3× more exposed.** In a controlled split-sample model, Singapore and Malaysia are ~203% more sensitive to US demand than the Philippines and Thailand (β = 0.044 vs 0.014; model R² = 0.96 vs 0.71).
- **Trade openness raises volatility, it doesn't cushion it.** Exports/GDP has a positive, highly significant effect on macroeconomic volatility (p < 0.001), rejecting the hypothesis that trade integration smooths external shocks.

## Repository Structure
- `notebooks/main_analysis.ipynb` — full analysis pipeline (descriptives → regressions → charts)
- `notebooks/interaction_model.ipynb` — regression with trade-openness interaction term
- `notebooks/revised_figures.ipynb` — descriptive figures aligned to regression (levels)
- `outputs/` — generated charts
- `data/` — panel dataset

## Author
**Yaroslav Deineka** — MSc International Business with Business Analytics, Anglia Ruskin University  
[LinkedIn](https://www.linkedin.com/in/yaroslav-deineka/) 
