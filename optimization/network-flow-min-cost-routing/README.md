# 🚚 **Capacity-Constrained Network Flow Optimization (LP)**

**Decision system for routing flow across multi-node networks under capacity and cost constraints.**

---

## 🔖 Tech & Method Badges

![Python](https://img.shields.io/badge/Python-3776AB?logo=python&logoColor=white)
![Linear Programming](https://img.shields.io/badge/LP-Optimization-blue)
![PuLP](https://img.shields.io/badge/PuLP-00457C)
![Decision Science](https://img.shields.io/badge/Decision%20Science-000000)
![Operations Research](https://img.shields.io/badge/Operations%20Research-6A5ACD)

---

## 🧩 Problem Framing

In multi-node networks, flow must be allocated across competing paths with different cost structures and physical limits.  
The central question is:

> *How should we route flow through the network to meet demand at minimum total cost while respecting real-world constraints?*

This formulation enforces feasibility through:

- Supplier → Hub capacities  
- Hub → Customer capacities  
- Demand fulfillment  
- Flow conservation at hub  
- Non-negativity  

---

## 🗺️ Network Diagram

<p align="center">
  <img src="network_flow_diagram.png" width="650"/>
  <br>
  <em>Figure: Capacity-constrained routing between suppliers, hubs, and customers.</em>
</p>
*(Diagram illustrates supplier → hub → customer flow with route capacities & cost structure.)*

---

## 🔢 Mathematical Form (LP)

**Decision variables**  
\( x_{ij} = \text{units shipped from node } i \text{ to node } j \)

**Objective (minimize total transportation cost)**  
\( \min \sum_{(i,j) \in \text{routes}} c_{ij} \cdot x_{ij} \)

**Subject to constraints**

Capacity:  
\( x_{ij} \leq \text{cap}_{ij} \)

Demand satisfaction:  
\( \sum_i x_{iC} = D_C \)

Flow conservation (hub):  
\( \sum_i x_{iH} = \sum_j x_{Hj} \)

Non-negativity:  
\( x_{ij} \geq 0 \)

---

## 🧮 Implementation Details

- Formulated as a **Linear Program (LP)**
- Solved using **PuLP + CBC**
- Reports:
  - route-level flows
  - total network cost
  - constraint utilization (binding vs slack)

Optional extensions supported in notebook:

- MIP variant (capacity decisions + fixed costs)
- Sensitivity on capacity
- Multi-sourcing structures

---

## 📊 Outputs (Executive-Facing)

The notebook reports:

✔ Optimal allocation across network  
✔ Binding vs non-binding constraints  
✔ Total cost decomposition  
✔ Flow visualization  
✔ Utilization insight  

---

## 🧭 Applicability

**Decision Type:**  
Global optimization of routing and capacity in interconnected systems.

**Industry Contexts:**  
Logistics networks, transportation, distributed compute routing, telecommunications, and energy/grid planning.

---

## 🛠️ Tech Stack

**Languages & Libraries**
- Python
- PuLP
- NumPy
- Pandas
- Matplotlib

**Optimization**
- Linear Programming (LP)

**Solver**
- CBC (open-source)

---

## ▶️ How to Run

**Install dependencies**
```bash
pip install pulp numpy pandas matplotlib
```

**Execute notebook**
```
network_flow_model_refactored.ipynb
```

No external data required.

---

## 📝 Repository Structure

```
network_flow/
│
├── network_flow_model_refactored.ipynb   # model + outputs
├── assets/
│   └── network_flow_diagram.png          # diagram used above
└── README.md
```

---

## 🔒 Disclosure

Synthetic values used to illustrate route capacity and cost allocation.  
No proprietary network data or operational constraints included.

---

## 🧩 Role in Portfolio

This project represents the **routing allocation** decision class in the broader portfolio, complementing:

- **Risk transfer** (Konys — Monte Carlo)
- **Blending/feasibility** (Landhills — LP/MIP)
- **Real-time adaptive control** (AV/MAB)
- **Investment under uncertainty** (Moore Pharmaceuticals — Monte Carlo)

---
