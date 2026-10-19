# Quantum Computing Mastery — Roadmap

**Master Edition 1.0 | October 2026**

This roadmap follows the final Quantum Computing Mastery plan. It is the central guide for building a reproducible quantum computing learning, engineering, and research laboratory.

## Mission

Progress from quantum computing foundations to advanced engineering and carefully scoped, reproducible research through mathematical understanding, practical implementation, automated verification, and independent investigation.

## Core Principles

- Quality over quantity.
- Understand concepts before implementing them.
- Predict outcomes before running experiments.
- Verify mathematical properties and test edge cases.
- Record software versions, configurations, and experimental results.
- Use fair classical baselines and report limitations honestly.
- Keep learning notes separate from polished deliverables.
- Advance only after meeting the relevant mastery checks.

## Learning Cycle

Every project follows these six steps:

1. Understand
2. Predict
3. Implement
4. Verify
5. Modify
6. Investigate

## Curriculum

### Stage 0 — Computing and Mathematics Bridge
Python, complex numbers, vectors, matrices, probability, and quantum vocabulary.

### Stage 1 — Quantum Foundations Laboratory
Qubits, quantum gates, Bloch sphere, measurement, entanglement, teleportation, superdense coding, and density matrices.

### Stage 2 — Quantum Algorithms and Protocols
Deutsch–Jozsa, Bernstein–Vazirani, Grover search, quantum Fourier transform, phase estimation, and factoring concepts.

### Stage 3 — Hardware Engineering, Noise, and Mitigation
Transpilation, noise models, hardware experiments, error mitigation, benchmarking, and randomized benchmarking.

### Stage 4 — Quantum Error Correction
Repetition codes, classical coding theory, Shor and Steane codes, stabilizer formalism, Stim, PyMatching, Sinter, fault tolerance, and surface-code research.

### Stage 5 — Variational Algorithms and Applications
VQE, QAOA, quantum machine learning, quantum physics simulation, resource estimation, and trainability.

### Stage 6 — Research Laboratory and Community
Research capstone, reproducibility tools, paper reproduction, open-source contributions, and scientific reports.

## Theory Spine

Theoretical study runs alongside practical projects:

- Quantum information theory
- Computational complexity and quantum advantage
- Coding and stabilizer theory
- Fault tolerance
- Quantum machine-learning theory
- Quantum hardware physics

## Technology Stack

- Python 3.10+
- Qiskit 2.x and Qiskit Aer
- NumPy, SciPy, and Matplotlib
- Jupyter and Google Colab
- Git and GitHub
- pytest and property-based testing
- Stim, PyMatching, and Sinter for quantum error correction
- Mitiq for error-mitigation comparisons
- PennyLane at the applications stage

Use documented, tested dependency versions for every release.

## Repository Structure

The repository will progressively contain:

- `00-start-here/`
- `01-mathematical-foundations/`
- `02-quantum-fundamentals/`
- `03-quantum-algorithms-protocols/`
- `04-quantum-hardware-engineering/`
- `05-quantum-error-correction/`
- `06-quantum-applications/`
- `07-research-laboratory/`
- `08-community-teaching/`
- `theory-notes/`
- `src/`
- `tests/`
- `benchmarks/`
- `docs/`
- `reports/`

Create and populate folders as their modules are developed and validated.

## Project Quality Gate

A project is not complete simply because its notebook runs. It must include appropriate explanations, mathematical reasoning, predictions, runnable code, tests, independent exercises, references, results, and documented limitations.

Research experiments must record relevant configurations, versions, sample sizes, uncertainty, and hardware details. Claims must be supported by evidence and reproducible procedures.

## Repository Separation

- `quantum-computing-200-hours`: daily learning notes, sprint tasks, and unfinished experiments.
- `quantum-computing-mastery`: polished, tested, documented modules and research deliverables.

Preserve previous learning progress. Work on one active module at a time.

## Source of Truth

The controlling document is **Quantum Computing Mastery — Master Edition 1.0 (October 2026)**. This file is an implementation overview, not a replacement for the complete master plan.

Minor corrections and additions should be recorded in the roadmap changelog. Do not create a new roadmap version unless a material strategic change requires it.
