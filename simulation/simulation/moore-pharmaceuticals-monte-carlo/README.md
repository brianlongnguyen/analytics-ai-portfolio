# 💊 Moore Pharmaceuticals — Monte Carlo NPV Simulation

![Python](https://img.shields.io/badge/Python-3776AB?logo=python&logoColor=white)
![NumPy](https://img.shields.io/badge/NumPy-013243?logo=numpy&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-150458?logo=pandas&logoColor=white)
![Matplotlib](https://img.shields.io/badge/Matplotlib-11557C)
![Monte Carlo Simulation](https://img.shields.io/badge/Monte%20Carlo%20Simulation-4A7EBB)
![Domain: Pharma](https://img.shields.io/badge/Domain-Pharmaceuticals-8E44AD)

## Overview

This project implements a **Monte Carlo simulation** of a major R&D investment decision for a pharmaceutical company.

The goal is to understand the **distribution of Net Present Value (NPV)** for a new drug over a five-year horizon, under uncertainty in:

- Total R&D costs  
- Clinical trial costs  
- Market size and growth  
- Market share growth  

Rather than relying on a single NPV estimate, the model provides a **probabilistic view of project value**, including downside risk and the probability of capital loss.

---

## Business Context

A pharmaceutical firm is evaluating whether to move forward with a promising new drug. Key elements of the base case include: :contentReference[oaicite:0]{index=0}  

- R&D costs expected to total around **$700M**  
- Clinical trial costs around **$150M**  
- Initial market size of **2 million patients**, with annual growth  
- Initial market share of **8%**, with expected growth over time  
- Monthly revenue per patient of **$130** and variable cost of **$40**  
- A five-year horizon and a **9% discount rate** for NPV  

A simple spreadsheet using point estimates suggests a positive NPV. However, every key input is uncertain. The question is:

> **What does the distribution of NPV look like once we acknowledge uncertainty in costs, market size, and adoption?**

---

## Modeling Approach

The notebook follows a standard **Monte Carlo simulation** structure: :contentReference[oaicite:1]{index=1}  

1. **Define the financial model**

   - Annual profits are based on:
     - Market size × market share × monthly margin × 12  
   - Cash flows are projected for **5 years**.  
   - NPV is calculated at a **9% discount rate**.  
   - Upfront R&D and clinical trial costs are deducted.

2. **Model key uncertainties**

   Based on the case assumptions, the following input distributions are used: :contentReference[oaicite:2]{index=2}  

   - R&D costs: `Uniform(600M, 800M)`  
   - Clinical trial costs: `Normal(mean = 150M, sd = 30M)`  
   - Current market size: `Normal(mean = 2M, sd = 0.4M)`  
   - Annual market growth: `Uniform(2%, 6%)`  
   - Annual market share growth: `Uniform(15%, 25%)`  

3. **Run simulations**

   - For each iteration:
     - Draw one scenario from the joint distribution of inputs  
     - Compute the resulting NPV  
   - Repeat for **1,000+ iterations** to approximate the NPV distribution.

4. **Analyze results**

   - Mean and standard deviation of NPV  
   - 95% confidence interval for the **mean NPV**  
   - Percentiles (e.g., 5th, 25th, 50th, 75th, 95th)  
   - **Probability that NPV < 0** (capital loss risk)  
   - Histogram of the NPV distribution

---

## What This Notebook Shows

For each run, the notebook computes and reports:

- **Expected NPV** of the drug project  
- **95% confidence interval** for the mean NPV based on simulation output  
- **Downside risk metrics**, including:
  - Probability that NPV is negative  
  - 5th percentile NPV (severe downside scenario)  
- **Histogram of NPV outcomes**, visualizing the entire distribution  

These outputs give decision makers a much richer view than a single base-case NPV:

> Two strategies can have similar average NPV but very different downside profiles.

---

## Applicability

Although framed in a pharmaceutical context, this structure generalizes to many **capital budgeting** and **strategic investment** decisions:

- Large R&D programs (pharma, biotech, deeptech)  
- Product launches with uncertain adoption paths  
- Capacity expansion (plants, data centers, logistics infrastructure)  
- Long-horizon technology bets where:
  - Costs, demand, and pricing are uncertain  
  - Management needs to understand both upside and downside  
  - Traditional point-estimate NPV looks artificially precise  

This project fits into a broader portfolio of work focused on **decision quality under uncertainty**, complementing:

- **Konys Inc.** — Procurement risk and contract design under demand and price uncertainty  
- **Moore** — Investment value under uncertain costs, adoption, and market growth  

---

## How to Run

1. **Clone this repository**

   ```bash
   git clone https://github.com/brianlongnguyen/analytics-ai-portfolio.git
   cd analytics-ai-portfolio/simulation/moore-pharma-npv-monte-carlo
