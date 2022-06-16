# Kickstarting with Excel

## Overview of Project
  For the Module 1 Challenge, we were expected to use data from the kickstarter sheet and use that data to determine outcomes of plays based on different ranges of goal amounts and by theater launch dates. 
  
### Purpose
  The purpose of this analysis is to determine how well different fundraising campaigns did relative to their launch dates, and their funding goals. The dataset that was used, included thousands of different types of campaign goals and what was pledged, which was used to determine each category and their sub-categorical success rate. Also, the dataset included other information, that allowed for further analysis of which campaigns were more or less successful during different times of the year, which was determined by analyzing the launch dates of each campaign. 
  
## Analysis and Challenges
  In order to perform this analysis, a number of steps had to be taken to prepare and organize the dataset. These steps included creating parent and subcategories, that were initially grouped together, which would have otherwise limited further analysis. Thus, by separating these two categories and creating a pivot table, I was able to look at the outcomes of which parent categories were more successful than others, as well as diving deeper into how successful specific subcategories, within each parent category, did in comparison to other subcategories. For example, the parent category that was determined to have the most successful outcome was "Theater" campaigns. 

### Analysis of Outcomes Based on Launch Date
  Once it was determined that theater campaigns were most successful over all other parent categories, Louise wanted to know whether a campaign's outcome was dependent on their launch dates. In order to determine this, I had to convert epoch & Unix timestamps, using an epoch converter tool, that would provide a readable launch date for each campaign. Another pivot table and pivot chart was created to graphically represent the outcomes of all theater campaigns by their launch date, divided by months of the year. By placing filters within the pivot table, I was able to quickly analyze the outcomes of each categorized campaign in different countries.
  
  ![Theater_Outcomes_vs_Launch](https://user-images.githubusercontent.com/104864579/174192872-432600b1-0e47-46c8-b270-0e3dd26158c4.png)

### Analysis of Outcomes Based on Goals
  A pivot chart and table was created to determine which subcategories were the most successful over the rest. The subcategory, "plays" was determined to be most successful by looking at the stacked column bar chart. Upon this analysis, Louise wanted to know if the outcomes of play campaigns were dependent on the fundraising goals. 
	In order to determine whether fundraising goals factored into the campaign outcomes, a new table was created. This table was broken down into goal amount ranges, for example, less than 1000, between 1000 to 4999, 5000 to 9999, and so on. Using the kickstarter dataset, the COUNTIFS() function in excel was needed to quickly count up how many were successful, failed, or canceled for each of the aforementioned ranges. Following these calculations, the SUM() function in excel was used to count up total projects within each range. Finally, a percentage calculation was used to condense the data of each range and its outcome, so that this data was able to be represented graphically. 
	
  ![Outcomes_vs_Goals](https://user-images.githubusercontent.com/104864579/174192903-4b698bb7-4d08-423b-935e-dfe8a980967d.png)


### Challenges and Difficulties Encountered
  One of the challenges of creating this pivot table in "Theater Outcomes Based on Launch Date", was that when I applied the, "Date Created Conversion" to the "Rows" pivot table fields, the data was expressed in years and quarters, by default. In order to express the data in months, I had to adjust the row field settings by removing the years and quarters rows field settings. 
	The COUNTIFS() calculation was tricky because I had to include multiple arguments within the function, and the order of where to place each argument was challenging at first. Once I realized the appropriate order of how excel would interpret the formula, I remembered I had to include my absolute values so that excel would analyze the same data for each range and outcome values. 
	Another challenge I encountered was making the pivot chart for "Play Outcomes Based on Goal", because the lines were almost going off the chart. This could not have been an accurate representation of what was being analyzed, because the graph didn't seem to make much sense. This led me to believe that my formula functions for COUNTIFS() must not have been right. I looked at the range, "50000 or more" and the "number failed" column resulted in a low number, so I went back to the kickstarter data sheet, and filtered the goal amount to only show goals 50000 or more, and the outcome column to failed. The number I had in my table was lower than the amount in the kickstarter sheet, which verified my thought that something was not right. Then I realized that I had not included ">=" or "<=" in my COUNTIFS() formula arguments, but instead, I had only included "<" or ">", in which excel didn't count the goals that fell on the outermost part of each of the goal amount ranges. Once I fixed that for all of my columns, the graph accurately represented the data I was trying to show. I have provided an example (as shown below), of how I set up my COUNTIFS() function, for the range between 1000 to 4999, to show how I utilized the ">=" and "<=" in my range functions.
	
  ![Screen Shot 2022-06-16 at 4 17 04 PM](https://user-images.githubusercontent.com/104864579/174193559-80a4b71d-20f0-4e91-97cd-97df59db5936.png)

## Results

- What are two conclusions you can draw about the Outcomes based on Launch Date?

  One conclusion I can draw about the outcomes based on launch date data analysis, is that the month of May was the most successful time to launch a theater campaign. Another conclusion I can draw from this chart, is that summer time months have more successful theater campaign outcomes as opposed to launching theater campaigns in the winter, in which the amount failed vs. successful seem to result in a similar outcome. 
	
- What can you conclude about the Outcomes based on Goals?

  I can conclude that play outcomes based on goal are more successful when the goal is set at 4999 or lower, so a lower goal amount results in a higher success rate. Another conclusion is that a goal set at 49999 or higher, results in an increasingly lower success rate and an increasingly higher fail rate. 
  
- What are some limitations of this dataset?

  One limitation to this dataset is that countries are represented but not actual locations within each country. This could be problematic because it is trying to be determined when and where each campaigns might be more successful, which can't be found by looking at the country as a whole. 
	Another limitation is that the data is representative of a dataset over the course of 9 years, which means the sample size for each year might not be proportionally distributed. Also, the sample size for each country doesn't appear to have the same amount of sample size from each, which makes it hard to compare campaign outcome success to one another. 
  
- What are some other possible tables and/or graphs that we could create?

  Other possible tables and/or graphs that could be created would be to identify which countries had a higher amount of backers that led to successful campaign outcomes, or which countries had higher average donations. 
