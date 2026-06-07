# DQN Agent for ConnectX

A Deep Q-Network (DQN) agent trained to play ConnectX via PyTorch. This project systematically experiments across hidden layer depth and size to quantify the trade-off between network complexity and training efficiency.

**Stack:** Python, PyTorch, Reinforcement Learning, DQN

---

## Project Overview

ConnectX is a generalized version of Connect Four where the board dimensions and winning condition (number of consecutive pieces) are configurable. This project trains DQN agents with varying architectures and measures how network depth and width affect both training wall-time and in-game learning performance.

---

## Approach

A DQN agent was trained across multiple architectural configurations, varying:

- **Number of hidden layers:** shallow (1–2 layers) vs. deep (3–4 layers)
- **Hidden layer size:** smaller (64–128 units) vs. larger (256–512 units)

Each configuration was trained for a fixed number of episodes. Training time and learning behavior were recorded and compared across all configurations.

---

## Key Findings

**Training Time:** Training time scaled significantly with both layer count and layer size. Deeper and wider networks required substantially more computation per update step.

**Learning Performance:** Deeper architectures showed marginal improvements in learning quality — the agent demonstrated slightly more stable policy convergence with additional layers, but the gains were modest relative to the added cost.

**Trade-off:** Simpler architectures (1–2 hidden layers, moderate size) achieved adequate performance at a fraction of the training cost. The performance gains from additional depth did not justify the computational overhead in most configurations.

**Conclusion:** For environments of this complexity, lighter network architectures are preferable. Future work could explore experience replay tuning, epsilon-decay schedules, and target network update frequencies to further improve sample efficiency.

---

## Repository Structure

```
DQN-ConnectX-Agent/
├── notebooks/
│   └── DS669FinalProject_PabloSalar.ipynb   # Full experiment notebook with visualizations
├── src/
│   └── DS669FinalProject_PabloSalar.py      # Standalone Python script
├── reports/
│   └── DS669FinalProject_PabloSalar.html    # Complete project report
└── README.md
```

---

## Technologies

| Library | Purpose |
|---|---|
| PyTorch | DQN model definition and training loop |
| NumPy | Array operations and reward processing |
| Matplotlib | Training curve and performance visualizations |
| Jupyter | Interactive experimentation and reporting |
