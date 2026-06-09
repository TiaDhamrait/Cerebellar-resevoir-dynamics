# Cerebellar Reservoir Dynamics & Context-Dependent Population Separation

This repository contains the Python implementation of a recurrent neural network model simulating reservoir dynamics and temporal processing within the cerebellar cortex, inspired by the frameworks of Rossert et al. 

The project evaluates how localized contextual perturbations scale to drive high-dimensional population state separation across identical time-series inputs.

---

## Neuroscience Logic & Core Mechanisms

In cerebellar architecture, the granular layer acts as a high-dimensional computational reservoir. This model simulates an inhibitory recurrent network of **N = 1000 neurons** processing temporal stimuli over **T = 2000 time steps**. 

- **Recurrent Dynamics:** Incorporates fixed, normalized inhibitory connectivity matrices (W) to assess recurrent feedback stabilization.
- **Synaptic Decay:** Implements an exponential historical decay factor (τ = 50 ms) integrating past network activity states via dynamic matrix operations.
- **Contextual Perturbation:** Evaluates network state trajectories by introducing opposing input perturbations (Context A vs. Context B) across an identical 50 ms time-series pulse stimulus.

---

## Technical Stack & Dependencies

The simulation framework is built completely from scratch using standard Python computational libraries to ensure lean, optimized array operations.

- **Language:** Python 3.x
- **Data Engineering:** `NumPy` for vectorization, random matrix generation, and high-performance matrix multiplications (`np.matmul`).
- **Data Visualization:** `Matplotlib` for generating high-resolution spatial and temporal firing-rate profiles, multidimensional distance calculations, and population activity heatmaps.

---

## Evaluation Metrics Implemented

The architecture processes and visualizes three critical data streams to monitor network divergence:
1. **Mean Population Activity:** Compares global mean firing trajectories between contexts over time.
2. **Normalized Euclidean Distance:** Computes the dynamic spatial distance separating the two multi-dimensional population vectors step-by-step:
   \[\text{Distance}(t) = \sqrt{\frac{1}{N} \sum_{i=1}^{N} (z_{A,i}(t) - z_{B,i}(t))^2}\]
3. **Difference Matrices:** Generates transposable spatial-temporal heatmaps mapping individual neural firing variations across context shifts.

---

## Repository Structure

```text
├── README.md               # Project documentation and architecture overview
├── reservoir_simulation.py # Main executable script containing the core simulation loop
```

---

## Execution & Quick Start

Ensure you have your environment configured with the required dependencies:

```bash
pip install numpy matplotlib
```

To execute the network simulation loop and plot the context-separation dynamics, run:

```bash
python reservoir_simulation.py

---
**Author:** Tia Dhamrait  
**Background:** B.Sc. Neuroscience, McMaster University  
