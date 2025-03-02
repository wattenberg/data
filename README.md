# Data

This repo contains data for classroom use in visualization homework.

* **names_by_decade.js** decade-by-decade data on US baby name popularity. See [(names_by_decade_doc.md](names_by_decade_doc.html) for documentation.

## Older material

* **us_name_history.csv** contains yearly data 1880-2021 for male and female baby names across the US.
* **us_name_history_small.csv** contains a selected set of yearly data 1880-2021 for male and female baby names across the US.
* **state_history_decades.csv** contains data at decade intervals 1880-2020 for male and female baby names for each US state
* **nyc_names_final.csv** contains yearly (recent) data for babies born in New York City. Unlike the other data sets, it has data on ethnicity.



# Sources
**US name history** is US government data, from the Social Security Administration (SSA).

**us_name_history_small** is a filtered version of the same data set, including only most popular names, designed to be small and easy to work with.**

See this link for full info: https://www.ssa.gov/oact/babynames/limits.html

Counts for baby names come from: https://www.ssa.gov/oact/babynames/names.zip

Proportion values for the US overall were calculated using: https://www.ssa.gov/oact/babynames/numberUSbirths.html

Proportion values for the state data are calculated simply as a proportion of all births reported in the file. The resulting numbers are not precisely accurate, because this method ignores babies born with rare names not reported in the data, but it is a reasonable approximation given what we have available. Note that the approximation is better for more populous states.

I have also added a new "Name-Gender" field for convenience.

Data is yearly 1880-2021 for overall US; and 1880-2020 by decade for state data.


**NYC name history** is from NYC Open Data: https://data.cityofnewyork.us/Health/Popular-Baby-Names/25th-nujf/data

Note that this data set is processed to remove duplicate lines (which I believe are errors in the original), normalize case for names (which varied in the original) and normalize ethnicity fields (which also varied in number of characters in original). As with the US data, I have added a Name-Gender field for convenience.

**CPI-U** data is from Jan. 2023 .xslx file at this address: https://www.bls.gov/cpi/tables/supplemental-files/home.htm

I have edited this spreadsheet to make it fit for Tableau.

