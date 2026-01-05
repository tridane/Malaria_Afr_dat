README — Combined Maternal, Health, Demographic, Education, Abortion, Preterm Birth,
Diabetes, HIV, Malaria & Female-Specific Genetic/Autoimmune/Infectious Disease Indicators
=====================================================================================================================

This dataset merges country–year indicators for 54 African countries from:
• Our World in Data (OWID)
• World Bank World Development Indicators (WDI)
• WHO Global Health Observatory (GHO)
• WHO–UNICEF Preterm Birth Estimates (“Born Too Soon”)
• Institute for Health Metrics and Evaluation (IHME) — Global Burden of Disease (GBD)

It now includes maternal health, demographics, socioeconomic indicators,
fertility, abortion, preterm birth, diabetes, HIV, malaria, and *female-only*
burden of selected genetic, autoimmune, and infectious diseases.

--------------------------------------------------------------------------------
COLUMN DEFINITIONS (meaning, units, official source)
--------------------------------------------------------------------------------

[ALL PREVIOUS COLUMNS REMAIN UNCHANGED — see prior README for items 1–33]

--------------------------------------------------------------------------------
FEMALE-ONLY GENETIC & AUTOIMMUNE DISEASE INDICATORS (GBD)
--------------------------------------------------------------------------------

These indicators come from the **Global Burden of Disease (GBD 2023)** study
and represent **female-only prevalence rates**, defined as:

> “Prevalence rate among females of all ages, measured per 100,000 female population,
>  based on IHME/GBD modelling.”

Filters used for all indicators in this group:
• Sex = **Female**
• Age = **All ages**
• Measure = **Prevalence**
• Metric = **Rate**
• Years = **1990–2023**
• Locations = All countries (filtered later to 54 African ISO3 codes)

34. ds_prev_rate_female_per_100k
   • Description: Female prevalence rate of **Down syndrome** per 100,000 female population.
   • Unit: Cases per 100,000 females.
   • Source: IHME Global Burden of Disease (GBD 2023), cause “Down syndrome”.
   • Interpretation: Higher values indicate greater estimated burden of Down syndrome
     among females in the population for that year.

35. ra_prev_rate_female_per_100k
   • Description: Female prevalence rate of **Rheumatoid arthritis (RA)** per 100,000 females.
   • Unit: Cases per 100,000 females.
   • Source: IHME GBD 2023, cause “Rheumatoid arthritis”.
   • Interpretation: RA disproportionately affects females; this variable captures the
     female-specific burden.

36. ms_prev_rate_female_per_100k
   • Description: Female prevalence rate of **Multiple sclerosis (MS)** per 100,000 females.
   • Unit: Cases per 100,000 females.
   • Source: IHME GBD 2023, cause “Multiple sclerosis”.
   • Interpretation: MS has higher prevalence among adult women globally; this indicator
     measures the modeled burden in each country-year.

37. psoriasis_prev_rate_female_per_100k
   • Description: Female prevalence rate of **Psoriasis** per 100,000 female population.
   • Unit: Cases per 100,000 females.
   • Source: IHME GBD 2023, cause “Psoriasis”.
   • Interpretation: Estimates the overall psoriasis burden among females in the population.

--------------------------------------------------------------------------------
FEMALE-ONLY HIV & MALARIA PREVALENCE (GBD)
--------------------------------------------------------------------------------

These indicators extend the female-only GBD set to **HIV/AIDS** and **Malaria**.
They use the same GBD filters:

• Sex = **Female**
• Age = **All ages**
• Measure = **Prevalence**
• Metric = **Rate** (per 100,000 population)
• Years = **1990–2023**
• Locations = All countries (later restricted to the 54 African ISO3 codes)

38. hiv_prev_rate_female_per_100k
   • Description: Female prevalence rate of **HIV/AIDS** per 100,000 female population.
   • Unit: Cases per 100,000 females.
   • Source: IHME Global Burden of Disease (GBD 2023), cause “HIV/AIDS”,
     using prevalence, rate, females, all ages.
   • Interpretation: Estimated burden of HIV among females in the total female population.
     Note this is an all-ages prevalence rate, not an incidence rate.

39. malaria_prev_rate_female_per_100k
   • Description: Female prevalence rate of **Malaria** per 100,000 female population.
   • Unit: Cases per 100,000 females.
   • Source: IHME Global Burden of Disease (GBD 2023), cause “Malaria”,
     using prevalence, rate, females, all ages.
   • Interpretation: Estimated burden of malaria among females in the total female
     population, including both acute and chronic prevalent cases as defined in GBD.

--------------------------------------------------------------------------------
NOTES
--------------------------------------------------------------------------------
• Female-only disease data (Down syndrome, RA, MS, psoriasis, HIV, malaria) all come
  from IHME’s Global Burden of Disease (GBD 2023) multi-cause exports, filtered to
  prevalence, rate, female, all ages.
• GBD figures are **model-based**, using epidemiological inputs, covariates,
  and statistical modelling — not direct surveillance counts.
• Missing values appear where IHME did not produce an estimate for a specific
  country-year combination.

EXTERNAL SOURCES:
• Our World in Data (OWID): https://ourworldindata.org/
• World Bank WDI: https://data.worldbank.org/
• WHO GHO: https://ghoapi.azureedge.net/
• WHO–UNICEF Preterm: “Born Too Soon” datasets
• IHME Global Burden of Disease Results (GBD 2023): https://vizhub.healthdata.org/gbd-results/

--------------------------------------------------------------------------------
END OF README
--------------------------------------------------------------------------------
