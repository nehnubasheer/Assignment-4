# Assignment-4
Calculated Columns:

Create a Calculated Column for 'Category Type': Category Type = 'Order Details'[Category] & " - " & 'Order Details'[Sub-Category]

Calculate Revenue per Order in Order Details Table:  Revenue = 'Order Details'[Amount] * 'Order Details'[Quantity]
Create a Calculated Column to Categorize Sales: Sales Category = VAR AvgAmt = AVERAGE('Order Details'[Amount]) RETURN IF('Order Details'[Amount] > AvgAmt, "Above Average", "Below Average")

Calculated Measures:

Calculate Order Count: Order Count = DISTINCTCOUNT('Order Details'[Order ID])
Calculate Average Profit in Delhi:  Avg Profit Delhi = CALCULATE(AVERAGE('Order Details'[Profit]), 'List of Orders'[City] = "Delhi")
Calculate Year-to-Date (YTD) Sales: YTD Sales = CALCULATE( [Total Sales], FILTER(ALL('Calendar'[Date]), 'Calendar'[Date] MAX('Calendar'[Date])))

Data Visualization:

Sales Target Achievement by Category: Compare actual sales with sales targets by category using a clustered column chart.

Axis: Category 

Values: Total Sales = SUM(Order Details[Amount]) vs  Total Target = SUM(Sales target[Target])

Max Profit Margin by Sub-Category: Analyze the maximum profit margin for each sub-category of products using a donut chart.

Profit Margin = DIVIDE(SUM('Order Details'[Profit]), SUM('Order Details'[Amount]))

Values: MAXX(VALUES('Order Details'[Sub-Category]), [Profit Margin])

Monthly Sales Trend: Show the trend of monthly sales over time using a line chart.

Axis: Month of Order Date

Values: Total Sales = SUM('Order Details'[Amount])

Comparison of Profit and Quantity by Sub-Category: Compare the relationship between profit and quantity sold for different sub-categories using a scatter chart.

X-axis: Total Quantity = SUM(Order Details[Quantity])

Y-axis: Total Profit = SUM(Order Details[Profit])

Details: Sub-Category

Comparison of Total Sales Amount and Target: Create cards to succinctly display the total sales amount alongside the sales target for quick comparison and analysis. Also, create a multi-row card to display the minimum target for each segment.

Card 1: Total Sales = SUM(Order Details[Amount])

Card 2: Total Target = SUM(Sales target[Target])

Multi-row card: Min Target = MIN('Sales target'[Target]) by Category

Sales Performance Matrix: Build a matrix view to analyze how actual sales compare to sales targets across different categories and months.
Rows: Category

Columns: Month

Values: Total Sales, Total Target

Geographic Sales Analysis: Visualize total sales on a map by city to identify regional sales patterns.

Location: City

Values: Total Sales

Sales Distribution by Sub-Category: Represent the sales distribution across different sub-categories using a treemap.

Group: Sub-Category

Values: Total Sales

Order Count Analysis by State: Create a funnel chart to visualize the distribution of order counts across different states.

Category: State

Values: Order Count
