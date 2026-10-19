# Automated Tests

This directory contains automated tests that verify the correctness and reliability of reusable code and quantum computing experiments.

## Planned Test Categories

- Mathematical property tests
- Quantum state normalization checks
- Quantum gate unitarity checks
- Quantum circuit behavior tests
- Algorithm correctness tests
- Quantum error-correction tests
- Input validation and edge-case tests
- Regression tests for previously fixed issues

## Testing Principles

- Test mathematical properties, not only individual outputs.
- Use appropriate numerical tolerances for floating-point calculations.
- Include representative edge cases.
- Keep tests reproducible and independent where possible.
- Separate ideal simulation checks from noisy simulation or hardware experiments.
- Record relevant dependencies and configuration details.

## Tools

Tests will primarily use Python testing tools such as `pytest`, alongside NumPy and the relevant quantum computing libraries required by each project.

## Relationship to Other Directories

- `src/` contains reusable implementation code.
- `tests/` verifies that code behaves as intended.
- Numbered curriculum modules contain learning activities and practical examples.
- `benchmarks/` contains performance measurements and comparisons.

## Status

**Status: Planned — tests will be added as implementation code is developed.**
