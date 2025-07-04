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
### 1. Data Cleaning & Preparation
- Converted the raw dataset into an Excel Table for easier referencing, sorting, and filtering.
- Missing values:
   - Used Conditional Formatting to highlight blank cells in important numeric fields like rating count. 
   - Replaced missing numeric entries with 0 where appropriate.
   - Replaced irregular characters like | and blank spaces that indicated incomplete data.
- Numbers and Commas:
   - Converted text-formatted numbers into numeric values for formulas and pivot table compatibility.

### 2. Handling Duplicates
- Used Conditional Formatting to identify duplicate product ids.
- Grouped the duplicates using Power Query, selecting the most complete entry based on: Highest rating count and most accurate or up-to-date information

### 3.Text Cleanup and Transformation
- Created short names for long product titles using:
   - Helper columns (manually in early stages)
   - Power Query for scalable extraction and clean-up
- Extracted the main product category from complex strings in the category column using:
   - LEFT, FIND, and TEXTSPLIT functions
  
### 4. Derived Columns
Created new calculated columns to support deeper analysis:

| **Column Name**       | **Description**                                                       |
|-----------------------|-----------------------------------------------------------------------|
| Discount Percentage   | (Actual Price - Discounted Price) / Actual Price * 100                |
| Potential Revenue     | Actual Price × Rating Count                                           |
| Price Range Bucket    | Categorized prices into <₹200, ₹200–₹500, and >₹500                   |
| Rating Bucket         | Grouped ratings into 0–2.9, 3.0–3.9, 4.0–4.4, 4.5–5.0                 |
| Combined Score        | Rating + (Rating Count ÷ 1000) to rank top-performing products        |

### 5. Pivot Table Analysis
- Created a pivot table for each of the 14 business questions, using fields such as:
  - Main category, product name, rating count, rating, actual price, discount percentage, etc.
- Used filters, row/column labels, and calculated values to extract key insights.

### 6. Dashboard Creation
- Designed an interactive Excel Dashboard to present summary insights.
- Limited dashboard display to the most important insights to avoid clutter.
- Grouped insights into logical sections such as Product Overview, Rating & Review Insights, Pricing and Discount Insight.
- Used clean layout, uniform fonts, color-coded tiles, and slicers for interactivity.
- Visualized results with:
  - Column Charts
  - Bar Charts
  - Pie Charts
  - Slicers
  
## ANALYSIS QUESTIONS ANSWERED
1. What is the average discount percentage by product category? 
2. How many products are listed under each category? 
3. What is the total number of reviews per category?  
4. Which products have the highest average ratings? 
5. What is the average actual price vs the discounted price by category? 
6. Which products have the highest number of reviews?
7. How many products have a discount of 50% or more?
8. What is the distribution of product ratings (e.g., how many products are rated 3.0, 4.0, etc.)?
9. What is the total potential revenue (actual price × rating count) by category?
10. What is the number of unique products per price range bucket (e.g., <₹200, ₹200–₹500, >₹500)?
11. How does the rating relate to the level of discount? 
12. How many products have fewer than 1,000 reviews? 
13. Which categories have products with the highest discounts? 
14. Identify the top 5 products in terms of rating and number of reviews combined.

## ANSWERS & FORMULAS
### Q1. Average Discount Percentage by Product Category
- **Answer**: 
  - Home Improvement – 58.50%
  - Computers & Accessories – 53.80%
  - Health & Personal Care – 53.00%
  - Electronics – 50.00%
  - Musical Instruments – 46.00%
  - Car & Motorbike – 42.00%
  - Home & Kitchen – 40.65%
  - Office Products – 12.58%
  - Toys & Games – 0.00%. 
- **Method**:
  - Pivot Table
- **Formula Used**:
  - `Discount % = (Actual Price – Discounted Price) / Actual Price * 100`

### Q2. Number of Products per Category
- **Answer**:
  - Electronics: 490.00 products  
  - Home & Kitchen: 448.00 products  
  - Computers & Accessories: 375.00 products
  - Office Products: 31.00 products
  - Musical Instruments: 2.00 products
  - Car & Motorbike: 1.00 product
  - Toys & Games: 1.00 product
  - Health & Personal Care: 1.00 product
- **Method**:
  - Pivot Table
- **Pivot Fields**:  
  - Rows: `Main_Category`  
  - Values: `Product_ID` (Count)

### Q3. Total Number of Reviews per Category
- **Answer**:
  - Electronics – 14,208,441.00  
  - Computers & Accessories – 6,335,182.00
  - Home & Kitchen - 2,991,069.00
  - Office Products - 149,675.00
  - Musical Instruments - 88,882.00
  - Toys & Games - 15,867.00
  - Home Improvement - 8,566.00
  - Health & Personal Care - 3,663.00
  - Car & Motorbike - 1,118.00
- **Method**:
  - Pivot Table
- **Pivot Fields**:    
  - Rows: `Main_Category`  
  - Values: `Rating_Count` (Sum)

### Q4. The products with the highest average ratings
- **Answer**:
  - Syncwire LTG to USB Cable – 5.00  
  - REDTECH USB-C to Lightning Cable – 5.00
  - Amazon Basics Wireless Mouse - 5.00
  - Swiffer Instant Electric Water Heater - 4.80
  - Instant Pot Air Fryer - 4.80
  - Oratech Coffee Frother electric - 4.80
- **Method**:
  - Pivot Table (Top 6 filter)
- **Pivot Fields**: 
  - Rows: `Product_displayed_name`  
  - Values: `Rating (Average)

### Q5. Average actual vs discounted price by category
- **Answer**:
  - Electronics: ₹ 10.4 k ; ₹ 6.2 k
  - Car & Motorbike: ₹ 4.0 k ; ₹ 2.3 k
  - Home & Kitchen: ₹ 4.2 k ; ₹ 2.3 k
  - Computers & Accessories: ₹ 1.9 k ; ₹ 947
  - Health & Personal Care: ₹ 1.9 k ; ₹ 899
  - Musical Instruments: ₹ 1.3 k ; ₹ 638
  - Home Improvement: ₹ 799 ; ₹ 337
  - Office Products: ₹ 397 ; ₹ 302
  - Toys & Games: ₹ 150 ; ₹ 150
- **Method**: Pivot Table (Top 6 filter)  
- **Pivot Fields**:
  - Rows: `Main_Category`  
  - Values: `Actual Price` (Average), `Discounted Price` (Average)

### Q6. The products with the highest number of reviews
- **Answer**:
  - Amazon Basics High-Speed HDMI – 853,946.00   
  - boAt Bassheads 100 in Ear Wire – 727,426.00
  - Amazon Basics Flexible Premium -  426,973.00
  - JBL C100SI Wired In Ear Headphone - 385,179.00
  - boAt BassHeads 100 in-Ear Wire - 363,711.00
  - boAt Bassheads 242 in Ear Wire - 323,356.00
- **Method**:
  - Pivot Table (Top 6 filter)
- **Pivot Fields**: 
  - Rows: `Product_displayed_name`  
  - Values: `Rating_Count` (Sum).

### Q7. Number of products with discount >= 50%
**Answer**: 670 products
- **Method**:
  - Helper column + Pivot Table
- **Formula Used**:
  - `IF([Discount %] >= 50, “>=50%”, “<50%”)`

### Q8. Distribution of product ratings 
**Answer**: 
  - 4.5 – 5.0: 96.00 products
  - 4.0 – 4.4: 914.00 products
  - 3.0 – 3.9: 334.00 products
  - 2.0 – 2.9: 6.00 products
  - <2.0:1.00 product 
- **Method**:
  - Helper column + Pivot Table
- **Formula Used**:
  - `IF([@Rating] < 2, "<2.0", IF([@Rating] <3, "2.0 - 2.9", IF([@Rating]<4, "3.0 - 3.9", IF([@Rating] < 4.5, "4.0 - 4.4", "4.5 - 5.0"))))`

### Q9. Total potential revenue by category 
- **Answer**:
  - Electronics: ₹ 91,324,237,562.00
  - Computers & Accessories: ₹ 11,623,471,677.38
  - Home & Kitchen: ₹ 10,459,722,337.00
  - Musical Instruments: ₹ 151,117,062.00
  - Office Products: ₹ 60,778,817.00
  - Health & Personal Care: ₹ 6,959,700.00
  - Home Improvement: ₹ 6,163,434.00
  - Car & Motorbike: ₹ 4,472,000.00
  - Toys & Games: ₹ 2,380,050.00
- **Method**:
  - Calculated Column + Pivot Table    
- **Formula Used**:  
  - `Potential Revenue = Actual Price * Rating_Count`

### Q10. Number of unique products per price range  
**Answer**: 
  - >  ₹500: 1168.00 products
  - ₹200 -  ₹500: 149.00 products
  - < ₹200: 34.00 products
- **Method**:
  - Helper column + Pivot Table
- **Formula Used**:
  - `IF([@[Actual Price]] < 200, "< ₹200", IF([@[Actual Price]] < 500, " ₹200 -  ₹500", ">  ₹500"))`
 
### Q11. How rating relates to discount level  
- **Answer**: 
  - Products with 4.5 – 5.0 ratings tend to have discount of 43.16%,
  - Products with 4.0 – 4.4 ratings tend to have discount of 45.76%  
  - Products with 3.0 – 3.9 ratings tend to have discount of 52.21%  
  - Products with 2.0 – 2.9 ratings tend to have discount of 64.50%  
  - Products with <2.0 ratings tend to have discount of 17.00%  
- **Method**:
  - Helper column + Pivot Table
- **Pivot Fields**:
  - Rows: `Rating group`
  - Values: `Discount decimal` (Average)

### Q12. Products with fewer than 1,000 reviews  
**Answer**:
  - 310.00 products
- **Method**:
  - Helper column + Pivot Table
- **Formula Used**:
 - `IF([@[Rating Count]] < 1000, 1, 0)`

### Q13. Categories with highest discounts
- **Answer**:
  - Home Improvement: 58.50%
  - Computers & Accessories: 53.80%
  - Health & Personal Care: 53.00%
  - Electronics: 50.48%
  - Musical Instruments: 46.00%
  - Car & Motorbike: 42.00%
  - Home & Kitchen: 40.65%
  - Office Products: 12.58%
  - Toys & Games: 0.00%
- **Method**:
  - Pivot Table
- **Pivot Fields**:
  - Rows: `Main_Category`  
  - Values: `Discounted decimal` (Average)

### Q14. Top 5 products by combined rating and review count
- **Answer**:
  - Amazon Basics Flexible Premium – 1,878,681.20   
  - Amazon Basics High-Speed HDMI –  1,878,681.20
  - boAt Bassheads 100 in Ear Wire - 1,491,223.30
  - boAt BassHeads 100 in-Ear Wire - 1,491,215.10
  - Redmi 9A Sport (Coral Green) - 1,286,727.60
  - Redmi 9 Activ (Carbon Black) - 1,286,727.60
- **Method**:
  - Helper Column + Pivot Table (Top 5 filter)  
- **Pivot Fields**:
  - Rows: `Product_displayed_name`  
  - Values: `Rating_Count` (Sum).
- **Formula Used**:
  - `=[@Rating] * [@[Rating Count]]`

## KEY INSIGHT 
- The average discount across all categories is **47.23%**. This indicate that Amazon products are heavily discounted.
- Products with **lower ratings (2.0–2.9)** receive the **highest average discounts (64.5%)**. This might be a strategy to boost sales.
- **Electronics** dominate with the highest number of listings **(490 products)** and reviews **(14.2 million reviews)**. Also the **Home & Kitchen** category is heavily featured. This high review volumes often indicate high sales and customer trust.
- Most products are priced **above ₹500**, showing a mid-to-premium price focus.
- **Electronics** category leads with potential revenue of over ₹91 billion, far ahead of others. This indicates a lucrative market for sellers and a potential area for deeper investment or product expansion.
- Categories like **Car & Motorbike** and **Musical Instruments** are underrepresented (1–2 products only), which may suggest that these niche markets have low seller representation on Amazon
- **Electronics** and **Home & Kitchen** dominate in both listings and review counts, this probably indicate a narrow sales focus or market saturation in these niches.
- The **Combined Score metric** balances rating and review volume for ranking top products more fairly.
- A total of **114 duplicate listings** were identified and cleaned using **Power Query**. This to enhance data accuracy and avoid inflated metrics.

 ## DASHBOARD HIGHLIGHTS 
- Three interactive Excel Dashboards designed to present summary insights, namly:
  - Amazon Products Overview
  - Amazon Product Ratings & Reviews Insights
  - Amazon Product Pricing and Discount Insights.
- Interactive charts with slicers for:
  - Main Category
  - Rating Group
  - Reviews under 1000
  - Price Range 



