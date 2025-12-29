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

As a dedicated quantitative finance professional, this portfolio showcases a curated collection of my projects. It serves as a testament to my deep-seated expertise in applying rigorous mathematical, statistical, and computational methodologies to solve complex financial challenges. The work detailed here spans the critical domains of risk management, derivative valuation, and advanced stochastic modeling. Each project summary is crafted to provide not only a high-level overview of the objectives and outcomes but also a granular look at the technical approaches and theoretical foundations. For those interested in a deeper dive, corresponding GitHub repositories are linked, offering complete access to the underlying code, data, and analyses.

## Risk Management

The cornerstone of a resilient financial system is a robust and forward-looking risk management framework. My projects in this discipline are focused on the precise identification, measurement, and strategic mitigation of multifaceted financial risks, leveraging both traditional and machine learning-based approaches.

### Credit Risk Modeling and Expected Loss Calculation
This flagship project centers on the development of a comprehensive credit risk framework compliant with international regulatory standards such as the Basel Accords and IFRS 9. [2, 3] The primary goal is to predict and quantify potential credit losses by modeling the three core components of Expected Loss (EL). [5]

*   **Methodology & Implementation:**
    *   **Probability of Default (PD):** A logistic regression model was developed to estimate the likelihood of a borrower defaulting. [3, 5] This model produces a practical scorecard for assessing new loan applications. [2]
    *   **Loss Given Default (LGD):** This component quantifies the proportion of the exposure that will be lost if a borrower defaults. A regression model was implemented to predict this value. [2, 29]
    *   **Exposure at Default (EAD):** This model estimates the total value a lender is exposed to when a borrower defaults. [2, 29]
    *   **Expected Loss (EL):** The final EL is calculated as the product of PD, LGD, and EAD, providing a forward-looking measure of anticipated credit losses. [5]
*   **Technical Stack:** The entire pipeline was built in Python, utilizing `pandas` for data manipulation, and `scikit-learn` for implementing the regression models. [5, 20]
*   **Insights:** The project successfully created a functional pipeline for credit risk assessment. A key finding was the trade-off between the interpretability of traditional logistic regression for scorecarding and the superior predictive power of more complex machine learning models like Random Forests for default prediction. [20]

*   **Associated Repository:** [GitHub - Credit Risk Modelling](https://github.com/levist7/Credit_Risk_Modelling) [2]

### Market Risk and Volatility Forecasting
This project delves into the quantification of market risk, with a focus on estimating potential portfolio losses under adverse market movements using standard risk measures like Value at Risk (VaR) and Conditional Value at Risk (CVaR).

*   **Methodology & Implementation:**
    *   **VaR Estimation:** VaR was calculated using multiple methods to provide a comprehensive risk picture. This included Historical Simulation, Parametric methods assuming a specific distribution, and Monte Carlo simulation for a more flexible approach. [6]
    *   **Volatility Modeling:** To capture the time-varying nature of market volatility (volatility clustering), GARCH (Generalized Autoregressive Conditional Heteroskedasticity) and EWMA (Exponentially Weighted Moving Average) models were implemented. [17, 30] These models provide more accurate, short-term volatility forecasts, which are critical inputs for VaR calculations. [31]
    *   **Backtesting:** The accuracy of the VaR models was rigorously validated through systematic backtesting, comparing predicted losses against actual outcomes to ensure model robustness. [6, 30]
*   **Technical Stack:** The analysis was conducted in Python, using libraries such as `numpy`, `pandas`, and specialized packages for time series analysis and GARCH modeling. [6, 17]
*   **Insights:** The analysis demonstrated that while historical simulation is straightforward, GARCH-based models offer superior accuracy in forecasting VaR, especially during periods of high market turbulence. [33] CVaR was also highlighted as a more informative risk measure as it quantifies the expected loss *beyond* the VaR level. [6]

*   **Associated Repository:** [GitHub - Value-at-Risk-VaR-Modeling-in-Python](https://github.com/MehrdadHeyrani/Value-at-Risk-VaR-Modeling-in-Python) [17]

### Operational Risk Capital Modeling (Loss Distribution Approach)
In alignment with the Basel II framework's Advanced Measurement Approach (AMA), this project models operational risk capital. [26, 35] Operational risk stems from failed internal processes, people, systems, or external events. [34]

*   **Methodology & Implementation:**
    *   The **Loss Distribution Approach (LDA)** was employed, which is a sophisticated statistical method for this purpose. [16, 26]
    *   **Frequency and Severity Modeling:** The model separately simulates the frequency of operational loss events (e.g., using a Poisson distribution) and the severity of each loss (e.g., using a Log-normal or Generalized Pareto distribution). [16, 32, 34]
    *   **Monte Carlo Simulation:** A large number of Monte Carlo simulations are run to convolve the frequency and severity distributions, generating a comprehensive aggregate loss distribution for a one-year period. [16, 32]
    *   **Capital Calculation:** The required regulatory capital is determined by calculating the Value-at-Risk (VaR) on this aggregate loss distribution at a very high confidence level (e.g., 99.9%). [16, 35]
*   **Insights:** A significant challenge in this domain is the scarcity of internal data for high-severity, low-frequency events. [34] This project underscores the importance of combining internal data with external data and scenario analysis to create a more robust model of the tail of the loss distribution. [35]

*   **Associated Repository:** [GitHub - Loss-Distribution-Model-Validation](https://github.com/aadusumilli87/Loss-Distribution-Model-Validation) [32]

## Derivative Pricing and Stochastic Modeling

This section details my work in valuing financial derivatives and modeling the stochastic nature of underlying assets, forming the core of quantitative finance.

### Multi-Method Option Pricing
This project provides a comparative implementation of the canonical models used for pricing European and American style options, highlighting the strengths and weaknesses of each approach.

*   **Models Implemented:**
    *   **Black-Scholes-Merton Model:** A closed-form solution for European options, valued for its speed and analytical tractability. [13, 18, 23] Implemented in Python to serve as a baseline. [23]
    *   **Binomial/Trinomial Tree Models:** Discrete-time numerical methods that are particularly well-suited for pricing American options, which allow for early exercise. [18]
    *   **Monte Carlo Simulation:** A powerful and flexible method that can handle complex payoff structures and asset dynamics. It involves simulating thousands of random price paths for the underlying asset to price the option. [13, 19, 22]
*   **Technical Stack:** The models were implemented in Python, leveraging `NumPy` and `SciPy` for numerical computations and simulations. [1, 4]
*   **Insights:** The project provides a clear illustration of the trade-offs in derivative pricing: the Black-Scholes model is fast but relies on strong assumptions (e.g., constant volatility), while Monte Carlo simulations are highly flexible but computationally intensive. [11, 18] The choice of model is demonstrated to be highly dependent on the specific derivative and the desired balance between speed and accuracy. [22]

*   **Associated Repository:** [GitHub - Black-Scholes-Option-Pricing-with-Monte-Carlo](https://github.com/aldodec/Black-Scholes-Option-Pricing-with-Monte-Carlo) [19]

### Advanced Stochastic Modeling for Asset Prices
Standard asset price models like Geometric Brownian Motion (GBM) often fail to capture real-world phenomena like market jumps. This project explores more advanced stochastic processes.

*   **Methodology & Implementation:**
    *   **Geometric Brownian Motion (GBM):** Implemented as the foundational continuous-time stochastic process for asset price modeling. [11]
    *   **Jump-Diffusion Models (Merton Model):** To better capture the "fat tails" and sudden, large movements observed in financial markets, a jump-diffusion process was implemented. This model superimposes a Poisson process (for jumps) onto a standard GBM process. [7, 9, 14]
*   **Insights:** The results show that jump-diffusion models provide a better fit for historical asset returns compared to pure GBM, as they can account for sudden shocks and crashes. [12, 14] This superior fit translates into more realistic option prices and risk assessments, though it comes at the cost of increased model complexity and more parameters to calibrate. [7, 9]

*   **Associated Repository (Conceptual):** [GitHub - Jump Diffusion & Stochastic Volatility Models](https://github.com/AliMohammadGhanbari/Jump-Diffusion-Stochastic-Volatility-Models-for-Option-Pricing) [11]

### Stochastic Interest Rate Modeling (Short-Rate Models)
This project focuses on modeling the term structure of interest rates, which is crucial for pricing fixed-income securities and their derivatives.

*   **Models Implemented:**
    *   **Vasicek Model:** A mean-reverting model where the short-rate tends to drift towards a long-term mean. It is analytically tractable but has the limitation of allowing negative interest rates. [21, 25, 28]
    *   **Cox-Ingersoll-Ross (CIR) Model:** An extension of the Vasicek model that includes a square-root term, preventing interest rates from becoming negative and making the volatility level-dependent. [10, 28]
*   **Methodology & Implementation:** The project involved calibrating these one-factor models to historical market data using techniques like Maximum Likelihood Estimation (MLE) or Least Squares. [10, 27] Once calibrated, the models were used to simulate future interest rate paths and price interest rate derivatives. [25]
*   **Insights:** The project highlights the fundamental differences between equilibrium models (like Vasicek and CIR) and no-arbitrage models. While the CIR model improves upon Vasicek by precluding negative rates, both are relatively simple one-factor models that may not capture all the complex dynamics of the yield curve. [27, 28]

*   **Associated Repository:** [GitHub - interest_rate_forecasting](https://github.com/YuriAntonelli/interest_rate_forecasting) [10]

## Numerical Analysis in Finance

Many problems in quantitative finance do not have closed-form solutions and must be solved using numerical approximation techniques. This section showcases my work in implementing these foundational algorithms. [8]

### Practical Applications of Numerical Methods
This project is a collection of essential numerical algorithms applied to common financial problems, demonstrating the computational backbone of modern finance. [15]

*   **Algorithms & Applications:**
    *   **Root-Finding (e.g., Newton-Raphson, Bisection):** Implemented to solve for quantities like a bond's Yield-to-Maturity (YTM) or to find the implied volatility from an option's market price.
    *   **Numerical Integration (e.g., Quadrature):** Used for pricing derivatives where the payoff is path-dependent or the underlying distribution is complex.
    *   **Solvers for Ordinary and Partial Differential Equations (ODEs/PDEs):** Finite difference methods were implemented to solve the Black-Scholes PDE, providing another avenue for pricing American and exotic options. [15]
*   **Technical Stack:** These methods were coded from scratch in Python to ensure a deep understanding of their mechanics, with comparisons made against optimized libraries like `SciPy`. [8]
*   **Insights:** This work emphasizes that numerical analysis is not just a theoretical exercise but a practical necessity in finance for risk assessment and portfolio optimization. [8] It demonstrates the ability to translate complex mathematical formulas into robust and efficient code.

*   **Associated Repository (Conceptual):** [GitHub - Numerical Analysis with Applications in Python](https://github.com/TienChih-Lin/Numerical-Analysis-with-Python-for-Finance)
