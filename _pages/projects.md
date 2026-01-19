---
title: "Portfolio"
layout: single
sitemap: true
permalink: /projects/
author_profile: true
toc: true
toc_label: "Portfolio"
toc_icon: "gear"
toc_sticky: true
---

This portfolio presents a collection of my key projects in quantitative risk management and financial engineering. Grounded in my professional experience at institutions like [EUREX Clearing](https://www.eurex.com/ec-en) and [Deutsche Börse](https://deutsche-boerse.com/dbg-de/), and academic work at [WorldQuant](https://www.wqu.edu/), these projects demonstrate my proficiency in _developing, validating, and implementing sophisticated risk models_. Each project is designed to solve practical financial problems, leveraging advanced analytical techniques and robust programming in `Python`. The associated GitHub repositories provide a transparent view of my methodologies and coding expertise.

## Market Risk Modeling

My work in market risk focuses on quantifying and validating potential losses in financial portfolios, ensuring that risk measurement frameworks are both accurate and compliant with regulatory standards.

### VaR Backtesting Engine
A critical component of market risk management is not only calculating Value at Risk (VaR) but also rigorously validating its predictive accuracy. This project involved building a comprehensive VaR backtesting engine in Python to test the performance of various VaR models, directly inspired by my graduate thesis on the empirical testing of VaR.

*   **Objective:** To create a reusable and automated framework for backtesting VaR models, ensuring they meet regulatory scrutiny and provide reliable risk estimates.
*   **Methodology & Implementation:**
    *   The engine implements two industry-standard hypothesis tests:
        *   **Kupiec's Proportion of Failures (POF) Test:** To assess whether the observed frequency of VaR breaches (exceptions) is statistically consistent with the model's specified confidence level.
        *   **Christoffersen's Independence Test:** To test whether VaR breaches are independent of each other, ensuring that exceptions do not cluster, which would indicate a failing model.
    *   The framework is designed to ingest portfolio return series and corresponding VaR estimates to automatically generate test statistics, p-values, and clear model performance summaries.
*   **Technical Stack:** Developed in Python, utilizing `Pandas` for time series manipulation, `NumPy` and `SciPy`/`Statsmodels` for statistical calculations and hypothesis testing.

*   **Associated Repository:** [Link to the GitHub Repository Here](https://github.com/Mostafa-MMK/VaRBacktestingEngine)]

## Credit Risk Modeling

These projects reflect my experience in modeling credit risk for both regulatory capital purposes and internal decision-making, covering the complete lifecycle from data processing to model deployment.

### PD, LGD, and EAD Models for Regulatory Capital
This project showcases the development of a full suite of credit risk models—Probability of Default (PD), Loss Given Default (LGD), and Exposure at Default (EAD)—aligned with the Internal Ratings-Based (IRB) approach under the Basel framework.

*   **Objective:** To construct and validate robust models for estimating Expected Loss (EL) and regulatory capital (RWA) for a corporate credit portfolio.
*   **Methodology & Implementation:**
    *   **PD Model:** Developed using logistic regression, leveraging financial statement data and macroeconomic variables to predict the 1-year default probability. The model output facilitates internal credit scoring.
    *   **LGD & EAD Models:** Implemented regression-based models to predict the loss severity and exposure amount in the event of a default, respectively, considering factors like collateral and seniority.
    *   **Model Types:** Explored both structural models (Merton-style) and reduced-form models to understand their theoretical underpinnings and practical implications.
*   **Technical Stack:** The project was built using Python, with `scikit-learn` for machine learning model implementation, `Statsmodels` for detailed statistical analysis, and `Matplotlib` for performance visualization.

*   **Associated Repository:** [Link to the GitHub Repository Here](https://github.com/Mostafa-MMK/CreditRiskModels)

## Fixed Income & Interest Rate Modeling

My work in fixed income involves analyzing the term structure of interest rates, a cornerstone for pricing bonds and interest rate derivatives.

### Yield Curve Modeling and Analysis
Accurately constructing and interpreting the yield curve is fundamental to fixed income analysis. This project focuses on building yield curves from raw bond data and analyzing their dynamics.

*   **Objective:** To develop a Python-based tool for bootstrapping yield curves from government bond data and to perform principal component analysis (PCA) to understand the main drivers of curve movements.
*   **Methodology & Implementation:**
    *   **Bootstrapping:** Implemented an algorithm to derive zero-coupon rates (spot rates) iteratively from the prices of coupon-bearing bonds.
    *   **Principal Component Analysis (PCA):** Applied PCA to a time series of historical yield curve shifts to identify the primary factors of interest rate movements, typically interpreted as Level, Slope, and Curvature.
    *   **Risk Calculation:** The constructed curves and PCA factors were then used to calculate key risk metrics like DV01 (Dollar Value of a '01) and Convexity for fixed income portfolios.
*   **Technical Stack:** Python, with `NumPy` and `SciPy` for optimization and interpolation during bootstrapping, and `scikit-learn` for performing PCA.

*   **Associated Repository:** [Link to the GitHub Repository Here](https://github.com/Mostafa-MMK/FixedIncomeModels)

## Derivative Pricing Models

This section highlights my expertise in implementing both foundational and advanced models for the valuation of financial derivatives, a key skill for any quantitative risk role.

### Advanced Option Pricing Models
This project goes beyond the standard Black-Scholes model to implement more sophisticated models that capture well-known stylized facts of financial markets, such as the volatility smile and smirk.

*   **Objective:** To implement and compare a suite of option pricing models, from the classic Black-Scholes to advanced stochastic volatility models, in a unified Python framework.
*   **Models Implemented:**
    *   **Black-Scholes-Merton:** The foundational model, serving as a benchmark.
    *   **Heston Model:** A stochastic volatility model that assumes volatility itself follows a random, mean-reverting process. It is capable of generating a volatility smirk.
    *   **SABR (Stochastic Alpha, Beta, Rho) Model:** A popular stochastic volatility model used extensively by practitioners, especially in interest rate derivative markets, for its ability to fit smile dynamics accurately.
    *   **Local Volatility Model:** An alternative approach that assumes volatility is a deterministic function of the asset price and time, calibrated to perfectly match observed market option prices.
*   **Technical Stack:** This project was implemented in Python, leveraging `QuantLib` for its powerful financial engineering capabilities, alongside `NumPy` and `SciPy` for numerical methods like Monte Carlo simulation and PDE solvers.

*   **Associated Repository:** [Link to the GitHub Repository Here](https://github.com/Mostafa-MMK/DerivativePricing)



