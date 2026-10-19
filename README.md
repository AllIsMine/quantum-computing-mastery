# Quantum Computing Mastery

### From First Principles to Reproducible Quantum Research

**An open learning, engineering, and research laboratory by [AllIsMine](https://github.com/AllIsMine).**

Quantum Computing Mastery is a structured, project-driven initiative designed to develop quantum computing understanding through mathematical foundations, practical programming, rigorous verification, and reproducible experimentation.

The project follows **Quantum Computing Mastery — Master Edition 1.0 (October 2026)**, the authoritative roadmap for its learning stages, engineering practices, and research direction.

## Mission

Build a dependable learning and research environment where quantum computing concepts are explained clearly, implemented carefully, tested systematically, and investigated scientifically.

## Research Focus

- **Quantum Error Correction:** Coding theory, stabilizer formalism, decoding, fault tolerance, and surface-code experiments.
- **Quantum Algorithms:** Quantum circuits, search, phase estimation, and algorithmic resource analysis.
- **Quantum Hardware Engineering:** Transpilation, noise characterization, benchmarking, and error mitigation.
- **Quantum Machine Learning:** Variational circuits, quantum kernels, trainability, and fair classical comparisons.
- **Scientific Education:** Accessible explanations, guided notebooks, independent exercises, and reproducible demonstrations.

## Learning Method

Every project follows six steps:

1. **Understand** — develop intuition and mathematical understanding.
2. **Predict** — state the expected result before execution.
3. **Implement** — build the solution and explain important code.
4. **Verify** — test correctness against theory and known properties.
5. **Modify** — solve variations independently.
6. **Investigate** — explore a defined question, establish a baseline, and report limitations.

## The 200-Hour Quantum Computing Journey

This Mastery repository is supported by a separate, hands-on learning track that documents progress toward a **200-hour quantum computing learning goal**.

**[Explore the 200-Hour Quantum Computing Learning Tracker](https://github.com/AllIsMine/quantum-computing-200-hours)**

The tracker records learning milestones, Qiskit programming exercises, quantum algorithm implementations, simulation experiments, and technical notes.

The two repositories have complementary roles:

- **200-Hour Learning Tracker:** Daily learning records, practice exercises, unfinished experiments, and progress documentation.
- **Quantum Computing Mastery:** A curated portfolio of refined, tested, documented, and reproducible projects and research deliverables.

The 200-hour target represents a structured learning goal, not a claim that all planned hours or topics have been completed. Existing learning progress is preserved rather than restarted.

## Technology Stack

- Python and Qiskit 2.x
- Qiskit Aer for quantum circuit simulation
- NumPy, SciPy, and Matplotlib
- Jupyter Notebook and Google Colab
- Git and GitHub
- pytest and property-based testing
- Stim, PyMatching, and Sinter for quantum error-correction research
- Mitiq for error-mitigation comparisons
- PennyLane for selected later-stage applications

Tools and package versions will be documented and tested for each release.

## Curriculum

| Stage | Focus |
|---|---|
| 0 | Computing and Mathematics Bridge |
| 1 | Quantum Foundations Laboratory |
| 2 | Quantum Algorithms and Protocols |
| 3 | Hardware Engineering, Noise, and Mitigation |
| 4 | Quantum Error Correction |
| 5 | Variational Algorithms and Applications |
| 6 | Research Laboratory and Community |

The theory spine runs in parallel with practical work, covering quantum information, computational complexity, coding and stabilizer theory, fault tolerance, quantum machine-learning theory, and hardware physics.

See [ROADMAP.md](ROADMAP.md) for the curriculum overview, technical direction, planned repository structure, and project quality standards.

## Repository Structure

The repository will grow progressively as modules are implemented, tested, documented, and reviewed.

The planned structure includes:

- `00-start-here/` — project orientation and guidance.
- `01-mathematical-foundations/` — computing and mathematical foundations.
- `02-quantum-fundamentals/` — quantum information and core concepts.
- `03-quantum-algorithms-protocols/` — algorithms and protocols.
- `04-quantum-hardware-engineering/` — hardware, noise, and mitigation.
- `05-quantum-error-correction/` — error correction and fault tolerance.
- `06-quantum-applications/` — quantum applications and machine learning.
- `07-research-laboratory/` — reproducible experiments and research.
- `08-community-teaching/` — educational resources and community contributions.
- `theory-notes/` — supporting theoretical notes.
- `src/` — reusable source code.
- `tests/` — automated tests.
- `benchmarks/` — performance and experimental comparisons.
- `docs/` — technical documentation.
- `reports/` — research and project reports.

Folders will be added as their corresponding work develops.

## Scientific Standards

This project prioritizes:

- Mathematical correctness and automated verification.
- Reproducible experiments and documented configurations.
- Appropriate classical baselines and fair comparisons.
- Statistical uncertainty and transparent reporting.
- Clear assumptions, limitations, and negative results.
- Responsible scientific claims without unsupported quantum-advantage or novelty assertions.

A notebook running successfully is not, by itself, evidence of mastery or research validity.

Where relevant, projects should include analytical checks, automated tests, software versions, experimental settings, appropriate references, and explanations of limitations.

Simulator results must be distinguished from experiments performed on physical quantum hardware.

## Current Status

The master repository, initial roadmap, contribution guidelines, license, and Start Here guide have been established.

Technical modules will be added progressively as they are developed, tested, documented, and reviewed. The companion 200-hour tracker continues to preserve learning progress and ongoing experiments.

## Contributing

Contributions that improve correctness, reproducibility, documentation, testing, and scientific clarity are welcome.

Before contributing, please review the [Contribution Guidelines](CONTRIBUTING.md) and the repository's [MIT License](LICENSE).

All contributions should follow the project's quality standards, respect third-party licenses, and distinguish verified results from assumptions or planned work.

## License

This repository includes an MIT License for original material that the repository owner has the right to license under those terms. Third-party code, datasets, images, and other materials may be subject to separate licenses or usage conditions.

See the [LICENSE](LICENSE) file for the license text.

## Guiding Principle

**Build understanding. Test every claim. Publish only what can be reproduced.**

---

Maintained by [AllIsMine](https://github.com/AllIsMine).
