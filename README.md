# Optimal Resource Allocation using Simulated Annealing

Assigning drones to task zones under battery constraints.
Course project for **Foundations of Artificial Intelligence**, Woxsen University.
Faculty: Dr. N. Steven Raj

## Problem
A fleet of drones must service a set of task zones. Each zone needs exactly one
drone, and a drone may serve several zones. Goal: minimize total travel distance
while keeping each drone within its battery/range cap.

## Method
- **Simulated Annealing (SA):** swap/reassign moves, Metropolis acceptance
  `P(accept) = exp(-Δcost / T)`, geometric cooling.
- **Baseline:** greedy nearest-drone assignment.
- **Cost function:** total Euclidean drone-to-zone distance + penalty of 50 per
  unit of battery-cap overshoot.

## Parameters (reported run)
| Parameter | Value |
|---|---|
| Drones / Zones | 4 / 8 |
| Grid | 100 x 100 |
| Battery cap | 80 units |
| Initial temperature | 100 |
| Cooling factor | 0.995 |
| Iterations | 1500 |

## Results (single instance)
| Method | Final cost |
|---|---|
| Greedy | 1164.2 |
| Simulated Annealing | 171.8 |

Improvement: **85.2%** on this instance. Result is from one run; see the report
for limitations and the proposed repeated-trial plan.

## Repository contents
- `presentation/` : slide deck (HTML and PPTX)
- `report/` : full project report (Word)
- `src/` : Python implementation
- `results/` : output plots

## Run
    pip install matplotlib
    python src/sa_drone_allocation.py

## Team
Gourav Saha, Yash Raj, Pranav Yeddula, Morla Kartik, Shwechith Charan

## Future scope
Quantum annealing (e.g. D-Wave) for the same assignment problem.