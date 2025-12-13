![Reinforcement Learning](https://img.shields.io/badge/Reinforcement%20Learning-1F2937?style=for-the-badge)
![Multi-Armed Bandits](https://img.shields.io/badge/Multi--Armed%20Bandits-374151?style=for-the-badge)
![Prescriptive Analytics](https://img.shields.io/badge/Prescriptive%20Analytics-4B5563?style=for-the-badge)
![Simulation](https://img.shields.io/badge/Simulation-6B7280?style=for-the-badge)
![Python](https://img.shields.io/badge/Python-3776AB?style=for-the-badge&logo=python&logoColor=white)

🚗 Pedestrian Collision Avoidance for Autonomous Vehicles Using Multi-Armed Bandit Optimization
Prescriptive Analytics Capstone Project – Reinforcement Learning for AV Evasive Maneuvers

This project applies prescriptive analytics and reinforcement learning to determine the safest evasive maneuver when an autonomous vehicle (AV) suddenly encounters a prone pedestrian on a downhill grade. Using an epsilon-greedy multi-armed bandit, the model learns optimal actions across 3,000 simulated mannequin encounters, updating Q-values after every trial.

The simulation is grounded in AV testing scenarios similar to those conducted by Zoox and motivated by real industry events where perception failures led to pedestrian injuries.

⭐ Problem Overview

Autonomous vehicles must make rapid, safety-critical decisions when encountering unexpected obstacles. Real-world testing of pedestrian collision edge cases is limited by ethical and safety constraints; therefore simulation-based reinforcement learning provides a powerful alternative.

Core Question:

When a vehicle suddenly encounters a prone pedestrian while descending a downhill grade, which evasive maneuver minimizes expected harm across speeds of 25, 35, and 45 mph?

Available Actions:

Hard Brake

Swerve Left

Swerve Right

This aligns naturally with a multi-armed bandit formulation, where each maneuver is an “arm” with uncertain but learnable outcomes.

⭐ Modeling Approach
Reinforcement Learning Method

Algorithm: Epsilon-Greedy (ε = 0.1)

Learning: Incremental Q-value updates

Simulated Encounters: 3,000

Speed States: 25 mph, 35 mph, 45 mph

Reward Design

Rewards reflect AV safety engineering priorities:

Outcome	Reward
Successful perception	+100
Successful full stop	+50
Successful swerve	+20
Non-catastrophic failure	-20 to -100
Collision	-700
Catastrophic perception failure	-1000

This structure strongly penalizes outcomes that would correlate with real-world harm.

⭐ Environment Parameters

Each maneuver’s success probability changes with speed:

Stopping distance increases with speed

Lateral maneuver reliability decreases at higher speeds

Perception accuracy slightly degrades

Catastrophic failure probabilities increase at high speeds

These relationships create meaningful differences in expected reward across actions.

⭐ Key Results
🟩 Hard Brake emerged as the optimal action across all speed levels.

Despite lower stopping reliability at higher speeds, braking still dominated due to:

Extreme penalties for failed swerves

Escalating catastrophic impact likelihood

Strong positive reward for successful stopping or perception

Policy Interpretation

25 mph: High chance of stopping — braking is overwhelmingly best

35 mph: Failing to swerve is too risky → braking dominates

45 mph: Swerves become highly unreliable → braking still yields highest expected safety

Sensitivity Analysis Findings

Perception failure penalties dominate action selection

Lateral control reliability would need major improvement to make swerving competitive

Stopping probability has a nonlinear contribution to expected reward

This highlights which AV subsystems most influence safety.

⭐ Why This Matters

This project demonstrates how prescriptive analytics + reinforcement learning can support AV safety governance:

Identifies which maneuvers minimize expected harm

Helps AV teams evaluate risk without dangerous real-world testing

Provides a transparent, simulation-based decision framework

Supports prioritization of engineering improvements (braking, perception, lateral control)

It showcases the power of reinforcement learning for rare, catastrophic edge-case analysis, where traditional supervised learning lacks sufficient data.

⭐ Files in This Repository

AV_MAB.ipynb — full implementation of the MAB model

Presentation Deck — summarizes methodology & insights

Written Technical Report — full academic-style documentation containing images, Q-value plots, cumulative reward curves, and policy visuals.

⭐ Future Work

Potential enhancements:

Multi-step RL (Q-learning, SARSA, DQN, PPO)

Continuous steering/braking action space

Integration with real AV sensor logs

Road geometry and curvature-based decision conditioning

⭐ How to Run

Open the notebook: AV_MAB.ipynb

Install dependencies:

pip install numpy matplotlib pandas


Run all cells to reproduce the 3,000-episode learning simulation.

⭐ Contact

For questions or collaboration:
Brian Nguyen – MBA, Management Analytics
LinkedIn: https://www.linkedin.com/in/brianlongnguyen

GitHub: https://github.com/brianlongnguyen
