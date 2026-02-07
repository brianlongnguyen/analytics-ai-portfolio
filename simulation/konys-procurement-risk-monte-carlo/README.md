# 📦 Konys Inc — Procurement Risk Simulation
### Monte Carlo Simulation for Contract & Spot Procurement Decisions

![Monte Carlo](https://img.shields.io/badge/Simulation-Monte%20Carlo-0A9396?style=for-the-badge)
![Risk Analytics](https://img.shields.io/badge/Risk%20Analytics-2962FF?style=for-the-badge)
![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)

---

## Executive Summary

Procurement decisions must balance contract purchases with uncertain demand and spot pricing. Overcommitting creates waste, while undercommitting exposes firms to costly spot purchases.

This project models procurement decisions under uncertainty using Monte Carlo simulation to evaluate risk-adjusted profitability.

---

## Decision Problem

The company must decide how much to purchase via long-term contracts versus spot markets under uncertain demand.

Key tradeoffs include:

- Over-purchasing risk
- Spot price exposure
- Inventory salvage value

---

## Approach

Demand and spot prices are modeled as random variables.

Monte Carlo simulation generates thousands of possible demand-price scenarios.

Profit outcomes are evaluated for each procurement strategy.

Statistical summaries quantify expected profit and downside risk.

---

## Impact / Key Findings

Results show:

- Contract purchasing stabilizes profits but risks excess inventory.
- Spot purchasing increases volatility.
- Optimal decisions balance risk and cost exposure.

Decision quality improves when procurement strategy considers distribution outcomes rather than averages.

---

## 📐 Mathematical Formulation (Simplified)

Profit:

\[
Profit = Revenue - ContractCost - SpotCost + Salvage
\]

Demand and spot prices follow distributions:

\[
D \sim N(\mu, \sigma), \quad P_{spot} \sim U(a, b)
\]

Monte Carlo simulation estimates outcome distributions.

---

## 🌍 Industry Applicability

Procurement risk frameworks apply across industries including:

- Supply chain operations
- Manufacturing sourcing
- Commodity procurement
- Infrastructure purchasing

---

## ▶️ How to Run

Clone repo → open notebook → run simulation cells.
