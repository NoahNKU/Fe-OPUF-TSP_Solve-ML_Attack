# Reconfigurable Fe-OPUF Benchmark Suite: Machine Learning Attack Resilience & Hardware-TRNG-Driven Genetic Optimization

[![MATLAB](https://img.shields.io/badge/MATLAB-R2022b%2B-orange.svg)](https://www.mathworks.com/products/matlab.html)
[![PUF Security](https://img.shields.io/badge/Security-PUF%20Modeling%20Resilience-blue.svg)](#)
[![Optimization](https://img.shields.io/badge/Optimization-TSP%20Genetic%20Algorithm-green.svg)](#)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

An end-to-end, high-performance MATLAB benchmark framework evaluating **reconfigurable PMN-PT Ferroelectric Optical Physical Unclonable Functions (Fe-OPUF)**. 

This repository provides an integrated platform covering two primary research dimensions of Fe-OPUFs:
1. **Security Dimension**: Quantitative machine learning (ML) modeling attack resilience across diverse AI architectures.
2. **Application Dimension**: Hardware-entropy-driven heuristic optimization (Permutation Genetic Algorithm & hybrid GA + 2-opt for the Traveling Salesperson Problem) with exact physical timing boundary accounting.

---

## 📋 Table of Contents

- [Overview](#-overview)
- [Repository Architecture](#-repository-architecture)
- [Module 1: ML Modeling Attack Benchmark](#-module-1-ml-modeling-attack-benchmark)
- [Module 2: TRNG-Driven GA for TSP](#-module-2-trng-driven-ga-for-tsp)
- [Prerequisites & Toolboxes](#-prerequisites--toolboxes)
- [Data Organization](#-data-organization)
- [Getting Started](#-getting-started)
- [Output Artifacts & Diagnostics](#-output-artifacts--diagnostics)
- [Citation & License](#-citation--license)

---

## 🔬 Overview

Reconfigurable optical PUFs (Fe-OPUFs) exploit domain switching and field-induced phase transitions in ferroelectric single crystals (such as PMN-PT) to perturb optical speckle patterns upon electrical excitation voltages. 

- **Security Verification**: To assess whether an adversary can numerically clone the optical PUF or predict Challenge-Response Pairs (CRPs), the modeling attack benchmark subjects physical responses to advanced linear, tree-ensemble, and deep learning algorithms under leak-free nested cross-validation protocols.
- **Hardware Entropy Deployment**: Physical optical speckle patterns are extracted, spatial-decorrelated, and packed into in-memory FIFO bitstreams. We evaluate these high-entropy bitstreams as true random physical seeds for hard combinatorial optimization (TSPLIB instances), benchmarked against pseudo-random number generator (PRNG) controls with nanosecond-calibrated latency decomposition.

---

## 📂 Repository Architecture

```text
├── ML_Attack/                          # Module 1: Machine learning modeling attack evaluation
│   ├── run_ml_attack.m                 # Main entry script for ML modeling attacks
│   └── models/                         # Model training, cross-validation, and metric subroutines
├── TSP_Solve/                          # Module 2: Hardware-TRNG-assisted TSP optimization
│   ├── run_benchmark.m                 # Main entry script for GA / GA + 2-opt benchmark
│   └── utils/                          # Bit-packing, rejection sampling, and local search routines
├── data/
│   ├── images/                         # Raw optical speckle dataset (CHIP0..11, 10 cycles, 15 voltages)
│   └── tsplib/                         # Standard TSPLIB benchmark problem files (*.tsp)
├── results/                            # Auto-generated diagnostic plots, tables, and CSV audits
├── .gitignore                          # Pre-configured Git exclusion rules for large datasets
├── LICENSE                             # MIT License
└── README.md                           # Project documentation
