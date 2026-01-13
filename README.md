# Spectral Embeddings of Non-Linear Manifolds: A Graph Laplacian Framework

This project implements *Spectral Clustering from scratch* to demonstrate how the eigen-structure of a Graph Laplacian can be used to discover topological patterns in data that are not linearly separable. 

As a Mathematics major, I have focused this implementation on the *Spectral Graph Theory* foundations, specifically analyzing the *Fiedler Vector* and the *Spectral Gap* to achieve optimal graph partitioning.

## 🚀 The Challenge: Why Spectral?
Standard clustering algorithms like K-Means assume that clusters are convex (blobs). However, real-world data often lives on curved manifolds. In this project, I demonstrate that while K-Means fails on the "Two Moons" dataset, Spectral Clustering successfully recovers the underlying geometry.



## 🧠 Mathematical Framework
The algorithm follows a rigorous Linear Algebra pipeline:

1. *Similarity Matrix (W):* Constructed using a Gaussian Radial Basis Function (RBF) kernel:
   $$W_{ij} = \exp\left(-\frac{\|x_i - x_j\|^2}{2\sigma^2}\right)$$
2. *Degree Matrix (D):*  $D_{ii} = \sum_j W_{ij}$.
3. *Graph Laplacian (L):* Calculated as $L = D - W$. This operator represents the discrete version of the Laplace-Beltrami operator.
4. *Eigen-decomposition:* Solving $Lv = \lambda v$ to find the *Spectral Gap*.



## 📊 Key Results
### 1. The Spectral Gap
The plot of eigenvalues shows a distinct jump between $\lambda_1$ (which is 0) and $\lambda_2$. This "gap" is a signature of the number of connected components in the graph.

### 2. The Fiedler Vector
The second smallest eigenvector (The Fiedler Vector) provides the *Algebraic Connectivity*. By taking the sign of this vector, we achieve a continuous relaxation of the discrete Min-Cut problem.
