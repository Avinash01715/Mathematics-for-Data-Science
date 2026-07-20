# Essence of Linear Algebra


Series by **3Blue1Brown (Grant Sanderson)**


---

<details>
<summary><strong>Chapter 1: Vectors, what even are they?</strong></summary>

**Key Takeaway**  
A vector is an arrow starting at the origin, and its coordinates are just instructions for how far to walk along each axis to reach its tip. Adding vectors and scaling them are the two core operations that everything else in linear algebra builds on.

**Definitions**

- **Vector (geometric view)**  
  An arrow rooted at the origin; direction and length encode the two numbers (x, y).

- **Vector (coordinate view)**  
  An ordered list of numbers, e.g. (3, 2), each number telling you the displacement along one axis.

- **Scalar**  
  A single number used to stretch, shrink, or reverse a vector (multiplication).

- **Vector addition**  
  Place the tail of the second vector at the tip of the first; the sum is the arrow from the origin to the final tip.

- **Scalar multiplication**  
  Stretches a vector if the scalar is greater than 1, shrinks it if between 0 and 1, and flips its direction if negative.

**Visualization Intuition**
- Think 'movement', not 'point' — a vector is a step you take, so the same arrow can be drawn anywhere, but in this course it's always drawn from the origin for consistency.
- Vector addition visually = walk-then-walk: follow the first arrow, then follow the second from where you land.
- Scaling visually = stretching the arrow along its own line without changing its direction (unless the scalar is negative, which flips it).

**Important Points**
- There are 3 common views of a vector: physics (arrow in space), computer science (ordered list of numbers), and math (anything you can add and scale — the abstract, general definition).
- The origin is the anchor point for every vector in this series — it is what makes 'linear' transformations well defined later on.
- This chapter sets the two fundamental operations (addition, scalar multiplication) that define what 'linear' means throughout the whole series.

</details>

---

<details>
<summary><strong>Chapter 2: Linear combinations, span, and basis vectors</strong></summary>

**Key Takeaway**  
Every vector can be described as a weighted mix (linear combination) of basis vectors like i-hat and j-hat. The span of a set of vectors is everything you can reach using linear combinations of them, and whether vectors are 'independent' tells you if any of them are redundant.

**Definitions**

- **Basis vectors (i-hat, j-hat)**  
  The unit vectors along the x and y axes; i-hat = (1,0), j-hat = (0,1). Coordinates are just the scalars used to scale these.

- **Linear combination**  
  Any sum of scaled vectors: a*v + b*w, where a and b are scalars.

- **Span**  
  The set of every possible vector reachable via linear combinations of a given set of vectors.

- **Linearly dependent**  
  When one vector in the set already lies in the span of the others — it adds no new direction.

- **Linearly independent**  
  When every vector adds a new dimension to the span (none is redundant).

- **Basis of a space**  
  A set of linearly independent vectors that spans the full space.

**Visualization Intuition**
- Span of one non-zero vector = a straight line through the origin.
- Span of two vectors (not pointing the same/opposite way) in 2D = the entire 2D plane.
- Span of two vectors that do point along the same line = still just that line (dependent, redundant).
- In 3D, the span of two independent vectors is a flat plane slicing through the origin; a third independent vector can 'lift' the span to fill all of 3D space.

**Important Points**
- Any coordinate pair (x, y) is really shorthand for the linear combination x*(i-hat) + y*(j-hat).
- Basis vectors are a choice, not a law of nature — any two independent vectors can serve as a basis.
- Dependence/independence is the formal way of asking: 'does removing this vector shrink what I can reach?'

</details>

---

<details>
<summary><strong>Chapter 3: Linear transformations and matrices</strong></summary>

**Key Takeaway**  
A linear transformation is a special kind of function on vectors that keeps grid lines parallel, evenly spaced, and fixes the origin. Because of this, the transformation is completely determined by where it sends just the basis vectors — and a matrix is simply a table recording those landing spots.

**Definitions**

- **Transformation**  
  A function that takes an input vector and produces an output vector (a fancy word for a vector-to-vector function).

- **Linear transformation**  
  A transformation where the origin stays fixed and all grid lines remain parallel and evenly spaced after transforming.

- **Matrix**  
  A grid of numbers whose columns tell you exactly where each basis vector (i-hat, j-hat, ...) lands after the transformation.

- **Matrix-vector multiplication**  
  The computed way of applying a matrix's transformation to any vector, using the columns as the transformed basis vectors.

**Visualization Intuition**
- Picture the whole coordinate grid as a sheet of graph paper; a linear transformation moves/stretches/rotates that sheet, but the lines stay straight, parallel, and evenly spaced, and the origin never moves.
- Because i-hat and j-hat land somewhere new after the transform, and every other vector is just a combination of i-hat and j-hat, you can find where ANY vector lands using only those two landing spots.
- A 2x2 matrix's first column = where i-hat lands, second column = where j-hat lands.

**Important Points**
- This is the central insight of the whole series: a matrix is not just a number grid — it is a compact description of a transformation, fully defined by tracking only the basis vectors.
- Rotations, shears, reflections, and stretches are all examples of linear transformations, each representable as a matrix.
- If grid lines curve or become unevenly spaced, or the origin moves, the transformation is NOT linear.

</details>

---

<details>
<summary><strong>Chapter 4: Matrix multiplication as composition</strong></summary>

**Key Takeaway**  
Multiplying two matrices together represents applying one linear transformation and then another — the resulting product matrix is a single transformation that captures the combined effect. Order matters because applying transformations in a different sequence generally lands vectors in different places.

**Definitions**

- **Composition of transformations**  
  Applying one transformation, then applying a second transformation to the result.

- **Matrix product (M2 * M1)**  
  The single matrix that represents 'first apply M1, then apply M2' — read right to left.

- **Non-commutativity**  
  In general, M1*M2 does not equal M2*M1 — applying transformations in a different order gives a different outcome.

- **Associativity**  
  (M1*M2)*M3 = M1*(M2*M3) — grouping doesn't matter because both sides just mean 'apply the three transformations in the same left-to-right order'.

**Visualization Intuition**
- Picture rotating a sheet of paper and then shearing it, versus shearing it first and then rotating — the two end results look visually different, which is why order matters.
- To compute the product matrix, transform i-hat and j-hat using the right-hand matrix first, then feed those results through the left-hand matrix.
- Reading matrix products right-to-left mirrors function composition notation f(g(x)) — g acts first, f acts second.

**Important Points**
- Matrix multiplication was DEFINED this way historically specifically so it would represent composition of transformations, not as an arbitrary rule to memorize.
- Associativity is 'obvious' geometrically (doing 3 transforms in sequence has one unambiguous order) even though it looks non-obvious as a row/column computation.
- This composition view makes it much easier to recall the mechanical multiplication formula, instead of memorizing it by rote.

</details>

---

<details>
<summary><strong>Chapter 5: Three-dimensional linear transformations</strong></summary>

**Key Takeaway**  
Everything from 2D generalizes directly to 3D: a linear transformation is still fully described by where the basis vectors land, now i-hat, j-hat, and k-hat, giving a 3x3 matrix, and matrix multiplication still represents composing transformations in 3D space.

**Definitions**

- **3D basis vectors**  
  i-hat, j-hat, k-hat — unit vectors along the x, y, and z axes respectively.

- **3x3 matrix**  
  Each of the 3 columns records where one of the 3 basis vectors lands after the transformation.

- **3D matrix multiplication**  
  Same composition idea as 2D: multiplying two 3x3 matrices gives the single matrix for applying both transformations in sequence.

**Visualization Intuition**
- Picture a 3D grid of little cubes; a linear transformation can rotate, stretch, or shear that grid, but straight lines stay straight and evenly spaced, and the origin stays fixed — identical rules to 2D, just one dimension up.
- To find where a 3D vector lands, express it as a linear combination of i-hat, j-hat, k-hat, then combine their transformed landing spots the same way.

**Important Points**
- The core recipe from Chapters 2-4 (basis vectors → matrix columns → matrix-vector multiplication → composition) is dimension-agnostic; nothing conceptually new is introduced here, only extended.
- This generalization is what allows all these ideas to scale to even higher dimensions (4D, 100D, etc.), which matters heavily for machine learning where 'dimensions' are just features.

</details>

---

<details>
<summary><strong>Chapter 6: The determinant</strong></summary>

**Key Takeaway**  
The determinant of a matrix is a single number measuring how much a linear transformation scales areas (in 2D) or volumes (in 3D). A negative determinant means the transformation flips orientation, and a determinant of zero means the transformation squashes space into a lower dimension.

**Definitions**

- **Determinant**  
  The factor by which a linear transformation scales area (2D) or volume (3D).

- **Orientation flip**  
  Happens when the determinant is negative — e.g. i-hat and j-hat swap relative positions (clockwise vs counter-clockwise).

- **Zero determinant**  
  Means the transformation squishes the plane onto a line/point (2D) or space onto a plane/line/point (3D) — area or volume collapses to zero.

- **2x2 determinant formula**  
  For matrix [[a, b], [c, d]], determinant = a*d - b*c.

**Visualization Intuition**
- Picture the unit square formed by i-hat and j-hat before the transform; the determinant tells you the area of the square that unit square becomes after transforming.
- If the transformed i-hat, j-hat square area doubles, the determinant is 2 — meaning every region's area is scaled by 2, not just that one square.
- In 3D, picture the unit cube formed by i-hat, j-hat, k-hat; the determinant is the transformed cube's volume.

**Important Points**
- det(M1 * M2) = det(M1) * det(M2) — applying two transformations in sequence multiplies their scaling factors, which makes intuitive sense (scale by 2, then by 3, means an overall 6x scale).
- A zero determinant is the geometric test for whether a matrix is invertible: if space is squashed flat, information is lost and the transformation cannot be undone.
- The sign of the determinant (positive/negative) is a check on orientation, not magnitude — always take the absolute value for pure area/volume scaling.

</details>

---

<details>
<summary><strong>Chapter 7: Inverse matrices, column space and null space</strong></summary>

**Key Takeaway**  
Systems of linear equations (Ax = v) can be solved geometrically by finding the inverse transformation A⁻¹ that undoes A — but this only works when the determinant is non-zero. Column space describes all possible outputs of a transformation, and null space describes every input that gets squashed to the origin.

**Definitions**

- **Linear system of equations**  
  A set of equations that can be written compactly as A*x = v, where A is the matrix, x is the unknown vector, v is the known output vector.

- **Inverse matrix (A⁻¹)**  
  The matrix that reverses/undoes the transformation done by A, so that A⁻¹ * A = the identity transformation (no change).

- **Identity matrix**  
  The 'do nothing' transformation — leaves every basis vector exactly where it is.

- **Rank**  
  The number of dimensions in the output of a transformation (i.e. the dimensionality of the column space).

- **Column space**  
  The set of all possible outputs of a matrix — literally the span of its columns.

- **Full rank**  
  When rank equals the number of columns, meaning no dimensions are lost in the transformation.

- **Null space (kernel)**  
  The set of all input vectors that land exactly on the origin after the transformation.

**Visualization Intuition**
- Picture solving Ax = v as asking: 'which input vector x, after being transformed by A, lands exactly on v?' Finding A⁻¹ is like rewinding the transformation to walk backward from v to x.
- If det(A) is non-zero, space isn't squashed, so there's a unique unrewind path — A⁻¹ exists and gives exactly one solution.
- If det(A) = 0, the transformation squashes space onto a lower-dimensional line or point (reducing rank); many different input vectors can collapse onto the same output, or the target output v may not be reachable at all.
- Null space visualizes as whichever line, plane, or point gets squashed directly onto the origin during the transformation.

**Important Points**
- det(A) = 0 is precisely the condition under which A⁻¹ does NOT exist — a zero determinant means information is lost and the transform can't be reversed.
- 'Rank 2' for a 2x2 matrix means the columns still span the full 2D plane (full rank); 'rank 1' means they collapse onto a single line.
- Column space answers 'what outputs are possible?' while null space answers 'what inputs get destroyed (mapped to zero)?' — together they fully describe a transformation's behavior.

</details>

---

<details>
<summary><strong>Chapter 8: Nonsquare matrices as transformations between dimensions</strong></summary>

**Key Takeaway**  
A matrix doesn't have to be square — a matrix with different numbers of rows and columns represents a transformation that changes the number of dimensions, mapping an input space into an output space of a different dimensionality.

**Definitions**

- **Nonsquare matrix**  
  A matrix with a different number of rows than columns, e.g. 3 rows x 2 columns.

- **Number of columns**  
  Tells you the dimension of the INPUT space (how many basis vectors you're tracking).

- **Number of rows**  
  Tells you the dimension of the OUTPUT space (how many coordinates each landing spot needs).

- **2D-to-3D transformation example**  
  A 3x2 matrix: 2 columns (2 input basis vectors, i-hat and j-hat) each landing somewhere in 3D space (3 rows).

**Visualization Intuition**
- Picture a flat 2D plane floating inside 3D space; a 3x2 matrix takes that flat grid and repositions it as a tilted plane somewhere in 3D, still keeping lines straight and evenly spaced.
- Picture a 2x3 matrix doing the reverse: squashing all of 3D space down onto a flat 2D plane — three basis vectors' landing spots, each described with only 2 coordinates.
- The matrix's shape alone (rows x columns) tells you the 'before' and 'after' dimensions before you even look at the numbers inside it.

**Important Points**
- This generalizes the Chapter 3 idea (matrix columns = transformed basis vectors) to the case where input and output spaces aren't the same size.
- A full-column-rank matrix mapping from a lower dimension into a higher one still produces a lower-dimensional image (e.g. a 2D plane living inside 3D) — you can't gain dimensions you didn't start with.
- This concept underlies real-world uses like projecting high-dimensional data down to 2D/3D for visualization, or embedding low-dimensional features into higher-dimensional spaces in ML.

</details>

---

<details>
<summary><strong>Chapter 9: Dot products and duality</strong></summary>

**Key Takeaway**  
The dot product of two vectors combines a numerical shortcut (multiply and add matching components) with a deep geometric meaning: it measures how much one vector extends in the direction of another, scaled by length — and it secretly links every vector to a linear transformation from space to a number line.

**Definitions**

- **Dot product (numerical)**  
  For v=(v1,v2) and w=(w1,w2): v·w = v1*w1 + v2*w2 — multiply matching components and add.

- **Dot product (geometric)**  
  v·w = |v| * |w| * cos(theta), where theta is the angle between them — related to projecting one vector onto the other.

- **Projection**  
  The 'shadow' one vector casts onto the line spanned by another, found by dropping a perpendicular line onto that line.

- **Duality**  
  The surprising fact that every linear transformation from space to a single number line corresponds to a unique vector, and applying that transformation is the same as taking a dot product with that vector.

**Visualization Intuition**
- Picture shining a light perpendicular to vector w so that vector v casts a shadow onto the line through w; the length of that shadow, times |w|, gives the dot product.
- If v and w point in similar directions, the dot product is large and positive; if they're perpendicular, it's zero; if they point opposite ways, it's negative — picture the shadow shrinking to nothing, then reversing, as the angle grows past 90 degrees.
- Duality visualized: a 1xN matrix (a single row) is geometrically the same as a vector — multiplying by that matrix and taking a dot product with that vector are the exact same physical action of 'projecting and scaling'.

**Important Points**
- The numerical shortcut (multiply-and-add) works ONLY because of the deeper geometric projection idea — 3B1B stresses understanding why the shortcut is valid, not just using it.
- Order doesn't matter for the dot product (v·w = w·v), unlike matrix multiplication in general.
- This duality (vectors as transformations, transformations as vectors) is a recurring, deep theme — it reappears in the cross product chapters that follow.

</details>

---

<details>
<summary><strong>Chapter 10: Cross products</strong></summary>

**Key Takeaway**  
The (standard, 'high-school') cross product of two 2D vectors gives the signed area of the parallelogram they form, and in 3D it produces a new vector perpendicular to both inputs, whose length equals the area of the parallelogram they span.

**Definitions**

- **2D cross product**  
  For v=(v1,v2), w=(w1,w2): v × w = v1*w2 - v2*w1 — equals the determinant of the 2x2 matrix with v, w as columns.

- **Signed area**  
  The 2D cross product's magnitude = area of the parallelogram formed by v and w; sign is positive if w is counter-clockwise from v, negative otherwise.

- **3D cross product**  
  v × w produces a new vector, perpendicular to both v and w, whose length equals the parallelogram area they span; direction found via the right-hand rule.

**Visualization Intuition**
- Picture the parallelogram formed by placing v and w tail-to-tail; the 2D cross product is exactly that parallelogram's area (with a sign showing orientation).
- In 3D, picture that same parallelogram lying tilted somewhere in space; the cross product vector sticks straight out of it (perpendicular to the whole parallelogram), and its length equals the parallelogram's area.
- Right-hand rule visualized: point fingers along v, curl toward w, thumb points in the direction of v × w.

**Important Points**
- The 2D cross product is really just a special case/shortcut of the determinant (Chapter 6) — it's literally det([v w]).
- Order matters: w × v = -(v × w) — swapping the two vectors flips the sign/direction.
- The 'standard' formula taught in most courses is a computational shortcut; the deeper reasoning behind WHY it works is saved for the next chapter.

</details>

---

<details>
<summary><strong>Chapter 11: Cross products in the light of linear transformations</strong></summary>

**Key Takeaway**  
The true, more general definition of the 3D cross product comes from duality (Chapter 9): define a linear transformation that takes any vector and outputs the volume of the parallelepiped it forms with v and w — the vector representing that transformation IS the cross product v × w.

**Definitions**

- **Parallelepiped**  
  A 3D 'squished box' shape formed by three vectors.

- **Volume function**  
  A linear transformation that takes any input vector u and returns the signed volume of the parallelepiped formed by u, v, w.

- **Cross product (dual-vector definition)**  
  The unique vector p such that p·u equals the volume of the parallelepiped formed by u, v, w, for every possible u — this vector p is v × w.

**Visualization Intuition**
- Picture building a 3-vector parallelepiped with a placeholder vector u, plus fixed v and w; as u varies, the volume changes linearly — exactly the kind of linear function duality (Ch. 9) says corresponds to a vector.
- That corresponding vector turns out to literally be the geometric cross product from Chapter 10 — picture it as the 'volume-detector' vector: dotting any u with it instantly tells you the volume u would create with v and w.
- This ties directly back to why v × w must be perpendicular to both v and w: if u=v or u=w, the parallelepiped has zero volume (it's flattened), so the dot product must be zero — meaning the cross product vector is orthogonal to both.

**Important Points**
- This chapter is explicitly about the 'why' behind Chapter 10's formula — it reframes cross product from 'memorized computation' to 'a natural consequence of duality'.
- 3B1B flags this chapter as more optional/advanced — useful for real conceptual depth, but not strictly required to move forward in the series.
- This is a strong real-world example of duality in action: a geometric quantity (volume) and a vector (cross product) turn out to be two views of the same underlying linear structure.

</details>

---

<details>
<summary><strong>Chapter 12: Cramer's rule, explained geometrically</strong></summary>

**Key Takeaway**  
Cramer's Rule — the formula that solves Ax = v using ratios of determinants — has a clean geometric explanation: it's tracking how the area/volume of a transformed parallelogram/parallelepiped changes as you swap in the target vector v for one of the basis vectors.

**Definitions**

- **Cramer's Rule**  
  A formula for solving Ax = v (when A is invertible) using determinants: each coordinate of x = det(a modified version of A) / det(A).

- **Modified matrix**  
  To find coordinate x_i, replace the i-th column of A with the vector v, then take that new matrix's determinant.

**Visualization Intuition**
- Picture the unit square/cube of the input space (before transformation) with one side stretched by an unknown factor x — Cramer's Rule visualizes finding x by comparing the area/volume the transformation produces to the area/volume it would have produced from the original basis vectors.
- Swapping a column for v visualized: literally replace one edge of the parallelogram/parallelepiped with the target vector v, and see how the resulting area/volume compares to the original transformation's scaling (its determinant).
- The ratio of the two areas/volumes IS the unknown coordinate — because area/volume scales linearly and predictably under a linear transformation.

**Important Points**
- Cramer's Rule is elegant conceptually but computationally inefficient for large systems — 3B1B notes Gaussian elimination is faster in practice for solving Ax=v numerically.
- This chapter is a direct payoff of understanding determinants (Ch. 6) and linear systems (Ch. 7) geometrically, rather than a new independent idea.
- The formula only works when det(A) is non-zero — same invertibility condition from Chapter 7.

</details>

---

<details>
<summary><strong>Chapter 13: Change of basis</strong></summary>

**Key Takeaway**  
Coordinates always depend on a choice of basis vectors — 'change of basis' is the process of translating vector coordinates between two different coordinate systems, using a matrix built from one system's basis vectors expressed in the other system's language.

**Definitions**

- **Change-of-basis matrix**  
  A matrix whose columns are a new basis's vectors, expressed in your standard (i-hat, j-hat) coordinates — used to translate coordinates FROM the new system TO the standard system.

- **Translating coordinates in**  
  Multiplying the change-of-basis matrix by a vector's coordinates in the new system converts them into standard coordinates.

- **Translating coordinates out**  
  Multiplying by the INVERSE of the change-of-basis matrix converts standard coordinates back into the new system's coordinates.

**Visualization Intuition**
- Picture two people looking at the exact same arrow in space, but using different grids (different basis vectors) to describe it — they'll write down different coordinate numbers for the identical physical vector.
- The change-of-basis matrix is a translator: picture literally overlaying the new person's grid onto your own standard grid — their basis vectors, redrawn using your axes, become the matrix's columns.
- To apply a transformation described in another basis to your own coordinates: translate your vector INTO their system (multiply by the matrix), apply the transformation there, then translate back OUT (multiply by the inverse) — a 'translate, act, translate back' sandwich.

**Important Points**
- There's no single 'correct' basis — i-hat/j-hat are just one convenient, standard choice; any linearly independent set works as a coordinate system.
- This chapter reframes every prior chapter's matrix examples as being written in the 'standard basis' all along — change of basis reveals that assumption.
- This sets up eigenvectors/eigenbases (a later chapter beyond this set) where choosing the RIGHT basis can make a transformation's matrix radically simpler (e.g. diagonal).

</details>