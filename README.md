Project Overview:
Developed a PCA-based risk factor model to decompose equity portfolio risk into systematic and idiosyncratic components, enabling dimensionality reduction, factor attribution, and improved covariance understanding for downstream risk applications (VaR, ES, stress testing, portfolio optimization).
Using daily returns of 5 liquid equities, the model identifies dominant co-movement drivers and quantifies how much portfolio variance is explained by each latent factor—mirroring institutional statistical factor models used in market risk frameworks.

Objectives:
Identify dominant systematic risk factors driving equity co-movement.
Quantify variance contribution of each factor for risk attribution.
Construct eigenportfolios to interpret factor exposures.
Generate factor return series for risk monitoring and diagnostics.
Demonstrate dimensionality reduction while preserving risk information.

Methodology:

1. Data Preparation
Collected multi-year daily equity returns for 5 stocks.
Handled missing data and standardized returns to ensure scale-invariant PCA.
Focused on return covariance structure relevant for market risk estimation.

2. PCA Risk Factor Extraction
Computed covariance matrix of standardized returns.
Extracted eigenvalues (risk explained) and eigenvectors (factor loadings).
Ranked components by variance contribution.
Retained economically meaningful components based on explained variance thresholds.


3. Factor Construction & Diagnostics
Built eigenportfolios representing each PCA factor.
Derived factor returns as linear combinations of asset returns.
Visualized:
Explained variance and cumulative variance.
PC1 and PC2 factor return dynamics.
Eigenportfolio weights for interpretability.

Results
| **PCA Factor** | **Variance Contribution** | **% of Total Risk** |
| -------------- | ------------------------- | ------------------- |
| **PC1**        | 0.75095                   | **75.10%**          |
| **PC2**        | 0.15743                   | **15.74%**          |
| **PC3**        | 0.06320                   | **6.32%**           |
| **PC4**        | 0.02547                   | **2.55%**           |
| **PC5**        | 0.00294                   | **0.29%**           |


Interpretation:

PC1 (≈75%) — Market/Systematic Risk Factor
Represents broad equity market exposure with uniform positive loadings, analogous to an implicit equity beta factor. Dominates portfolio risk and drives stress sensitivity.

PC2 (≈16%) — Relative / Style Risk Factor
Orthogonal to PC1, capturing cross-sectional dispersion (sector or style rotation). Becomes prominent during relative-value or rotation-driven markets.

PC3 (≈6%) — Residual/Idiosyncratic Risk
Reflects stock-specific dynamics not explained by common factors; marginal impact on total risk.

PC4 & PC5 (<3% combined)
Represent statistical noise with negligible contribution—excluded without material information loss.


Dimensionality Reduction Impact
Reduced 5 correlated return series → 2 dominant risk factors.
Preserved >90% of total variance.
Simplified covariance structure while retaining systematic risk fidelity.
Directly applicable to factor-based VaR, ES, and stress testing.


Eigenportfolio Insights:

PC1 Eigenportfolio:
Long-only, evenly weighted → market beta proxy.

PC2 Eigenportfolio:
Long/short structure → relative risk / style factor, useful for hedging and diversification analysis.


Tech Stack:NumPy,Pandas,scikit-learn,Matplotlib,YFinance.


Future Enhancements:

Rolling PCA (Time-Varying Risk Factors)
Track factor stability using rolling 252-day windows; detect regime shifts.

PCA-Based Covariance Forecasting
Reconstruct forward covariance matrices from factor variances and loadings.

Integration with Risk Capital Models
Use PCA factors in minimum variance, risk parity, and hedging frameworks.

Model Comparison & Validation
Benchmark PCA against CAPM, multi-factor models, ICA, and PLS.

Stress & Shock Analysis
Quantify factor behavior under equity crashes, volatility spikes, and correlation breakdowns.



Key Takeaways:
Equity portfolio risk is highly concentrated in a small number of latent factors.
PCA effectively separates systematic vs. idiosyncratic risk without imposing economic assumptions.
Enables parsimonious risk models with strong explanatory power.
Provides a robust statistical foundation for covariance forecasting, VaR/ES, and stress analysis.
