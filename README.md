# CSMODEL_MCO1
This project focuses on the correlation between the provincial socioeconomic and demographic profiles and the time-lagged response and effectiveness of COVID-19 quarantine classifications. This repository deals with Data Preprocessing and Exploratory Data Analysis of the datasets aquired.

## Dataset Explanations
### DOH Covid Data Drop Dataset
- `CaseCode` is the unique code used to store each case.
- `Age` is the age of the person.
- `AgeGroup` is the category the patient belongs to in terms of their age.
- `Sex` indicates the sex of the patient.
- `DateSpecimen` is the date when their COVID-19 test was taken.
- `DateResultRelease` is the date when the result of the aforementioned test was released.
- `DateRepConf` is the date when the user was recorded as "confirmed" to have COVID-19 in the database of the Department of Health.
- `DateDied` and `DateRecover` recorded the date of death or the date of recovery.
- `RemovalType` indicated how the patient was removed from the DOH's list of active cases, either through death or recovery.
- `Admitted` indicates whether the patient was admitted to a hospital when they were infected with COVID-19.
- `RegionRes`, `ProvRes`, `CityMunRes`, and `BarangayRes` all refer to the patient's official place of residence at different administrative levels (Region, Province, City, and lastly, Barangay).
- `CityMuniPSGC` and `BarangayPSGC` refer to the city and barangay's PSGC code. PSGC, which stands for Philippine Standard Geographic Code, is the government's way of processing data that requires geographical disaggregation (breaking down into specifics to check trends in smaller areas).
- `Quarantined` indicates whether the patient has been quarantined at some point following a COVID-19 infection.
- `DateOnset` indicates the date when symptoms first started showing.
- `Pregnant` indicates whether the patient is pregnant.
- `ValidationStatus` indicates the completeness and consistency of the data in the record (e.g., lacking age/birthdate, lacking recovery date, etc.).

### Quarantine Timeline CSV
- `Region/Province/City` is the specific region, province, or city where a quarantine occured.
- `Kind of Quarantine` is the specific quaratine being implemented which are (ECQ, MECQ, GCQ, MGCQ, and Alert Levels 1-5).
- `Start Date` is the starting date of the quarantine implementation.
- `End Date` is the ending date of the quarantine implementation.
- `Source` is where the data from that row is sorced from.

### Province Ranking
- `Rank` is the numerical rank of the province compared to others.
- `Score` is the calculated score of the province.
- `Province` is the name of the province.
- `Region` is the region where the province is located.
- `Ranking-Year` is the year the provinces were ranked.

### Province Population
- `Province` is the name of the province.
- `2020 Recorded Population` is the official recorded population for that province by the PSA.
- `2021 Projected Population` is the computed population for that province using the growth rate.
- `2022 Projected Population` is the computed population for that province using the growth rate.

## Exploratory Data Analysis
1. What are the common demographic, geographic, admission characteristics of COVID-19 patients based on the measure of central tendencies?
   - Demographic: The age distribution is skewed to the right, with an interquartile range of 25-50 years. Females are more likely to be recorded with COVID-19, making up 52.17% of the population dataset. Majority of the population were not admitted to the hospital nor quarantined after contracting COVID-19. NCR (though not a province, but serves as a group for all NCR cities) has the most confirmed number of COVID-19 cases.

2. Is there a significant difference in the volume of cases of the rate of infection between high-income provinces and low-income provinces?
   - Income appears to strongly affect COVID-19 incidence. While mid- and high- income provinces exhibit smiliar rates, lower income provinces have lower incidence rates, which may be associated with lower population density, fewer employment opportunities and reduced human mobility. 
     - This may also be attributed to socio-economic factors rather than lower transmission rates. Limited hospital infrastructure and reduced access to diagnostic testing and impoverished areas likely led to a significant underreporting of cases.

3. How did the number of confirmed cases change over time in the areas with most quarantine periods in relation to the implementation of different quarantine levels?
   - Stricter quarantine levels (ECQ/MECQ) coincide with the absolute peaks of the cases for those specific time periods, acting as a reactive "ceiling" that forced the numbers to eventually die down after a short lag, while more relaxed levels (GCQ/MGCQ) often allowed for the build-up of subsequent cases.

## Prerequisites
To run the python notebook in Google Collab, you must put these folders into your Google Drive:
   - `cases` - make a folder for this first, then download all the data drops [here](https://data.gov.ph/index/public/dataset/COVID-19%20DOH%20Data%20Drop%20%28November%2026,%202022%29/vuo95enr-tttu-24cu-3x70-agzd8kcvhkop) and put it in the `cases` folder
   - `quarantine_timeline` - downloadable in the repository, drag and drop it into your Google Drive
   - `socioeconomics and population` - downloadable in the repository, drag and drop it into your Google Drive

## Tools Used
   - Google Collab

## Authors
   - [Byron Scott Ang](https://github.com/niloucode)
   - [Karl Deejay Omandac](https://github.com/PieIsSpy)
   - [Anne Camille Samonte](https://github.com/cam-coop)
   - [Kimberly Wynelle Sotingco](https://github.com/Kwimbow)
   - [John Lorens Tee](https://github.com/LorensTee)

## Acknowledgments
  - DOH Covid-19 Data Drop from [data.gov.ph](https://data.gov.ph/index/public/dataset/COVID-19%20DOH%20Data%20Drop%20%28November%2026,%202022%29/vuo95enr-tttu-24cu-3x70-agzd8kcvhkop)
  - Quarantine Timeline CSV from [https://www.officialgazette.gov.ph/](https://www.officialgazette.gov.ph/) and [https://pco.gov.ph/](https://pco.gov.ph/)
  - Provincial Socioeconomic Rankings CSV from [Cities and Municipalities Competitiveness Index (Department of Trade and Industry)](https://cmci.dti.gov.ph/)
  - Provincial Population CSV from [Philippine Statistics Authority](https://psa.gov.ph/content/2020-census-population-and-housing-2020-cph-population-counts-declared-official-president)

## AI Declaration
- During the preparation of this work the author(s) used gemini for the following purposes:
  - Webscrapper for gathering data for provincial rankings and city-wide scores from https://cmci.dti.gov.ph/

- After using this tool/service, the authors(s) reviewed and edited the content as needed and take(s) full responsibility for the content of the publication.