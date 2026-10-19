# Contributing to Quantum Computing Mastery

Thank you for your interest in Quantum Computing Mastery.

This repository is an educational and experimental quantum computing laboratory focused on mathematical understanding, tested implementations, reproducible experiments, and scientifically honest reporting.

All contributions should follow **Quantum Computing Mastery — Master Edition 1.0 (October 2026)** and the project standards described in [README.md](README.md) and [ROADMAP.md](ROADMAP.md).

## 1. Contribution Principles

Contributions should prioritize:

- Correctness over quantity.
- Clear explanations alongside working code.
- Reproducibility and maintainability.
- Accessible educational material.
- Independent verification of important claims.
- Honest reporting of assumptions, limitations, and negative results.

Do not claim quantum advantage or research novelty without appropriate evidence.

## 2. Areas for Contribution

Potential contributions include:

- Mathematical explanations and corrections.
- Quantum circuit implementations using Qiskit 2.x.
- Educational Jupyter notebooks.
- Automated tests and bug fixes.
- Quantum error-correction experiments.
- Noise, benchmarking, and error-mitigation studies.
- Quantum algorithms and selected quantum machine-learning projects.
- Documentation, exercises, references, and reproducibility improvements.

Work should align with the curriculum and the current active module.

## 3. Before Starting

1. Read the README and roadmap.
2. Check existing files and issues, if available.
3. Identify the relevant module and its prerequisites.
4. Define the intended change and how it will be verified.
5. Avoid duplicating existing work or expanding the scope unnecessarily.

Only one module should be the primary active development focus at a time.

## 4. The Six-Step Learning Cycle

Educational projects should follow this sequence:

1. **Understand:** Explain the concept and its mathematical basis.
2. **Predict:** Record the expected result before executing the experiment.
3. **Implement:** Build a clear, documented implementation.
4. **Verify:** Compare the result with theory and automated tests.
5. **Modify:** Provide an independent exercise or meaningful variation.
6. **Investigate:** For advanced work, establish a baseline, investigate a defined question, and report limitations.

## 5. Code and Testing Standards

- Use clear names, readable code, and focused functions.
- Document non-obvious mathematical and implementation decisions.
- Test mathematical properties and known results where applicable.
- Include relevant edge cases and regression checks.
- For important test suites, verify that a deliberately incorrect implementation is detected.
- Keep reusable code separate from explanatory notebook cells when appropriate.
- Document the supported environment and tested dependency versions.
- Ensure that core examples have a simulator-based path and do not require quantum hardware.

## 6. Notebook Standards

Notebooks should:

- Explain the objective and prerequisites.
- Define mathematical symbols and assumptions.
- Include a prediction before the main experiment.
- Run in the documented environment.
- Explain outputs rather than merely display them.
- Include independent exercises where appropriate.
- Record relevant configurations, seeds, shots, and backend details.
- Separate simulated results from real-hardware observations.

Never include API tokens, passwords, private credentials, or other secrets.

## 7. Research and Reproducibility

Research contributions should document, as applicable:

- The research question and relevant references.
- Methods, assumptions, and experimental configurations.
- Software versions and data provenance.
- Classical baselines and fair resource comparisons.
- Sample sizes, uncertainty, and statistical methods.
- Results, limitations, and deviations from the source method.

Negative or inconclusive findings are acceptable when carefully documented.

Do not describe a reproduced result as a novel discovery merely because it differs from a published result.

## 8. Documentation and References

- Link to authoritative documentation, textbooks, and primary research papers where appropriate.
- Cite the source of claims, algorithms, and adapted implementations.
- Respect upstream licenses and copyright.
- Explain technical terms for learners who may be new to the topic.
- State known limitations and provide a clear next step.

## 9. Suggested Contribution Workflow

When contributing through Git:

1. Create a focused branch for your change.
2. Make a small, clearly scoped improvement.
3. Run relevant tests and notebook checks.
4. Review the documentation and experimental claims.
5. Commit the changes with a descriptive message.
6. Open a pull request describing the motivation, implementation, tests, and limitations.

For small documentation corrections, use the simplest workflow supported by GitHub.

## 10. Definition of Done

A contribution is ready for review when:

- Its purpose and scope are clear.
- The code or documentation is internally consistent.
- Relevant tests and checks have been run.
- Results and claims are supported by evidence.
- References and limitations are included where applicable.
- No credentials or unintended private data are included.
- The contribution aligns with the master roadmap.

Not every documentation change requires a new experiment, but every technical claim must remain appropriately supported.

## 11. Questions and Improvements

For questions, corrections, or proposed improvements, use the repository's available GitHub discussion and issue mechanisms where enabled.

Thank you for helping make quantum computing education and research more understandable, reliable, and reproducible.

**Build understanding. Test every claim. Publish only what can be reproduced.**
