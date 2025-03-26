---
layout: default
title: Documentation for names_by_decade.js
---

# Boston city employee compensation, 2024

The file [employee-comp-2024.js](https://wattenberg.github.io/data/employee-comp-2024.js) contains data on the compensation of Boston city employees in 2024.

Each row of the file represents an individual employee, identified by name, job title, and department. The row also holds compensation for 2024, both the total and a breakdown by different type.

## Data source

The data comes from the city of Boston. [See this page](https://data.boston.gov/dataset/employee-earnings-report) for details, including what the various fields mean. You can find many more related data sets at https://data.boston.gov


## Data contents and format

This is a special format designed to be easy to use for a Javascript program that can be run from your own computer's file system.
It is essentially putting a comma-separated table into a Javascript variable. The table itself looks like this:
```
const bostonPayroll2024 = 
`_id,NAME,DEPARTMENT_NAME,TITLE,REGULAR,RETRO,OTHER,OVERTIME,INJURED,DETAIL,QUINN_EDUCATION,TOTAL GROSS,POSTAL
1,"Demesmin,Stanley",Boston Police Department,Police Lieutenant (Det),"161,306.48","105,724.70","6,906.86","223,773.96",12.52,"45,597.23","32,261.36","575,583.11",02052
2,"Sordillo,Paul J",Facilities Management,Building Services Fleet Mgr,"108,815.78","20,055.71","413,783.39","24,772.61",,,,"567,427.49",02127
3,"Smith,Sean P",Boston Police Department,Police Lieutenant,"155,265.97","96,850.51","21,740.86","148,505.22",,"97,045.79","38,816.51","558,224.86",02186
[etc.]
```
The fields are:
* _id: A numeric ID; probably not relevant for visualization
* NAME: Employee name
* DEPARTMENT_NAME: The department where the employee works
* TITLE: The employee's job title
* REGULAR: "Regular" annual compensation (typically salary)
* RETRO: Retroactive earnings, including overtime
* OTHER: Bonuses, vacation buybacks, etc.
* OVERTIME: For work beyond normal hours
* INJURED: Regular / retroactive injured earnings
* DETAIL: Paid (police) detail work, e.g. working at a construction site after hours
* QUINN_EDUCATION: Education incentive (police) 
* TOTAL_GROSS: Total of all earnings, from all categories
* POSTAL: Zip code


Note that these definitions are an approximation of the exact legal meanings; [this page](https://data.boston.gov/dataset/employee-earnings-report/resource/609a6014-5ab0-49d9-8c38-1389e7bf0d41) contains precise definitions.

## How to use with ChatGPT

### Simple bar chart

Here's a prompt that provides a starting point for making a visualization with this data.
It lets you see a simple bar chart of total compensation.

```
I am building a data visualization tool,
and would like you to write the code for me. 

From a technical perspective:
I want a standalone HTML page that I can run locally from my computer.

The data should be loaded by including this Javascript file: 
https://wattenberg.github.io/data/employee-comp-2024.js
It is formatted as comma-separated values (CSV), contained in a Javascript variable;
the first few lines look like this:


const bostonPayroll2024 = 
`_id,NAME,DEPARTMENT_NAME,TITLE,REGULAR,RETRO,OTHER,OVERTIME,INJURED,DETAIL,QUINN_EDUCATION,TOTAL GROSS,POSTAL
1,"Demesmin,Stanley",Boston Police Department,Police Lieutenant (Det),"161,306.48","105,724.70","6,906.86","223,773.96",12.52,"45,597.23","32,261.36","575,583.11",02052
2,"Sordillo,Paul J",Facilities Management,Building Services Fleet Mgr,"108,815.78","20,055.71","413,783.39","24,772.61",,,,"567,427.49",02127
3,"Smith,Sean P",Boston Police Department,Police Lieutenant,"155,265.97","96,850.51","21,740.86","148,505.22",,"97,045.79","38,816.51","558,224.86",02186
[etc.]

The fields are:
* _id: A numeric ID; probably not relevant for visualization
* NAME: Employee name
* DEPARTMENT_NAME: The department where the employee works
* TITLE: The employee's job title
* Multiple fields for different types of compensation ("REGULAR", "RETRO", etc.)
* POSTAL: Zip code

I'd like the visualization tool to show a bar chart of
job titles vs. the average total compensation of people with that job title.
Please only show bars for job titles where there are at least 10 employees with that job title.
I'd like the bars to be horizontal, with compensation amount on the x-axis.
```

### More complex prompt
This prompt shows that you can actually see all the data at once! Note that visualizations that are this complex can take a few seconds to load.

```
I am building a data visualization tool,
and would like you to write the code for me. 

From a technical perspective:
I want a standalone HTML page that I can run locally from my computer.

The data should be loaded by including this Javascript file: 
https://wattenberg.github.io/data/employee-comp-2024.js
It is formatted as comma-separated values (CSV), contained in a Javascript variable;
the first few lines look like this:


const bostonPayroll2024 = 
`_id,NAME,DEPARTMENT_NAME,TITLE,REGULAR,RETRO,OTHER,OVERTIME,INJURED,DETAIL,QUINN_EDUCATION,TOTAL GROSS,POSTAL
1,"Demesmin,Stanley",Boston Police Department,Police Lieutenant (Det),"161,306.48","105,724.70","6,906.86","223,773.96",12.52,"45,597.23","32,261.36","575,583.11",02052
2,"Sordillo,Paul J",Facilities Management,Building Services Fleet Mgr,"108,815.78","20,055.71","413,783.39","24,772.61",,,,"567,427.49",02127
3,"Smith,Sean P",Boston Police Department,Police Lieutenant,"155,265.97","96,850.51","21,740.86","148,505.22",,"97,045.79","38,816.51","558,224.86",02186
[etc.]

The fields are:
* _id: A numeric ID; probably not relevant for visualization
* NAME: Employee name
* DEPARTMENT_NAME: The department where the employee works
* TITLE: The employee's job title
* Multiple fields for different types of compensation ("REGULAR", "RETRO", etc.)
* POSTAL: Zip code

I'd like the visualization tool to show a treemap of the data. The treemap should fill the entire browser window,
to use space efficiently. The top level of hierarchy should
represent the department, the next level should be job title, and the nodes should be employees.
The area of a node should represent the total compensation of the employee. 
Colors of the nodes should reflect the department. 
The borders of each node should be 1/2 pixel wide and light gray. 
Borders of departments should be 2 pixels wide and white.

When the user hovers the mouse over a node, they should see a well-formatted hover card showing
all the field values for that node. The employee name, job title, and total compensation should be
in large type; the other fields should be in smaller type. Field names should be flush left;
field values should be flush right. Round all dollar amounts to the nearest dollar.

When the user clicks on a node, it should launch a Google search for the employee's name, plus the word "boston", in a new tab.
```
