# Essence of Linear Algebra — 3Blue1Brown - ShortNotes
---

## One-Line Thread Through the Whole ShortNotes

**Vectors** → combine them (**span/basis**) → transform them (**matrices**) → measure the transform (**determinant**) → undo it (**inverse**) → describe transforms independent of a grid (**dot product, eigenvectors**) → generalize beyond arrows (**abstract vector spaces**).

---

## Chapters

<details open>
<summary><strong>1. Vectors, what even are they?</strong></summary>

**Key Idea**: A vector is an arrow from the origin, defined by coordinates (x, y).

**Three Lenses**:
- **Physics**: Arrow in space (direction + magnitude)
- **Computer Science**: Ordered list of numbers
- **Mathematics**: Anything you can add and scale

**Operations**:
- **Addition**: Tip-to-tail
- **Scaling**: k * [x, y] = [kx, ky]

**Intuition**: A vector is an instruction — "walk this far in this direction" — **not a point**.

</details>

<details>
<summary><strong>2. Linear combinations, span, and basis vectors</strong></summary>

**Key Idea**: Any vector in the plane is a weighted sum of the basis vectors î and ĵ.

**Formula**:  
v = a*î + b*ĵ

**Span**: All points reachable by a*v + b*w.

**Intuition**:
- Span of two non-parallel vectors = entire plane.
- If parallel (or zero) → **linearly dependent**; span collapses to a line or point.
- Linearly independent vectors each add a new dimension.

</details>

<details>
<summary><strong>3. Linear transformations and matrices</strong></summary>

**Key Idea**: A matrix represents a linear transformation that keeps grid lines parallel and evenly spaced, with the origin fixed.

**Core Insight**: The **columns** of the matrix show where the basis vectors î and ĵ land after transformation.

**Formula**:  
[a c; b d] * [x; y] = x*[a; b] + y*[c; d]

**Intuition**: Track only where the basis vectors go — linearity takes care of everything else.

</details>

<details>
<summary><strong>4. Matrix multiplication as composition</strong></summary>

**Key Idea**: Matrix multiplication = applying one transformation after another.

**Formula**:  
(M2 * M1) * v = M2(M1(v))  
(Read right to left.)

**Intuition**: Two transformations squashed into one new matrix. Multiplication is **not** commutative in general.

</details>

<details>
<summary><strong>5. Three-dimensional linear transformations</strong></summary>

**Key Idea**: Same principles extend to 3D. Columns of a 3×3 matrix show where î, ĵ, k̂ land.

**Intuition**: Visualize squishing, rotating, stretching 3D space while the origin stays fixed.

</details>

<details>
<summary><strong>6. The determinant</strong></summary>

**Key Idea**: The determinant tells you the **scaling factor** of areas (2D) or volumes (3D) under the transformation.

**2×2 Formula**:  
det([a c; b d]) = ad - bc

**Intuition**:
- Negative → orientation flip (mirrored space)
- Zero → transformation squishes space into lower dimension

</details>

<details>
<summary><strong>7. Inverse matrices, column space, null space</strong></summary>

**Key Idea**: A⁻¹ undoes A. Solving Ax = v means "which input lands on v?"

**Conditions**: Unique solution exists only if det(A) ≠ 0.

**Important Spaces**:
- **Rank**: Dimension of the column space (output space)
- **Column space**: All possible outputs
- **Null space (kernel)**: All vectors that map to the origin

</details>

<details>
<summary><strong>8. Nonsquare matrices — transformations between dimensions</strong></summary>

**Key Idea**: An m×n matrix maps n-dimensional space to m-dimensional space.

**Examples**:
- 3×2 matrix: 2D → 3D
- 2×3 matrix: 3D → 2D (flattening)

**Intuition**: Columns still show where basis vectors go, but now in a space of different dimension.

</details>

<details>
<summary><strong>9. Dot products and duality</strong></summary>

**Formula**:  
v · w = |v| |w| cos(θ) = x1x2 + y1y2

**Intuition**:
- Dot product = (projection of v onto w) × |w|
- Every linear transformation from vectors **to a number** corresponds to "dot with some fixed vector" (**duality**).

</details>

<details>
<summary><strong>10. Cross products (standard intro)</strong></summary>

**Key Idea**: Magnitude = area of parallelogram spanned by two vectors.

**2D Formula** (signed area):  
vx wy - vy wx

**3D**: Produces a vector perpendicular to both (right-hand rule).

**Intuition**: Sign indicates orientation (clockwise vs counterclockwise).

</details>

<details>
<summary><strong>11. Cross products in light of linear transformations</strong></summary>

**Formula**:  
v × w = det([ î  ĵ  k̂ ;  
             v1 v2 v3 ;  
             w1 w2 w3 ])

**Intuition**: Volume as a linear function → corresponds to a dual vector (the cross product).

</details>

<details>
<summary><strong>12. Cramer's Rule, explained geometrically</strong></summary>

**Formula**:  
xi = det(Ai) / det(A)  
(where Ai replaces column i with v)

**Intuition**: The transformation scales all areas/volumes by det(A). Ratios of areas give the coordinates.

</details>

<details>
<summary><strong>13. Change of basis</strong></summary>

**Key Idea**: Coordinates are relative to a chosen basis.

**Formulas**:
- v_standard = B * v_B
- v_B = B⁻¹ * v_standard

**Similarity Transformation**: B⁻¹ A B

**Intuition**: Matrices act as translators between different coordinate grids.

</details>

<details>
<summary><strong>14. Eigenvectors and eigenvalues</strong></summary>

**Key Idea**: Eigenvectors stay on their own line (only scaled, not rotated).

**Equation**:  
A v = λ v

**Finding Them**:
1. Solve det(A - λI) = 0 for eigenvalues
2. Solve (A - λI) v = 0 for eigenvectors

**Intuition**: Eigenvectors are the "natural axes" of the transformation. In eigenbasis, the matrix becomes diagonal (pure scaling).

</details>

<details>
<summary><strong>15. A quick trick for computing eigenvalues (2×2)</strong></summary>

**Formula**:  
Let m = trace(A)/2, p = det(A)  
Eigenvalues = m ± √(m² - p)

**Intuition**: Fast mental check and verification tool.

</details>

<details>
<summary><strong>16. Abstract vector spaces</strong></summary>

**Key Idea**: Linear algebra generalizes far beyond arrows — to functions, polynomials, etc.

**Vector Space Axioms** (8 total): closure under addition & scaling, distributivity, zero vector, inverses, etc.

**Intuition**: A "vector" is anything obeying these rules. The same concepts (span, basis, linear transformations, eigenvectors) apply directly.

**Example**: The derivative is a linear transformation on the space of polynomials.

</details>

---

