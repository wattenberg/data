---
layout: default
title: Documentation for names_by_decade.js
---

# US baby names, by decade

The file [names_by_decade.js](https://wattenberg.github.io/data/names_by_decade.js) contains historical data on US baby names, providing
the proportion of babies (and average number of babies per year) in the decades from the 1880s to 2020s.

## Data source

The data comes from the Social Security Administration. [See this page](https://www.ssa.gov/OACT/babynames/limits.html) for details,
or [this intro page](https://www.ssa.gov/oact/babynames/) for more general baby name info.
We have condensed and filtered the information from this site to make it easier to work with. Note that this data
only runs until 2021, so the decade of the 2020s is not completely up to date. Another quirk of the data
is that it comes from social security cards, rather than birth certificates; in earlier decades this means
that you're seeing a small proportion of actual people. One final note: for privacy reasons, the tables only counts names
that are used at least five times in a given year. 

We've calculated a figure for the proportion of babies born with each name, but for the reasons above it should be considered only an approximation,
especially in earlier decades.

## Data format

This is a special format designed to be easy to use for a Javascript program that can be run from your own computer's file system.
It is essentially putting a comma-separated table into a Javascript variable. The table itself looks like this:
```
Name,Gender,Name-Gender,Decade,Number,Proportion
Aaban,Male,Aaban-M,2000,5.5,2.543841029340606e-06
Aaban,Male,Aaban-M,2010,10.9,5.406029402420773e-06
Aabha,Female,Aabha-F,2010,6.83,3.5474218280428824e-06
Aabha,Female,Aabha-F,2020,5.0,2.823499969428362e-06
[etc.]
```
The fields are:
* Name: the name, like "Martin"
* Gender: "Male" or "Female" (This field follows the Social Security Adminstration conventions)
* Name-Gender: A unique identifier combining name and gender, which sometimes is useful
* Decade: The start of the decade. (e.g., "1880" means "1880-1889")
* Number: Average number of entries in the SSA database for this year. (For early years, this is very different from number of births)
* Proportion: The approximate proportion of babies born with this name, as calculated from this database.

## How to use with ChatGPT

Here's a prompt that provides a starting point for making a visualization with this data:

```
I am building a data visualization tool,
and would like you to write the code for me. 

From a technical perspective:
I want a standalone HTML page that I can run locally from my computer.

The data should be loaded by including this Javascript file: 
https://wattenberg.github.io/data/names_by_decade.js
It is formatted as comma-separated values (CSV), contained in a Javascript variable;
the first few lines look like this:

const name_data=`Name,Gender,Name-Gender,Decade,Number,Proportion
Aaban,Male,Aaban-M,2000,5.5,2.543841029340606e-06
Aaban,Male,Aaban-M,2010,10.9,5.406029402420773e-06
Aabha,Female,Aabha-F,2010,6.83,3.5474218280428824e-06
Aabha,Female,Aabha-F,2020,5.0,2.823499969428362e-06
[etc.]
The format is: name, gender, a unique identified made of the name and gender, decade,
and proportion of babies with that name born that decade.

I'd like the visualization tool to have a text entry box for a name,
and also UI to choose male or female.
There should be a "submit" button next to the text entry box.
Then, below that, I'd like a line graph showing the proportion of babies
born over time with the name entered. If the name isn't found,
the graph should be empty, with the message, "name not found".
```
