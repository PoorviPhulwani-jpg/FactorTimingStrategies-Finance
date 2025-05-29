# Factor Timing Strategies Using Machine Learning

This project investigates whether factor timing—adjusting exposure to factors like Value (HML) based on macroeconomic conditions and past performance—can outperform a static investment strategy. We evaluate statistical and machine learning models for predictive power and test their robustness under varying transaction cost scenarios.

## Objective
To assess whether timing exposure to the HML factor using predictive indicators and ML models can improve portfolio performance while managing trading costs and drawdowns.

## Key Components

### 1. Backtesting Timing Strategies
- Strategies tested: `tbl_change`, `HML_rolling_12m`, `bm_percentile`
- Rolling 5-year OLS regressions to determine market entry/exit.
- Benchmarked against a fully invested static strategy.

### 2. Machine Learning Models
Tested for out-of-sample predictive power and performance:
- **Logistic Regression**  
  - Out-of-sample R²: 0.0009  
  - Sharpe Ratio: 0.15 (at 10 bps)
- **Random Forest**  
  - ROC AUC: 0.652  
  - Sharpe Ratio: 0.38
- **XGBoost**  
  - ROC AUC: 0.546  
  - Sharpe Ratio: 0.37  
  - Lower drawdowns observed

### 3. Transaction Cost Analysis
- Evaluated impact of 10, 20, and 50 basis points.
- Compared monthly, quarterly, and semi-annual rebalancing.
- Modeled quadratic (market impact) costs at capital levels: $1M to $50M.

## Results Summary
| Strategy          | Sharpe Ratio | Max Drawdown | Predictive Power (R²) |
|------------------|--------------|---------------|------------------------|
| Logistic Reg     | 0.15 (10bps) | Moderate      | 0.0009                 |
| Random Forest    | 0.38         | 0.26          | 0.074                  |
| XGBoost          | 0.37         | 0.159         | -0.022                 |

- All models offered marginal improvements over static HML strategy.
- Performance highly sensitive to transaction costs and rebalancing frequency.

## Tools & Technologies
- Python (pandas, numpy, scikit-learn, xgboost, matplotlib)
- Quantitative finance concepts: Factor investing, Sharpe ratio, drawdowns
- ML models: Logistic Regression, Random Forest, XGBoost

## Business Relevance
Demonstrates how asset managers can:
- Evaluate dynamic factor exposure strategies
- Balance return, risk, and trading costs
- Use ML to identify periods of factor outperformance
## Contact
For questions or collaboration opportunities, reach out via [LinkedIn](https://linkedin.com/in/poorviphulwani)
