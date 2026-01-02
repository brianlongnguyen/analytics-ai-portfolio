# 🍇 Landhills Winery — Optimal Blending Plan  
**Prescriptive Analytics Using Linear & Mixed-Integer Optimization**

![Prescriptive Analytics](https://img.shields.io/badge/Prescriptive%20Analytics-0A9396?style=for-the-badge)
![Optimization](https://img.shields.io/badge/Optimization-6A4C93?style=for-the-badge)
![Operations Research](https://img.shields.io/badge/Operations%20Research-8E44AD?style=for-the-badge)
![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)

---

## Executive Summary

Landhills Winery faces a constrained decision problem: how to allocate limited grape inventories across a portfolio of wine products while complying with regulatory, quality, and commercial constraints.

This project demonstrates how **prescriptive analytics**, using linear and mixed-integer optimization, can replace heuristic planning with a transparent and defensible decision framework that maximizes profit while respecting real-world constraints.

The emphasis is not on mathematical complexity, but on **decision quality under constraints**.

---

## The Decision Problem

Management must decide:

- How much of each grape type to allocate to each wine product  
- Which products to produce, and at what scale  
- How to balance profitability against regulatory and quality requirements  

These decisions are tightly coupled: changing one blend affects feasibility and profitability elsewhere in the portfolio.

---

## Why Heuristic Planning Falls Short

Spreadsheet-based or intuition-driven approaches struggle because:

- Constraints interact across products and vintages  
- Locally reasonable decisions can create global infeasibility  
- Profitability is driven by binding constraints, not averages  
- Commercial features (e.g., quantity discounts) introduce discrete choices  

As a result, manual planning often leaves value on the table or produces fragile plans.

---

## Modeling Approach

The problem is formulated as a **profit-maximization optimization model** with:

- Continuous decision variables representing blend quantities  
- Binary decision variables capturing discrete commercial decisions  
- A linear objective function reflecting total contribution margin  

The model transitions from **LP to MIP only where discrete logic is economically meaningful**, preserving interpretability and computational efficiency.

---

## Constraint Structure

Rather than presenting dense mathematical notation, constraints are grouped into business-meaningful categories:

- **Supply constraints:** limited availability of each grape type  
- **Regulatory constraints:** alcohol content, regional composition, varietal requirements  
- **Quality constraints:** minimum and maximum blend percentages  
- **Commercial constraints:** demand limits, quantity discounts, exclusivity conditions  

This structure mirrors how managers reason about feasibility and tradeoffs.

---

## Key Insights

The optimized solution highlights that:

- A small subset of constraints consistently drives the optimal plan  
- Some high-margin products are excluded due to binding quality or regulatory limits  
- Quantity discounts materially change the optimal product mix  
- Concentrating production where constraints are least restrictive maximizes profit  

These insights are difficult to uncover without a global optimization framework.

---

## Managerial Implications

From a decision-making perspective, the model enables leaders to:

- Identify which constraints truly limit profitability  
- Evaluate tradeoffs between compliance, quality, and margin  
- Test “what-if” scenarios before committing production  
- Defend decisions with a transparent, auditable rationale  

The value lies not only in the optimal solution, but in the **decision structure** the model provides.

---

## Scope & Limitations

This project is intentionally scoped to illustrate methodology and reasoning.

All data used are synthetic or illustrative, and results are not intended to represent the operations of any specific winery.

---

## Repository Contents

- `landhills_optimization_model.ipynb` — clean, reproducible optimization model  
- `README.md` — executive-level explanation of the decision framework  

---

## How to Run

1. Open the notebook in Jupyter or JupyterLab  
2. Install required packages if needed (e.g., PuLP, NumPy, Pandas)  
3. Run cells top-to-bottom to reproduce the results  

---

## Closing Note

This project complements safety-critical decision work by illustrating how **optimization clarifies tradeoffs** in economic settings where feasibility and constraints, rather than prediction accuracy, determine outcomes.

Together, these projects reflect a consistent approach to **decision quality under uncertainty and constraints** across domains.
