# From Efficient Frontier to Climate Footprint: Portfolio Construction and ESG Diagnostics of a Concentrated U.S. Growth Equity Portfolio

## Overview

This project combines **portfolio optimization**, **performance evaluation**, and **climate diagnostics** to analyze a concentrated U.S. growth equity portfolio derived from the **top 10 holdings of the JPMorgan Large Cap Growth Fund (SEEGX)**.

The analysis was built primarily in **Excel**, with market data initially extracted using **Python / yfinance** and then transformed into a full financial modeling workflow. The project moves from **return and covariance estimation**, to **efficient frontier construction**, to **utility-based portfolio selection**, and finally to a **carbon exposure and transition analysis** using institutional-style climate metrics.

The objective was not only to build a high-return portfolio, but also to evaluate whether that portfolio was:
- financially efficient,
- appropriately aligned with a chosen risk profile,
- and robust when assessed through an ESG / climate lens.

---

## Project Objective

The project answers three related questions:

1. **How can a concentrated equity portfolio be constructed from a restricted investment universe using modern portfolio theory?**
2. **Which efficient portfolio best matches a given investor risk preference?**
3. **What does the final portfolio look like once climate exposure and carbon transition dynamics are incorporated?**

To answer these questions, I:
- selected the **10 largest holdings of SEEGX** as the investable universe,
- estimated annualized expected returns, variances, volatilities, and a covariance matrix from historical monthly data,
- constructed the **efficient frontier** under long-only and fully-invested constraints,
- selected the final portfolio using a **quadratic utility function**,
- evaluated the final portfolio against **SEEGX**, the **Russell 1000**, and the **MSCI World**,
- and extended the analysis using **Weighted Average Carbon Intensity (WACI)** and **five-year carbon intensity evolution**.

---

## Investment Universe

The portfolio universe is restricted to the top 10 holdings of the **JPMorgan Large Cap Growth Fund (SEEGX)**:

- AAPL
- AMZN
- AVGO
- GOOGL
- MA
- META
- MSFT
- NVDA
- ORCL
- TSLA

This approach creates a realistic constrained-universe exercise: rather than optimizing over the whole market, the project builds a portfolio from the core holdings of an actively managed large-cap growth mutual fund.

---

## Methodology

### 1. Data Collection and Standardization

Historical price data were collected for the 10 securities and converted into **monthly returns** over the period **September 2020 to September 2025**.

From these monthly returns, I computed:
- annualized expected returns,
- annualized variances,
- annualized volatilities,
- and the annualized **variance-covariance matrix**.

A **4% risk-free rate** was used in the portfolio optimization framework.

### 2. Efficient Frontier Construction

Using the annualized return vector and covariance matrix, I constructed the **efficient frontier** under the following constraints:

- fully invested portfolio: weights sum to 100%
- long-only portfolio: no short selling

The frontier includes:
- the **Global Minimum Variance Portfolio (GMVP)**
- and multiple efficient portfolios associated with target expected returns

This creates the full menu of minimum-variance portfolios achievable within the SEEGX top-holdings universe.

### 3. Utility-Based Portfolio Selection

To move from the full efficient frontier to one implementable portfolio, I introduced a **utility function** reflecting investor risk aversion.

I tested several values of the risk-aversion parameter and selected the portfolio that maximized utility at **A = 700**. This portfolio is labeled **Effective PF** in the workbook.

This step ensures that the final portfolio is not simply “high return,” but instead the portfolio that offers the most attractive **risk-return trade-off** for the chosen investor profile.

### 4. Performance Evaluation

The selected portfolio was then compared against:
- **SEEGX**
- **Russell 1000**
- **MSCI World**

The evaluation used standard portfolio analytics:
- Standard Deviation
- Sharpe Ratio
- Beta
- Jensen’s Alpha
- Treynor Ratio

This allows the portfolio to be assessed not only in absolute return terms, but also in terms of total risk, systematic risk, and risk-adjusted performance.

### 5. Climate Diagnostics

After the financial optimization stage, I extended the project to include **climate-risk diagnostics** using company-level ESG and carbon data.

Two main indicators were used:

- **Weighted Average Carbon Intensity (WACI)**
- **Five-year carbon intensity evolution**

The analysis focuses on **Scope 3 carbon intensity**, which is especially relevant for technology and digital-platform firms because a significant share of their climate exposure is embedded in supply chains, hardware manufacturing, logistics, and upstream infrastructure.

This second layer transforms the project from a pure portfolio optimization exercise into a more modern **portfolio construction + sustainability diagnostics** framework.

---

## Key Financial Results

The final portfolio selected through the utility-maximization process is a **concentrated six-stock portfolio** with the following approximate weights:

- **AVGO** – 48%
- **ORCL** – 20%
- **GOOGL** – 14%
- **MA** – 12%
- **NVDA** – 4%
- **AAPL** – 3%

The portfolio excludes:
- AMZN
- META
- MSFT
- TSLA

because, within the chosen optimization framework and risk preference, they did not improve the portfolio’s utility.

The final portfolio delivers approximately:
- **Expected return:** 36% p.a.
- **Variance:** 6%
- **Volatility:** 25%

This places it between the 35% and 40% target-return portfolios on the efficient frontier.

The financial interpretation is clear:
- the portfolio is **aggressive and concentrated**
- it generated **exceptional stock-selection alpha**
- but it also carries substantial **specific risk** due to limited diversification

The strongest result is the portfolio’s very high **Jensen’s Alpha**, which indicates that the stock-selection process generated returns well above what would normally be justified by its level of market risk. At the same time, the relatively weak Treynor profile highlights that a large share of performance comes from **idiosyncratic bets**, not from efficient market-risk capture.

In short, the project demonstrates both:
- the **power of concentrated active selection**, and
- the **cost of limited diversification**.

---

## Key Climate Results

The climate analysis shows that the portfolio has a **Weighted Average Carbon Intensity (WACI) of approximately 42.9 tCO₂e / $M revenue**, which is materially below broad U.S. equity benchmark estimates.

This indicates that, despite its aggressive return profile, the portfolio has a relatively favorable **current carbon footprint**, largely because of its strong exposure to technology and digital-services businesses.

However, climate exposure is **not evenly distributed**:
- **Broadcom** and **Oracle** represent the main drivers of the portfolio’s carbon footprint,
- while other holdings contribute much less.

This concentration effect is important because it means that relatively small allocation changes could materially improve the climate profile of the portfolio.

The transition analysis also shows that the underlying holdings are reducing carbon intensity at roughly **10% per year over five years**, which is stronger than many broad net-zero alignment reference paths.

Taken together, the diagnostics suggest that the portfolio combines:
- **low relative current carbon exposure**
- **concentrated emissions risk**
- and a **favorable decarbonization trajectory**

This makes the project stronger than a standard ESG-score exercise: it evaluates both **static exposure** and **dynamic transition momentum**.

---

## Files in this Repository

- Portfolio_Construction.xlsx 
  Main Excel model containing return calculations, covariance matrix, efficient frontier construction, utility analysis, benchmark comparison, and climate diagnostics.

- climate_diagnostics_report.pdf  
  Summary of the ESG / climate analysis, including WACI and carbon transition results.

- Portfolio construction description.docx
    Detailed explanation of the Portfolio Construction.

---

## Tools Used

- **Excel** for portfolio construction, optimization, and diagnostics
- **Python / yfinance** for initial market data extraction
- **LSEG ESG data** for carbon and climate metrics

---


## Summary

This project builds a concentrated U.S. growth equity portfolio from the top holdings of SEEGX, maps the efficient frontier of that restricted universe, selects the final allocation using a utility-maximization framework, evaluates its financial performance against key benchmarks, and then layers in climate diagnostics using WACI and emissions-transition metrics.



