# XORPSO

This repository contains the implementation of the research described in the following paper:

**Title:** Optimized Deep Feature Selection for Pneumonia Detection: A Novel RegNet and XOR-Based PSO Approach

**Authors:** Fatemehsadat Ghanadi Ladani, Samaneh Hosseini Semnani

**Abstract:** Pneumonia remains a significant cause of child mortality, particularly in developing countries where resources and expertise are limited. The automated detection of Pneumonia can greatly assist in addressing this challenge. In this research, an XOR based Particle Swarm Optimization (PSO) is proposed
to select deep features from the second last layer of a RegNet model, aiming to improve the accuracy of the CNN model on Pneumonia detection. The proposed XOR PSO algorithm offers simplicity by incorporating just one hyperparameter for initialization, and each iteration requires minimal computation time. Moreover, it achieves a balance between exploration and exploitation, leading to convergence on a suitable solution. By extracting 163 features, an impressive accuracy level of 98% was attained which demonstrates comparable accuracy to previous PSO-based methods. The following diagram illustrates the pipeline:

![Pipeline Overview](PN_pip.png)


---

## Code Overview

The code in this repository corresponds to the research presented in the paper. It includes implementations of the algorithms, experiments, and analysis conducted in the paper. You can find detailed explanations and usage instructions in the relevant directories.


---


## XOR PSO: A Binary Particle Swarm Optimization Algorithm

### Overview

XOR PSO is a modified Particle Swarm Optimization (PSO) algorithm tailored for discrete optimization problems, such as feature selection. Unlike conventional PSO designed for continuous spaces, XOR PSO uses binary vectors to represent solutions and employs XOR logic to update positions and velocities.

---

### Key Features
<ul>
  <li><strong>Binary Solution Representation:</strong> Each position is a binary vector indicating selected features.</li>
  <li><strong>XOR Logic:</strong> Captures the difference between personal best (<code>P<sub>best</sub></code>), global best (<code>G<sub>best</sub></code>), and current position (<code>X</code>).</li>
  <li><strong>Reduced Hyperparameters:</strong> Simplifies the algorithm by eliminating or setting standard values for some parameters (e.g., <code>C<sub>1</sub></code> and <code>C<sub>2</sub></code>).</li>
  <li><strong>Discrete Optimization:</strong> Efficiently explores binary solution spaces.</li>
</ul>

---
## Formulas

### Velocity Update
<p align="center">
  <img src="images/velocity_update_blue.png" alt="Velocity Update Formula" width="600">
</p>
<ul>
  <li><strong>W:</strong> Inertia weight (<code>0 ≤ W ≤ 1</code>).</li>
  <li><strong>R<sub>1</sub>:</strong> Random factor (<code>−1 ≤ R<sub>1</sub> ≤ 1</code>).</li>
  <li><strong>R<sub>2</sub>:</strong> Random factor (<code>0 ≤ R<sub>2</sub> ≤ 1</code>).</li>
</ul>

### Threshold Mapping
<p align="center">
  <img src="images/threshold_mapping_blue.png" alt="Threshold Mapping Formula" width="600">
</p>

### Position Update
<p align="center">
  <img src="images/position_update_blue.png" alt="Position Update Formula" width="600">
</p>

---

## Advantages
<ul>
  <li><strong>Simplified Parameter Tuning:</strong> No need for <code>C<sub>1</sub></code> and <code>C<sub>2</sub></code>.</li>
  <li><strong>Effective for Feature Selection:</strong> Specifically designed for binary optimization tasks.</li>
  <li><strong>Fewer Hyperparameters:</strong> Reduces complexity compared to other swarm algorithms.</li>
</ul>

---

## How It Works
<ol>
  <li><strong>Initialization:</strong> Binary positions (<code>X</code>) and velocities (<code>V</code>) are initialized randomly.</li>
  <li><strong>Velocity Update:</strong> Update velocity using XOR logic, inertia weight, and random factors.</li>
  <li><strong>Threshold Mapping:</strong> Map <code>V<sub>t+1</sub></code> to binary values using a 0.5 threshold.</li>
  <li><strong>Position Update:</strong> Update positions using the XOR operation.</li>
  <li><strong>Evaluation:</strong> Calculate fitness and update <code>P<sub>best</sub></code> and <code>G<sub>best</sub></code>.</li>
  <li><strong>Repeat:</strong> Continue until convergence or a termination condition is met.</li>
</ol>

---

## Applications
<ul>
  <li><strong>Feature Selection:</strong> Selects the most relevant features in a dataset for machine learning models.</li>
  <li><strong>Discrete Optimization:</strong> Solves problems where solutions are represented in binary form.</li>
</ul>

---
## Paper Reference

For further details, please refer to the full paper:

[Optimized Deep Feature Selection for Pneumonia Detection: A Novel RegNet and XOR-Based PSO Approach](https://arxiv.org/pdf/2309.00147.pdf)


