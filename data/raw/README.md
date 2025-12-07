# Raw Data Documentation

This directory contains the original, unprocessed datasets used for the **Cinnamon Supply & Demand Forecasting** project.

## Directory Structure

- **`supply/`**: Data related to production, export volumes, and local prices.
- **`demand/`**: Data related to global imports, Google Trends interest scores, and consumer market indicators.
- **`context/`**: Environmental data including temperature, rainfall, and climate anomaly indices (e.g., ENSO).

## Data Standards

All files in this directory should adhere to the following standards:

1. **File Format**: `.csv` (Comma Separated Values)
2. **Date Column**: Must be named `date` and formatted as `YYYY-MM`.
3. **Missing Values**: Denoted by empty strings or `NaN` (do not use `-999` or other placeholder numbers without documenting them).

## Data Sources

| Dataset Name | Source | Frequency | Units | Description |
|---|---|---|---|---|
| `sri_lanka_exports.csv` | UN Comtrade / Customs | Monthly | kg, USD | Monthly export volume and value of HS 0906 from Sri Lanka. |
| `production_annual.csv` | FAOSTAT | Annual | tonnes | Annual production figures (will be interpolated for monthly models). |
| `climate_sri_lanka.csv` | Met Dept / NASA POWER | Monthly | mm, °C | Rainfall and average temperature for key growing regions (Galle, Matara, etc.). |
| `google_trends_cinnamon.csv`| Google Trends | Monthly | Index (0-100)| Search interest for "Ceylon Cinnamon" worldwide. |

## Notes

- **Do not modify these files manually** to fix errors. If errors are found, fix them in the cleaning pipeline (`src/data_ingest.py`) or upload a corrected version of the raw file if the source itself was updated.
- **Backup**: Always keep a copy of the original source files outside this repo if they are not publicly available online.
