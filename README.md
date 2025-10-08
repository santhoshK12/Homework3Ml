# Homework3Ml
====================================================================
CS5710 – MACHINE LEARNING
HOMEWORK 3 – COMPLETE EXPLANATION README
====================================================================

Student Name: SANTHOSH REDDY KISTIPATI
University of Central Missouri
Department of Computer Science & Cybersecurity
Easily accuss the pdf : https://github.com/santhoshK12/Homework3Ml/tree/main
====================================================================

This README explains all the questions from both Part A (Computations)
and Part B (Conceptual Short Answers). Each question includes clear 
descriptions of methods, reasoning, and interpretation.

====================================================================
PART A – CALCULATION AND EXPLANATION
====================================================================

--------------------------------------------------------------------
Q1. MULTI-INPUT FEEDFORWARD NETWORK
--------------------------------------------------------------------
Given: x1 = 2, x2 = 1, x3 = 3
Weights:
A = [[0.2, -0.5], [0.1, 0.3], [-0.2, 0.8], [0.4, -0.6]]
B = [0.7, -1.2, 0.5]

Explanation:
This network has three inputs plus a bias term. The first layer computes
z = Aᵀx, applies a sigmoid activation to produce hidden activations, and 
then the output layer combines them using another sigmoid.

Result:
Hidden pre-activations: z = [0.3, 1.1]
Hidden activations: h = [0.5744, 0.7503]
Final output: y = 0.5004

Concept:
This demonstrates how weighted sums and nonlinear activations combine 
to produce nonlinear decision boundaries even in small networks.

--------------------------------------------------------------------
Q2. XOR WITH RELU NETWORK
--------------------------------------------------------------------
Equations:
h1 = ReLU(x1 + x2)
h2 = ReLU(x1 + x2 - 1)
h3 = ReLU(2x1 - x2)
y  = ReLU(h1 - 2h2 + h3)

Computed Outputs:
(0,0) → y = 0
(0,1) → y = 1
(1,0) → y = 3
(1,1) → y = 1

Explanation:
The additional hidden unit introduces a new linear region, changing
the decision boundary compared to the original XOR network.
The new line (2x1 = x2) modifies separability and breaks the exact XOR
mapping because input (1,1) now outputs 1 instead of 0.

Concept:
Adding hidden units can expand capacity but also change learned logic
if not carefully trained.

--------------------------------------------------------------------
Q3. PERCEPTRON DECISION BOUNDARY
--------------------------------------------------------------------
Weights: w1 = 1, w2 = -2, b = 1
Decision function: ŷ = 1 if (w·x + b) > 0

Boundary equation:
x1 - 2x2 + 1 = 0  →  x1 = 2x2 - 1

Classification Results:
(2,1): Correct
(1,3): Correct
(3,2): Incorrect
(0,1): Correct

Perceptron loss = 1 (one misclassification)

Concept:
The perceptron separates data linearly. Any overlap or nonlinearity
cannot be corrected since it lacks a margin-based optimization.

--------------------------------------------------------------------
Q4. TWO-HIDDEN-LAYER NETWORK
--------------------------------------------------------------------
Input: (x1, x2) = (2, 3)

Layer 1 weights: [[0.2, -0.3], [0.4, 0.1], [0.5, -0.6]]
Layer 2 weights: [[0.7, -0.5], [-0.2, 0.3], [0.1, 0.4]]
Output weights: [1.0, -1.2, 0.3]

Results:
Layer 1 → z1 = [2.1, -0.9], h1 = [0.8909, 0.2891]
Layer 2 → z2 = [0.6658, 0.0413], h2 = [0.6606, 0.5103]
Final output → y = 0.5862

Concept:
Multiple layers allow nonlinear transformations to build complex
functions by stacking simple units.

--------------------------------------------------------------------
Q5. LINEAR SVM
--------------------------------------------------------------------
Data:
Positive points: (1,3), (2,2)
Negative point: (0,0)

Result of margin equations:
w = (0.5, 0.5)
b = -1
Equation: x1 + x2 = 2

Verification:
All support vectors satisfy y_i*(w·x_i + b) = 1

Extras:
Margin (1/||w||) = √2 ≈ 1.414
Decision function: f(x) = 0.5x1 + 0.5x2 - 1

Concept:
The linear SVM maximizes the margin between classes, ensuring robustness
and clear separation. Support vectors are the only points defining the
decision boundary.

--------------------------------------------------------------------
Q6. NONLINEAR SVM
--------------------------------------------------------------------
Support vectors:
s1 = (1, 0), y = -1
s2 = (0, 1), y = +1

Feature transformation:
Φ(x) = (x1, x2) for small inputs (radius ≤ 2)

Result:
w = (-1, 1)
b = 0
Hyperplane: x1 = x2
Decision function: f(x) = -x1 + x2

Classification:
For q = (1,1), f(q) = 0 → on boundary

Concept:
Even under nonlinear mappings, the margin principle applies. SVMs
remain interpretable by optimizing margin geometry in transformed spaces.

====================================================================
PART B – SHORT ANSWER EXPLANATIONS
====================================================================

--------------------------------------------------------------------
Q1. FROM BIOLOGICAL TO ARTIFICIAL
--------------------------------------------------------------------
(a) A neuron in biology transmits electrical impulses; in neural networks
it processes weighted inputs through an activation function.
A synapse in biology connects neurons chemically; in NNs it represents
a weighted link.
The activation function determines whether a neuron fires (bio) or
introduces nonlinearity (artificial).

(b) Nonlinearity allows networks to model complex relationships and
prevents them from reducing to a single linear transformation.

(c) A directed acyclic graph structure ensures information flows forward
without feedback loops, keeping computation stable.

--------------------------------------------------------------------
Q2. ARCHITECTURE & CAPACITY
--------------------------------------------------------------------
(a) Depth = number of layers; Width = number of neurons per layer.
(b) Hidden units may perform feature selection or projection.
(c) If D < M, the model expands feature space for better separability but
can overfit. If D > M, it compresses data for efficiency but may lose
information.
(d) The universal approximation theorem states that a single hidden
layer can approximate any continuous function on bounded input space.

--------------------------------------------------------------------
Q3. PERCEPTRON VS. SVM
--------------------------------------------------------------------
(a) The perceptron minimizes classification errors by adjusting weights.
(b) The SVM maximizes the margin between classes while minimizing errors.
(c) SVMs generalize better due to the margin principle. For example, in
spam filtering, SVMs handle noisy, overlapping text data more reliably
than perceptrons.

--------------------------------------------------------------------
Q4. MARGINS AND SUPPORT VECTORS
--------------------------------------------------------------------
(a) The margin is the distance between the separating hyperplane and the
nearest data points.
(b) Support vectors are those nearest points that determine the hyperplane.
(c) A larger margin increases tolerance to noise, leading to robust
generalization.

--------------------------------------------------------------------
Q5. PCA CONCEPTS
--------------------------------------------------------------------
(a) PCA assumes data varies most along certain key directions.
(b) PCA can be defined as (1) the projection maximizing variance, or (2)
the orthogonal transformation that diagonalizes the covariance matrix.
(c) Data must be centered to ensure components capture variance instead
of mean shift.
(d) The eigenvalue of each principal component equals the variance
explained by that component.

--------------------------------------------------------------------
Q6. PCA VS. RANDOM PROJECTION
--------------------------------------------------------------------
(a) PCA chooses projection directions based on maximum variance; random
projection selects random directions without data awareness.
(b) PCA’s advantage: preserves information and interpretable structure.
    Disadvantage: computationally expensive and sensitive to scaling.
    Random projection: faster but less precise.

====================================================================
END OF README
====================================================================

