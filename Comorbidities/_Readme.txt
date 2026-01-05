Cancer Incidence — Females (Africa, 2022)

SOURCE
- Publisher: International Agency for Research on Cancer (IARC), World Health Organization.
- Portal: Global Cancer Observatory (GCO) – “Cancer Today (GLOBOCAN 2022)” tables view.
- What was downloaded: CSV export for EACH African country/territory, plus an Africa-wide file.
- Filter used: sex = 2 (Females), year = 2022, all cancer sites (includes the “All cancers excl. non-melanoma skin cancer” total).
- Notes: Files come directly from the site’s CSV export; no transformations were applied.

HEADERS (what each column means)
- Cancer code        : Internal GCO numeric code for the cancer site.
- ICD Code           : ICD-10 topography range identifying the site (e.g., C50 breast, C53 cervix uteri).
- Country            : Country/territory population code (ISO-3166 numeric for most files).
                        • In country files: a single numeric code (e.g., 404 = Kenya).
                        • In the Africa aggregate: an underscore-separated list of included population codes.
- Label              : Cancer site name (e.g., Breast, Cervix uteri, Colorectum). The overall total appears as
                        “All cancers excl. non-melanoma skin cancer”.
- Sex                : Sex code; 2 = Female (all files in this folder are female-only).
- Number             : Estimated NEW cancer cases in 2022 (count).
- 95% UI low         : Lower bound of the 95% uncertainty interval for “Number”.
- 95% UI high        : Upper bound of the 95% uncertainty interval for “Number”.
                        (In some aggregate files this may appear as “-” when bounds aren’t shown.)
- Number.1           : Duplicate of “Number” present in these exports; can be ignored.
- ASR (World)        : Age-standardized incidence rate per 100,000 (World standard population).
- Crude rate         : Crude incidence rate per 100,000.
- Cumulative risk    : Risk of developing the cancer from age 0–74, in percent (%).
