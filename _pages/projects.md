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
This flagship project centers on the development of a comprehensive credit risk framework compliant with international regulatory standards such as the Basel Accords and IFRS 9. The primary goal is to predict and quantify potential credit losses by modeling the three core components of Expected Loss (EL).

*   **Methodology & Implementation:**
    *   **Probability of Default (PD):** A logistic regression model was developed to estimate the likelihood of a borrower defaulting. This model produces a practical scorecard for assessing new loan applications.
    *   **Loss Given Default (LGD):** This component quantifies the proportion of the exposure that will be lost if a borrower defaults. A regression model was implemented to predict this value.
    *   **Exposure at Default (EAD):** This model estimates the total value a lender is exposed to when a borrower defaults.
    *   **Expected Loss (EL):** The final EL is calculated as the product of PD, LGD, and EAD, providing a forward-looking measure of anticipated credit losses.
*   **Technical Stack:** The entire pipeline was built in Python, utilizing `pandas` for data manipulation, and `scikit-learn` for implementing the regression models.
*   **Insights:** The project successfully created a functional pipeline for credit risk assessment. A key finding was the trade-off between the interpretability of traditional logistic regression for scorecarding and the superior predictive power of more complex machine learning models like Random Forests for default prediction.

*   **Associated Repository:** [Link to Your GitHub Repository Here]

### Market Risk and Volatility Forecasting
This project delves into the quantification of market risk, with a focus on estimating potential portfolio losses under adverse market movements using standard risk measures like Value at Risk (VaR) and Conditional Value at Risk (CVaR).

*   **Methodology & Implementation:**
    *   **VaR Estimation:** VaR was calculated using multiple methods to provide a comprehensive risk picture. This included Historical Simulation, Parametric methods assuming a specific distribution, and Monte Carlo simulation for a more flexible approach.
    *   **Volatility Modeling:** To capture the time-varying nature of market volatility (volatility clustering), GARCH (Generalized Autoregressive Conditional Heteroskedasticity) and EWMA (Exponentially Weighted Moving Average) models were implemented. These models provide more accurate, short-term volatility forecasts, which are critical inputs for VaR calculations.
    *   **Backtesting:** The accuracy of the VaR models was rigorously validated through systematic backtesting, comparing predicted losses against actual outcomes to ensure model robustness.
*   **Technical Stack:** The analysis was conducted in Python, using libraries such as `numpy`, `pandas`, and specialized packages for time series analysis and GARCH modeling.
*   **Insights:** The analysis demonstrated that while historical simulation is straightforward, GARCH-based models offer superior accuracy in forecasting VaR, especially during periods of high market turbulence. CVaR was also highlighted as a more informative risk measure as it quantifies the expected loss *beyond* the VaR level.

*   **Associated Repository:** [Link to Your GitHub Repository Here]

### Operational Risk Capital Modeling (Loss Distribution Approach)
In alignment with the Basel II framework's Advanced Measurement Approach (AMA), this project models operational risk capital. Operational risk stems from failed internal processes, people, systems, or from external events.

*   **Methodology & Implementation:**
    *   The **Loss Distribution Approach (LDA)** was employed, which is a sophisticated statistical method for this purpose.
    *   **Frequency and Severity Modeling:** The model separately simulates the frequency of operational loss events (e.g., using a Poisson distribution) and the severity of each loss (e.g., using a Log-normal or Generalized Pareto distribution).
    *   **Monte Carlo Simulation:** A large number of Monte Carlo simulations are run to convolve the frequency and severity distributions, generating a comprehensive aggregate loss distribution for a one-year period.
    *   **Capital Calculation:** The required regulatory capital is determined by calculating the Value-at-Risk (VaR) on this aggregate loss distribution at a very high confidence level (e.g., 99.9%).
*   **Insights:** A significant challenge in this domain is the scarcity of internal data for high-severity, low-frequency events. This project underscores the importance of combining internal data with external data and scenario analysis to create a more robust model of the tail of the loss distribution.

*   **Associated Repository:** [Link to Your GitHub Repository Here]

## Derivative Pricing and Stochastic Modeling

This section details my work in valuing financial derivatives and modeling the stochastic nature of underlying assets, forming the core of quantitative finance.

### Multi-Method Option Pricing
This project provides a comparative implementation of the canonical models used for pricing European and American style options, highlighting the strengths and weaknesses of each approach.

*   **Models Implemented:**
    *   **Black-Scholes-Merton Model:** A closed-form solution for European options, valued for its speed and analytical tractability. Implemented in Python to serve as a baseline.
    *   **Binomial/Trinomial Tree Models:** Discrete-time numerical methods that are particularly well-suited for pricing American options, which allow for early exercise.
    *   **Monte Carlo Simulation:** A powerful and flexible method that can handle complex payoff structures and asset dynamics. It involves simulating thousands of random price paths for the underlying asset to price the option.
*   **Technical Stack:** The models were implemented in Python, leveraging `NumPy` and `SciPy` for numerical computations and simulations.
*   **Insights:** The project provides a clear illustration of the trade-offs in derivative pricing: the Black-Scholes model is fast but relies on strong assumptions (e.g., constant volatility), while Monte Carlo simulations are highly flexible but computationally intensive. The choice of model is demonstrated to be highly dependent on the specific derivative and the desired balance between speed and accuracy.

*   **Associated Repository:** [Link to Your GitHub Repository Here]

### Advanced Stochastic Modeling for Asset Prices
Standard asset price models like Geometric Brownian Motion (GBM) often fail to capture real-world phenomena like market jumps. This project explores more advanced stochastic processes.

*   **Methodology & Implementation:**
    *   **Geometric Brownian Motion (GBM):** Implemented as the foundational continuous-time stochastic process for asset price modeling.
    *   **Jump-Diffusion Models (Merton Model):** To better capture the "fat tails" and sudden, large movements observed in financial markets, a jump-diffusion process was implemented. This model superimposes a Poisson process (for jumps) onto a standard GBM process.
*   **Insights:** The results show that jump-diffusion models provide a better fit for historical asset returns compared to pure GBM, as they can account for sudden shocks and crashes. This superior fit translates into more realistic option prices and risk assessments, though it comes at the cost of increased model complexity and more parameters to calibrate.

*   **Associated Repository:** [Link to Your GitHub Repository Here]

### Stochastic Interest Rate Modeling (Short-Rate Models)
This project focuses on modeling the term structure of interest rates, which is crucial for pricing fixed-income securities and their derivatives.

*   **Models Implemented:**
    *   **Vasicek Model:** A mean-reverting model where the short-rate tends to drift towards a long-term mean. It is analytically tractable but has the limitation of allowing negative interest rates.
    *   **Cox-Ingersoll-Ross (CIR) Model:** An extension of the Vasicek model that includes a square-root term, preventing interest rates from becoming negative and making the volatility level-dependent.
*   **Methodology & Implementation:** The project involved calibrating these one-factor models to historical market data using techniques like Maximum Likelihood Estimation (MLE) or Least Squares. Once calibrated, the models were used to simulate future interest rate paths and price interest rate derivatives.
*   **Insights:** The project highlights the fundamental differences between equilibrium models (like Vasicek and CIR) and no-arbitrage models. While the CIR model improves upon Vasicek by precluding negative rates, both are relatively simple one-factor models that may not capture all the complex dynamics of the yield curve.

*   **Associated Repository:** [Link to Your GitHub Repository Here]

## Numerical Analysis in Finance

Many problems in quantitative finance do not have closed-form solutions and must be solved using numerical approximation techniques. This section showcases my work in implementing these foundational algorithms.

### Practical Applications of Numerical Methods
This project is a collection of essential numerical algorithms applied to common financial problems, demonstrating the computational backbone of modern finance.

*   **Algorithms & Applications:**
    *   **Root-Finding (e.g., Newton-Raphson, Bisection):** Implemented to solve for quantities like a bond's Yield-to-Maturity (YTM) or to find the implied volatility from an option's market price.
    *   **Numerical Integration (e.g., Quadrature):** Used for pricing derivatives where the payoff is path-dependent or the underlying distribution is complex.
    *   **Solvers for Ordinary and Partial Differential Equations (ODEs/PDEs):** Finite difference methods were implemented to solve the Black-Scholes PDE, providing another avenue for pricing American and exotic options.
*   **Technical Stack:** These methods were coded from scratch in Python to ensure a deep understanding of their mechanics, with comparisons made against optimized libraries like `SciPy`.
*   **Insights:** This work emphasizes that numerical analysis is not just a theoretical exercise but a practical necessity in finance for risk assessment and portfolio optimization. It demonstrates the ability to translate complex mathematical formulas into robust and efficient code.

*   **Associated Repository:** [Link to Your GitHub Repository Here]


---


This portfolio presents a collection of my key projects in quantitative risk management and financial engineering. Grounded in my professional experience at institutions like EUREX Clearing and Deutsche Börse, and academic work at WorldQuant and Goethe University, these projects demonstrate my proficiency in developing, validating, and implementing sophisticated risk models. Each project is designed to solve practical financial problems, leveraging advanced analytical techniques and robust programming in Python. The associated GitHub repositories provide a transparent view of my methodologies and coding expertise.

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

*   **Associated Repository:** [Link to Your GitHub Repository Here]

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

*   **Associated Repository:** [Link to Your GitHub Repository Here]

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

*   **Associated Repository:** [Link to Your GitHub Repository Here]

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

*   **Associated Repository:** [Link to Your GitHub Repository Here]



