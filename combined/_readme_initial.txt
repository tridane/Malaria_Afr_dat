README — Combined Maternal, Health, Demographic, Education, Abortion, Preterm Birth, Diabetes, HIV & Malaria Indicators
======================================================================================================================

This dataset merges country–year indicators for 54 African countries from:
• Our World in Data (OWID)
• World Bank World Development Indicators (WDI)
• WHO Global Health Observatory (GHO)
• WHO–UNICEF Preterm Birth Estimates (“Born Too Soon”)

It combines maternal health, demographics, socioeconomic variables,
education indicators, abortion rate estimates, preterm birth estimates,
adult diabetes prevalence, and HIV & malaria indicators.

--------------------------------------------------------------------------------
COLUMN DEFINITIONS (meaning, units, official source)
--------------------------------------------------------------------------------

1. Entity – Standardized country name (OWID)
2. Code – ISO3 code (OWID/WDI)
3. Year – Observation year (OWID/WDI)
4. country – Duplicate country field (OWID)

MATERNAL & CHILD HEALTH
5. anemia_pregnant_women_pct – % pregnant women with anemia (OWID/WHO/UN)
6. anemia_children_pct – % children with anemia (OWID/WHO/UNICEF)
7. art_coverage_pregnant_women_pct – ART coverage in HIV+ pregnant women (OWID/UNAIDS)
8. stillbirth_rate – Stillbirths per 1,000 births (OWID/WHO/IGME)
9. low_birthweight_share – % infants < 2,500 g (OWID/UNICEF/WHO)
10. maternal_mortality_ratio – Maternal deaths per 100,000 live births (OWID/WHO)

DEMOGRAPHICS & ECONOMICS
11. gdp_per_capita_ppp – GDP per capita, PPP (OWID/WDI)
12. gdp_constant_usd – GDP constant USD (OWID/WDI)
13. hdi – Human Development Index (OWID/UNDP)
14. female_lfp – Female labour force participation (OWID/ILO/WDI)
15. anemia_wra_15_29 – Anemia in women 15–29 (OWID/WHO/UN)
16. tfr_children_per_woman – Total fertility rate (OWID/UN WPP)
17. anc1_plus – ≥1 ANC visit (%) (OWID/WHO/UNICEF)
18. anc4_plus – ≥4 ANC visits (%) (OWID/WHO/UNICEF)

EDUCATION (WDI)
19–22. female_primary_gross_enrol, female_secondary_gross_enrol,
       female_tertiary_gross_enrol, female_primary_completion_rate – All from WDI

FEMALE POPULATION (WDI / UN WPP)
23. female_pop_total – Total female population
24. female_pop_15_24 – Female 15–24 population
25. female_pop_25_64 – Female 25–64 population
26. female_pop_65_plus – Female 65+ population
    • All derived from WDI age–sex shares × total female population
    • Source: World Bank WDI (population by age and sex, based on UN World Population Prospects)

ABORTION (WHO GHO)
27. abortion_rate_per_1000_women_15_49
    • Abortions per 1,000 women aged 15–49.
    • Unit: Abortions per 1,000 women 15–49.
    • Source: WHO Global Health Observatory (GHO), indicator SRH_ABORTION_RATE (model-estimated).

PRETERM BIRTH (WHO–UNICEF)
28. preterm_rate_per_100_live_births
    • Percentage of births occurring before 37 completed weeks of gestation.
    • Unit: Preterm births per 100 live births (%).
    • Source: WHO–UNICEF preterm birth estimates (Born Too Soon initiative).

29. preterm_births_number
    • Estimated number of preterm births in a given country–year.
    • Unit: Number of preterm live births.
    • Source: WHO–UNICEF preterm birth estimates (Born Too Soon initiative).

DIABETES (OWID / WHO GHO)
30. diabetes_prev_adults_pct
    • Adult diabetes prevalence: estimated share of adults (18+ years) with diabetes.
    • Unit: Percent (% of adults 18+).
    • Source: Our World in Data grapher “diabetes-prevalence-who-gho”,
      based on WHO Global Health Observatory modelling of diabetes prevalence.

HIV & MALARIA (OWID / UNAIDS / WHO / IHME)
31. hiv_incidence_per_1000_uninfected_15_49
    • HIV incidence: number of people aged 15–49 newly infected with HIV per 1,000
      people aged 15–49 who were previously uninfected (central estimate).
    • Unit: New HIV infections per 1,000 uninfected people (ages 15–49).
    • Source: Our World in Data grapher
      “incidence-of-hiv-the-share-of-new-infections-among-the-previously-uninfected-population-ages-15-49”,
      based on UNAIDS incidence estimates.

32. malaria_incidence_per_1000_at_risk
    • Malaria incidence: number of new malaria cases per 1,000 population at risk per year.
    • Unit: New malaria cases per 1,000 population at risk.
    • Source: Our World in Data grapher “incidence-of-malaria”,
      based primarily on IHME Global Burden of Disease / WHO malaria estimates.

33. share_women_among_plhiv_pct
    • Share of women among people living with HIV (PLHIV), ages 15+.
    • Unit: Percent (%) of PLHIV who are women.
    • Source: Our World in Data grapher “share-of-women-among-the-population-living-with-hiv”,
      which republishes World Bank WDI / UNAIDS indicator (e.g. SH.DYN.AIDS.FE.ZS).

--------------------------------------------------------------------------------
NOTES
--------------------------------------------------------------------------------
• Missing values appear where OWID, WDI, WHO GHO, WHO–UNICEF, UNAIDS, or IHME do not report data.
• Abortion, preterm birth, diabetes, HIV, and malaria indicators are model-based estimates, not direct surveillance counts.
• All variables are merged by Code (ISO3) and Year.
• External sources:
    - Our World in Data (OWID): https://ourworldindata.org/
    - World Bank World Development Indicators (WDI): https://data.worldbank.org/
    - WHO Global Health Observatory (GHO): https://ghoapi.azureedge.net/
    - WHO–UNICEF Preterm (Born Too Soon): official WHO/UNICEF technical files
    - UNAIDS / IHME as underlying sources for HIV and malaria series republished by OWID.

--------------------------------------------------------------------------------
END OF README
--------------------------------------------------------------------------------
