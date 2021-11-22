# Kickstarting with Excel

## Overview of Project

Cleaning and analyzing the provided Kickstarter data to provide necessary context to ensure a new campaign's success.

### Purpose

The purpose of the analysis was to know how different campaigns fared in relation to their launch dates and funding goals.

## Analysis and Challenges

### Analysis of Outcomes Based on Launch Date

The purpose of this portion of the analysis was to visualize campaign outcomes in reference to their launch dates.  To do this, I first used the YEAR() function on the column labeled "Date Created Conver." to extract only the year from the dates in that column.  Then, I created a pivot table using the data in the Kickstarter worksheet in a new worksheet labeled "Theater Outcomes by Launch Date."  This purpose of the table was to show the outcomes of theater Kickstarters separated by month.  The way to do this was to place "Parent Category" and "Years" under the filters section, "Outcomes" under the columns section, "Date Created Conver" under the rows section, and "Count of Outcomes" under the values section.  The resulting table looked as follows:

![This is an image](https://github.com/amacancio/Kickstarter-analysis/issues/1#issue-1059514928)

From this table, I created a line chart to better visualize the results.  It looked as follows:

![This is an image](https://github.com/amacancio/Kickstarter-analysis/blob/main/Resources/Theater_Outcomes_vs_Launch.png)

### Analysis of Outcomes Based on Goals

The purpose of this portion of the analysis was to visualize campaign outcomes in reference to their goals.  To do this, I utilized the COUNTIFS() function to create a table detailing the number of successful, failed, and canceled Kickstarter play campaigns as well as the percentages for each based on the funding goal amount.  The amounts were further separated by funding goal intervals of $5,000, with the lower range as less than $1,000 and upper range as more than $50,000.  The COUNTIFS() function therefore had three to four criteria, dependent on the specified funding goal interval.  For example, in order to find the number of successful play campaigns with a funding goal of less than $1,000, the formula was the 'following:' =COUNTIFS(Kickstarter!D:D, "<1000", Kickstarter!F:F, "successful", Kickstarter!R:R, "plays").  Although the "plays" criteria never changed, the goal amounts corresponding to column D and the outcomes corresponding to column F changed based on the goal interval or outcome being specified.  Then, I populated the total column utilizing the SUM() function.  Finally, I found the percentages by simply dividing each amount by the total.  Below is the resulting table.

![This is an image](https://github.com/amacancio/Kickstarter-analysis/issues/2)

From this table, I created a line chart using only the percentages to visualize the results.  It looked as follows:

![This is an image](https://github.com/amacancio/Kickstarter-analysis/blob/main/Resources/Theater_Outcomes_vs_Launch.png)

### Challenges and Difficulties Encountered

Though I personally didn't face any difficulty in the Analysis of Outcomes Based on Launch Date, there is a challenge when creating the pivot table pictured above.  When you first add "Date Created Conver" to the rows section, it automatically populates with two other labels: "Years" and "Quarters."  In order for the data to be accurately displayed, you have to remove those two extra labels by dragging and dropping them onto the spreadsheet so that the data will be arranged by months.

For the Analysis of Outcomes Based on Goals, the challenge I faced was ensuring that each criteria in the COUNTIF() formula was accurately defined so that the resulting amount was correct.  Each criteria referenced columns in the Kickstarter worksheet.  Further, each formula for each cell had a criteria changed to get the necessary amount.  Keeping track of each changing variable was a challenge.

## Results

- What are two conclusions you can draw about the Outcomes based on Launch Date?

According to the line graph, May, June, and July are the three best months to launch a campaign.  In addition, December is the worst month to launch a campaign, considering it has the fewest number of successful campaigns as compared to other months, as well as having an almost equal number of failed campaigns.

- What can you conclude about the Outcomes based on Goals?

The goals with the highest success rate were less than $1,000 and between $1,000 and $4,999 with success rates of 76% and 73%, respectively.  Alternatively, the goal with the lowest success rate was between $45,000 and $49,999, with a success rate of 0%.

- What are some limitations of this dataset?

The most obvious limitation of this dataset is the lack of reasoning given for the cancelation of campaigns.  It's not possible to know if the campaigns were canceled due to lack of funds, issues with the productions themselves, or a variety of other potential reasons.  Furthermore, while the data can be filtered by country, there is no data indicating city or region, which would add another layer of detail to the analysis and assist in creating an even clearer picture of campaign trends.

- What are some other possible tables and/or graphs that we could create?

Options for additional tables and/or graphs include a table with each parent category and it's corresponding outcomes, a graph representing the relation between backers and average donations, a table utilizing the staff pick and outcome to determine if staff picks influence campaign success or failure, and more.
