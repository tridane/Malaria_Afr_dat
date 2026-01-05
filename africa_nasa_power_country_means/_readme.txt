README — National Monthly Climate Dataset (NASA POWER) for African Countries
==========================================================================

Overview
--------
This dataset provides monthly, country-level climate variables for all
African countries, aggregated from NASA POWER global reanalysis data.
Values represent area-weighted averages over each country's land area
using a regular latitude–longitude sampling grid.

The dataset is intended for epidemiological analyses, climate sensitivity
studies, environmental modeling, and general scientific use.


Data Source
-----------
NASA Prediction Of Worldwide Energy Resources (NASA POWER) API  
Source: https://power.larc.nasa.gov  
Community: AG (Agroclimatology)  
Temporal Resolution: Monthly  
Spatial Resolution: Native POWER grid (~0.5° × 0.5°)  
Coverage: 1981 – most recent full year available  
Variables pulled from POWER parameters list:
    - T2M
    - T2M_MAX
    - T2M_MIN
    - RH2M
    - PRECTOTCORR


Country Boundary Data
---------------------
Country shapes were taken from:
Natural Earth — Admin 0 Countries (1:10m resolution)  
Source: https://www.naturalearthdata.com  
File used: ne_10m_admin_0_countries.shp

Countries were subset to the African continent based on the
"CONTINENT = Africa" attribute.


Methodology
-----------
For each country:

1. A regular lat/lon grid (step = 1°) was generated across the
   bounding box of the country.

2. Points falling inside the country's polygon were kept.

3. For each point:
      - A NASA POWER API request was made for all monthly data from
        START_YEAR to END_YEAR.
      - Returned monthly values were stored along with a latitude-based
        area weight computed as: cos(latitude).

4. For each month/year:
      - Weighted averages across sampling points inside the country were
        computed for each variable:
            WeightedMean = Σ(value_i * weight_i) / Σ(weight_i)

5. Rainfall was provided by NASA POWER as a monthly mean precipitation
   RATE (mm/day). A second variable was derived:
      - Monthly rainfall total (mm/month) = (mm/day) × (days in month).


File Naming Convention
----------------------
Each country has its own CSV file:

    countryname.csv

Example:
    ethiopia.csv
    nigeria.csv
    kenya.csv


Column Definitions
------------------

1. country  
    - Name of the country
    - String

2. year  
    - Calendar year of the observation  
    - Integer (1981–present)

3. month  
    - Calendar month of the observation (1–12)  
    - Integer

4. T2M  
    - Monthly mean 2-meter air temperature  
    - Units: °C  
    - Source parameter: "T2M"

5. T2M_MAX  
    - Monthly mean of daily maximum 2-meter temperature  
    - Units: °C  
    - Source parameter: "T2M_MAX"

6. T2M_MIN  
    - Monthly mean of daily minimum 2-meter temperature  
    - Units: °C  
    - Source parameter: "T2M_MIN"

7. RH2M  
    - Monthly mean relative humidity at 2 meters  
    - Units: %  
    - Source parameter: "RH2M"

8. PRECTOTCORR_mm_per_day  
    - Monthly mean precipitation RATE (mm/day)  
    - This is the POWER variable PRECTOTCORR.  
    - Units: mm/day  
    - NOTE: This is NOT total rainfall, but the average rainfall per day 
      for that month.

9. PRECTOTCORR_monthly_mm  
    - Total rainfall for that month  
    - Computed as:
            PRECTOTCORR_mm_per_day × days_in_month  
    - Units: mm/month  
    - Example:
        If PRECTOTCORR_mm_per_day = 2.0 mm/day in March,
        then total = 2.0 × 31 = 62 mm.

Spatial Weighting
-----------------
Aggregation to the country level uses area weighting:

    weight = cos(latitude_in_degrees)

This approximates the area represented by each sampled grid point on
the Earth's spherical surface.