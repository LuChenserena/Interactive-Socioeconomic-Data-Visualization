# Interactive-Socioeconomic-Data-Visualization
An interactive HTML data visualization project using R (ggiraph, tidyverse) to analyze VAST Challenge datasets, exploring financial trade-offs between education costs and civic vitality.
# Interactive Socioeconomic Data Visualization: The Urban Education Squeeze 🏙️📊

This repository contains an advanced exploratory data analysis (EDA) and interactive visualization project examining socioeconomic inequality within a simulated urban environment[cite: 8]. 

Using relational datasets from the **VAST Challenge 2022** (simulating ~1,000 residents in Engagement, Ohio)[cite: 8], this project quantifies the intense financial trade-offs low-income families face between funding education and maintaining civic vitality (recreation)[cite: 8].

## 🛠 Tech Stack & Methodologies
* **Language:** R
* **Data Wrangling:** `tidyverse` (`dplyr`, `tidyr` for `pivot_wider`/`pivot_longer`, `left_join`)
* **Interactive Visualization:** `ggplot2`, `ggiraph` (for SVG-based interactive tooltips and CSS hover effects)[cite: 9]
* **Reporting:** R Markdown (rendered to Interactive HTML)[cite: 9]

## ⚙️ Data Engineering Pipeline
A significant portion of this project involved reshaping fragmented transactional data into analyzable household metrics:
1. **Relational Merging:** Joined the `FinancialJournal.csv` (transaction logs) with `Participants.csv` (demographic profiles) using `participantId` as the primary key[cite: 9].
2. **Data Reshaping:** Aggregated absolute financial transactions and utilized `pivot_wider` to structure spending categories (Basic Needs, Education, Recreation) across distinct household types[cite: 9].
3. **Metric Engineering:** Calculated custom socioeconomic indicators, such as the "Recreation Spending Gap," to baseline individual family leisure budgets against the city-wide average[cite: 9].

## 📈 Interactive Visualizations
Rather than static images, the analysis was designed for web-based interactivity using the `ggiraph` package[cite: 9]:
* **Diverging Stacked Bars:** Visualizes the disproportionate budget share consumed by education for low-income families[cite: 8, 9].
* **Violin-Box Plots:** Displays the absolute dollar distribution of education spending, highlighting the density of low-income families trapped below the city average[cite: 8, 9].
* **Interactive Scatter Plots (with Linear Trendlines):** Maps the stark negative correlation between education cost burden (% of wage) and recreation deficit for families without university degrees[cite: 8, 9]. *Hovering over data points reveals specific household metrics.*

## 💡 Key Findings
1. **The Education Squeeze:** Low-income families with children allocate a severely disproportionate share of their limited budget to education, forcing extreme sacrifices in basic needs and recreation[cite: 8].
2. **The Recreation Gap:** Wealth insulates middle- and high-income families, allowing them to enjoy city recreation regardless of parental education levels. Conversely, low-income parents without degrees face massive recreation deficits to afford schooling[cite: 8].
3. **Civic Vitality:** The data proves that access to urban leisure is not equal; for those at the bottom of the income bracket, fighting for a child's future systematically strips away daily joy[cite: 8].

## 📂 Repository Structure
* `data/` - Contains the `Participants.csv` and `FinancialJournal.csv` (VAST Challenge 2022 datasets)[cite: 9].
* `scripts/interactive_analysis_report.Rmd` - The core R Markdown script containing the data cleaning pipeline and `ggiraph` visualization code.
* `report/urban_inequality_report.pdf` - The static version of the analytical report. *(Note: Knit the `.Rmd` locally to HTML to experience the full CSS hover interactivity).*

---
**⚠️ Academic Integrity Disclaimer:** 
*This project was developed for academic purposes at the University of Toronto. The codebase and analytical reports are shared here strictly for professional portfolio demonstration. Current or future students are prohibited from copying or adapting this work for their own assignments.*
