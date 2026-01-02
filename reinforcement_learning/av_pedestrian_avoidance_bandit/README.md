# 🚗 Prescriptive Analytics for Pedestrian Collision Avoidance  
**Multi-Armed Bandit Optimization for Autonomous Vehicle Safety Testing**

![Prescriptive Analytics](https://img.shields.io/badge/Prescriptive%20Analytics-0A9396?style=for-the-badge)
![Reinforcement Learning](https://img.shields.io/badge/Reinforcement%20Learning-2962FF?style=for-the-badge)
![Simulation](https://img.shields.io/badge/Simulation-2A9D8F?style=for-the-badge)
![Safety--Critical Systems](https://img.shields.io/badge/Safety--Critical%20Systems-D00000?style=for-the-badge)
![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)

---

## Executive Summary

Autonomous vehicles operating in pedestrian environments must make real-time decisions under uncertainty where errors carry asymmetric and irreversible consequences.

This project demonstrates how **prescriptive analytics**, implemented through a **multi-armed bandit reinforcement learning framework**, can be used to evaluate and select evasive maneuvers that prioritize safety over performance metrics.

The emphasis is not on prediction accuracy or algorithmic novelty, but on **decision quality in safety-critical systems**.

---

## The Decision Problem

When a pedestrian enters a vehicle’s path unexpectedly, the system must choose an evasive maneuver:

- Hard braking  
- Swerving left  
- Swerving right  

Each action carries different risk profiles depending on vehicle speed, perception uncertainty, and reaction time.

The core question is not *which maneuver performs best on average*, but **which decision minimizes catastrophic outcomes under uncertainty**.

---

## Why Heuristic or Rule-Based Logic Falls Short

Hand-crafted rules and threshold-based logic struggle because:

- Outcome distributions are highly skewed  
- Rare failures dominate system risk  
- Average-case performance masks worst-case consequences  
- Conservative decisions are often penalized in standard optimization frameworks  

In safety-critical settings, **penalization structure matters more than raw reward**.

---

## Modeling Approach

The problem is modeled as a **multi-armed bandit decision system** where:

- Each evasive maneuver is treated as an arm  
- The environment simulates thousands of vehicle–pedestrian encounters  
- Rewards are shaped to heavily penalize collisions and near-misses  

An **ε-greedy learning policy** updates action values iteratively, allowing the system to learn which maneuver minimizes safety risk across scenarios.

This approach prioritizes **interpretability and policy stability** over deep model complexity.

---

## Simulation Design

The simulation framework incorporates:

- Multiple vehicle speed regimes  
- Stochastic pedestrian behavior  
- Probabilistic perception and reaction delays  
- Explicit safety-centric reward shaping  

Over **3,000+ simulated encounters**, the system converges toward a consistent decision policy.

---

## Key Insights

The learned policy reveals that:

- Hard braking dominates as the safest maneuver across most scenarios  
- Swerving actions introduce higher variance and tail risk  
- Conservative actions outperform aggressive maneuvers under asymmetric loss  
- Penalizing rare catastrophic events reshapes optimal behavior  

These outcomes are difficult to uncover using average-based evaluation alone.

---

## Managerial Implications

From a decision-system perspective, this project illustrates that:

- Safety optimization requires explicit treatment of downside risk  
- Reward design encodes organizational values  
- Interpretable policies are critical for validation and governance  
- Conservative decisions can be optimal when failure costs dominate  

The value lies not in automation alone, but in **making safety tradeoffs explicit and defensible**.

---

## Scope & Limitations

This project is based on publicly discussed autonomous vehicle safety challenges and academic simulation techniques.

No proprietary data, internal testing systems, or confidential materials from Zoox, Cruise, or any other organization are included.

All scenarios and results are illustrative and intended to demonstrate methodology rather than production-ready deployment.

---

## Repository Contents

- `av_pedestrian_avoidance_bandit.ipynb` — simulation and learning framework  
- `README.md` — executive-level explanation of the decision system  

---

## How to Run

1. Open the notebook in Jupyter or JupyterLab  
2. Install required dependencies (e.g., NumPy, Pandas)  
3. Run cells top-to-bottom to reproduce the simulation results  

---

## Closing Note

This project serves as a foundation for understanding how **learning-based decision systems behave under asymmetric risk**.

Together with economic optimization and procurement risk modeling projects in this portfolio, it reflects a consistent approach to **designing decision systems where tradeoffs matter more than predictions**.
