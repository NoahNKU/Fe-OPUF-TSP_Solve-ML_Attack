# Reconfigurable Fe-OPUF Benchmark Suite: Machine Learning Attack Resilience & Hardware-TRNG-Driven Genetic Optimization

[![MATLAB](https://img.shields.io/badge/MATLAB-R2022b%2B-orange.svg)](https://www.mathworks.com/products/matlab.html)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![Format: MATLAB Live Script](https://img.shields.io/badge/Format-MATLAB%20Live%20Script%20(.mlx)-blue.svg)](#quick-start)

An integrated benchmark suite evaluating **reconfigurable PMN-PT Ferroelectric Optical Physical Unclonable Functions (Fe-OPUF)** through machine learning (ML) modeling attacks and physical-bitstream-driven genetic optimization.

Both benchmarks are provided as **MATLAB Live Scripts (`.mlx`)**, allowing users to run the analyses and inspect numerical results and figures directly in the MATLAB Live Editor.

---

## Quick Start

The benchmarks run directly as MATLAB Live Scripts. No separate compilation or command-line execution is required. Numerical results and figures appear inline in the **MATLAB Live Editor** as the corresponding computations finish.

### 1. Run the ML Attack Benchmark

1. Open `ML_Attack.mlx` in MATLAB.
2. Review the configuration and data-loading sections, keeping the provided default settings for an initial run.
3. Click **Run** in the Live Editor to execute the complete script.
4. Inspect the classification results, accuracy summaries, AUC values, and ROC curves directly in the script output.

**Expected runtime:** approximately **5 minutes** with the provided default configuration.

### 2. Run the TSP Optimization Benchmark

1. Open `TSP_Benchmark.mlx` in MATLAB.
2. Review the benchmark configuration and confirm that the required input data are available at the paths specified in the script.
3. Click **Run** in the Live Editor to execute the benchmark.
4. Inspect the optimization results, fitness evolution, tour-length convergence curves, and timing summaries directly in the script output.

**Expected runtime:** approximately **30 minutes for one complete benchmark round** with the provided default configuration. This refers to a complete run, rather than a single GA generation.

### 3. Run Individual Sections

For selective inspection, use **Run Section** to execute an individual Live Script section. Run any preceding setup and data-loading sections first so that the required variables are available.

### Runtime Summary

| Script | Execution Scope | Approximate Runtime | Results Display |
| :--- | :--- | :--- | :--- |
| `ML_Attack.mlx` | Default ML attack benchmark | 5 minutes | Inline numerical results and classification figures in the Live Editor |
| `TSP_Benchmark.mlx` | One complete benchmark round | 30 minutes | Inline optimization results, convergence curves, and timing summaries in the Live Editor |

These times are reference estimates. Actual runtime depends on the processor, MATLAB version, dataset size, selected models, TSP instance size, and the number of repeated runs. Larger configurations or additional repetitions may take longer.

---

## Structure

### 1. `ML_Attack.mlx`

- Implements an end-to-end machine learning modeling attack benchmark suite to:
  - Evaluate Fe-OPUF response predictability using Logistic Regression, Support Vector Machines, Random Forests, and Multi-Layer Perceptrons.
  - Execute nested cross-validation protocols with separate training and evaluation data.
  - Display classification accuracy, Area Under the Curve (AUC), and ROC curves inline.
- Includes a self-contained demonstration subset for rapid assessment without requiring large external image datasets.
- **Typical runtime:** approximately **5 minutes** for the provided default configuration.

### 2. `TSP_Benchmark.mlx`

- Implements a physical-bitstream-driven combinatorial optimization framework to:
  - Use Fe-OPUF-derived physical bitstreams as the random-number source for genetic optimization.
  - Run Permutation Genetic Algorithm (PGA) and hybrid GA + 2-opt solvers on standard TSPLIB benchmark instances.
  - Compare Fe-OPUF-driven optimization with pseudo-random number generator (PRNG) controls and analyze computational timing.
  - Display fitness evolution and tour-length convergence curves inline.
- **Typical runtime:** approximately **30 minutes per complete benchmark round** under the provided default configuration.

### 3. `LICENSE`

- Complete terms of the open-source **MIT License**.

---

## Dependencies & System Requirements

This repository is implemented in MATLAB Live Scripts (`.mlx`). Configure the following environment and toolboxes before running the benchmarks:

| Dependency | Required Version | Description |
| :--- | :--- | :--- |
| MATLAB | R2022b or later | Core execution environment; tested on R2023b and R2024a. |
| Statistics and Machine Learning Toolbox | Compatible with MATLAB | Supervised learning algorithms, cross-validation routines, and ROC metrics. |
| Deep Learning Toolbox | Optional; depends on the selected classifier implementation | Neural network and MLP classifier architectures for modeling attacks. |
| Image Processing Toolbox | Optional; required for image-processing workflows that use its functions | Speckle feature extraction and image preprocessing. |

### System & Hardware Specifications

- **Operating systems:** Windows 10/11 (64-bit), Ubuntu 20.04/22.04 LTS, or macOS Monterey (12.0+) or later, subject to compatibility with the installed MATLAB release.
- **Reference hardware:** a standard desktop computer with an Intel Core i7 processor and 16 GB RAM.
- **Non-standard hardware:** none required to run the supplied computational benchmarks using prerecorded Fe-OPUF data. The scripts execute on standard CPU architectures without dedicated hardware accelerators.

### Installation

1. Clone the repository:

   ```bash
   git clone https://github.com/NoahNKU/Fe-OPUF-TSP_Solve-ML_Attack.git
   ```

   Alternatively, download and extract the repository ZIP archive.

2. Launch MATLAB and set the extracted repository folder as the **Current Folder**.

3. Confirm that the toolboxes required by the selected script are installed.

---

## License

This project is distributed under the **MIT License**. See [LICENSE](LICENSE) for details.
