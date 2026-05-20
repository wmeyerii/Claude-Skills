# Data: Statistical Analysis

Run statistical analysis on real estate data — regression, correlation, distributions, forecasting.

## Use Cases
- Market rent analysis and forecasting
- Cap rate regression against market variables
- Rent growth trend analysis
- Occupancy and absorption modeling
- Tenant default probability estimation
- CapEx spend vs. value-add correlation analysis

## Step 1 — Define the Question
- What decision does this analysis support?
- What is the dependent variable?
- What are the independent variables?
- What is the time period and geographic scope?

## Step 2 — Data Assessment
- Sample size (n): sufficient?
- Missing values: how many, which fields?
- Outliers: include or exclude?
- Data type: continuous, categorical, time series?

## Analysis Types

**Descriptive Statistics**
Count, mean, median, std dev, min/max, 25th/75th percentile.

**Trend Analysis (Time Series)**
CAGR: `(Ending Value / Beginning Value)^(1/years) - 1`

**Correlation Analysis**
Pearson r: |r| > 0.7 = strong | 0.4–0.7 = moderate | <0.4 = weak
Useful pairs: vacancy × rent growth, absorption × new supply

**Regression Analysis**
`Y = a + bX + ε` — Report R², coefficient, p-value, confidence interval.

**Forecasting Methods**
Simple moving average, exponential smoothing, linear extrapolation, or market consensus. Always include: assumptions, confidence range, base/bull/bear scenarios.

## Output Format
1. Summary table with key statistics
2. Findings narrative (plain language)
3. Chart description
4. Implications for the decision
5. Limitations and caveats
