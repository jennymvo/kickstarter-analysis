# kickstarter-analysis: An Analysis of Kickstarter Campaigns
Performing analysis on Kickstarter to uncover trends 
# Kickstarting with Excel

## Overview of Project
The project consists of a database of kickstarter projects, and any relevant data that pertains to the project.

### Purpose
The purpose of this project is to better understand the overall success and falure rate of the different theater and play kickstarter campaigns and to analyze for any trends in the dates and goals. 

## Analysis and Challenges

### Analysis of Outcomes Based on Launch Date
To analyze the outcomes of theater kickstarter campaigns based on the launch date month, a pivot table was created using the information from the kickstarter worksheet.

The year of the launch date of the kickstarter was determined by the "Date Created Conversion" Column, by using the following format:

=year()

Fields from the column headers of the kickstarter worksheet were dragged to the areas:

1. Filters:
    1. Parent Category
    2. Years
2. Columns
    outcomes
3. Rows
    Date Created Conversion
4. Values
    outcomes

When the "Date Created Conversion" was dragged into "Rows", different parts of the date was separated out as sub-categorial options for organizing the data. All of the different fields were deleted until the Row labels only showed the month. 

The Pivot table Fields showed as:
![Pivot Table Fields for Outcomes Based on Launch Date](https://github.com/jennymvo/kickstarter-analysis/blob/main/images/launch_date_PivotTableFields.png)

The parent Catagory in the pivot table was filtered to "theater", and the column lables were arranged by "successful," "failed," and "canceled" by using the filter icon next to "Column labels" and arranging by Z to A order. 

The resulting pivot table is shown as:
![Pivot table for outcomes based on launch date](https://github.com/jennymvo/kickstarter-analysis/blob/main/images/launch_date_PivotTable.png)

A line chart was created using the data from this table:

![Line chart showing the theater outcomes based on launch date](https://github.com/jennymvo/kickstarter-analysis/blob/main/resources/Theater_Outcomes_vs_Launch.png)
    
### Analysis of Outcomes Based on Goals
To analyze the outcomes of the kickstarter campaigns based on the goals, the kickstarter campaigns were grouped in increments of $5000, from less than $1000, $1000 to $4999, etc until $50,000 or more. 

The number of kickstarters with outcomes of "sucessful", "failed", and "canceled" were calculated from each monetary category, then summed for determining the total number of projects from those monetary categories. the percentage of successful, failed, and canceled and kickstarter campaigns were then determined. 

For determining the number of successful, failed, and canceled products, the =countifs() function was used, with filtering for certain strings from the "outcome", "subcategory" and "goal" ranges. 

An example of one of the calculations for determining the number of "successful" campaigns is here:
![countifs() for goals](https://github.com/jennymvo/kickstarter-analysis/blob/main/images/countifs_goals.png)

This was used with the F column filered for "failed" and "canceled" for their respective columns. 

For total projects, the sum of the row of values from the sucessful, failed, and cancelled campaigns were determined using the =sum() function. 

To find the percentage successful and failed projects, the value from the outcome of the project was divided by the total number of projects, then the number format was changed to "percentage"

The resulting table looks like this:
![Table of outcomes based on goals](https://github.com/jennymvo/kickstarter-analysis/blob/main/images/table_goals.png)

A line graph with the x-axis as the goal level and the percentage of successful and failed were plotted against the y-axis, resulting in a table like this:

![Outcomes based on goal](https://github.com/jennymvo/kickstarter-analysis/blob/main/resources/Outcomes_vs_Goals.png)

### Challenges and Difficulties Encountered
A challenge that I faced while doing this assigment was using a range of rows for determining the number of successful, failed, and canceled campaigns. The inaccurate number of rows resulted in an incorrect calculation for each outcome. When I took the range out for the calculation to be based on all values within the row, it fixed the proble. 

## Results

- What are two conclusions you can draw about the Outcomes based on Launch Date?

1. The most sucessful campaigns were launched during the summer.
2. The campaigns during December have the lowest success rate. 

- What can you conclude about the Outcomes based on Goals?

The more ambitious goals ($45,000 and up) have the highest failure rate, and the goals that are less ambitious ($4999 and lower) have the highest success rate

- What are some limitations of this dataset?

The dataset has the average donation, but it does not show the range of donation amounts, or if the kickstarter gave any incentives for backing or certain types of advertisements that could influence the success of the campaign. 

- What are some other possible tables and/or graphs that we could create?

Some tables that we could create are:
1. to compare the outcomes of the kickstarter based the categories goals
2. create box and whisker plots of the different categories with the goal amounts, comparing the boxes of successful, failed, and cancelled. 
