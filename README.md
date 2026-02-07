<h1 align="center">Analytics & AI Portfolio</h1>
<h3 align="center">Decision Systems Under Uncertainty, Constraints, and Risk</h3>

---

## Overview

This portfolio focuses on **prescriptive and decision-centric analytics** — where uncertainty, constraints, and asymmetric risk shape outcomes more than point predictions.

Rather than optimizing metrics in isolation, the projects below emphasize how decisions should be structured when:
- information is incomplete,
- tradeoffs are irreversible,
- and system-wide behavior emerges from binding constraints.

The work spans **reinforcement learning, optimization, and simulation**, with applications in safety-critical systems, operations, supply chains, and capital allocation.

---

## ⭐ Featured Projects

- 🚗 AV Collision Avoidance — Reinforcement Learning Safety Decisions
- 🌐 Network Flow Optimization — Capacity-Constrained Routing
- 📦 Konys Procurement Risk — Monte Carlo Simulation

## Core Decision Frameworks

### 🚗 Prescriptive Analytics for Pedestrian Collision Avoidance (Multi-Armed Bandits)

**Decision Problem:**  
How should an autonomous system select evasive actions under uncertainty when the cost of failure is asymmetric and irreversible?

**Approach:**  
Modeled as a multi-armed bandit using ε-greedy exploration to evaluate maneuver selection (braking vs. swerving) across heterogeneous pedestrian–vehicle encounters. Reward structure emphasizes safety penalties over average outcomes.

**Impact:**  
Demonstrates how prescriptive analytics reframes autonomy as a decision problem rather than a prediction task. Applicable to robotics, autonomous vehicles, industrial safety systems, and other risk-dominant environments.

📁 `reinforcement_learning/av_pedestrian_avoidance_bandit`

---

### 🍇 Optimal Blending Under Constraints (Linear & Mixed-Integer Programming)

**Decision Problem:**  
How should scarce inputs be allocated to maximize profit while satisfying regulatory, quality, and capacity constraints?

**Approach:**  
Formulated as an LP/MIP blending model with compositional, availability, and compliance constraints. Sensitivity analysis used to identify binding constraints and marginal values.

**Impact:**  
Illustrates how constrained optimization outperforms heuristic decision-making in tightly regulated environments. Generalizes to food & beverage, chemicals, energy, and manufacturing.

📁 `optimization/landhills-winery-optimal-blending`

---

### 📦 Procurement Risk Under Uncertainty (Monte Carlo Simulation)

**Decision Problem:**  
How should procurement contracts be structured when demand and spot prices are volatile and downside risk matters as much as expected cost?

**Approach:**  
Monte Carlo simulation of purchase, option, and spot-market contracts. Evaluated expected profit, downside percentiles, and flexibility premiums under uncertainty.

**Impact:**  
Shows how simulation improves contract design and risk transfer decisions. Applicable to supply chains, commodities, energy markets, and regulated procurement.

📁 `simulation/konys-procurement-risk-monte-carlo`

---

### 🌐 Capacity-Constrained Network Flow Optimization (Linear Programming)

**Decision Problem:**  
How should flow be allocated across a constrained network to meet demand at minimum cost, recognizing that system performance is governed by bottlenecks?

**Approach:**  
Linear programming formulation with capacity, conservation, and cost constraints. Shadow prices used to identify binding arcs and high-leverage interventions.

**Impact:**  
Demonstrates how system-wide optimization reveals where capacity expansions matter — and where they do not. Generalizes to logistics, supply chains, infrastructure planning, and energy networks.

📁 `optimization/network-flow-min-cost-routing`

---

### 💊 Portfolio Valuation Under Regulatory Uncertainty (Monte Carlo Simulation)

**Decision Problem:**  
How should pharmaceutical investments be evaluated when regulatory approval, timing, and market dynamics introduce material uncertainty?

**Approach:**  
Monte Carlo simulation of NPV incorporating regulatory probability, delay risk, and market variability. Compared deterministic vs. stochastic valuation frameworks.

**Impact:**  
Highlights why distributions — not averages — should guide capital allocation in long-cycle, high-uncertainty industries. Applicable to life sciences, biotech, and infrastructure investment.

📁 `simulation/moore-pharmaceuticals-monte-carlo`

---

## How to Read This Portfolio

Each project is structured around:
1. **Decision framing** — what choice is being made and why it is non-trivial  
2. **Method selection** — why a specific analytical approach is appropriate  
3. **Managerial insight** — how results inform real-world decisions  

The common thread across all projects is **decision quality under uncertainty**, not model sophistication for its own sake.

---

<p align="center"><em>Always learning. Always optimizing. Always building.</em></p>
