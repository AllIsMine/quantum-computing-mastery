
# 02 — Vectors and Quantum States

**Module:** Mathematical Foundations  
**Lesson:** Vectors and Quantum States  
**Author:** AllIsMine  
**Tools:** Python, NumPy, Google Colab  
**Status:** In Progress — Validation Pending  
**Prerequisites:** Lesson 01 — Complex Numbers; basic algebra; Python fundamentals.

---

## 1. Objective

Understand how vectors represent quantum states, how to calculate vector norms and normalize vectors, and how the components of a state determine measurement probabilities. Use Python and NumPy to test the mathematics numerically.

## 2. Learning Objectives

By the end of this lesson, you should be able to:

- Represent vectors using component and column-vector notation.
- Explain computational basis states and Dirac ket notation.
- Calculate vector norms and squared norms.
- Explain normalization and why a quantum state must have total probability one.
- Calculate measurement probabilities from complex amplitudes.
- Use NumPy to verify orthogonality, normalization, and probability calculations.
- Recognize the difference between a mathematical state-vector model and an actual quantum-hardware experiment.

## 3. The Learning Workflow

Follow the project workflow:

**Understand → Predict → Implement → Verify → Modify → Investigate**

Before running a code cell, try to predict what it will print. After execution, compare the result with your prediction and explain any difference.

---

## 4. What Is a Vector?

A vector is an ordered collection of components. For example,

$$
v = \begin{bmatrix}
3\\
4
\end{bmatrix}
$$

has two components: 3 and 4. We can think of it as an arrow in a two-dimensional coordinate system, but in quantum computing vectors also represent mathematical states.

A vector can contain real or complex numbers. For example,

$$
v = \begin{bmatrix}
1+i\\
1-i
\end{bmatrix}
$$

is a complex vector. Complex numbers are important because quantum amplitudes can have both magnitude and phase.

### 4.1 Python: Create a Vector

```python
import numpy as np

v = np.array([3, 4], dtype=float)

print("Vector:", v)
print("First component:", v[0])
print("Second component:", v[1])

assert np.allclose(v, [3, 4])
print("Vector representation check passed.")
```

**Expected result:** The vector is `[3. 4.]`, its first component is `3.0`, and its second component is `4.0`.

**Why this matters:** NumPy arrays give us a convenient way to represent vectors and perform calculations that we will use later for quantum states.

---

## 5. Column Vectors and State Vectors

In mathematics, a two-component column vector is often written as

$$
v = \begin{bmatrix}
a\\
b
\end{bmatrix}.
$$

In Python, we commonly represent the same components as a one-dimensional array:

```python
a = 3
b = 4
v = np.array([a, b])
```

The mathematical column-vector notation and the Python array are related representations, but they are not literally the same data structure.

In quantum computing, a **state vector** encodes the amplitudes associated with a chosen basis. For a single qubit, we use two computational basis states.

---

## 6. Dirac Notation and Computational Basis States

Dirac notation, also called bra-ket notation, is widely used in quantum mechanics.

The two computational basis states for one qubit are

$$
|0\rangle = \begin{bmatrix}
1\\
0
\end{bmatrix},
\qquad
|1\rangle = \begin{bmatrix}
0\\
1
\end{bmatrix}.
$$

The symbols $|0\rangle$ and $|1\rangle$ are called **kets**. They represent computational basis states, not ordinary text strings.

These basis vectors are normalized:

$$
\lVert |0\rangle\rVert = 1,
\qquad
\lVert |1\rangle\rVert = 1.
$$

They are also orthogonal to each other. Their inner product is zero:

$$
\langle 0|1\rangle = 0.
$$

Here, $\langle 0|$ is the bra corresponding to $|0\rangle$. In finite-dimensional complex vector spaces, a bra is the conjugate transpose of the corresponding ket.

### 6.1 Python: Represent the Basis States

```python
zero = np.array([1, 0], dtype=complex)
one = np.array([0, 1], dtype=complex)

print("|0> =", zero)
print("|1> =", one)

assert np.allclose(zero, [1, 0])
assert np.allclose(one, [0, 1])
print("Computational basis-state checks passed.")
```

### 6.2 Python: Check Their Norms and Orthogonality

```python
norm_zero = np.linalg.norm(zero)
norm_one = np.linalg.norm(one)
inner_product = np.vdot(zero, one)

print("Norm of |0>:", norm_zero)
print("Norm of |1>:", norm_one)
print("<0|1>:", inner_product)

assert np.isclose(norm_zero, 1.0)
assert np.isclose(norm_one, 1.0)
assert np.isclose(inner_product, 0.0)
print("Norm and orthogonality checks passed.")
```

**Important:** `np.vdot(a, b)` conjugates the entries of its first argument before computing the inner product. This matters for complex vectors.

---

## 7. General Pure State of a Qubit

A general pure state of one qubit can be written as

$$
|\psi\rangle = \alpha|0\rangle + \beta|1\rangle
= \begin{bmatrix}
\alpha\\
\beta
\end{bmatrix},
$$

where $\alpha$ and $\beta$ are complex probability amplitudes.

The amplitudes are not themselves probabilities. The measurement probabilities in the computational basis are

$$
P(0)=|\alpha|^2,
\qquad
P(1)=|\beta|^2.
$$

For a valid normalized state,

$$
|\alpha|^2 + |\beta|^2 = 1.
$$

The notation $|\alpha|^2$ means the squared magnitude of the complex number $\alpha$, not the square of the symbol without taking its magnitude.

### 7.1 Python: Calculate Probabilities from Amplitudes

Consider the state

$$
|\psi\rangle = \frac{3}{5}|0\rangle + \frac{4}{5}|1\rangle.
$$

Its probabilities should be $P(0)=9/25=0.36$ and $P(1)=16/25=0.64$.

```python
psi = np.array([3/5, 4/5], dtype=complex)
probabilities = np.abs(psi) ** 2

print("State:", psi)
print("P(0):", probabilities[0])
print("P(1):", probabilities[1])
print("Total probability:", probabilities.sum())

assert np.allclose(probabilities, [0.36, 0.64])
assert np.isclose(probabilities.sum(), 1.0)
print("Measurement-probability checks passed.")
```

**Interpretation:** In an ideal measurement in the computational basis, the predicted probability of obtaining outcome 0 is 36%, and the probability of obtaining outcome 1 is 64%. A single measurement gives one outcome; probabilities describe the distribution across repeated identically prepared measurements.

---

## 8. Vector Norm and Squared Norm

The Euclidean norm of a real vector

$$
v = \begin{bmatrix}
v_1\\
\vdots\\
v_n
\end{bmatrix}
$$

is

$$
\lVert v\rVert = \sqrt{\sum_{j=1}^{n}|v_j|^2}.
$$

For complex vectors, the magnitude of each component is used. The **squared norm** is

$$
\lVert v\rVert^2 = \sum_{j=1}^{n}|v_j|^2.
$$

For a normalized quantum state, the norm is 1 and the squared norm is also 1.

### 8.1 Python: Calculate a Norm

```python
v = np.array([3.0, 4.0])
norm_v = np.linalg.norm(v)
squared_norm = norm_v ** 2

print("Vector:", v)
print("Norm:", norm_v)
print("Squared norm:", squared_norm)

assert np.isclose(norm_v, 5.0)
assert np.isclose(squared_norm, 25.0)
print("Norm checks passed.")
```

The vector

$$
v = \begin{bmatrix}
3\\
4
\end{bmatrix}
$$

has norm 5, so it is not yet normalized as a quantum state.

---

## 9. Normalization

To normalize a nonzero vector $v$, divide it by its norm:

$$
|\psi\rangle = \frac{v}{\lVert v\rVert}.
$$

This produces a vector with norm 1. The zero vector cannot be normalized because its norm is zero and division by zero is undefined.

### 9.1 Python: Normalize a Real Vector

```python
v = np.array([3.0, 4.0])
norm_v = np.linalg.norm(v)

if np.isclose(norm_v, 0.0):
    raise ValueError("The zero vector cannot be normalized.")

psi = v / norm_v

print("Original vector:", v)
print("Original norm:", norm_v)
print("Normalized vector:", psi)
print("Normalized norm:", np.linalg.norm(psi))

assert np.allclose(psi, [0.6, 0.8])
assert np.isclose(np.linalg.norm(psi), 1.0)
print("Real-vector normalization checks passed.")
```

The normalized vector is

$$
|\psi\rangle = \begin{bmatrix}
0.6\\
0.8
\end{bmatrix}.
$$

Its components have squared magnitudes 0.36 and 0.64, which sum to 1.

### 9.2 Python: Normalize a Complex Vector

Consider

$$
v = \begin{bmatrix}
1+i\\
1-i
\end{bmatrix}.
$$

Each component has squared magnitude 2, so the squared norm is 4 and the norm is 2.

```python
v = np.array([1 + 1j, 1 - 1j], dtype=complex)
norm_v = np.linalg.norm(v)

if np.isclose(norm_v, 0.0):
    raise ValueError("The zero vector cannot be normalized.")

psi = v / norm_v
probabilities = np.abs(psi) ** 2

print("Original vector:", v)
print("Original norm:", norm_v)
print("Normalized state:", psi)
print("Component probabilities:", probabilities)
print("Total probability:", probabilities.sum())

assert np.isclose(norm_v, 2.0)
assert np.allclose(psi, [(1 + 1j)/2, (1 - 1j)/2])
assert np.allclose(probabilities, [0.5, 0.5])
assert np.isclose(np.linalg.norm(psi), 1.0)
print("Complex-state normalization checks passed.")
```

This example connects Lesson 01 to Lesson 02: complex amplitudes are components of a vector, and their squared magnitudes determine the computational-basis measurement probabilities.

---

## 10. Equal Superposition

An important single-qubit state is

$$
|+\rangle = \frac{|0\rangle+|1\rangle}{\sqrt{2}}
= \frac{1}{\sqrt{2}}
\begin{bmatrix}
1\\
1
\end{bmatrix}.
$$

Both computational-basis outcomes have probability $1/2$. This state is called an equal superposition in the computational basis.

```python
plus = np.array([1 / np.sqrt(2), 1 / np.sqrt(2)], dtype=complex)
probabilities = np.abs(plus) ** 2

print("|+> =", plus)
print("Norm:", np.linalg.norm(plus))
print("Probabilities:", probabilities)
print("Total probability:", probabilities.sum())

assert np.isclose(np.linalg.norm(plus), 1.0)
assert np.allclose(probabilities, [0.5, 0.5])
assert np.isclose(probabilities.sum(), 1.0)
print("Equal-superposition checks passed.")
```

**Conceptual caution:** A superposition is a quantum state, not merely uncertainty about a classical bit. The relative phase between amplitudes can affect the results of later quantum operations, even when the computational-basis probabilities are initially the same.

---

## 11. A State with Unequal Probabilities

Consider the normalized state

$$
|\psi\rangle = \frac{1}{\sqrt{5}}|0\rangle
+ \frac{2}{\sqrt{5}}|1\rangle
= \begin{bmatrix}
\frac{1}{\sqrt{5}}\\
\frac{2}{\sqrt{5}}
\end{bmatrix}.
$$

Its probabilities are $1/5=0.2$ and $4/5=0.8$.

```python
psi = np.array([1 / np.sqrt(5), 2 / np.sqrt(5)], dtype=complex)
probabilities = np.abs(psi) ** 2

print("State:", psi)
print("Probabilities:", probabilities)
print("Total probability:", probabilities.sum())

assert np.allclose(probabilities, [0.2, 0.8])
assert np.isclose(np.linalg.norm(psi), 1.0)
assert np.isclose(probabilities.sum(), 1.0)
print("Unequal-probability state checks passed.")
```

---

## 12. Challenges

Try each challenge yourself before looking at the solution code in the notebook. Predict the answer first, then implement, run, and explain the result.

### Challenge A — Normalize a Real Vector

Given

$$
v = \begin{bmatrix}
5\\
12
\end{bmatrix},
$$

1. Calculate its norm.
2. Normalize the vector.
3. Verify that the normalized norm equals 1.

**Expected mathematical norm:** 13.

### Challenge B — Normalize a Complex Vector

Given

$$
v = \begin{bmatrix}
1+i\\
1-i
\end{bmatrix},
$$

1. Calculate the norm.
2. Normalize the vector.
3. Calculate each component's squared magnitude.
4. Verify that the probabilities sum to 1.

**Expected norm:** 2.

### Challenge C — Measurement Probabilities

Given

$$
|\psi\rangle = \frac{\sqrt{3}}{2}|0\rangle
+ \frac{1}{2}|1\rangle
= \begin{bmatrix}
\frac{\sqrt{3}}{2}\\
\frac{1}{2}
\end{bmatrix},
$$

calculate $P(0)$, $P(1)$, and their sum.

**Expected probabilities:** 0.75 and 0.25.

### Challenge D — Identify an Unnormalized Vector

Given

$$
v = \begin{bmatrix}
1\\
1
\end{bmatrix},
$$

1. Calculate its norm.
2. Explain why it is not a normalized quantum state as written.
3. Normalize it and verify the result.

**Expected norm before normalization:** $\sqrt{2}$.

### Challenge E — Test a Phase Change

Compare the states

$$
|\psi_1\rangle = \frac{1}{\sqrt{2}}
\begin{bmatrix}
1\\
1
\end{bmatrix},
\qquad
|\psi_2\rangle = \frac{1}{\sqrt{2}}
\begin{bmatrix}
1\\
-1
\end{bmatrix}.
$$

Calculate their computational-basis probabilities. Are those probabilities the same? Are the state vectors identical? Explain why different relative phases can matter for later quantum operations.

---

## 13. Investigation Questions

Write short answers in your notebook or project notes.

1. Why must a normalized pure quantum state have squared norm equal to 1?
2. Why do we calculate probabilities using squared magnitudes instead of amplitudes directly?
3. What would go wrong if a vector with norm zero were normalized?
4. Why does `np.vdot(a, b)` matter when the vectors contain complex numbers?
5. Can two different state vectors have the same computational-basis probabilities? What might distinguish them in a later experiment?
6. What does this notebook demonstrate, and what does it not demonstrate about a physical quantum computer?

---

## 14. Key Findings

| Concept | Meaning |
|---|---|
| Vector | An ordered set of components |
| State vector | A vector of amplitudes representing a quantum state in a chosen basis |
| Ket notation | `\|ψ⟩` represents a quantum state |
| Norm | The vector's length |
| Normalized state | A state whose norm is 1 |
| Amplitude | A generally complex component of a state vector |
| Measurement probability | Squared magnitude of the relevant amplitude in the chosen measurement basis |
| Orthogonal vectors | Vectors with zero inner product |
| Equal superposition | A state with equal computational-basis probabilities for this single-qubit example |

---

## 15. Limitations and Scientific Honesty

- This lesson uses classical numerical calculations with Python and NumPy.
- It does not execute a quantum circuit or access quantum hardware.
- The probabilities are theoretical predictions for ideal measurements in the stated basis.
- Numerical floating-point calculations can produce tiny rounding differences.
- A state vector alone does not specify every detail of an experimental setup; preparation, operations, measurement basis, and noise can matter.

---

## 16. Reproducibility

- **Environment:** Google Colab
- **Language:** Python
- **Library:** NumPy
- **Verification:** `assert` statements and numerical comparisons
- **Record:** Note the NumPy version, any errors, and any changes needed to reproduce the results.

---

## 17. Verification Checklist

Complete these items only after running and reviewing the relevant notebook cells.

- [ ] NumPy setup executed successfully.
- [ ] Computational basis states verified.
- [ ] Basis-state norms verified.
- [ ] Basis-state orthogonality verified.
- [ ] Measurement probabilities verified.
- [ ] Real-vector norm calculated correctly.
- [ ] Real-vector normalization verified.
- [ ] Complex-vector normalization verified.
- [ ] Equal-superposition checks passed.
- [ ] Unequal-probability state checks passed.
- [ ] Challenges A–D completed and checked.
- [ ] Challenge E investigated and explained.
- [ ] Investigation questions answered.
- [ ] All notebook cells executed successfully.
- [ ] Outputs and limitations reviewed.

---

## 18. Completion Criteria

This lesson is ready for validation only after:

1. Every notebook cell has been executed in Google Colab.
2. All assertions pass.
3. All five challenges have been attempted, with Challenge E explained.
4. The outputs are consistent with the expected mathematics.
5. The learner can explain normalization and measurement probabilities without relying only on memorized code.
6. The Markdown lesson and notebook have been reviewed for consistency.

**Final status:** In Progress — Validation Pending.

Change the status to **Validated** only after the completion criteria have been met and the results have been reviewed.

---

## 19. References and Next Lesson

Use a standard quantum-information text or reputable university course to deepen the mathematical interpretation of vectors, inner products, and quantum states. Record the exact resource and section used when you consult it.

**Next lesson:** Inner Products and Orthogonality.

The next lesson will build on vectors and complex conjugation to study inner products, orthogonality, and their role in quantum information.
