# AdventureWorks Sales Dashboard - Data Model Documentation

## Data Model Overview
My Power BI model consists of multiple related tables forming a star schema design for sales analysis.

## Table Structure

### Fact Tables
1. **Sales Data**
   - CustomerID
   - OrderDate
   - OrderNumber
   - OrderQuantity
   - ProductKey
   - Quantity Type
   - StockDate

2. **Returns Data**
   - ProductKey
   - ReturnDate
   - ReturnQuantity
   - TerritoryKey

### Dimension Tables
1. **Territory Lookup**
   - Continent
   - Country
   - Region
   - Subcategory/State
   - Territory Name

2. **Customer Lookup**
   - AnnualIncome
   - Birth Year
   - BirthDate
   - Customer Full Name (ID)
   - Customer Priority
   - Customerbuy

3. **Calendar Lookup**
   - ID/Date
   - Day Name
   - Day of week
   - Month
   - Month Name

4. **Product Lookup**
   - Discount Price
   - ModelName
   - Price Point
   - PriceDate
   - ProductCost
   - ProductDescription
   - ProductKey
   - ProductName
   - ProductPrice

5. **Product Categories Lookup**
   - Category/Name
   - Product/Subcategory 
   - Category

6. **Product Subcategories Lookup**
   - ProductKey
   - ProductSubcategoryKey
   - SubCategoryName

7. **Price Adjustment**
   - Price Adjustment
   - Price Adjustment Value

8. **Product Metric Selection**
   - Product Metric Selection
   - Customer Metric Selection
   - Product Metric Selection 2
   - Product Metric Selection X

## Key Relationships
- Sales Data connects to Product Lookup via ProductKey
- Sales Data connects to Customer Lookup via CustomerID
- Returns Data connects to Product Lookup via ProductKey
- Territory Lookup provides geographical hierarchies
- Calendar Lookup provides time intelligence capabilities
- Product Lookup connects to Product Categories via category relationships

## Model Design Notes
- I implemented a star schema design with Sales Data as the primary fact table
- Dimensional tables provide attributes for analysis and filtering
- The model supports hierarchical navigation through territories, products and time
- Multiple lookup tables enable rich slicing and dicing capabilities

## Usage
This data model supports analysis of:
- Sales performance by territory, product, and time
- Customer purchasing patterns
- Product returns analysis
- Price and discount impact analysis
