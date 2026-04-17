# Sales Performance & Revenue Growth Dashboard

## Objective
To build an interactive Power BI dashboard that helps sales managers, analysts, and leadership teams track revenue, profit, sales achievement, growth trends, product performance, regional performance, and sales executive productivity.

## Tools Used
- Power BI Desktop
- Power Query
- DAX
- Excel / CSV
- GitHub
- LinkedIn

## Dataset Description
The sample dataset includes sales transactions across regions, categories, products, channels, and sales executives.

### Main Columns
- Date
- Month
- Quarter
- Year
- Region
- State/City
- Sales Executive Name
- Product Category
- Product Name
- Units Sold
- Selling Price
- Revenue
- Cost
- Profit
- Profit Margin %
- Customer Type (New/Existing)
- Sales Channel (Online/Offline)
- Target Sales
- Actual Sales
- Achievement %
- Growth %

## Power Query Steps
1. Import CSV/Excel file into Power BI
2. Check null values and replace/remove them
3. Fix data types for date, text, currency, and percentage fields
4. Remove duplicates
5. Rename columns for clarity
6. Create Month, Quarter, and Year columns if not already present
7. Validate Revenue, Profit, and Achievement values
8. Load cleaned data into the data model

## Suggested DAX Measures
```DAX
Total Revenue = SUM('SalesData'[Revenue])

Total Cost = SUM('SalesData'[Cost])

Total Profit = SUM('SalesData'[Profit])

Profit Margin % = DIVIDE([Total Profit], [Total Revenue], 0)

Total Units Sold = SUM('SalesData'[Units Sold])

Target Sales = SUM('SalesData'[Target Sales])

Actual Sales = SUM('SalesData'[Actual Sales])

Achievement % = DIVIDE([Actual Sales], [Target Sales], 0)

Growth % =
DIVIDE(
    [Total Revenue] - CALCULATE([Total Revenue], DATEADD('Calendar'[Date], -1, MONTH)),
    CALCULATE([Total Revenue], DATEADD('Calendar'[Date], -1, MONTH)),
    0
)
```

## Dashboard Features
- KPI cards for Revenue, Profit, Units Sold, Achievement %, Growth %
- Revenue by Region
- Product Category Performance
- Monthly Revenue Trend
- Sales Channel Distribution
- Target vs Actual Sales
- Matrix table for region-level comparison
- Slicers for Region, Category, Channel, Sales Executive, Month

## Key Insights
- Identify top-performing regions
- Track profitable product categories
- Compare target vs actual sales
- Monitor monthly growth trends
- Evaluate channel effectiveness
- Assess sales executive performance

## Screenshots Section
Add dashboard screenshots in a `screenshots/` folder and reference them like this:

```md
![Dashboard Overview](screenshots/dashboard-overview.png)
![Revenue Analysis](screenshots/revenue-analysis.png)
```

## Conclusion
This project demonstrates practical skills in sales analytics, business intelligence, KPI design, DAX, Power Query, dashboard design, and business storytelling using Power BI.
