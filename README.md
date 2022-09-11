# Kickstarting with Excel

## Overview of Project
The client is planning on launching a Kickstarter campaign for a theater play and wants to know the feasibility of one.

### Purpose
A number of Kickstarter projects over a period of 8 years (from 2009 to 2017) was collected and then analyzed to find any trends in how successful a project will be depending on timing and the goal amount. A particular emphasis was placed on theater projects, specifically plays, to determine the feasibility of launching a Kickstarter campaign for a play and the parameters that will ensure the best chance of success. The main points of focus from the client are the best time and the best goal amount when launching the project.

## Analysis and Challenges
Comparing the success rate of a Kickstarter project to parameters like the launch date or the amount set as the goal can be done with charts. However, a chart that handles thousands of data points would be heavily cluttered, so one solution is to categorize the data into groups. A Pivot Table allows the launch date would be grouped by month while focusing on the outcome column only (and filter out the live projects to leave only the successful, the failed, and the canceled). Additionally, Pivot Tables allow for filtering according to any desired parameters including the launch year or the parent category of a project. When grouping the goals into different intervals is difficult to do with Pivot Tables, a series of COUNTIFS functions can accomplish the desired results of grouping the outcomes within the goal amount ranges.

The necessary charts can then be created using these organized data.

### Analysis of Outcomes Based on Launch Date
This chart below illustrates the relationship between the time of the year and the outcomes of the Kickstarter theater projects.

![Theater Outcomes vs. Launch](https://github.com/Owen-Wang1234/Kickstarter-Analysis/blob/main/resources/Theater_Outcomes_vs_Launch.png)

Generally, most of the campaigns are successful, as the line for successful projects always stay above the line for failed projects. Very few get canceled, and one month (October) does not even have any canceled projects. Most projects start in the summer range (from May to August) although there are bumps in February and October. December appears to present the worst chance of success; December has the fewest projects launched, and there are nearly equal numbers of successful and failed projects (the difference is only two more successful projects).

### Analysis of Outcomes Based on Goals
This chart below illustrates the relationship between the goal set for a Kickstarter play project and the resulting outcome.

![Outcomes vs. Goals](https://github.com/Owen-Wang1234/Kickstarter-Analysis/blob/main/resources/Outcomes_vs_Goals.png)

One feature standing out is that the lines for successful and failed projects actually intersect three different times, which implies that there are two ranges of goal values where Kickstarter projects are more likely to succeed. Generally plays on Kickstarter are more likely to succeed when the goal is below $15,000 (with a drop after $5,000), but there is also a good chance at success for plays with a goal between $35,000 and $45,000. Interestingly, there are no canceled Kickstarter plays.

### Challenges and Difficulties Encountered
A quick look at the launch and due dates shows that the dates were formatted to Epoch time, which is very unlikely to be understood by most people unfamiliar with Unix timing (the number of seconds past Midnight January 1, 1970). Thus, columns for date conversions were added where the time stamp is converted into the more conventionally familiar MM/DD/YYYY format. Additionally, the parent category and the subcategory were both combined in one column. Two more columns were added in order to hold the separated parent category and the subcategory.

## Results

- What are two conclusions you can draw about the Outcomes based on Launch Date?
The month of May has the most Kickstarter theater projects created and the most successful projects, and the total project and successful project numbers slope downwards monthly until September.
The month of December has the fewest Kickstarter theater projects created and the fewest successful projects; although December does not have the most failed projects there were enough to nearly intersect with the successful projects line.
- What can you conclude about the Outcomes based on Goals?
Kickstarter play projects are more likely to succeed when the goal is less than $15,000, but there is an intersting interval where successful projects take a greater distribution between the goals $35,000 and $45,000.
- What are some limitations of this dataset?
One observation is that this dataset cannot necessarily provide much detail about how much advertising was done for a project beyond two boolean columns for "Staff Pick" and "Spotlight." Additionally, the main orchestrator(s) of the projects are not provided, so it can not be verified whether they might have some influence on the success or failure of a project.
- What are some other possible tables and/or graphs that we could create?
After the initial set of charts and tables were created, the next set should reflect the refinement of the analysis. Some specific examples include charting the relationship between the length of the project (either in days or months) and the outcomes, and perhaps the expected funding rate (goal divided by project length) may help determine if a project was given reasonable parameters.
