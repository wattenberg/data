# Data

This repo contains data for classroom use in visualization homework.

# Sources
**US name history** is US government data, from the Social Security Administration (SSA).

See this link for full info: https://www.ssa.gov/oact/babynames/limits.html

Counts for baby names come from: https://www.ssa.gov/oact/babynames/names.zip

Proportion values for the US overall were calculated using: https://www.ssa.gov/oact/babynames/numberUSbirths.html

Proportion values for the state data are calculated simply as a proportion of all births reported in the file. The resulting numbers are not precisely accurate, because this method ignores babies born with rare names not reported in the data, but it is a reasonable approximation given what we have available. Note that the approximation is better for more populous states.

I have also added a new "Name-Gender" field for convenience.


**NYC name history** is from NYC Open Data: https://data.cityofnewyork.us/Health/Popular-Baby-Names/25th-nujf/data

Note that this data set is processed to remove duplicate lines (which I believe are errors in the original), normalize case for names (which varied in the original) and normalize ethnicity fields (which also varied in number of characters in original). As with the US data, I have added a Name-Gender field for convenience.
