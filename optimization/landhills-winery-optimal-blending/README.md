# 🍇 Landhills Winery — Optimal Blending Plan
### Linear & Mixed-Integer Optimization for Production Planning

![Optimization](https://img.shields.io/badge/Optimization-LP%2FMIP-0A9396?style=for-the-badge)
![Operations Research](https://img.shields.io/badge/Operations%20Research-2962FF?style=for-the-badge)
![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)

---

## Executive Summary

Wine blending decisions must satisfy regulatory requirements, supply availability, and quality standards while maximizing profitability. Decisions are constrained by grape inventory, varietal composition rules, alcohol requirements, and production capacity.

This project formulates the blending problem as a linear and mixed-integer optimization model to determine optimal production volumes across multiple wines.

Rather than optimizing individual products, the model demonstrates how constrained systems require coordinated allocation decisions across all outputs.

---

## Decision Problem

The winery must determine:

- How much of each wine to produce
- How to allocate limited grape inventory
- How to satisfy regulatory blending constraints

while maximizing profit.

Decisions must simultaneously satisfy supply, regulatory, and production limitations.

---

## Approach

The problem is formulated as a Linear Programming / Mixed-Integer Programming model.

The model includes:

- Inventory availability constraints
- Alcohol composition requirements
- Regional and varietal blending rules
- Production and capacity limits
- Binary decisions for product activation

An optimization solver determines production volumes that maximize profitability while respecting all constraints.

---

## Impact / Key Findings

Results show:

- A small number of supply constraints drive optimal production decisions.
- Producing non-binding products reduces profitability.
- Profitability improves when scarce resources are allocated toward higher-margin blends.

The key takeaway is that production planning is primarily constrained by bottleneck resources, not demand alone.

---

## 📐 Mathematical Formulation (Simplified)

Maximize profit:

\[
\max \sum_i (price_i - cost_i)x_i
\]

Subject to:

Resource constraints:

\[
\sum_i a_{ij}x_i \le b_j
\]

Blending and regulatory requirements:

\[
x_i \ge 0
\]

Binary variables activate production decisions where necessary.

---

## 🌍 Industry Applicability

This framework generalizes to industries requiring constrained production planning.

Examples include:

- Food and beverage manufacturing
- Chemical processing
- Energy production allocation
- Manufacturing operations planning

---

## ▶️ How to Run

1. Clone the repository
2. Navigate to the project folder
3. Launch the notebook
4. Run all cells to reproduce optimization results
