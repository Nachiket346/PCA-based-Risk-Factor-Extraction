Project Overview — PCA-Based Risk Factor Extraction:
This project applies Principal Component Analysis (PCA) to equity return data to identify the underlying systematic risk factors driving asset co-movements.
Using 5 stocks and historical daily returns, the model decomposes portfolio risk into common factors and idiosyncratic components, enabling improved risk understanding and dimensionality reduction.

Objectives:
Extract key risk factors from a set of equity return series.
Quantify how much of total portfolio variance is explained by each factor.
Construct eigenportfolios (factor loadings) based on PCA components.
Generate factor returns and analyze their behavior.
Demonstrate how PCA can simplify risk modeling by reducing dimensionality.

Process & Methodology
1. Data Preparation
Collected daily returns for 5 equities over a multi-year period.
Cleaned missing values and standardized returns for PCA suitability.

2. PCA Computation
Computed the covariance matrix of standardized returns.
Extracted eigenvalues and eigenvectors.
Identified principal components and their explained variance.

3. Factor Interpretation
Constructed factor loadings (weights of each stock in each component).
Derived factor returns as linear combinations of standardized returns.

Visualized:
Explained variance by each component
Cumulative variance
PC1 & PC2 factor return series
Eigenportfolio weights

4. Evaluation
Assessed stability of PCA factors over time.
Identified which factors dominate total variance.

Results:
Below are typical results for 5 liquid equities (values may differ with dataset but structure remains similar):

Explained Variance
| **PCA Component** | **Variance Contribution** | **Percentage (%)** |
| ----------------- | ------------------------- | ------------------ |
| **PC1**           | 0.75095256                | **75.10%**         |
| **PC2**           | 0.15742838                | **15.74%**         |
| **PC3**           | 0.06320376                | **6.32%**          |
| **PC4**           | 0.02547061                | **2.55%**          |
| **PC5**           | 0.00294469                | **0.29%**          |


Top 2 components typically explain ~75–90% of the total risk.

Interpretation:
PC1 explains ~75% of total variance, indicating a broad market factor driving overall co-movement across assets — similar to an equity “market beta” component.
PC2 captures ~16% of variance, representing a sector- or style-specific factor (e.g., growth vs. value rotation) that is independent of the main market trend.
PC3 contributes ~6%, reflecting idiosyncratic or residual risk, typically linked to stock-specific movements not explained by broader factors.
PC4 and PC5 together explain <3%, showing that higher-order components add minimal explanatory power and mostly represent noise.

Dimensionality Reduction:
Reduced 5 correlated return series into 2 interpretable risk factors with very low information loss.

Eigenportfolios:
PC1 eigenportfolio: roughly equal positive weights → “market beta factor”.
PC2 eigenportfolio: long certain stocks, short others → “sector/style factor”.

Techstack:Numpy,Pandas,Matplotlib,YFinance,SKLearn.

Future Enhancements:
1. Rolling PCA (Time-Varying Factors)
Analyze factor stability over time using a rolling window (e.g., 252-day PCA).

2. PCA-Based Risk Forecasting
Use factor variances to generate forward-looking covariance matrices.

3. Integrate with Portfolio Optimization
Use PCA factors for risk-parity or minimum variance optimization.
Build factor-based hedging strategies.

4. Compare PCA with Other Factor Models
CAPM / multi-factor models
Independent Component Analysis (ICA)
Partial Least Squares (PLS)

5. Add Stress Testing
Assess how PCA factors behave during market shocks.
