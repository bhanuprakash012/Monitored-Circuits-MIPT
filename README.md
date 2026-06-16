# Phase Transitions in Monitored Quantum Circuits

## Overview
This repository investigates the dynamics of Measurement-Induced Phase Transitions (MIPT) and Learnability Transitions (Barren Plateaus) in deep, highly entangled parameterized quantum circuits. The goal is to track how the introduction of classical interactions—either through environmental noise or projective measurements—forces a transition from a highly entangled, untrainable volume-law phase to a disentangled, trainable area-law phase.

To rigorously analyze these transitions beyond the limits of exact state-vector simulation, this project utilizes Matrix Product State (MPS) tensor networks. 

## Two-Pronged Approach
This repository tackles the phase transition problem using two distinct methodologies and tech stacks:

### Part 1: Noise-Driven Transitions (Python)
Instead of using projective measurements, this approach introduces **Amplitude Damping Noise** to drive the transition.
* **Architecture:** Deep alternating even/odd Brickwork circuits using a highly parameterized 15-rotation $W$ gate.
* **Tech Stack:** `Cirq` for quantum circuit construction, `quimb.tensor` for MPS simulation, and `PyTorch` for GPU acceleration.
* **Metrics Tracked:** Maximum Bond Dimension ($\chi$), Half-Cut Entanglement Entropy, and Parameter-Shift Gradient Variance.

### Part 2: Measurement-Driven Transitions (Julia)
This approach models the traditional MIPT framework, utilizing random projective measurements at a set probability $p$ to collapse the entanglement.
* **Tech Stack:** Written in Julia using the [`QuantumCircuitsMPS.jl`](https://github.com/jpixley/QuantumCircuitsMPS.jl) package, developed by Jedediah Pixley's research group at Rutgers University. 
* **Focus:** High-performance tensor network simulation specifically optimized for monitored quantum circuits and measurement-induced dynamics.

## Acknowledgments & Contributions
The foundation of the Python tensor network simulation codebase relies on a collaborative effort:
* **Ryan La Rose:** Authored the initial, foundational tensor network simulation framework for quantum circuits.
* **Harkirat Verma:** Adapted and expanded the initial framework specifically for analyzing Quantum Convolutional Neural Networks (QCNNs).
* **My Contributions:** Adapted the architecture to support deep, highly expressive Brickwork circuits. Implemented the amplitude damping noise models, engineered the dual-experiment pipeline to concurrently track MIPT and Barren Plateaus, and integrated the comparative Julia approach using `QuantumCircuitsMPS.jl`.

## How to Run

**For Part 1 (Python):**
```bash
pip install cirq quimb torch numpy matplotlib tqdm sympy
