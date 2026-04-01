# AQFT: Circuit Compression for the NISQ Era
**Optimizing the Quantum Fourier Transform for Near-Term Hardware**

## Project Overview
The Quantum Fourier Transform (QFT) is a fundamental mathematical engine for major quantum algorithms. However, standard QFT implementation requires microscopic phase rotations (fractions of a degree) between distant qubits, leading to an $O(n^2)$ gate complexity. On Noisy Intermediate-Scale Quantum (NISQ) hardware, these long-distance entanglements often introduce more physical hardware noise than mathematical accuracy.

This project implements an **Approximate Quantum Fourier Transform (AQFT)**. By introducing an Approximation Degree ($m$), we systematically prune long-distance, low-impact phase gates. This drastically reduces circuit depth and execution time while maintaining a mathematically viable state fidelity.

## Key Findings
Our simulation engine tests an 8-qubit system scaling from $m=8$ (Standard QFT) down to $m=1$ (Extreme Approximation). 
* **Performance Gain:** Total gate count is reduced by nearly 25% by snipping unnecessary operations.
* **State Fidelity:** At an optimal approximation degree of $m=4$, the circuit maintains >98% accuracy compared to the standard, uncompressed algorithm.

## Installation & Setup
To run the simulation and generate the performance graphs locally, you will need Python 3.8+ installed.

1. **Clone the repository:**
   git clone [https://github.com/YOUR_USERNAME/YOUR_REPO_NAME.git]
   cd YOUR_REPO_NAME

2. **Install the required dependencies:**
   pip install -r requirements.txt

## Usage
1. Open the Jupyter Notebook environment: `jupyter notebook`
2. Open `main_research.ipynb`.
3. Run all cells to execute the quantum statevector simulation. 
4. The script will automatically calculate the state fidelities and output `aqft_results_graph.png`, plotting Gate Count vs. State Fidelity.


## Stack & Technologies
* **Language:** Python
* **Quantum SDK:** IBM Qiskit (Aer Simulator, Quantum Info)
* **Data Visualization:** Matplotlib, NumPy