# Week 3 Activity 3: Subscription Data Analysis

## 1. Project Summary
This project performs an exploratory data analysis (EDA) on customer subscription datasets (`st422_week3_subscription_*.csv`). It automates the cleaning of raw data, generates a demographic summary table stratified by region, and produces visualizations for key distributions (tenure and monthly fees). The goal is to ensure reproducibility in reporting customer characteristics and retention metrics across different data versions.

## 2. Data Description
The analysis uses CSV files located in `week_3/data/raw/`. 

* **Unit of Analysis:** Each row represents a single **customer subscription account**.
* **Key Variables:**
    * `region` (Group Variable): The geographic location of the customer, used for stratifying Table 1.
    * `tenure_months` (Outcome Variable): The duration of the customer's subscription in months.
    * `monthly_fee_gbp`: The monthly cost of the subscription in GBP.
    * `customer_id`: Unique identifier (excluded from summary statistics).
    * `signup_date`: Date of account creation.

## 3. Dependencies
This project uses `renv` for dependency management to ensure the analysis is reproducible.

**Core R Libraries used:**
* `ggplot2`, `gtsummary`, `gt` (Visualization and Tables)
* `dplyr`, `janitor` (Data Wrangling)
* `here` (Relative file paths)

**How to restore the environment:**
1.  Open the project in RStudio.
2.  Run the following command in the console to install the exact package versions used in this analysis:
    ```r
    renv::restore()
    ```

## 4. Run Steps
To replicate the analysis:

1.  **Verify Directory Structure:** Ensure your project has the following structure relative to the project root:
    ```
    week_3
    ├── data
    │   ├── processed
    │   └── raw
    │       ├── st422_week3_subscription_v1.csv
    │       ├── st422_week3_subscription_v2.csv
    │       └── st422_week3_subscription_v3.csv
    ├── HANDOVER.md
    ├── HANDOVER_LOG.md
    ├── outputs
    │   ├── figures
    │   └── tables
    ├── README.md
    ├── reports
    │   └── week_3_activity_3.Rmd
    └── src
    ```

2.  **Execute via R Console:**
    You can generate the HTML report and outputs for a specific dataset version by running the `rmarkdown::render` command in your RStudio Console. 
    
    *Make sure to change the `data_version` parameter as needed ("v1", "v2", or "v3").*

    ```r
    # Example: Render the report using Data Version 2
    rmarkdown::render("week_3/reports/week_3_activity_3.Rmd", params = list(data_version = "v2", group_var="region"))

    # Example: Render the report using Data Version 3
    rmarkdown::render("week_3/reports/week_3_activity_3.Rmd", params = list(data_version = "v3", group_var="region")))
    ```

## 5. Expected Outputs
Upon successful execution, the following files will be generated in the `week_3/outputs/` folder:

* **Tables:**
    * `tables/table_1_v1.html`: A formatted HTML summary table showing statistics by Region.
* **Figures:**
    * `figures/boxplot_v1.png`: A box-plot of Tenure Months by Region.
    * `figures/histogram_v1.png`: A histogram of Monthly Fees with dynamically calculated bins.

*(Note: Filenames will change based on the `data_version` selected in the code).*

## 6. Assumptions and Limitations
* **Assumptions:** The script assumes the raw data follows the naming convention `st422_week3_subscription_{version}.csv` and contains consistent column names across versions. It utilizes the `here` package, assuming the `.Rproj` file is at the root directory.
* **Limitations** The script only 
