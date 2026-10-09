# Prescriptive Digital Twins and Explainable AI for Energy-Aware, Human-Centric Industrial Automation

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.23251139.svg)](https://doi.org/10.5281/zenodo.23251139)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Python 3.10+](https://img.shields.io/badge/python-3.10+-blue.svg)](https://www.python.org/downloads/)

This repository contains the replication code, computational state-space observer pipeline, and *in silico* validation scripts for the paper:

> **Gerolimos, N., Kiskira, K., Chatzopoulos, A., Drosos, C., Papakostas, G. A., Priniotakis, G., & Nikolopoulos, D. (2026).**  
> *Prescriptive Digital Twins and Explainable AI for Energy-Aware, Human-Centric Industrial Automation.*  
> **MDPI Processes**, 14(x), xxx.

---

## Repository Overview

This project implements a multi-tier closed-loop Prescriptive Cyber-Physical System (CPS) architecture designed for collaborative assembly workcells (pHRI) in Industry 5.0:

1. **Non-Linear Biological State Observer (LET):** Reconstructs kinematic state-space manifolds using Takens delay coordinate embedding ($m=3, \tau_{\text{emb}}=4$) and quantifies neuromuscular stability via Largest Lyapunov Exponents ($\text{LyE}$) and coronal plane configurational Shannon Entropy ($H_{\text{Roll}}$).
2. **Supervisory Explainable AI (XAI):** Predicts operational risk probabilities via LightGBM and decomposes decision boundaries in real time ($<2.5\text{ ms}$) using TreeSHAP (φ(t)).
3. **Multi-Tier Prescriptive Actuation:**
   - **Kinematic Adaptation:** Executes FABRIK-A* delivery waypoint elevation ($\Delta z = +0.15\text{ m}$) to reduce lumbar compressive loads ($F_{\text{comp}}$ at L5/S1 below the $3,400\text{ N}$ NIOSH limit).
   - **Physical Damping:** Dampens dynamic operator tremor via non-linear hyperbolic tangent ($\tanh$) admittance control ($\dot{V} \le 0$).
   - **Enterprise Integration:** Emits asynchronous JSON payloads to plant MES (takt time derating) and ERP (fatigue-aware recovery scheduling).

---

## Repository Structure

```text
├── data/
│   └── empirical_cervical_fatigue_data.csv   # Raw/Filtered kinematic time series (N = 8,151 samples)
├── scripts/
│   ├── generate_figure_3.py                  # Evaluation of LightGBM, TreeSHAP importance & Takens manifold
│   └── generate_figure_4.py                  # In silico closed-loop multi-tier validation plots (300 DPI)
├── figures/
│   ├── Figure_3_Machine_Learning_Evaluation.png
│   └── Figure_4_Closed_Loop_Validation.png
├── requirements.txt                          # Python dependencies
├── LICENSE                                   # MIT Open-Source License
└── README.md                                 # Project documentation
