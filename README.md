# Reconfigurable Fe-OPUF Benchmark Suite: Machine Learning Attack Resilience & Hardware-TRNG-Driven Genetic Optimization

[![MATLAB](https://img.shields.io/badge/MATLAB-R2022b%2B-orange.svg)](https://www.mathworks.com/products/matlab.html)
[![PUF Security](https://img.shields.io/badge/Security-PUF%20Modeling%20Resilience-blue.svg)](#)
[![Optimization](https://img.shields.io/badge/Optimization-TSP%20Genetic%20Algorithm-green.svg)](#)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

An end-to-end, high-performance MATLAB benchmark framework evaluating **reconfigurable PMN-PT Ferroelectric Optical Physical Unclonable Functions (Fe-OPUF)**.

This repository provides an integrated platform covering two primary research dimensions of Fe-OPUFs:
1. **Security Dimension**: Quantitative machine learning (ML) modeling attack resilience across diverse AI architectures (LR, SVM, Random Forest, XGBoost, MLP, CNN).
2. **Application Dimension**: Hardware-entropy-driven heuristic optimization (Permutation Genetic Algorithm & hybrid GA + 2-opt for Traveling Salesperson Problems) with physical timing boundary accounting.

---

## 📋 Table of Contents

- [Overview](#-overview)
- [Repository Architecture](#-repository-architecture)
- [System Requirements](#-system-requirements)
- [Installation Guide](#-installation-guide)
- [Demo / Quick Start](#-demo--quick-start)
- [Instructions for Use](#-instructions-for-use)
- [Reproduction of Manuscript Results](#-reproduction-of-manuscript-results)
- [License](#-license)

---

## 🔬 Overview

Reconfigurable optical PUFs (Fe-OPUFs) exploit domain switching and field-induced phase transitions in ferroelectric single crystals (such as PMN-PT) to perturb optical speckle patterns upon electrical excitation voltages.

- **Security Verification**: Evaluates whether an adversary can numerically clone the optical PUF or predict Challenge-Response Pairs (CRPs). Physical responses are evaluated under leak-free nested cross-validation protocols across diverse machine learning and deep learning models.
- **Hardware Entropy Deployment**: Physical optical speckle patterns are extracted, spatial-decorrelated, and packed into in-memory bitstreams. These physical entropy bitstreams serve as true random seeds for combinatorial optimization (TSPLIB instances), benchmarked against standard pseudo-random number generator (PRNG) controls.

---

## 📂 Repository Architecture

```text
├── ML_Attack/                          # Module 1: Machine learning modeling attack evaluation
│   ├── run_ml_attack.m                 # Main entry script for ML modeling attacks
│   ├── config_attack.m                 # Hyperparameter configuration
│   └── models/                         # ML algorithms, cross-validation, and metrics
├── TSP_Solve/                          # Module 2: Hardware-TRNG-assisted TSP optimization
│   ├── run_benchmark.m                 # Main entry script for GA / GA + 2-opt benchmark
│   ├── config_tsp.m                    # Population, mutation, and crossover settings
│   └── utils/                          # Bit-packing, rejection sampling, local search
├── data/
│   ├── demo/                           # Lightweight demo dataset for rapid testing
│   │   ├── toy_crps.mat                # 500-sample CRP subset for quick ML verification
│   │   └── eil51.tsp                   # Standard TSPLIB 51-city instance
│   ├── images/                         # Raw optical speckle dataset (CHIP0..11)
│   └── tsplib/                         # Full TSPLIB benchmark problem files (*.tsp)
├── results/                            # Auto-generated diagnostic plots, logs, and CSV audits
├── run_demo.m                          # One-click execution script for reviewers
├── LICENSE                             # MIT License
└── README.md                           # Technical documentation and reproduction guide
