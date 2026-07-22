# Essence of Calculus — 3Blue1Brown - summary

---

<details >
<summary><strong>1. The Essence of Calculus</strong></summary>

**Key Idea**: Calculus is about understanding continuous change. You can "discover" its core ideas by deeply thinking about simple geometry problems like the area of a circle.

**Main Example**: Area of a circle (πr²)

**How to Derive It**:
- Slice the circle into many thin concentric rings.
- Each ring has circumference ≈ 2πr and tiny thickness dr.
- "Unroll" a ring → it approximates a rectangle with area 2πr · dr.
- Sum all rings (integrate) from r=0 to r=R → Area = ∫ 2πr dr from 0 to R = πR².

**Big Ideas Introduced**:
- **Integrals**: Accumulating tiny pieces (sum of many small things).
- **Derivatives**: Instantaneous rate of change.
- **Fundamental Theorem of Calculus**: Derivatives and integrals are inverses of each other.

**Intuition**: Calculus lets you solve hard problems by breaking them into infinitely many tiny, manageable pieces.

</details>

<details>
<summary><strong>2. The Paradox of the Derivative</strong></summary>

**Key Idea**: The derivative represents instantaneous rate of change, but this seems paradoxical because "instantaneous" implies no change in time/distance.

**Core Concept**: Derivative = limit of average rate of change as the interval shrinks to zero.

**Example with x³**:
- Change in function: (x + dx)³ - x³
- Divided by dx → 3x² + 3x(dx) + (dx)²
- As dx → 0, higher terms vanish → derivative = 3x² (Power Rule intuition)

**Intuition**:
- The derivative is **not** a ratio of infinitesimals.
- It is the **limit** of that ratio as the tiny change approaches zero.
- This resolves the paradox and makes the idea rigorous.

**Power Rule Insight**: For x^n, the derivative is n x^{n-1}. It feels discoverable through geometry or algebra.

</details>

<details>
<summary><strong>3. Derivative Formulas Through Geometry</strong></summary>

**Key Idea**: Many derivative formulas can be understood visually and geometrically rather than memorized.

**Key Derivatives Derived Geometrically**:

- **Constant**: d/dx [c] = 0 (flat line, no change)
- **Linear**: d/dx [x] = 1 (slope is constant 1)
- **Power Rule**: Already hinted in Video 2
- **Sum Rule**: Derivative of sum = sum of derivatives
- **Trig Functions**:
  - Derivative of sin(x) = cos(x)
  - Derivative of cos(x) = -sin(x)
- Explained via small changes and geometric interpretations (unit circle, small angle approximations).

**Intuition**: Think about how a tiny change in input affects the output by looking at the graph or shape. The derivative tells you the slope at every point.

**Overall Message**: These formulas aren't arbitrary — they emerge naturally from geometric thinking.

</details>

---

## Some useful functions of sympy library

Setup

```python
import sympy as sp
x, y, z = sp.symbols('x y z')    # declare variables you'll use

```

Core calculus functions
Differentiation

```python
sp.diff(x**2, x)              # basic derivative
sp.diff(x**2 * sp.sin(x), x)  # handles product rule automatically
sp.diff(f, x, 2)              # second derivative (change 2 to n for nth)
```

Integration

```python
sp.integrate(x**2, x)              # indefinite integral
sp.integrate(x**2, (x, 0, 5))      # definite integral from 0 to 5
```

Limits

```python
sp.limit(sp.sin(x)/x, x, 0)   # limit as x approaches 0
```

Simplifying expressions

```python
sp.simplify(expr)   # cleans up a messy expression
sp.expand(expr)     # expands brackets, e.g. (x+1)**2 -> x**2 + 2x + 1
sp.factor(expr)     # opposite of expand
```

Solving equations

```python
sp.solve(x**2 - 4, x)          # find roots -> [-2, 2]
sp.solve(sp.Eq(x**2, 4), x)    # same thing, more explicit style
```

Substituting values

```python
expr = x**2 + 3*x
expr.subs(x, 5)     # plug in x=5, get an actual number
```


