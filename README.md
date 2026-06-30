# Interactive Socioeconomic Data Visualization

This project analyzes socioeconomic inequality in a simulated urban environment using interactive data visualization in R. The goal is to examine how household income shapes education spending, recreation access, and financial pressure among families.

The project uses the VAST Challenge 2022 dataset, which simulates residents in the fictional city of Engagement, Ohio. The analysis focuses on the financial trade-offs that low-income families face between investing in education and maintaining access to recreation and civic life.

## Project Overview

This project investigates the relationship between income level, parental education, education spending, and recreation access. Households are grouped into low-, middle-, and high-income categories to compare how different families allocate their budgets across basic needs, education, and recreation.

The final output is an interactive HTML report built with R Markdown. Interactive tooltips allow readers to explore household-level and group-level spending patterns directly within the visualizations.

## Tools and Methods

* R
* R Markdown
* tidyverse
* dplyr
* tidyr
* ggplot2
* ggiraph
* Data cleaning and aggregation
* Relational data merging
* Interactive data visualization
* Socioeconomic analysis

## Data Processing Pipeline

### 1. Data Merging

The analysis combines financial transaction data with participant demographic data from the VAST Challenge 2022 dataset. This allows household spending patterns to be analyzed alongside income group, household structure, and parental education level.

### 2. Data Reshaping

Financial transactions are reshaped and aggregated to calculate household-level spending across categories such as basic needs, education, and recreation. The project uses `pivot_wider` and `pivot_longer` to restructure the data for visualization and comparison.

### 3. Metric Construction

Several custom metrics are created to support the analysis, including:

* household budget proportions
* education cost as a percentage of wage
* recreation spending gap relative to the city average
* income-level spending comparisons

These metrics help show whether families are spending more in absolute terms or whether certain expenses simply take up a larger share of a smaller budget.

## Interactive Visualizations

The project uses `ggplot2` and `ggiraph` to create interactive visualizations with hover tooltips.

### Budget Composition Chart

A stacked bar chart compares how families across income groups allocate their budgets to basic needs, education, and recreation. This visualization highlights how education takes up a much larger share of the budget for low-income families with children.

### Education Spending Distribution

A violin-box plot shows the distribution of actual education spending across income groups. This helps distinguish between spending a high proportion of income and spending a high dollar amount.

### Recreation Spending Gap

A diverging bar chart compares recreation spending across income and parental education groups relative to the city average. This visualization shows which groups have more or less money available for recreation.

### Education-Recreation Trade-off

An interactive scatter plot examines the relationship between education cost burden and recreation spending gap. Point size represents parental education level, and color represents income group. Trendlines are used to compare patterns across income levels.

## Key Findings

* Low-income families with children spend a much larger share of their limited budget on education.
* Although low-income families may spend less on education in absolute dollars, education costs create a much heavier burden relative to their income.
* Middle- and high-income families are more able to spend on both education and recreation without making severe trade-offs.
* Low-income families with lower parental education levels face the largest recreation spending deficits.
* The relationship between education spending and recreation access suggests that financial pressure can limit families' ability to participate in civic and leisure activities.

## Repository Structure

```text
Interactive-Socioeconomic-Data-Visualization/
├── README.md
├── interactive_socioeconomic_visualization.Rmd
├── urban_inequality_report.html
└── urban_inequality_report.pdf
```

* `interactive_socioeconomic_visualization.Rmd`: R Markdown source file containing the data cleaning, transformation, analysis, and interactive visualization code.
* `urban_inequality_report.html`: Interactive HTML report with hover tooltips and dynamic visualizations.
* `urban_inequality_report.pdf`: Static version of the report for easier viewing and sharing.

## Notes on Data

The dataset used in this project comes from the VAST Challenge 2022 simulated urban environment. If the full dataset cannot be redistributed, this repository provides the analysis code, report, and documentation rather than the raw data files.

## Academic Integrity Note

This project was completed as part of a university coursework assignment and is shared for personal portfolio purposes only. Please do not copy, submit, or reuse this work as your own academic assignment.
