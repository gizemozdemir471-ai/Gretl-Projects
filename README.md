# Gretl-Projects

## Financial Econometrics: Lockheed Martin vs Boeing Risk Analysis

A comprehensive **CAPM (Capital Asset Pricing Model)** analysis comparing systematic and specific risks of two aerospace & defense giants using Gretl econometric software.

---

 Executive Summary

This project examines the risk-return profiles of **Lockheed Martin** and **Boeing** stocks relative to the **S&P 500** market index over the period **February 2020 - January 2025** (60 monthly observations).

 Quick Results

| Metric | Lockheed Martin | Boeing | Portfolio (50-50) |
|--------|-----------------|---------|-------------------|
| **Beta (β)** | 0.998 | 0.994 | 0.996 |
| **Alpha (α)** | +0.794 (NS) | -1.416 (NS) | -0.311 (NS) |
| **R²** | 99.42% | 98.49% | 99.28% |
| **Systematic Risk** | 99.42% | 98.49% | 99.28% |
| **Specific Risk** | 0.58% | 1.51% | 0.72% |
| **F-statistic** | 9,961.51*** | 3,791.62*** | 8,167.94*** |

*NS = Not Significant (p > 0.05) | *** p < 0.001*

---

 Key Findings

1. Both stocks move identically with market** (Beta ≈ 1)
   - Lockheed: β = 0.998 (t = 99.81, p < 0.001)
   - Boeing: β = 0.994 (t = 61.58, p < 0.001)

2. No abnormal returns detected** (Alpha not significant)
   - No evidence of excess risk-adjusted performance
   - Portfolio managers not outperforming market

3. Diversification reduced specific risk by 31.1%**
   - Boeing's 1.51% specific risk → Portfolio's 0.72%
   - Volatility decreased from simple average

4. Systematic risk unchanged** (98-99% market-driven)
   - Both stocks highly correlated with S&P 500
   - Limited benefit from within-sector diversification

5. Lockheed Martin demonstrably superior**
   - Lower specific risk (0.58% vs 1.51%)
   - Higher R² (99.42% vs 98.49%)
   - Lower volatility (SD = 4,883 vs 12,706)

---

Full Analysis Report

 [Download Complete PDF Report](./Gizem%20Özdemir%20Gretl%20Project%201.pdf)

The full report includes:
-  Detailed regression outputs from Gretl
- Comprehensive hypothesis testing (t-tests, F-tests)
- Systematic vs specific risk decomposition
- Portfolio optimization recommendations
- Investment scenario analysis
- Statistical diagnostics (Durbin-Watson, AIC, BIC)

---

 Methodology

 CAPM Framework

Regression Model:

Rᵢ - Rf = αᵢ + βᵢ(Rm - Rf) + εᵢ


Where:
- **Rᵢ - Rf** = Stock excess return
- **Rm - Rf** = Market excess return (S&P 500)
- **αᵢ** = Jensen's Alpha (abnormal return)
- **βᵢ** = Beta (systematic risk measure)
- **εᵢ** = Residual (specific risk)

### Data Specifications

| Parameter | Details |
|-----------|---------|
| **Period**z | February 2020 - January 2025 |
| **Frequency** | Monthly |
| **Observations** | 60 |
| **Market Proxy** | S&P 500 Index (^GSPC) |
| **Stocks Analyzed** | Lockheed Martin (LMT), Boeing (BA) |
| **Portfolio** | Equal-weighted (50% LMT, 50% BA) |
| **Software** | Gretl (Gnu Regression, Econometrics and Time-series Library) |
| **Data Source** | [Investing.com](https://www.investing.com) |

---

## Statistical Results Summary

### Hypothesis Testing

**Beta Coefficients (H₀: β = 0 vs H₁: β ≠ 0)**

| Stock/Portfolio | β | SE(β) | t-stat | p-value | Decision |
|-----------------|---|-------|--------|---------|----------|
| Lockheed Martin | 0.998 | 0.010 | 99.81 | < 0.001 |  Reject H₀ |
| Boeing | 0.994 | 0.016 | 61.58 | < 0.001 |  Reject H₀ |
| Portfolio | 0.996 | 0.011 | 90.38 | < 0.001 | Reject H₀ |

**Alpha Coefficients (H₀: α = 0 vs H₁: α ≠ 0)**

| Stock/Portfolio | α | SE(α) | t-stat | p-value | Decision |
|-----------------|---|-------|--------|---------|----------|
| Lockheed Martin | +0.794 | 2.585 | 0.307 | 0.760 |  Cannot Reject H₀ |
| Boeing | -1.416 | 4.170 | -0.340 | 0.736 |  Cannot Reject H₀ |
| Portfolio | -0.311 | 2.848 | -0.109 | 0.913 |  Cannot Reject H₀ |

**F-Tests (Model Significance)**

| Model | F-statistic | p-value | R² | Adj. R² |
|-------|-------------|---------|-----|---------|
| Lockheed Martin | 9,961.51 | < 0.001 | 99.42% | 99.41% |
| Boeing | 3,791.62 | < 0.001 | 98.49% | 98.47% |
| Portfolio | 8,167.94 | < 0.001 | 99.28% | 99.27% |

---

## Risk Decomposition

### Total Risk = Systematic Risk + Specific Risk

**Lockheed Martin:**
- Systematic: 99.42% (market-driven, non-diversifiable)
- Specific: 0.58% (company-specific, diversifiable)

**Boeing:**
- Systematic: 98.49% (market-driven)
- Specific: 1.51% (company-specific, includes 737 MAX crisis, production issues)

**Portfolio (50-50):**
- Systematic: 99.28% (unchanged from individual stocks)
- Specific: 0.72% (31.1% reduction vs simple average)

### Diversification Effect
```
Expected Specific Risk (simple avg): (0.58% + 1.51%) / 2 = 1.045%
Actual Portfolio Specific Risk: 0.72%
Risk Reduction: (1.045% - 0.72%) / 1.045% = 31.1%
```

---

##  Investment Recommendations

### Scenario Analysis

**Scenario 1: Risk Minimization**
```
→ 100% Lockheed Martin
```
- Lowest specific risk (0.58%)
-  Lowest volatility (SD = 4,883)
-  Highest R² (99.42%)
-  Most reliable beta estimate

**Scenario 2: Balanced Diversification**
```
→ 70% Lockheed Martin + 30% Boeing
```
-  Maintains diversification benefits
-  Reduces Boeing's specific risk impact
-  Similar systematic risk (β ≈ 1)
-  Slightly higher volatility than 100% Lockheed

**Scenario 3: Sector Diversification**
```
→ 40% Lockheed + 30% Boeing + 30% Different Sector
```
-  Cross-sector risk reduction
-  Potential to reduce systematic risk (if other sector has β < 1)
-  Better portfolio optimization
-  Recommended for conservative investors

---

##  Model Diagnostics

### Durbin-Watson Statistics (Autocorrelation Test)

| Model | DW Statistic | Interpretation |
|-------|--------------|----------------|
| Lockheed Martin | 2.142 |  No autocorrelation (ideal ≈ 2) |
| Boeing | 1.980 |  No autocorrelation |
| Portfolio | 2.168 |  No autocorrelation |

*Acceptable range: 1.5 - 2.5*

### Information Criteria

| Model | AIC | BIC (Schwarz) | Hannan-Quinn |
|-------|-----|---------------|--------------|
| Lockheed Martin | 438.22 | 439.86 | 438.86 |
| Boeing | 495.68 | 497.24 | 499.79 |
| Portfolio | 449.84 | 454.03 | 451.48 |

*Lower values indicate better model fit*

---

##  Boeing-Specific Risk Factors

Boeing's elevated specific risk (1.51% vs sector average 0.58%) stems from:

-  **737 MAX Crisis (2018-2020)** - Fatal crashes, global grounding
-  **Production Quality Issues** - Manufacturing defects, delays
-  **Delivery Delays** - Supply chain disruptions
-  **FAA Regulatory Scrutiny** - Enhanced safety oversight
-  **Management Turnover** - Leadership instability
-  **Airbus Competition** - Market share pressure
-  **Defense Contract Variability** - Government spending cycles
-  **Geopolitical Exposure** - China & Russia market restrictions

---

##  Academic Context

**Course:** Financial Econometrics (ECO 672)  
**Level:** Graduate  
**Objective:** Apply CAPM framework to real-world equity analysis  
**Contribution:** Demonstrates portfolio theory principles and risk decomposition

---

##  Technical Notes

### Software & Tools
- **Gretl** v2024+ (Econometric analysis)
- **Investing.com** (Data source)
- **GitHub** (Version control & documentation)

### Replication
To replicate this analysis:
1. Download monthly returns data for LMT, BA, and ^GSPC from Investing.com
2. Calculate excess returns (subtract risk-free rate)
3. Run OLS regression: `Stock_Excess_Return = α + β * Market_Excess_Return + ε`
4. Interpret coefficients, test hypotheses, decompose risk

---

##  Theoretical Background

### Capital Asset Pricing Model (CAPM)

**Expected Return Formula:**
```
E(Rᵢ) = Rf + βᵢ[E(Rm) - Rf]
```

**Beta Interpretation:**
- **β < 1:** Defensive (less volatile than market)
- **β = 1:** Neutral (moves with market) ← Both stocks
- **β > 1:** Aggressive (more volatile than market)

**Alpha (Jensen's Alpha):**
- **α > 0:** Outperformance (risk-adjusted excess return)
- **α = 0:** Fair pricing (market equilibrium) ← Our finding
- **α < 0:** Underperformance

---

##  References

- **Sharpe, W. F. (1964).** "Capital Asset Prices: A Theory of Market Equilibrium under Conditions of Risk." *Journal of Finance*, 19(3), 425-442.
- **Jensen, M. C. (1968).** "The Performance of Mutual Funds in the Period 1945-1964." *Journal of Finance*, 23(2), 389-416.
- **Markowitz, H. (1952).** "Portfolio Selection." *Journal of Finance*, 7(1), 77-91.
- **Data Source:** [Investing.com](https://www.investing.com) - Stock price data
- **Software:** [Gretl](http://gretl.sourceforge.net/) - Econometric analysis

---

##  Contact & Collaboration

- **GitHub:** [@gizemozdemir471-ai](https://github.com/gizemozdemir471-ai)
- **Repository:** [Gretl-Projects](https://github.com/gizemozdemir471-ai/Gretl-Projects)

Questions, suggestions, or collaboration opportunities? Feel free to:
-  Open an issue
-  Start a discussion
-  Star the repository if you find it useful

---

##  License & Disclaimer

**Educational Use Only**  
This project is submitted as part of academic coursework in Financial Econometrics. 

**Investment Disclaimer:**  
This analysis is for educational purposes only and should **not** be considered investment advice. Past performance does not guarantee future results. Consult a licensed financial advisor before making investment decisions.

---

##  Acknowledgments

- **Course Instructor:** Prof. Dr. Lütfi Erden
- **Institution:** Graduate Economics Program
- **Analysis Period:** February 2020 - January 2025
- **Special Thanks:** Gretl open-source community

---

<div align="center">

** If this analysis helped you understand CAPM or portfolio theory, please star this repository!**

*Last Updated: January 2025*

</div>

