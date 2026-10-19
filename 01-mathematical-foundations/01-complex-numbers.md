# 01 — Complex Numbers for Quantum Computing

**Module:** Mathematical Foundations  
**Lesson:** Complex Numbers  
**Status:** In Progress — validation pending  
**Prerequisites:** Basic algebra and Python fundamentals

---

## Learning Objectives

By completing this lesson, you should be able to:

- Represent complex numbers in rectangular and polar forms.
- Identify the real and imaginary parts of a complex number.
- Perform complex arithmetic, conjugation, magnitude, and phase calculations.
- Apply Euler's formula.
- Implement and verify complex-number calculations using Python and NumPy.
- Normalize complex probability amplitudes.
- Explain how complex amplitudes, relative phase, and squared magnitudes relate to quantum states.

## 1. Understand — Mathematical Foundations

### 1.1 Complex Numbers

A complex number has the form

$$
z=a+bi
$$

where:

- $a$ is the real part.
- $b$ is the imaginary coefficient.
- $i$ is the imaginary unit, satisfying $i^2=-1$.

The real and imaginary parts are

$$
\mathrm{Re}(z)=a,\qquad
\mathrm{Im}(z)=b
$$

For example, if $z=3+4i$,

$$
\mathrm{Re}(z)=3,\qquad
\mathrm{Im}(z)=4
$$

The imaginary part is $4$, not $4i$.

### 1.2 Complex Arithmetic

Complex numbers can be added, subtracted, multiplied, and divided using ordinary algebra together with $i^2=-1$.

**Addition**

$$
(3+4i)+(1-2i)=4+2i
$$

**Subtraction**

$$
(3+4i)-(1-2i)=2+6i
$$

**Multiplication**

$$
(3+4i)(1-2i)
$$

Expanding,

$$
=3-6i+4i-8i^2
$$

Since $i^2=-1$,

$$
=3-2i+8=11-2i
$$

### 1.3 Complex Conjugate

The complex conjugate is obtained by reversing the sign of the imaginary term.

For

$$
z=a+bi
$$

the conjugate is

$$
z^*=a-bi
$$

For example,

$$
z=2-5i\quad\Rightarrow\quad z^*=2+5i
$$

Conjugation is essential in complex inner products and quantum probability calculations.

### 1.4 Magnitude and Squared Magnitude

The magnitude, also called the modulus, is

$$
|z|=\sqrt{a^2+b^2}
$$

The squared magnitude is

$$
|z|^2=a^2+b^2
$$

It can also be expressed using the conjugate:

$$
|z|^2=zz^*
$$

For $z=3+4i$,

$$
|z|=\sqrt{3^2+4^2}=5
$$

and

$$
|z|^2=(3+4i)(3-4i)=25
$$

The squared magnitude is always real and non-negative.

### 1.5 Phase and Polar Form

A nonzero complex number can be represented in rectangular form,

$$
z=a+bi
$$

or in polar form,

$$
z=re^{i\theta}
$$

where $r=|z|$ is the magnitude and $\theta$ is the phase, or argument, of the complex number.

The phase can be written as

$$
\theta=\arg(z)
$$

For numerical calculations, use the two-argument arctangent function `atan2(b, a)` to determine the angle in the correct quadrant.

**Example**

For $z=1+i$, the real part is $a=1$ and the imaginary coefficient is $b=1$.

The magnitude is

$$
r=|z|=\sqrt{1^2+1^2}=\sqrt{2}
$$

The phase is

$$
\theta=\mathrm{atan2}(1,1)=\frac{\pi}{4}=45^\circ
$$

Therefore, the polar form is

$$
z=\sqrt{2}\,e^{i\pi/4}
$$

The principal phase is commonly represented in $(-\pi,\pi]$. Other phase conventions are possible. The phase of zero is undefined.

### 1.6 Euler's Formula

Euler's formula connects exponential functions with trigonometric functions:

$$
e^{i\theta}=\cos\theta+i\sin\theta
$$

For $\theta=\pi/2$,

$$
e^{i\pi/2}
=\cos\left(\frac{\pi}{2}\right)
+i\sin\left(\frac{\pi}{2}\right)
=i
$$

A useful consequence is

$$
|e^{i\theta}|=1
$$

for every real $\theta$, because

$$
|e^{i\theta}|
=\sqrt{\cos^2\theta+\sin^2\theta}=1
$$

Multiplication by $e^{i\theta}$ rotates a nonzero complex number in the complex plane without changing its magnitude.

### 1.7 Quick Reference

| Concept | Formula | Example |
|---|---|---|
| Complex number | $z=a+bi$ | $3+4i$ |
| Real part | $\mathrm{Re}(z)=a$ | $3$ for $3+4i$ |
| Imaginary part | $\mathrm{Im}(z)=b$ | $4$ for $3+4i$ |
| Conjugate | $z^*=a-bi$ | $3-4i$ |
| Magnitude | $|z|=\sqrt{a^2+b^2}$ | $5$ for $3+4i$ |
| Squared magnitude | $|z|^2=zz^*$ | $25$ for $3+4i$ |
| Polar form | $z=re^{i\theta}$ | $\sqrt{2}e^{i\pi/4}$ for $1+i$ |
| Euler's formula | $e^{i\theta}=\cos\theta+i\sin\theta$ | $e^{i\pi/2}=i$ |

## 2. Predict — Work by Hand

Before running any code, solve the following exercises on paper.

### Exercise A — Complex Multiplication

Compute

$$
(3+4i)(1-2i)
$$

### Exercise B — Conjugate and Magnitude

For

$$
z=2-5i
$$

find $z^*$, $|z|$, and $|z|^2$.

### Exercise C — Polar Form

Express

$$
z=1+i
$$

in polar form. Give the magnitude and phase in radians and degrees.

### Exercise D — Euler's Formula

Use Euler's formula to verify that

$$
e^{i\pi/2}=i
$$

Write down your predictions before proceeding.

## 3. Implement — NumPy Experiments

Open [Google Colab](https://colab.research.google.com/) and create a Python notebook.

Run the following cells in order. First predict the result by hand, then compare your prediction with Python's output.

### 3.1 Setup

```python
import numpy as np
import math

np.set_printoptions(precision=4, suppress=True)
```

### 3.2 Exercise A — Complex Multiplication

```python
z1 = 3 + 4j
z2 = 1 - 2j

result = z1 * z2

print("Result:", result)

assert np.isclose(result, 11 - 2j)
print("Exercise A check passed.")
```

Expected result: `11-2j`, corresponding to $11-2i$.

### 3.3 Exercise B — Conjugate and Magnitude

```python
z = 2 - 5j

conjugate = np.conjugate(z)
magnitude = np.abs(z)
squared_magnitude = magnitude ** 2

print("Complex number:", z)
print("Conjugate:", conjugate)
print("Magnitude:", magnitude)
print("Squared magnitude:", squared_magnitude)

assert np.isclose(conjugate, 2 + 5j)
assert np.isclose(magnitude, np.sqrt(29))
assert np.isclose(squared_magnitude, 29)

print("Exercise B checks passed.")
```

Expected mathematical results:

$$
z^*=2+5i,\qquad |z|=\sqrt{29},\qquad |z|^2=29
$$

### 3.4 Exercise C — Polar Form

```python
z = 1 + 1j

r = np.abs(z)
theta = np.angle(z)
theta_deg = np.degrees(theta)

print("Rectangular form:", z)
print("Magnitude:", r)
print("Phase (radians):", theta)
print("Phase (degrees):", theta_deg)

assert np.isclose(r, np.sqrt(2))
assert np.isclose(theta, np.pi / 4)
assert np.isclose(theta_deg, 45.0)

print("Exercise C checks passed.")
```

Expected results:

$$
r=\sqrt{2},\qquad
\theta=\frac{\pi}{4}=45^\circ
$$

### 3.5 Exercise D — Euler's Formula

```python
theta = np.pi / 2
euler = np.exp(1j * theta)

print("e^(i*pi/2):", euler)
print("Approximately equal to i:", np.isclose(euler, 1j))
print("Magnitude:", np.abs(euler))

assert np.isclose(euler, 1j)
assert np.isclose(np.abs(euler), 1.0)

print("Euler's formula checks passed.")
```

The numerical result may contain a tiny real component close to zero. This is a normal floating-point rounding effect.

## 4. Verify — Quantum Amplitude Normalization

### 4.1 Quantum-State Representation

A pure single-qubit state can be expressed as

$$
|\psi\rangle=\alpha|0\rangle+\beta|1\rangle
$$

where $\alpha$ and $\beta$ are complex probability amplitudes.

The measurement probabilities are

$$
P(0)=|\alpha|^2,\qquad
P(1)=|\beta|^2
$$

A normalized state must satisfy

$$
|\alpha|^2+|\beta|^2=1
$$

This condition ensures that the total measurement probability is one.

### 4.2 Normalize Complex Amplitudes

Consider

$$
\alpha=1+i,\qquad \beta=1-i
$$

Their initial squared magnitudes are

$$
|\alpha|^2=2,\qquad |\beta|^2=2
$$

Therefore,

$$
|\alpha|^2+|\beta|^2=4
$$

The normalization factor is the square root of this sum:

$$
N=\sqrt{4}=2
$$

Divide each amplitude by $N$:

$$
\alpha'=\frac{1+i}{2},\qquad
\beta'=\frac{1-i}{2}
$$

The normalized squared magnitudes are both $1/2$, so their sum is one.

### 4.3 Implement and Verify Normalization

```python
alpha = 1 + 1j
beta = 1 - 1j

norm_sq = np.abs(alpha)**2 + np.abs(beta)**2
norm = np.sqrt(norm_sq)

alpha_norm = alpha / norm
beta_norm = beta / norm

p0 = np.abs(alpha_norm)**2
p1 = np.abs(beta_norm)**2
total_probability = p0 + p1

print("Initial squared norm:", norm_sq)
print("Normalization factor:", norm)
print("Normalized alpha:", alpha_norm)
print("Normalized beta:", beta_norm)
print("P(0):", p0)
print("P(1):", p1)
print("Total probability:", total_probability)

assert np.isclose(norm_sq, 4.0)
assert np.isclose(norm, 2.0)
assert np.isclose(p0, 0.5)
assert np.isclose(p1, 0.5)
assert np.isclose(total_probability, 1.0)

print("Quantum-state normalization checks passed.")
```

This example demonstrates normalization for a single-qubit pure state. It does not simulate quantum hardware or demonstrate a quantum speedup.

## 5. Modify — Change the Inputs

Now test whether you can apply the concepts to new cases.

### Challenge 1 — Complex Multiplication

Compute by hand and with NumPy:

$$
(2-3i)(4+i)
$$

Predict the result before running the code.

```python
z1 = 2 - 3j
z2 = 4 + 1j

result = z1 * z2

print("Product:", result)

assert np.isclose(result, 11 - 10j)
print("Challenge 1 passed.")
```

### Challenge 2 — Polar Form

Find the polar form of

$$
z=-1+i\sqrt{3}
$$

Calculate the magnitude and determine the principal phase in radians and degrees.

```python
z = -1 + 1j * np.sqrt(3)

r = np.abs(z)
theta = np.angle(z)

print("Magnitude:", r)
print("Phase (radians):", theta)
print("Phase (degrees):", np.degrees(theta))

assert np.isclose(r, 2.0)
assert np.isclose(theta, 2 * np.pi / 3)
assert np.isclose(np.degrees(theta), 120.0)

print("Challenge 2 passed.")
```

Expected mathematical results:

$$
r=2,\qquad \theta=\frac{2\pi}{3}=120^\circ
$$

### Challenge 3 — Normalize an Amplitude Pair

Normalize

$$
\alpha=3+4i,\qquad \beta=0
$$

```python
alpha = 3 + 4j
beta = 0 + 0j

norm = np.sqrt(np.abs(alpha)**2 + np.abs(beta)**2)

alpha_norm = alpha / norm
beta_norm = beta / norm

print("Normalized alpha:", alpha_norm)
print("Normalized beta:", beta_norm)
print(
    "Total squared magnitude:",
    np.abs(alpha_norm)**2 + np.abs(beta_norm)**2
)

assert np.isclose(alpha_norm, 0.6 + 0.8j)
assert np.isclose(beta_norm, 0.0)
assert np.isclose(
    np.abs(alpha_norm)**2 + np.abs(beta_norm)**2,
    1.0
)

print("Challenge 3 passed.")
```

### Challenge 4 — Magnitude Under a Phase Rotation

Show numerically that multiplying a complex number by $e^{i\theta}$ does not change its magnitude for real $\theta$.

```python
z = 2 + 3j
theta = 1.234

rotated = z * np.exp(1j * theta)

print("Original magnitude:", np.abs(z))
print("Rotated magnitude:", np.abs(rotated))

assert np.isclose(np.abs(z), np.abs(rotated))
print("Challenge 4 passed.")
```

This works because $|e^{i\theta}|=1$.

## 6. Investigate — Think Like a Quantum Scientist

Answer these questions in your own words before checking additional references.

1. Why are complex numbers useful for representing quantum amplitudes?
2. What role does relative phase play in quantum interference?
3. What happens to the magnitude when a complex number is multiplied by $e^{i\theta}$, where $\theta$ is real?
4. Why must the squared magnitudes of a normalized quantum state's amplitudes sum to one?
5. Why can two states with different relative phases produce different interference outcomes even if their individual amplitude magnitudes are equal?

### Key Insight — Global Phase Versus Relative Phase

Multiplying an entire quantum state by a common phase factor $e^{i\phi}$ does not change its measurement probabilities or physical predictions for an isolated state.

For example,

$$
|\psi'\rangle=e^{i\phi}|\psi\rangle
$$

has the same measurement probabilities as $|\psi\rangle$.

However, the relative phase between amplitudes can affect interference and therefore influence measurement outcomes after suitable quantum operations.

Complex amplitudes provide the mathematical framework for describing these phase relationships.

## 7. Summary

| Concept | Formula / Meaning | Quantum Relevance |
|---|---|---|
| Complex number | $a+bi$ | Represents complex amplitudes |
| Real part | $\mathrm{Re}(z)=a$ | Identifies the real component |
| Imaginary part | $\mathrm{Im}(z)=b$ | Identifies the imaginary coefficient |
| Conjugate | $a-bi$ | Used in inner products and squared magnitudes |
| Magnitude | $\sqrt{a^2+b^2}$ | Gives amplitude magnitude |
| Squared magnitude | $zz^*=|z|^2$ | Determines measurement probabilities |
| Polar form | $re^{i\theta}$ | Separates magnitude and phase |
| Euler's formula | $e^{i\theta}=\cos\theta+i\sin\theta$ | Connects phases to trigonometric functions |
| Normalization | $|\alpha|^2+|\beta|^2=1$ | Ensures total measurement probability is one |
| Relative phase | Phase difference between amplitudes | Can influence quantum interference |

## 8. Completion Criteria

This lesson is ready for validation when you can:

- Calculate complex arithmetic, conjugates, magnitudes, and phases by hand.
- Convert between rectangular and polar forms.
- Apply Euler's formula.
- Run the NumPy experiments successfully.
- Pass all supplied automated assertions.
- Normalize complex amplitudes correctly.
- Explain the difference between global phase and relative phase.
- Answer the investigation questions in your own words.

## 9. References

- [IBM Quantum Learning](https://quantum.cloud.ibm.com/learning)
- [NumPy — Data Types](https://numpy.org/doc/stable/user/basics.types.html)
- [Python — `cmath` Module](https://docs.python.org/3/library/cmath.html)

## 10. Scope and Next Lesson

This lesson introduces the complex-number mathematics needed for quantum computing. It does not complete the broader mathematical foundations module.

Subsequent lessons will cover vectors, vector norms, inner products, matrices, matrix multiplication, and unitary transformations.

**Current status:** In Progress — validation pending.

**Scientific standard:** Do not mark this lesson as Validated until the mathematical explanations, code, exercises, and verification evidence have been reviewed and checked.
