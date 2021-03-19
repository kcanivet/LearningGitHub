# Creating a Salesforce Dashboard

In my volunteer data work for MitoCanada, I've had the opportunity to work with Salesforce.  Prior to this I have never used Salesforce.  Given the fact that Salesforce occupies about 1/5th of the CRM (Customer Relationship Management) market with over 150,000 companies, you will probably encounter it at some point.  Salesforce checks all the boxes for a modern service, but launched in 1999!  It was one of the first SaaS (Software as a Service) and can also claim to be a PaaS (Platform as a Service) and DBaaS (Database as a Service).  Under the hood, Salesforce uses Oracle as a primary database structure with a few other things in the mix.  Salesforce has also done a great job opening up an app marketplace for developers to build applications that work with Salesforce in a variety of ways, making the product almost infinetly expandable.

## The keys to building a dashboard

The key relationships you need to realize before you get to a dashboard is that *a report summarizes a subset of the data, and a dashboard summarizes a subset of reports.*  
`Salesforce Data -> Report(s) -> Dashboard`  
Without a report you can't go straight to a dashboard.  What you summarize and choose as a chart for a report does impact what is available for your dashboard.

### The Salesforce Report
To start a report you can go to your reports list and you will *likely* find a *New Report* button in the upper right of the menu card.  I say likely because you might not have permission based on your set up or the menu has been customized.  
To start a report there are many default templates to choose from based on the type of report you would like to build. From there you can customize the report, adding or removing columns, or changing the order.  These tasks are accomplished by going into `Edit` from the button in the upper right.  


  1. images from reports
  2. Intro
  3. Reports  
    - distilled down into tile  
    - group and/or calculate to get chart  
    - report chart drives dashboard chart
  4. Assembling the dashboard 
