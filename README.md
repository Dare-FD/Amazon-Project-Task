# AMAZON PRODUCT DATASET ANALYSIS 
This project presents an in-depth analysis of Amazon product data using Microsoft Excel. The report covers pricing, discounts, reviews, ratings, and product categories. The dashboards provide visual insights to support business decision-making.

## TOOLS USED
- Microsoft Excel
  - Conditional Formatting
  - Calculated Column
  - Power Query
  - Pivot Tables
  - Dashboard Charts
  - Slicers
   
## METHODOLOGY
This project involved analyzing Amazon product data using Excel. The goal was to clean, transform, and analyze the dataset to generate actionable insights. Below are the key steps followed:
1. ### Data Cleaning & Preparation
- Converted the raw dataset into an Excel Table for easier referencing, sorting, and filtering.
- Missing values:
   - Used Conditional Formatting to highlight blank cells in important numeric fields like rating count. 
   - Replaced missing numeric entries with 0 where appropriate.
   - Replaced irregular characters like | and blank spaces that indicated incomplete data.
- Numbers and Commas:
   - Converted text-formatted numbers into numeric values for formulas and pivot table compatibility.

2. ### Handling Duplicates
- Used Conditional Formatting to identify duplicate product ids.
- Grouped the duplicates using Power Query, selecting the most complete entry based on: Highest rating count and most accurate or up-to-date information

3. ### Text Cleanup and Transformation
- Created short names for long product titles using:
   - Helper columns (manually in early stages)
   - Power Query for scalable extraction and clean-up
- Extracted the main product category from complex strings in the category column using:
   - LEFT, FIND, and TEXTSPLIT functions
