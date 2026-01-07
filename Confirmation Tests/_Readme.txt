# Reported Malaria Cases by Method of Confirmation (2015–2023) — African Countries

##  Overview
This dataset contains reported **malaria cases by method of confirmation** (microscopy, rapid diagnostic test [RDT], or clinical diagnosis) for **African countries**.  
The data were extracted from the **World Malaria Report 2024** — *Annex 4H: Reported malaria cases by method of confirmation, 2015–2023*, published by the **World Health Organization (WHO)**.

The original data file (`_wmr2024_annex_4h.xlsx`) was downloaded from WHO’s official publication page and then cleaned, filtered, and split into individual country-level CSV files for all African nations.

---

##  Data Source
- **Publication:** [World Malaria Report 2024 — Annexes](https://www.who.int/publications/m/item/annexes-world-malaria-report-2024)
- **Annex:** Annex 4H – *Reported malaria cases by method of confirmation, 2015–2023*
- **Publisher:** World Health Organization (WHO)
- **Division:** Global Malaria Programme (GMP)
- **Geographic Coverage:** Africa (subset of global WHO dataset)
- **Time Period:** 2015–2023
- **Update Frequency:** Annual

---

##  Included Files

| File Name | Description |
|------------|-------------|
| `_wmr2024_annex_4h.xlsx` | Original WHO Excel dataset (Annex 4H) |
| `Algeria.csv`, `Angola.csv`, `Benin.csv`, … | Cleaned and filtered CSV files for each African country (2015–2023 data) |

Each country file contains data for all available years and confirmation methods.

---

##  Data Structure

Each CSV file follows a standardized format:

| Column | Description |
|--------|--------------|
| **Country** | Official country name as per WHO database |
| **Year** | Reporting year (2015–2023) |
| **Microscopy_confirmed_cases** | Number of malaria cases confirmed by microscopy |
| **RDT_confirmed_cases** | Number of malaria cases confirmed by rapid diagnostic test (RDT) |
| **Clinical_cases** | Number of malaria cases diagnosed clinically (without lab confirmation) |
| **Total_reported_cases** | Sum of microscopy, RDT, and clinical cases |
| **Source** | WHO World Malaria Report 2024 |

**Example (Burkina_Faso.csv):**

| Country | Year | Microscopy_confirmed_cases | RDT_confirmed_cases | Clinical_cases | Total_reported_cases | Source |
|----------|------|-----------------------------|----------------------|----------------|----------------------|---------|
| Burkina Faso | 2015 | 425,983 | 6,284,134 | 93,102 | 6,803,219 | WHO WMR 2024 |
| Burkina Faso | 2018 | 512,401 | 7,139,852 | 47,315 | 7,699,568 | WHO WMR 2024 |
| Burkina Faso | 2023 | 624,112 | 8,012,604 | 25,808 | 8,662,524 | WHO WMR 2024 |

---

##  Data Processing Steps

1. **Download:**  
   The dataset was downloaded directly from the WHO publication page for the *World Malaria Report 2024 (Annex 4H)*.

2. **Cleaning:**  
   - Extracted the “Annex 4H” sheet.  
   - Retained only relevant columns (Country, Year, Microscopy, RDT, Clinical, Total).  
   - Removed non-country entries (e.g., regional or global totals).

3. **Splitting:**  
   - Filtered rows by country name.  
   - Created one CSV file per African country.

4. **Standardization:**  
   - Ensured consistent year range (2015–2023).  
   - Verified numerical integrity of case counts.  
   - Saved all files as UTF-8 encoded CSVs.

---

##  Usage Notes

###  Interpretation
- **Microscopy-confirmed cases**: Diagnoses confirmed using microscopic examination of blood smears.  
- **RDT-confirmed cases**: Diagnoses confirmed using rapid diagnostic tests detecting malaria antigens.  
- **Clinical cases**: Diagnoses made based on symptoms, without laboratory confirmation.  
- **Total cases**: The sum of the three confirmation methods.  

###  Data Gaps and Limitations
- **Incomplete reporting:** Some countries did not submit data for all years or all confirmation types. Missing values indicate *no data reported*, not zero cases.  
- **Method coverage:** Not all countries use both microscopy and RDT confirmation methods — some rely primarily on one method depending on health infrastructure.  
- **Consistency:** WHO compiles data from national malaria programs; reporting quality may vary year-to-year.  
- **Estimation differences:** Totals may not always match the sum of methods due to retrospective data revisions or rounding in national submissions.

---