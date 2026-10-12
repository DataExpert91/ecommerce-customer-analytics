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

- ## Visualizations

<img width="1041" height="449" alt="Screenshot 2026-10-12 124311" src="https://github.com/user-attachments/assets/15a90be0-df05-4d5b-930e-5940937fc3b5" /> 
<img width="1041" height="740" alt="Screenshot 2026-10-12 125640" src="https://github.com/user-attachments/assets/5648dffd-f62b-4dc0-a7c8-207e940a3b1e" />
<img width="1043" height="514" alt="Screenshot 2026-10-12 124818" src="https://github.com/user-attachments/assets/a6f5f5ad-454d-49d0-b283-87f7a2e73ac0" />
<img width="1040" height="509" alt="Screenshot 2026-10-12 124944" src="https://github.com/user-attachments/assets/9219cf14-29d6-432b-9e0c-0db782bca19b" />
<img width="1042" height="398" alt="Screenshot 2026-10-12 125459" src="https://github.com/user-attachments/assets/fa837c25-ff54-4c39-98b3-99ae5a5aa0ec" />
<img width="1039" height="508" alt="Screenshot 2026-10-12 125758" src="https://github.com/user-attachments/assets/59affea6-f88c-4a4a-9433-01982ca9de67" />










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
5. Run `01_data_exploration.ipynb` from top to bottom.

The notebook's final export cell can create CSV, JSON of the cleaned dataset in the `outputs` folder. These generated files are not included in the repository.

## Author

DataExpert91
