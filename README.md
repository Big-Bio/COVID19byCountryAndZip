# COVID19byZip

We are examining fine scale resolution of coronavirus growth rates, at the level of zip code or census tract.


**Table of contents**

* [External Resources](#external-resources)
* [Unacast Public Data](./UnacastData/README_Unacast.md)
* [COVID19 Case Data](./COVID19CaseData/README_COVID19CaseData.md)
* [Static Data](#static-data)
* [Data Formatting Guidelines](#data-formatting-guidelines)
* [Analysis Project](./AnalysisProject/README_AnalysisProjects.md)


# External Resources

* [CDC’s Social Vulnerability Index (SVI)](https://nation.maps.arcgis.com/home/item.html?id=425652f366d34c8ca33e6b014a304054): It includes all kinds of columns on the tract/county level including a social vulnerability score (calculated from 15 US Census metrics), data on population, housing stats, unemployment, poverty, per capita income, etc.


* [Unacast Data](https://www.unacast.com/post/the-unacast-social-distancing-scoreboard): Unacast has created country-level social distancing metrics based on cell-phone locations. They currently have a score for changes in travel compared to a baseline (from early March) for total and non-essential travel. A letter grade is available from their website for each county, but we have applied for and received permission to you their full summary datasets. We keep this dataset in a private repository. If you write to both us and to Unacast and show us proof that you have been granted access, we will link you to our private repo. In our private repo we have the data formatted to match our other data sets and we have the time series of scores, not just the current values. You can read their methodology [here](https://www.unacast.com/post/the-unacast-social-distancing-scoreboard). A public version of their data is available [here](https://coronavirus-resources.esri.com/datasets/unacast-social-distancing-latest-available/data?geometry=122.446%2C29.346%2C-7.632%2C67.392). We have also made a data folder with a copy of the public unacast data. We are not updating this file at this time.

* [nytimes' case counts data](https://github.com/nytimes/covid-19-data): Here the nytimes is gathering all the state and county case and death counts. Data is kept up to date and each county entry (or state entry) uses the corresponding FIPS code.

# Static Data

In this [folder](./StaticData) we are hoping to make machine readable [flat files](./StaticData/README_StaticData.md) of static covariates that can be used to understand disease spread and severity rates. We want all covariates to be at the zip and county code level of granularity.  We want any data on covariates that could indicate [risk](https://www.cdc.gov/coronavirus/2019-ncov/need-extra-precautions/people-at-higher-risk.html) and any covariates that we think might be correlated with these or with other measures of social distancing.

# Data Formatting Guidelines


## Column header

* For columns present on the [NYT data](https://github.com/nytimes/covid-19-data) (i.e.,  date, tract, county, state, fips, cases, and deaths), the column names must match identically and use lowercase.
* All column names must not have commas, so you must change these too.
* For all other column names, keep them exactly the same.
* Note: For all column names changed, mention in the README (1) the original column name that was changed, and (2) what the new column name is.


## Data format

* **date:** yyyy-mm-dd

* **state and county:** All specific State/County names capitalized (e.g., Santa Clara, Los Angeles, California, Michigan, New York). County names should not have &quot;County&quot; on their names. (e.g., &quot;King County&quot; becomes &quot;King&quot;)

* **fips:** Integers

  * State level: 1-2 digits (e.g., 1, 53)

  * County level: 4-5 digits (e.g., 1001, 53061)

  * Tract level: 10-11 digits (e.g., 1001021000, 53061940002)


* **cases:** Integers

* **deaths:** Integers
