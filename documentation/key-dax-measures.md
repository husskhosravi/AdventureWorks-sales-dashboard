# AdventureWorks Dashboard - Key DAX Measures

This document showcases the exact DAX measures I developed for the AdventureWorks Sales Dashboard, demonstrating my proficiency with DAX and Power BI development.

## Core Business Calculations

### Total Revenue
```dax
Total Revenue =
sumx(
    'Sales Data',
    'Sales Data'[OrderQuantity] *
    RELATED(
        'Product Lookup'[ProductPrice]
    )
)
```
I calculated total revenue using SUMX iterator to multiply each order's quantity by the related product price.

### Total Profit
```dax
Total Profit =
[Total Revenue] - [Total Cost]
```
A straightforward profit calculation building on my revenue measure.

### Return Rate
```dax
Return Rate =
    ([Quantity Returned]/
    [Quantity Sold]
)
```
This calculates the percentage of sold items that are returned.

### Total Cost
```dax
Total Cost =
SUMX(
    'Sales Data',
    'Sales Data'[OrderQuantity] *
    RELATED(
        'Product Lookup'[ProductCost]
    )
)
```
I mirrored my revenue calculation approach for consistency, calculating total cost using SUMX.

## Advanced Calculations

### Adjusted Profit
```dax
Adjusted Profit =
[Adjusted Revenue] - [Total Cost]
```
I built this complex calculation by layering multiple measures.

### Average Revenue Per Customer
```dax
Average Revenue Per Customer =
DIVIDE(
    [Total Revenue],
    [Total Customers]
)
```
This per-entity calculation uses DIVIDE to properly handle potential division by zero.

### High Ticket Orders
```dax
High Ticket Orders =
CALCULATE(
    [Total Orders],
    FILTER(
        'Product Lookup',
        'Product Lookup'[ProductPrice] > [Overall Average Price]
    )
)
```
I used FILTER to apply complex criteria, identifying orders with above-average pricing.

## Time Intelligence

### 90-day Rolling Profit
```dax
90-day Rolling Profit =
CALCULATE(
    [Total Profit],
    DATESINPERIOD(
        'Calendar Lookup'[Date],
        MAX(
            'Calendar Lookup'[Date]
        ),
        -90,
        DAY
    )
)
```
This demonstrates advanced time intelligence with a rolling period calculation.

### YTD Revenue
```dax
YTD Revenue =
CALCULATE(
    [Total Revenue],
    DATESYTD(
        'Calendar Lookup'[Date]
    )
)
```
A year-to-date calculation using the DATESYTD time intelligence function.

### Previous Month Orders
```dax
Previous Month Orders =
CALCULATE(
    [Total Orders],
    DATEADD(
        'Calendar Lookup'[Date],
        -1,
        MONTH
    )
)
```
This uses DATEADD for period-over-period comparison.

## Technical Skills Demonstrated

My DAX measures showcase several important skills:

1. **Table Iteration** - Using SUMX to process rows individually
2. **Relationship Navigation** - Using RELATED to access data across tables
3. **Measure Layering** - Building complex calculations from simpler measures
4. **Time Intelligence** - Implementing period-to-date and rolling period calculations
5. **Context Modification** - Using CALCULATE to modify filter context
6. **Safe Division** - Using DIVIDE to handle potential division by zero
7. **Date Functions** - Working with date tables and time calculations
