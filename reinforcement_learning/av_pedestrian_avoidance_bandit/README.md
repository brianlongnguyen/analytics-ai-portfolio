# 🚗 Prescriptive Analytics for Pedestrian Collision Avoidance  
### Multi-Armed Bandit Optimization for Autonomous Vehicle Safety Testing

![Reinforcement Learning](https://img.shields.io/badge/Reinforcement%20Learning-2962FF?style=for-the-badge)
![Prescriptive Analytics](https://img.shields.io/badge/Prescriptive%20Analytics-0A9396?style=for-the-badge)
![Simulation](https://img.shields.io/badge/Simulation-2A9D8F?style=for-the-badge)
![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)
![Autonomous Vehicles](https://img.shields.io/badge/Autonomous%20Vehicles-FF4D6D?style=for-the-badge)

---

## Executive Summary

Autonomous vehicles must make rapid decisions in uncertain environments where mistakes carry asymmetric consequences. In pedestrian encounter scenarios, the system must select evasive maneuvers that minimize collision risk while maintaining vehicle stability and passenger safety.

This project simulates thousands of autonomous vehicle–pedestrian encounters and applies a reinforcement learning framework to determine which evasive maneuver consistently produces the safest outcome.

Rather than optimizing for speed or efficiency, the model prioritizes **risk-aware decision-making**, illustrating how simulation and learning algorithms can support safety-critical operational decisions.

---

## Decision Problem

When a pedestrian suddenly appears in a vehicle’s path, the system must choose among discrete evasive actions:

- Hard braking
- Swerving left
- Swerving right

Each action carries uncertain outcomes influenced by vehicle speed, perception reliability, and environmental conditions.

The decision challenge is selecting the maneuver that minimizes collision probability across varying scenarios.

---

## Approach

A simulation environment generates **3,000+ encounter scenarios** across different speeds and conditions.

A **multi-armed bandit (MAB)** reinforcement learning agent evaluates actions using an **ε-greedy learning policy**, balancing:

- Exploration of alternative actions
- Exploitation of historically safer choices

After each simulated encounter:

- Rewards penalize collisions and unsafe outcomes
- Action value estimates are updated
- Policy gradually converges toward safer decisions

This framework mimics how safety policies improve through repeated testing and learning.

---

## Impact / Key Findings

Simulation results consistently show that:

- **Hard braking dominates as the safest evasive action** across most scenarios.
- A small subset of constraints drives safety outcomes.
- Policy learning converges rapidly once high-risk actions are penalized appropriately.

The broader insight is that **reward design and risk weighting often matter more than algorithm complexity** in safety-critical systems.

The project demonstrates how simulation-based learning can guide decision policy development before real-world deployment.

---

## 📐 Mathematical Formulation (Simplified)

The problem is modeled as a multi-armed bandit decision process.

At each encounter, an action \(a\) is selected to maximize expected safety reward:

\[
\max_a \; E[R(a)]
\]

Action value estimates are updated incrementally:

\[
Q_{t+1}(a) = Q_t(a) + \alpha (R_t - Q_t(a))
\]

where:

- \(Q(a)\) is the estimated value of action \(a\)
- \(R_t\) is the observed reward
- \(\alpha\) is the learning rate

An **ε-greedy policy** balances exploration and exploitation.

---

## 🌍 Industry Applicability

Although demonstrated in autonomous vehicle safety testing, this decision framework generalizes to environments where uncertainty and asymmetric risk dominate.

Examples include:

- Autonomous systems and robotics
- Industrial safety and automation
- Defense and unmanned systems
- Healthcare decision support
- Real-time operational control systems

Any domain requiring rapid decisions under uncertain risk can apply similar learning frameworks.

---

## ▶️ How to Run

1. Clone the repository:  git clone https://github.com/brianlongnguyen/analytics-ai-portfolio.git
2. Navigate to the project directory:  cd reinforcement_learning/av_pedestrian_avoidance_bandit
3. Launch the notebook:  jupyter notebook
4. Run all cells to reproduce simulation results and learning behavior.

---

## ⚠️ Disclosure & Confidentiality Notice

This project is based on publicly discussed autonomous vehicle safety challenges and academic simulation methods.

No proprietary data, internal testing material, or confidential information from Zoox or any other organization is included.

The work is intended solely for educational and demonstration purposes.
