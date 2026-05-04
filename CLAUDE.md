# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Development Workflow

### Setup and Execution
The project is primarily implemented as a Jupyter Notebook.
- **Environment**: Python 3.8+
- **Dependencies**: `qiskit`, `qiskit-aer`, `numpy`, `matplotlib`, `jupyterlab`
- **Execution**: Run the simulations using Jupyter Notebook:
  ```bash
  jupyter notebook triangle_of_quantum_security.ipynb
  ```

## Architecture Overview

The project implements the **Triangle of Quantum Security**, a defense-in-depth approach combining three quantum-based security layers:

### 1. QRNG (Quantum Random Number Generator)
- **Implementation**: `QuantumRNG` class in `triangle_of_quantum_security.ipynb`.
- **Mechanism**: Uses Qiskit to create a circuit with Hadamard gates on multiple qubits to generate true randomness via superposition and measurement.
- **Purpose**: Provides the entropy foundation for all cryptographic keys.

### 2. PQC (Post-Quantum Cryptography)
- **Implementation**: `SimplifiedKyberKEM` class in `triangle_of_quantum_security.ipynb`.
- **Mechanism**: A simplified Key Encapsulation Mechanism (KEM) based on the Module Learning With Errors (M-LWE) problem (Lattice-based cryptography).
- **Purpose**: Ensures keys remain secure against Shor's algorithm and future quantum computing attacks.

### 3. QKD (Quantum Key Distribution)
- **Implementation**: `BB84_QKD` class in `triangle_of_quantum_security.ipynb`.
- **Mechanism**: Implements the BB84 protocol using random basis selection and measurement to detect eavesdropping through increased error rates (No-Cloning Theorem).
- **Purpose**: Provides information-theoretic security for the physical transmission of keys.

### Integration
- **Integration Class**: `TriangleQuantumSecurity` orchestrates the full workflow: `QRNG (Key Gen) -> PQC (Encryption) -> QKD (Transmission)`.

## Project Structure
- `triangle_of_quantum_security.ipynb`: Main implementation and simulation notebook.
- `README.md`: Project overview and technical documentation.
- `images/`: Generated circuit diagrams, statistical analysis plots, and architectural visualizations.
- `*.html`: Exported reports/visualizations for specific metrics (e.g., QSRI, QARS).
