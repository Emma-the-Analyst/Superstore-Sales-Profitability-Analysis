# Superstore Sales & Profitability Analysis

## Table of Contents

- [1. Project Abstract](#1-project-abstract)
- [2. Project Overview](#2-project-overview)
- [3. User Story](#3-user-story)
- [4. Project Stages](#4-project-stages)
  - [I. Requirement Gathering](#i-requirement-gathering)
    - [Objectives](#objectives)
    - [Challenge](#challenge)
    - [Questions Asked](#questions-asked)
    - [Solution](#solution)
    - [Users](#users)
    - [Data Source](#data-source)
    - [Data Dictionary](#data-dictionary)
    - [Tools Used](#tools-used)
  - [II. Design](#ii-design)
    - [Wireframe](#wireframe)
    - [Prototype](#prototype)
  - [III. Development](#iii-development)
    - [Data Exploration and Cleaning](#data-exploration-and-cleaning)
    - [Visualisation](#visualisation)
  - [IV. Analysis](#iv-analysis)
    - [Findings Documentation and Discovery](#findings-documentation-and-discovery)
    - [Findings Validation](#findings-validation)
- [5. Recommendations](#5-recommendations)
- [6. Future Research](#6-future-research)
- [7. Conclusion](#7-conclusion)

---

## 1. Project Abstract

This project analyzed sales, profit, and customer data for a U.S. based Superstore to identify top-performing products, regions, categories, and customer segments. The goal was to help business managers and marketing teams allocate resources effectively to maximize profitability. The dataset was sourced from Kaggle and loaded into Python pandas for data exploration and cleaning. Missing values, duplicates, and data types were checked, confirming a clean dataset with no nulls or duplicates. Outliers in Sales, Quantity, and Profit were detected using box plots but were kept intact to preserve accurate aggregate totals. Power BI was used to create interactive dashboards visualizing key metrics. Microsoft Excel was also used to populate key findings. Key findings showed that Technology led in sales (36%), followed closely by Furniture (32%) and Office Supplies (31%). There were 17 product sub-categories. The top five profit-generating sub-categories were Copiers, Phones, Accessories, Paper, and Binders, contributing 72% of total profit. The West region and Consumer segment generated the highest sales. All findings were validated using Python, ensuring accuracy.

## 2. Project Overview

In today's highly competitive retail landscape, a Superstore Giant in the United States is seeking to optimize its operations, maximize profitability, and enhance customer satisfaction. To achieve these goals, a comprehensive analysis of sales performance, customer behavior, and product trends is essential. The project aims to create data-driven insights which the Superstore Giant can leverage on, to identify which products, regions, product categories, and customer segments to focus on, as well as which areas to avoid or improve.

## 3. User Story

As a business manager at Superstore, I want to see which products, regions, and customer segments drive the highest sales and profit, so that I can focus marketing efforts and inventory investments on the most profitable areas. I need an interactive dashboard that clearly shows top performers by category, sub-category, region, and segment. This will help me make data-driven decisions to improve overall profitability. The insights should be easy to understand and share with my team.

## 4. Project Stages

The project stages include Requirements gathering, Design, Development, Analysis.

### I. Requirement Gathering

The project requirement outlines the project objectives, challenge that requires solution, questions asked, the solution to the problem, users of the project result, data source, and tools used in the project.

#### Objectives

1. To identify which products, regions, product category and customer segment to focus on in order to optimize sales and increase profitability at Superstore.

#### Challenge

The Superstore giant is struggling to identify where (product and region) to channel resource to maximize profit.

#### Questions Asked

1. What is the top performing product category by sales?
2. What are the top 5 performing product sub-category in terms of profit?
3. What are the top performing region by sales?
4. What is the top customer segment in terms of sales?

#### Solution

1. Create a dashboard using Power BI to show:
   - i. Top performing product category by sales
   - ii. Top 5 performing product sub-categories by profit
   - iii. Top performing region by sales
   - iv. Top customer segment by sales
2. Derive tables from dashboard to provide summary of answers to questions asked using Excel.

#### Users

The results of the project will be used by business managers, marketing teams, and strategic decision-makers of Superstore to guide resource allocation, improve customer engagement, and drive profitability.

#### Data Source

Dataset was sourced from Kaggle.  
Link to dataset: [https://www.kaggle.com/datasets/vivek468/superstore-dataset-final](https://www.kaggle.com/datasets/vivek468/superstore-dataset-final)

#### Data Dictionary
The data dictionary below shows the selected variables and their variable type considered for this project and taken from the data.
| Variable | Variable Type | Description |
|----------|--------------|-------------|
| Category | Categorical (Nominal) | The high-level product group |
| Sub-Category | Categorical (Nominal) | The specific product type within a category |
| Region | Categorical (Nominal) | The geographic area where the sale occurred |
| Segment |Categorical (Nominal) | The customer type |
| Sales | Numerical (Continuous) | The total revenue generated from the sale, measured in dollars |
| Quantity | Numerical (Discrete) | The number of units sold |
| Profit | Numerical (Continuous) | The earnings after costs, measured in dollars |

#### Tools Used

- Figma - For wireframe and prototype visualization
- Excel - For documenting findings
- Python - For Data Exploration, cleaning and validating results
- Power BI - For visualization

### II. Design

A dashboard was designed in a wireframe and further modified to prototype using Figma.

#### Wireframe

![Sales Dashboard Wireframe](https://github.com/Emma-the-Analyst/Superstore-Sales-Profitability-Analysis/blob/main/IMAGES/DASHBOARD%20WIREFRAME.png?raw=true)

#### Prototype

![Sales Dashboard Prototype](https://github.com/Emma-the-Analyst/Superstore-Sales-Profitability-Analysis/blob/main/IMAGES/Dashboard%20Prototype.png?raw=true)

### III. Development

The development stage includes data exploration and cleaning, and Visualization.

#### Data Exploration and Cleaning

The dataset was loaded into Python pandas dataframe for exploration of data content and cleaning. Two main activities done here are Data Exploratory and Data cleaning. Activities performed under this stage includes:

**Loading dataset into Python pandas dataframe**

The dataset was loaded into a pandas dataframe. The first five rows was displayed, allowing for an initial visual inspection of the data structure, column names, and sample values to confirm successful loading.

![Dataset Loaded](https://github.com/Emma-the-Analyst/Superstore-Sales-Profitability-Analysis/blob/main/IMAGES/DATA%20LOADING.png?raw=true)

**Rows and columns check**

This involved reviewing the dimensions of the dataset to understand its size and structure.

![Rows and Columns Check](https://github.com/Emma-the-Analyst/Superstore-Sales-Profitability-Analysis/blob/main/IMAGES/ROWS%20AND%20COLUMNS%20CHECK.png?raw=true)

**Checking for missing values**

The missing value check confirmed that there are no null or missing values in any of the 21 columns within the dataset. This indicates the data is complete and requires no imputation or removal of rows due to missing entries, allowing the analysis to proceed without data cleaning for nulls.

![Missing Values Check](https://github.com/Emma-the-Analyst/Superstore-Sales-Profitability-Analysis/blob/main/IMAGES/MISSING%20VALUE%20CHECKS.png?raw=true)

**Checking for duplicates**

The duplicate check revealed that there are zero duplicate rows in the dataset. This confirms that every row is unique, eliminating the need for duplicate removal and ensuring the integrity of the analysis.

![Duplicate Check](https://github.com/Emma-the-Analyst/Superstore-Sales-Profitability-Analysis/blob/main/IMAGES/DUPLICATE%20CHECK.png?raw=true)

**Outliers check**

Box and whisker plots were used to detect outliers in Sales, Quantity, and Profit. All outliers were left as is without removal or capping to maintain accurate aggregate calculations, including total sales revenue, total units sold, and total profit.

![Sales Outlier](INSERT_SALES_OUTLIER_IMAGE_HERE)

![Quantity Outlier](INSERT_QUANTITY_OUTLIER_IMAGE_HERE)

![Profit Outlier](INSERT_PROFIT_OUTLIER_IMAGE_HERE)

**Data type check**

The data type check confirmed that all columns have appropriate data types formats for analysis. Numerical columns such as Sales, Quantity, and Profit are correctly formatted as float64 or int64, while categorical columns like Category, Segment, and Region are stored as object type, requiring no immediate conversion.

![Data Types Check](INSERT_DATA_TYPES_IMAGE_HERE)

#### Visualisation

Power BI was used to create interactive dashboards and charts that effectively communicate key insights from the data. Power BI allowed me to explore relationships between variables such as Sales, Quantity, and Profit across different categories, regions, and segments.

![Superstore Sales Performance Dashboard](https://github.com/Emma-the-Analyst/Superstore-Sales-Profitability-Analysis/blob/main/IMAGES/DASHBOARD.png) 

### IV. Analysis

Activities performed under the analysis stage were:

#### Findings Documentation and Discovery

Findings were documented from the Power BI visualization using Excel to provide answers to the questions asked.

**1. What is the top performing product category by sales?**

![Top Performing Product Category by Sales](INSERT_CATEGORY_SALES_IMAGE_HERE)

**Discovery:**
- Total sales across all three categories reached approximately $2.30 million.
- Technology led with $836,150, accounting for 36% of total sales.
- Furniture followed closely at $742,000 (32%).
- Office Supplies contributed $719,050 (31%), finishing a very close third.
- The three categories are nearly balanced, each representing roughly one-third of total sales, so focus could be on maintaining Technology's lead while boosting Office Supplies and Furniture to close the small gap.

**2. What are the top 5 performing product sub-category in terms of profit?**

![Top 5 Performing Product Sub-Category by Profit](INSERT_SUBCATEGORY_PROFIT_IMAGE_HERE)

**Discovery:**
- The top 5 sub-categories generated a combined profit of $206,350, accounting for 72.04% of total profit across all 17 sub-categories.
- Copiers led with $55,620 (19.42%).
- Phones followed with $44,520 (15.54%).
- Accessories came in third with $41,940 (14.64%).
- Paper contributed $34,050 (11.89%).
- Binders rounded out the top five with $30,220 (10.55%).
- The remaining 12 sub-categories together contribute less than 28% of total profit, indicating a heavy concentration of profitability in just these five areas.

**3. What are the top performing region by sales?**

![Top Performing Region by Sales](INSERT_REGION_SALES_IMAGE_HERE)

**Discovery:**
- Total sales across all four regions reached approximately $2.30 million.
- West led with $725,460, accounting for 31.58% of total sales.
- East followed closely at $678,780 (29.55%).
- Central contributed $501,240 (21.82%).
- South contributed $391,720 (17.05%).
- The West and East together make up over 60% of sales, so focusing on boosting performance in the Central and South regions presents the biggest growth opportunity.

**4. What is the top customer segment in terms of sales?**

![Top Customer Segment by Sales](INSERT_SEGMENT_SALES_IMAGE_HERE)

**Discovery:**
- Total sales across all three segments reached approximately $2.30 million.
- Consumer led by a wide margin with $1,160,000, accounting for over half (50.53%) of total sales.
- Corporate followed with $706,150 (30.76%).
- Home Office contributed $429,650 (18.71%), finishing third.
- The Consumer segment drives the majority of revenue, so maintaining its strength while finding ways to boost Corporate and especially Home Office could lead to more balanced growth.

#### Findings Validation

The documented findings from the visualization were verified using Python. All the results tallied with the documented findings from the visualization.

![Validation - Category Sales](INSERT_VALIDATION_CATEGORY_IMAGE_HERE)

![Validation - Top 5 Sub-Category Profit](INSERT_VALIDATION_SUBCATEGORY_IMAGE_HERE) 

![Validation - Top Region by sales](INSERT_VALIDATION_IMAGE_FOR_THIS_HERE)

![Validation - Customer Segment Sales](INSERT_VALIDATION_SEGMENT_IMAGE_HERE)

### 5. Recommendations

The following are recommendations and potential course of action deduced from discovery:

1. **Invest more in Technology and Office Supplies** - These categories, along with Furniture, are nearly balanced in sales. Slight investment in Technology can maintain its lead, while boosting Office Supplies and Furniture can close the small gap.

2. **Focus on the top 5 profit sub-categories** - Copiers, Phones, Accessories, Paper, and Binders generate over 72% of total profit. Prioritize inventory, promotions, and supplier negotiations for these items.

3. **Expand West and East region strengths** - These two regions account for over 60% of sales. Replicate successful strategies in the Central and South regions to lift their underperformance.

4. **Target the Consumer segment more** - Consumers drive more than half of all sales. Tailor loyalty programs, discounts, and product bundles specifically to this segment.

5. **Monitor loss-making sub-categories** - Since the remaining 12 sub-categories contribute less than 28% of profit, review their pricing, costs, and demand to either improve margins or discontinue low performers.

## 6. Future Research

One relevant area for future research is to analyze the impact of discounts on profit margins across different sub-categories and regions. This would help determine whether discounting drives volume at the expense of profitability, and identify which products benefit most from strategic markdowns.

## 7. Conclusion

The project successfully cleaned, explored, and validated the Superstore dataset, confirming no missing values or duplicates. Interactive Power BI dashboards revealed that Technology, the Consumer segment, and the West region are top sales drivers, while five sub-categories contribute most of the profit. These insights provide a solid foundation for data-driven resource allocation and strategic decision-making at Superstore.

---

## How to Run This Project

1. Clone this repository.
2. Install required Python libraries: `pandas`, `matplotlib`
3. Run the Jupyter Notebook or Python script to see data exploration and validation.
4. Open the Power BI file to view the interactive dashboard.

## Author

[Your Name] – [Your LinkedIn/GitHub Profile Link]

---
