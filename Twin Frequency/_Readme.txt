# Twin Birth Frequency — African Countries (DHS Data)

##  Overview
This dataset provides **twin birth frequencies** across multiple **Sub-Saharan African countries**, derived from **Demographic and Health Surveys (DHS)** Birth Recode files.

Each dataset contains the **annual twin birth rate (per 1,000 births)** estimated from DHS microdata, computed using DHS survey weights.  
The data cover surveys from the **1980s through 2020s**, depending on the availability of DHS rounds for each country.

All data were extracted and processed using a **custom Python workflow** that automatically:
- Reads `.dta` (Stata) Births Recode files  
- Identifies twin births (`b0 > 0`)  
- Applies DHS sampling weights (`v005 / 1,000,000`)  
- Aggregates by survey year (`b2` or derived from `b3`)  
- Produces one CSV file per country plus a master summary table

---

##  Data Source
- **Primary Source:** [Demographic and Health Surveys (DHS) Program](https://dhsprogram.com/)
- **File Type Used:** Births Recode (`BR`) datasets  
- **Variables Utilized:**
  | DHS Variable | Description | Use |
  |---------------|-------------|-----|
  | `b0` | Birth order in multiple birth | Detects twins (`b0 > 0`) |
  | `b2` | Year of child’s birth | Defines survey year |
  | `b3` | Century Month Code (backup for birth year) | Derived year if `b2` missing |
  | `v005` | Sample weight | Used to compute weighted estimates |
  | `v000`, `v024` | Country / Region codes | Identifies dataset origin |

---

##  Folder Structure

| File / Folder | Description |
|----------------|-------------|
| `_ALL_COUNTRIES_TWIN_RATES.csv` | Combined file of all countries and DHS surveys |
| `Angola.csv`, `Benin.csv`, `Burkina_Faso.csv`, … | One CSV file per country, listing year-wise twin birth rates |

Each country file includes:
| Column | Description |
|---------|-------------|
| **country** | Country name (standardized from DHS code) |
| **source_file** | Original DHS file name (e.g., `NGBR7HFL.DTA`) |
| **year** | Year of birth (derived from `b2` or `b3`) |
| **weighted_births** | Weighted number of total births in that year |
| **weighted_twin_births** | Weighted number of twin births |
| **twin_rate_per_1000** | Twin births per 1,000 total births |
| **weight_source** | `weighted_v005` (if `v005` used) or `unweighted` |

---

##  Example (from Benin.csv)

| country | source_file | year | weighted_births | weighted_twin_births | twin_rate_per_1000 | weight_source |
|----------|--------------|------|-----------------|----------------------|--------------------|----------------|
| Benin | BJBR31FL.DTA | 1996 | 14,832.5 | 286.9 | 19.34 | weighted_v005 |
| Benin | BJBR61FL.DTA | 2011 | 18,421.6 | 361.2 | 19.61 | weighted_v005 |
| Benin | BJBR81FL.DTA | 2018 | 20,229.7 | 405.5 | 20.05 | weighted_v005 |

---

## ⚙️ Methodology
1. **Data Extraction**  
   DHS `.zip` files were unpacked, and only `.dta` Births Recode files were used.

2. **Twin Detection**  
   `b0 > 0` identifies children born as part of multiple births (twin or higher order).

3. **Weighting**  
   Sampling weights (`v005 / 1,000,000`) were applied to compute weighted totals and rates.

4. **Aggregation**  
   Data were aggregated by **birth year**, producing a weighted twin rate (per 1,000 births).

5. **Output Generation**  
   Each country’s dataset was saved as an individual `.csv` file, and all were merged into a global `_ALL_COUNTRIES_TWIN_RATES.csv` master file.

---

##  Data Notes
- Not all countries have data for every year — only DHS survey years are included.  
- Missing variables (`b2`, `v005`) are handled automatically (with year derived from `b3` or unweighted counts flagged).  
- Some small countries have limited or no DHS Birth Recode surveys available.  
- All estimates represent **survey-weighted approximations**, not raw national counts.

---
