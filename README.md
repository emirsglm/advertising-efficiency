# Advertising Efficiency

A concise analysis of how different marketing channels contribute to product sales and cost efficiency. Using a Kaggle dataset of simulated multi-channel ad spend and sales, the notebook performs EDA, correlation analysis, and builds a linear regression model to quantify channel impact and surface actionable budget insights.

## Dataset
- Source: Kaggle — `singhnavjot2062001/product-advertising-data`
- Access: via `kagglehub` (notebook currently uses a local cached path)
- Features: `TV`, `Billboards`, `Google_Ads`, `Social_Media`, `Influencer_Marketing`, `Affiliate_Marketing`, and `Product_Sold`

## What the notebook does
- Creates `Total_Spend` and `Cost_Per_Prodcut_Sold` features
- Splits campaigns into Efficient vs Inefficient relative to a trend line
- Visualizes channel spend distributions and donut charts by efficiency group
- Computes Pearson/Spearman correlations across all variables
- Tests linear regression assumptions (linearity, normal residuals, homoscedasticity, multicollinearity)
- Fits OLS and scikit-learn Linear Regression models; reports metrics and coefficients
- Exports predictions and the enriched dataset to CSV

## Key insights
- Affiliate Marketing and Billboards associate most strongly with higher `Product_Sold`
- Higher allocations to Affiliate Marketing and Billboards correlate with lower `Cost_Per_Prodcut_Sold`
- Google Ads and Influencer Marketing show weaker contribution to sales and tend to increase cost per unit

## Results at a glance
- R² ≈ 0.999 on test split (synthetic dataset)
- Low MAE/RMSE relative to the mean of `Product_Sold`
- Coefficients (approx.):
  - Affiliate_Marketing ≈ 4.00
  - Billboards ≈ 3.00
  - Social_Media ≈ 2.50
  - TV ≈ 2.00
  - Google_Ads ≈ 1.50
  - Influencer_Marketing ≈ 1.20

## How to run
1. Install dependencies:
   - Python 3.9+
   - pandas, numpy, matplotlib, seaborn, statsmodels, scikit-learn, kagglehub
   - Example:
     ```bash
     pip install pandas numpy matplotlib seaborn statsmodels scikit-learn kagglehub
     ```
2. Obtain the dataset:
   - Option A (recommended): enable the `kagglehub.dataset_download("singhnavjot2062001/product-advertising-data")` line in `main.ipynb` and use the returned path
   - Option B: keep using your local cached path as in the notebook
3. Open and run `main.ipynb` sequentially
4. Outputs:
   - Visualizations displayed inline
   - `product_advertising_data.csv` saved to the project root

## Repository contents
- `main.ipynb`: end-to-end analysis and modeling
- `output.png`: example plot (optional artifact)

## Notes
- The dataset is synthetic; very high R² is expected. Focus on relative channel importance and efficiency patterns rather than absolute performance.
- The column name `Cost_Per_Prodcut_Sold` contains a minor typo but is kept consistent with the notebook. 