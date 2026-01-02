# 📦 Konys Inc. — Procurement Risk Under Uncertainty
**Monte Carlo Simulation for Contract Design and Risk Transfer**

![Prescriptive Analytics](https://img.shields.io/badge/Prescriptive%20Analytics-0A9396?style=for-the-badge)
![Simulation](https://img.shields.io/badge/Simulation-2A9D8F?style=for-the-badge)
![Risk Management](https://img.shields.io/badge/Risk%20Management-C1121F?style=for-the-badge)
![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)

## Executive Summary
Procurement leaders often face a repeatable tradeoff: commit early to lock in price and supply, or stay flexible and risk paying volatile spot prices. This project builds a Monte Carlo simulation to evaluate procurement policies under uncertainty and quantify both expected profit and downside risk.

The model compares:
- **Purchase contracts** (committed volume at a fixed price)
- **Option contracts** (pay a reservation fee for the right—not obligation—to buy later at a fixed exercise price)
- **Spot market purchases** (used to satisfy shortfalls when demand exceeds committed supply)

## Decision Problem
For a high-volume component with volatile demand and volatile spot prices:
- What **base order quantity** should we commit to under a purchase contract?
- How much **flexibility** (option capacity) should we reserve to manage upside demand and spot price spikes?

## Approach
1. **Model the uncertain drivers**
   - Demand modeled as a probability distribution (e.g., Normal)
   - Spot price modeled as a probability distribution (e.g., Uniform)

2. **Simulate outcomes**
   - Run 10,000+ scenarios
   - Compute profit per scenario based on sourcing rules:
     - Base commitment via purchase contract
     - Additional demand covered by exercising options (only when cheaper than spot) or buying spot
     - Excess committed inventory salvaged

3. **Compare policies**
   - Expected profit
   - 90% confidence interval for expected profit
   - Downside risk via percentiles (e.g., 5th percentile profit)

## What the Model Reveals (Manager Takeaways)
- **Contract structure is a risk management tool**: it reshapes the distribution of outcomes, not just the average.
- **Flexibility has an optimal level**: too little exposes the firm to spot spikes; too much wastes reservation fees.
- The best policy depends on the joint behavior of **demand volatility** and **spot price volatility**.

## Repository Contents
- `konys_monte_carlo_contracts_refactored.ipynb` — simulation model with clean, manager-readable notes and parameterized inputs
- `README.md` — executive framing and interpretation

## NDA-Safe / Educational Disclosure
This project demonstrates procurement decision modeling techniques (Monte Carlo simulation + contract logic). It does not include proprietary data, internal supplier terms, or case text.

**Note:** The original case used for classroom discussion is copyrighted and is not reproduced here.
