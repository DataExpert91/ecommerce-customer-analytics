# Online Retail Data Analysis

## Project Overview

This project uses Python to explore transaction data from a UK-based online retailer. It reviews data quality, prepares the data for analysis, and examines sales trends, product performance, country-level results, and customer purchasing behavior.

## Objectives

- Review the dataset structure and data quality.
- Clean and prepare the data for analysis.
- Examine sales trends over time.
- Compare products and countries using revenue, invoice counts, and units sold.
- Analyze customer purchase frequency and repeat purchasing.
- Summarize findings, recommendations, and limitations.

## Dataset and Source

The project uses the [Online Retail II dataset on Kaggle] https://www.kaggle.com/datasets/mashlyn/online-retail-ii-uci/data. It contains transaction records from a UK-based online retailer covering December 2009 to December 2011.

The original data file is stored locally and is not included in this repository. Download it from the source above and place it at `data/online_retail.csv` before running the notebook.

## Data Preparation

The original dataset contained 1,067,371 rows. After removing 34,335 exact duplicate rows, 1,033,036 rows remained. Invoice dates were converted to datetime format, with no unparseable dates.

Rows with missing customer IDs and negative quantities were retained in the cleaned dataset. Customer-level analysis includes only records with an identified customer ID.

## Revenue Definitions

**Revenue from positive sales** is calculated using transactions with positive quantities and positive prices. Several product, country, customer, and monthly comparisons use this subset.

**Net transaction revenue** includes recorded revenue across all retained transactions, including negative values such as returns or cancellations. A chart based on positive-sales rows should not be interpreted as net revenue after returns.

Revenue is not the same as profit because the dataset does not include product costs.

## Key Findings

- Monthly revenue from positive sales was highest in November 2010 and November 2011. February 2010 and February 2011 were among the weakest months, and March 2011 was also low. This may indicate seasonal variation, but the data cannot establish its cause.
- The United Kingdom ranked first in both revenue from positive sales and unique invoice count. Rankings for other countries varied depending on the measure.
- Product rankings differed when comparing revenue with units sold. High unit volume did not always correspond to high revenue. Unusually large quantities and related cancellations can also affect unit-based rankings.
- Among customers with an identified customer ID, repeat buyers represented 72.39% of customers and generated 96.78% of revenue in the positive-sales customer analysis.
- The average order value was 510.92, compared with a median of 302.22. The higher average suggests that some large orders raised the mean.
- For customers with at least two distinct invoices, the average time between the first and second invoice was 97.52 days; the median was 55.96 days.

## Recommendations

- Explore ways to encourage one-time buyers to make a second purchase.
- Use the November peaks and February lows as planning signals, and compare them with additional years before making seasonal decisions.
- Review unusually large quantity transactions and related cancellations before using unit rankings to guide business decisions.
- Compare countries using both revenue and unique invoice counts.
- Evaluate product performance using both revenue and units sold.

## Limitations

- Customer-level findings exclude transactions without a customer ID.
- Analyses based on positive-sales rows do not account for negative transactions such as returns and cancellations.
- The exact business meaning of some negative or unusual transactions is not known.
- The dataset covers about two years, with incomplete months at the beginning and end of the period. The observed pattern is not enough to confirm recurring seasonality.
- Revenue does not account for product costs and cannot be used to calculate profit.

## Tools

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Jupyter Notebook
- openpyxl

## How to Run

1. Clone or download this repository.
2. Download the dataset from Kaggle and save it as `data/online_retail.csv`.
3. Install the required packages:

   ```bash
   pip install -r requirements.txt
   ```

4. Open the project root folder in VS Code or Jupyter.
5. Run `notebooks/01_data_exploration.ipynb` from top to bottom.

The notebook's final export cell can create CSV, JSON, and Excel versions of the cleaned dataset in the `outputs` folder. These generated files are not included in the repository.

## Author

DataExpert91
