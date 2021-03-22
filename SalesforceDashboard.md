# Creating a Salesforce Dashboard

In my volunteer data work for MitoCanada, I've had the opportunity to work with Salesforce.  Prior to this I have never used Salesforce.  Given the fact that Salesforce occupies about 1/5th of the CRM (Customer Relationship Management) market with over 150,000 companies, you will probably encounter it at some point.  Salesforce checks all the boxes for a modern service, but launched in 1999!  It was one of the first SaaS (Software as a Service) and can also claim to be a PaaS (Platform as a Service) and DBaaS (Database as a Service).  Under the hood, Salesforce uses Oracle as a primary database structure with a few other things in the mix.  Salesforce has also done a great job opening up an app marketplace for developers to build applications that work with Salesforce in a variety of ways, making the product almost infinetly expandable.

## The keys to building a dashboard

The key relationships you need to realize before you get to a dashboard is that *a report summarizes a subset of the data, and a dashboard summarizes a subset of reports.*  
`Salesforce Data -> Report(s) -> Dashboard`  
Without a report you can't go straight to a dashboard.  What you summarize and choose as a chart for a report does impact what is available for your dashboard.

### The Salesforce Report
To start a report you can go to your reports list and you will *likely* find a *New Report* button in the upper right of the menu card.  I say likely because you might not have permission based on your set up or the menu has been customized.  
To start a report there are many default templates to choose from based on the type of report you would like to build. From there you can customize the report, adding or removing columns, or changing the order.  These tasks are accomplished by going into `Edit` from the button in the upper right.  

#### Editing the Report Contents
![Salesforce Dashboard Outline][Dashboard]

[Dashboard]: https://github.com/kcanivet/LearningGitHub/blob/main/Salesforce_Report_edit1_outline.jpg "Setting up a Report - Edit {Outline View}"  

On the left side of the edit menu is a choice between `Outline` and `Filter`.  `Outline` is where you can make changes to the data that appears in your report.  Drag an item up or down to change the column order, Hit the "x" to remove a column, Or search for and add a new column by using the search box with the magnifying glass.  At the top of this menu are sections to group rows or columns, I'll mention those in more detail when I talk about report charts.  

![Salesforce Dashboard Outline][Dashboard2]

[Dashboard2]: https://github.com/kcanivet/LearningGitHub/blob/main/Salesforce_Report_edit1_filter.jpg "Setting up a Report - Edit {Filter View}"  

Switching over to the `Filter` view, this is where you can limit or filter the data in the report.  For this project, the goal was to show the impact that donation amount had on the overall total of funds raised.  In this example I was investigating the donation amount greater than $100 and less than $500.  You will notice the bounding filters along with the default filters on the left side of the image.  The other two segments for investigation were donation amounts less than $100 and donation amounts greater than $500.  If all you wanted to do was look though the data you could just modify the filter to look at the different donation classifications.  In order to view the data as separate tiles on the dashboard however, I needed to douplicate the report and set a separate filter for each one.  

#### Adding a chart

![Salesforce Dashboard Outline][Dashboard3]

[Dashboard3]: https://github.com/kcanivet/LearningGitHub/blob/main/Salesforce_Report_edit1_chart.jpg "Report Chart Settings"  

The first thing needed to build a chart on a Salesforce report is to summarize or group something.  For these reports I chose to group by province and total the amount of donations (overall and by group).  Since MitoCanada is a charity that started in Alberta and grew across the country, it was important to see where the donations were coming from.  This will allow the charity to plan activities and to know where to raise awareness. 
Depending on the type of data and the grouping, you get a few standard chart options.  I couldn't find a way to customize the colours, but the default options where sufficient.  As I mentioned earlier, your choices here do impact the final dashboard.

#### Data Cleaning or the visual... which comes first?
As I began building the reports and ultimately the Dashboard, there was an issue with the province data that needed to be addressed.  Like any data endevor, data cleaning added a significant amount of time to the project. The province was particularily problematic.  Loading data into salesforce from multiple sources without any standardization or anyone managing the data led to provinces being entered as the short form (AB), the long form (Alberta), or somewhere in between (Alta.).  Although I noticed the multiple versions of the province names inspecting the raw data, building the chart and visualizing the data helped to show how widespread the issue was.  With data analytics there is usually an itterational process between the data and the visual that represents it.  Tweaking one impacts the other and around it goes.  The data cleaning process with Salesforce is a potential article on its own...  *(Insert Link to Potential future article here ;P )*  

## The Dashboard



  1. images from reports
  2. Intro
  3. Reports  
    - distilled down into tile  
    - group and/or calculate to get chart  
    - report chart drives dashboard chart
  4. Assembling the dashboard 
