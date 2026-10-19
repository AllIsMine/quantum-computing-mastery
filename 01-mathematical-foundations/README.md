# Mathematical Foundations for Quantum Computing

This module establishes the mathematical tools needed to understand, implement, and verify quantum computing algorithms.

It is part of the **Quantum Computing Mastery** curriculum and supports the progression from quantum foundations to quantum algorithms, quantum error correction, and research.

## Objectives

By working through this module, the learner aims to develop the ability to:

- Work confidently with complex numbers and complex arithmetic.
- Represent quantum states using vectors and matrices.
- Understand inner products, norms, and orthogonality.
- Perform matrix multiplication and reason about linear transformations.
- Calculate probabilities and interpret measurement outcomes.
- Understand the notation used to describe quantum states and operations.
- Connect mathematical predictions with quantum circuit simulations.
- Verify mathematical properties using Python and numerical tools.

## Topics

### 1. Complex Numbers

Study the form:

$$
z = a + bi,\qquad i^2 = -1
$$

Key concepts:

- Real and imaginary parts.
- Addition, subtraction, multiplication, and division.
- Complex conjugates.
- Magnitude and phase.
- Euler's formula and complex exponentials.

**Quantum connection:** Quantum-state amplitudes are generally complex numbers.

### 2. Vectors and Quantum States

Study vectors, components, vector addition, scalar multiplication, and vector norms.

For a single qubit, the computational basis states are:

$$
|0\rangle =
\begin{pmatrix}
1\\
0
\end{pmatrix},
\qquad
|1\rangle =
\begin{pmatrix}
0\\
1
\end{pmatrix}
$$

A general pure qubit state can be represented as:

$$
|\psi\rangle = \alpha|0\rangle + \beta|1\rangle
$$

where \(\alpha\) and \(\beta\) are complex amplitudes satisfying:

$$
|\alpha|^2 + |\beta|^2 = 1
$$

**Quantum connection:** State vectors describe pure quantum states in the standard state-vector formalism.

### 3. Inner Products and Orthogonality

Learn:

- Bra-ket notation.
- Inner products and complex conjugation.
- Vector norms and normalization.
- Orthogonal and orthonormal states.
- Projection onto a basis state.

**Quantum connection:** Inner products help calculate measurement probabilities and compare quantum states.

### 4. Matrices and Linear Algebra

Study:

- Matrix notation and dimensions.
- Matrix addition and multiplication.
- Identity and inverse matrices.
- Conjugate transpose.
- Eigenvalues and eigenvectors.
- Tensor products.

**Quantum connection:** Quantum gates are represented by matrices, and multi-qubit states use tensor products.

### 5. Probability

Study:

- Probability distributions.
- Conditional probability.
- Expected values and variance.
- Normalization.
- Repeated sampling and empirical frequencies.

For a state:

$$
|\psi\rangle = \alpha|0\rangle + \beta|1\rangle
$$

measurement in the computational basis gives:

$$
P(0) = |\alpha|^2,\qquad P(1) = |\beta|^2
$$

**Quantum connection:** Measurement outcomes are probabilistic, and repeated circuit executions produce statistical distributions.

### 6. Unitary Matrices

A matrix \(U\) is unitary if:

$$
U^\dagger U = I
$$

where \(U^\dagger\) denotes the conjugate transpose and \(I\) is the identity matrix.

Learn how to check unitarity and understand why ideal quantum gates preserve state-vector normalization.

**Quantum connection:** Ideal closed-system quantum operations are represented by unitary transformations.

### 7. Tensor Products

Study how to combine vectors and matrices into larger systems.

For example:

$$
|0\rangle \otimes |1\rangle = |01\rangle
$$

**Quantum connection:** Tensor products provide the mathematical representation of multi-qubit states and operations.

### 8. Mathematical Verification with Python

Use NumPy to:

- Represent complex numbers, vectors, and matrices.
- Calculate norms, inner products, and probabilities.
- Multiply matrices and apply gates to states.
- Check normalization and unitarity.
- Compare numerical results with analytical predictions.

Use numerical tolerances when comparing floating-point results instead of relying on exact equality where rounding may occur.

## Practical Learning Cycle

Follow the project's six-step method:

1. **Understand:** Study the concept and its mathematical meaning.
2. **Predict:** Calculate the expected result by hand.
3. **Implement:** Reproduce the calculation in Python.
4. **Verify:** Compare the result with the analytical prediction.
5. **Modify:** Change the input and test another case.
6. **Investigate:** Explain why the result occurs and identify relevant limitations.

## Suggested Exercises

1. Calculate the magnitude and complex conjugate of a complex number.
2. Normalize a two-component complex vector.
3. Calculate an inner product and determine whether two vectors are orthogonal.
4. Multiply two \(2 \times 2\) matrices.
5. Verify that the Pauli-X and Hadamard matrices are unitary.
6. Calculate measurement probabilities for a normalized qubit state.
7. Construct a two-qubit computational basis state using a tensor product.
8. Verify normalization and gate properties with NumPy assertions.

## Completion Criteria

Consider this module complete only after you can:

- Explain the principal concepts in your own words.
- Solve representative calculations independently.
- Implement the corresponding calculations in Python.
- Verify results with appropriate assertions.
- Explain how each concept connects to quantum states, gates, or measurement.

Record completed exercises and evidence of mastery as the work progresses.

## References

- [IBM Quantum Learning](https://quantum.cloud.ibm.com/learning)
- [Qiskit Documentation](https://docs.quantum.ibm.com/)
- [NumPy Documentation](https://numpy.org/doc/)

Consult the relevant lessons and documentation as you work through each topic.

## Status

**Status: Planned — not yet validated.**

This guide defines the intended scope of the module. Exercises, code examples, and validation results will be added as the material is developed and tested.
