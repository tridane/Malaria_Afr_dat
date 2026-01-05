# Caesarean Section Rates — African Countries (WHO GHO)

##  Overview
This dataset contains information on **births delivered by caesarean section (%)** for countries in **Africa**, sourced directly from the **World Health Organization (WHO) Global Health Observatory (GHO)**.

The files were obtained from the official WHO GHO indicator:
> **Births by caesarean section (%)**  
> [https://www.who.int/data/gho/data/indicators/indicator-details/GHO/births-by-caesarean-section-%28-%29](https://www.who.int/data/gho/data/indicators/indicator-details/GHO/births-by-caesarean-section-%28-%29)

The original WHO file (`_PANEL_ALL_COUNTRIES.csv`) contains data for all countries globally.  
It has been **cleaned** and **split** into individual CSV files for each African country for easier access and analysis.

---

##  Data Source
- **Source:** [WHO Global Health Observatory (GHO)](https://www.who.int/data/gho)
- **Indicator Name:** *Births by caesarean section (%)*  
- **Indicator Code:** `MDG_0000000015`
- **Publisher:** World Health Organization (WHO)
- **Update frequency:** Periodic (based on national reporting and surveys)
- **Geographic coverage:** Global (subset here is Africa)
- **Units:** Percentage (%)
- **Time range:** Varies by country (check `Year` column in each file)

---

##  Included Files

| File Name | Description |
|------------|-------------|
| `_PANEL_ALL_COUNTRIES.csv` | Original WHO GHO dataset (all countries) |
| `Algeria.csv` | Caesarean section data for Algeria |
| `Angola.csv` | Caesarean section data for Angola |
| `Benin.csv` | Caesarean section data for Benin |
| `Botswana.csv`, `Burkina_Faso.csv`, `Cabo_Verde.csv`, ... | Individual files for remaining African countries |

Each per-country file was extracted from `_PANEL_ALL_COUNTRIES.csv` and cleaned to contain only relevant rows and columns.

---

##  File Structure

Each CSV file contains four standardized columns:

| Column | Description |
|--------|--------------|
| **Country** | Official country name as per WHO GHO |
| **Year** | Year of reporting or estimate |
| **Indicator** | WHO GHO indicator name (*Births by caesarean section (%)*). This may appear as text or an indicator code. |
| **Value** | Percentage of live births delivered by caesarean section |

**Example (Benin.csv):**
| Country | Year | Indicator | Value |
|----------|------|------------|--------|
| Benin | 2000 | Births by caesarean section (%) | 3.2 |
| Benin | 2005 | Births by caesarean section (%) | 4.6 |
| Benin | 2010 | Births by caesarean section (%) | 5.4 |
| Benin | 2015 | Births by caesarean section (%) | 7.1 |

---

##  Data Processing Steps
1. **Download:** The dataset `_PANEL_ALL_COUNTRIES.csv` was downloaded directly from the WHO GHO indicator page.  
2. **Cleaning:** Unnecessary metadata columns were removed; only the relevant fields (Country, Year, Indicator, Value) were retained.  
3. **Splitting:** Data was filtered by country, and a separate CSV file was created for each African country.  
4. **Verification:** Country names were standardized to ensure consistent naming across all files.

---

##  Usage Notes
- The data represents **percentage of births delivered by caesarean section** in each country per year.  
- Missing years indicate unavailable or unreported data in the WHO source.  
- Data values may be based on **national health surveys**, **hospital records**, or **statistical estimates**.  
- Values are directly sourced — **no recalculations or transformations** were made.

---

##  Citation
When using this dataset, please cite:

> World Health Organization. *Global Health Observatory (GHO) data: Births by caesarean section (%)*.  
> Available at: [https://www.who.int/data/gho/data/indicators/indicator-details/GHO/births-by-caesarean-section-%28-%29](https://www.who.int/data/gho/data/indicators/indicator-details/GHO/births-by-caesarean-section-%28-%29)