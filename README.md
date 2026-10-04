# Reconfigurable Fe-OPUF Benchmark Suite: Machine Learning Attack Resilience & Hardware-TRNG-Driven Genetic Optimization

[![MATLAB](https://img.shields.io/badge/MATLAB-R2022b%2B-orange.svg)](https://www.mathworks.com/products/matlab.html)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Format: MATLAB Live Script](https://img.shields.io/badge/Format-MATLAB%20Live%20Script%20(.mlx)-blue.svg)](#)

An integrated, reproducible benchmark suite evaluating **reconfigurable PMN-PT Ferroelectric Optical Physical Unclonable Functions (Fe-OPUF)** across machine learning (ML) attack resilience and hardware-TRNG-driven heuristic optimization.

---

## Structure

### 1. `ML_Attack.mlx`
- Implements an end-to-end machine learning modeling attack benchmark suite to:
  - Subject physical Fe-OPUF responses to diverse machine learning algorithms (Logistic Regression, Support Vector Machines, Random Forests, and Multi-Layer Perceptrons).
  - Execute leak-free nested cross-validation protocols to evaluate Challenge-Response Pair (CRP) predictability.
  - Automatically evaluate and display inline classification accuracy, Area Under the Curve (AUC), and ROC curves.
- Includes a self-contained demonstration subset for rapid reviewer assessment without requiring large external image datasets.

### 2. `TSP_Benchmark.mlx`
- Implements a hardware-entropy-assisted combinatorial optimization framework to:
  - Ingest spatial-decorrelated Fe-OPUF physical bitstreams as true random seeds.
  - Run Permutation Genetic Algorithm (PGA) and hybrid GA + 2-opt solvers on standard TSPLIB benchmark instances.
  - Benchmark physical Fe-OPUF entropy against pseudo-random number generator (PRNG) controls with nanosecond-calibrated latency decomposition.
  - Output inline fitness evolution and tour length convergence curves.

### 3. `LICENSE`
- Complete terms of the open-source **MIT License**.

---

## Dependencies & System Requirements

This repository is implemented in native MATLAB Live Scripts (`.mlx`). Make sure the following environment and toolboxes are configured:

| Dependency | Required Version | Description |
| :--- | :--- | :--- |
| `MATLAB` | R2022b or later | Core execution environment (Tested on R2023b and R2024a). |
| `Statistics and Machine Learning Toolbox` | Compatible with MATLAB | Supervised learning algorithms, cross-validation routines, and ROC metrics. |
| `Deep Learning Toolbox` | (Optional) Compatible | Neural network and MLP classifier architectures for modeling attacks. |
| `Image Processing Toolbox` | (Optional) Compatible | Speckle feature extraction and decorrelation routines. |

### System & Hardware Specifications
- **Operating Systems**: Windows 10/11 (64-bit), Ubuntu 20.04/22.04 LTS, macOS Monterey (12.0+) or later (Fully tested).
- **Hardware Requirements**: Tested on a standard desktop computer (Intel Core i7, 16 GB RAM).
- **Non-Standard Hardware**: **None required**. All modeling attacks and GA optimization algorithms execute entirely on standard CPU architectures without dedicated hardware accelerators.

### Installation
1. Clone or download this repository to your local machine:
   ```bash
   git clone [https://github.com/NoahNKU/Fe-OPUF-TSP_Solve-ML_Attack.git](https://github.com/NoahNKU/Fe-OPUF-TSP_Solve-ML_Attack.git)
