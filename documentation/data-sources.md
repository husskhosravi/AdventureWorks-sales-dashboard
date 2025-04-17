# AdventureWorks Dashboard - Data Sources and ETL Documentation

This document provides an overview of the data sources and transformation processes I used in the AdventureWorks Sales Dashboard. Due to data sensitivity, specific details about the data are not included.

## Data Sources

I built the dashboard using the following 11 source tables:

1. **Sales Data.csv** - Primary fact table containing sales transactions
2. **Returns Data.csv** - Fact table for product returns information
3. **Product Lookup.csv** - Dimension table with product details including pricing
4. **Product Categories Lookup.csv** - Categorisation hierarchy for products
5. **Product Subcategories Lookup.csv** - Sub-categorisation details for products
6. **Customer Lookup.csv** - Customer demographic and contact information
7. **Territory Lookup.csv** - Geographic hierarchy for sales territories
8. **Calendar Lookup.csv** - Date dimension for time intelligence
9. **Product Metric Selection.csv** - Reference table for product metric selections
10. **Customer Metric Selection.csv** - Reference table for customer metric selections
11. **Price Adjustment.csv** - Parameter table for price adjustment scenarios

## Data Model Complexity

My AdventureWorks Sales Dashboard represents a complex analytical solution with:

- **Multiple fact tables** (Sales and Returns) in a star schema design
- **Several dimension tables** with proper relationships 
- **Supporting lookup tables** for parameters and selections
- **Date dimension** for time intelligence calculations

## Data Transformation Process

While specific details cannot be shared, my data preparation process included:

1. **Data Cleansing**
   - Handling of null values
   - Standardisation of text fields
   - Currency and numeric formatting

2. **Data Transformation**
   - Creation of calculated columns where needed
   - Date formatting and standardisation
   - Currency conversions where applicable

3. **Relationship Management**
   - Establishment of proper cardinality between tables
   - Creation of appropriate active vs inactive relationships
   - Implementation of bi-directional filtering where needed

4. **Performance Optimisation**
   - Data type optimisation for improved performance
   - Appropriate indexing and compression
