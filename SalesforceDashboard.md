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
![Salesforce Dashboard Outline][Dashboard_edit]

[Dashboard_edit]: https://github.com/kcanivet/LearningGitHub/blob/main/Salesforce_Dashboard_edit_view.jpg "Dashboard Edit View"  

To begin the dashboard creation you need to click the `+ Component` button in the upper right.  This takes you to a list of all of your reports.  You then select what from the report you want to display and how.  I highlighted 3 components from the same report we looked at earlier, These were added to the final dashboard separately.  Once you have a component selected you place it on the dashboard layout, sizing it to the layout rectangles shown at the bottom of the image as a dark blue / light blue grid.  There are some options to set for each tile or component, but if you are looking for ultimate control over the appearance of the end result there aren't many choices.  There is likely an add-on to expand the options or you can link Salesforce to other visualization tools like Power BI etc to get the result you are looking for.  
The final piece to this dashboard was the addition of the filters.  These allow a bit more interactivity with the data and eliminate the need for multiple dashboards. I added 3 filters:  
  1. Results by province  
  2. Results by country (Canada vs the rest of the world)  
  3. Won vs Lost.  

The first two are self explanitory, the "won vs lost" was a way to eliminate donations that were expected, but didn't utimately complete.  There were some attempts in the past to forcast revenue by entering expected donations but this practice was shortlived.  To eliminate these expected donations in a future data cleansing they first need to be identified!

### The End result

The end result is fairly similar to the edit view.  Each tile / component has a link to the report that generated it. When I started working with MitoCanada we had a conversation about what we wanted to achieve.  With this dashboard I was able to meet the majority of the CEO/CEO's wishlist items in one place.  She wanted to illustrate that donation amount had a bigger impact than number of donors on the fundraising efforts. She wanted to know if the donations were coming from individuals (Households) or from corporations (Organizations). Finally she wanted to know which method or donation partner is where the majority of the donations were coming from.  Check, check and check.
I continue to investigate the data set to pull out other details and insights, but this dashboard was a great start!  

![Salesforce Dashboard Outline][Dashboard_final]

[Dashboard_final]: https://github.com/kcanivet/LearningGitHub/blob/main/MitoCanada_Dashboard.jpg "Final Dashboard"  

