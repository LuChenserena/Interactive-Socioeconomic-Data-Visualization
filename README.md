# Interactive Socioeconomic Data Visualization: The Urban Education Squeeze 🏙️📊

This project analyzes socioeconomic inequality in a simulated urban environment using interactive data visualization in R. The goal is to examine how household income shapes education spending, recreation access, and financial pressure among families.

The project uses the **VAST Challenge 2022** dataset, which simulates residents in the fictional city of Engagement, Ohio. The analysis focuses on the intense financial trade-offs that low-income families face between investing in education and maintaining access to recreation and civic life.

## 📋 Project Overview

This project investigates the relationship between income level, parental education, education spending, and recreation access. Households are grouped into low-, middle-, and high-income categories to compare how different families allocate their budgets across basic needs, education, and recreation.

The final output is an interactive HTML report built with R Markdown. Interactive SVG tooltips and CSS hover effects allow readers to explore household-level and group-level spending patterns directly within the visualizations.

## 🛠 Tools and Methods

* **Language:** R
* **Data Wrangling:** `tidyverse` (`dplyr`, `tidyr` for `pivot_wider` and `pivot_longer`)
* **Interactive Visualization:** `ggplot2`, `ggiraph`
* **Reporting:** R Markdown (rendered to Interactive HTML)
* **Techniques:** Relational data merging, metric engineering, socioeconomic exploratory data analysis (EDA)

## ⚙️ Data Processing Pipeline

### 1. Data Merging
The analysis combines financial transaction logs (`FinancialJournal.csv`) with participant demographic data (`Participants.csv`) using relational merging (`left_join`). This allows household spending patterns to be analyzed alongside income group, household structure, and parental education level.

### 2. Data Reshaping
Financial transactions are reshaped and aggregated to calculate household-level spending across categories such as basic needs, education, and recreation. The project uses `pivot_wider` and `pivot_longer` to restructure the data from long transactional logs to wide analytical tables.

### 3. Metric Construction
Several custom metrics are engineered to support the analysis, including:
* Household budget proportions
* Education cost as a percentage of wage
* Recreation spending gap (relative to the city-wide average)

These metrics help expose whether families are spending more in absolute terms, or whether certain expenses simply consume a crippling share of a smaller budget.

## 📈 Interactive Visualizations

The project uses `ggiraph` to upgrade static `ggplot2` charts into web-based interactive visualizations:

* **Budget Composition (Diverging Stacked Bars):** Compares how families across income groups allocate their budgets. Highlights how education consumes a severely disproportionate share of the budget for low-income families with children.
* **Education Spending Distribution (Violin-Box Plots):** Shows the distribution of absolute education spending across income groups. Exposes the density of low-income families trapped at the bare-minimum spending level.
* **Recreation Spending Gap (Diverging Bar Chart):** Compares recreation spending across income and parental education groups. Visually separates the groups holding a recreation surplus from those in a recreation deficit.
* **Education-Recreation Trade-off (Interactive Scatter Plot):** Examines the negative correlation between education cost burden and recreation spending gap. *Hovering over individual data points reveals specific household metrics.*

## 💡 Key Findings

* **The Education Squeeze:** Low-income families with children spend a much larger share of their limited budget on education, forcing extreme sacrifices in basic needs and recreation.
* **The Absolute Cost:** Although low-income families spend less on education in absolute dollars, these minimal costs create a much heavier burden relative to their income.
* **Wealth as a Buffer:** Middle- and high-income families are insulated, allowing them to spend heavily on both education and recreation without making severe trade-offs.
* **The Degree Premium:** Low-income parents without university degrees face the most massive recreation spending deficits just to keep their children in school.
* **Civic Vitality:** The data proves that access to urban leisure is unequal; for those at the bottom of the income bracket, funding a child's education systematically strips away daily joy.

## 📂 Repository Structure

```text
├── README.md
├── Participants.csv                     # Demographic dataset (VAST Challenge 2022)
├── interactive_analysis_report.Rmd      # Core R script (data wrangling & visualization)
├── urban_inequality_report.html         # Interactive HTML report (with ggiraph hover effects)
└── urban_inequality_report.pdf          # Static version of the analytical report
