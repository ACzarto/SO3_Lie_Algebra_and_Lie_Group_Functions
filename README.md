# SO3_Lie_Algebra_and_Lie_Group_Functions
This repository contains the main functions associated with the Lie algebra and Lie group, especially considering the $SO(3)$ group, the Special Orthogonal Group (Group of Orthogonal Matrices of dimension 3 with determinant equal to 1).

For the applications proposed in the thesis, the following maps will be used:

$$
\exp : \mathfrak{so}(3) \rightarrow SO(3)
$$

$$
Exp : \mathbb{R}^3 \rightarrow SO(3)
$$

$$
\log : SO(3) \rightarrow \mathfrak{so}(3)
$$

$$
Log : SO(3) \rightarrow \mathbb{R}^3
$$

where:
- $\exp$ denotes the matrix exponential map from the Lie algebra $\mathfrak{so}(3)$ to the Lie group $SO(3)$;
- $Exp$ denotes the exponential map in vector (axis-angle) representation;
- $\log$ denotes the matrix logarithm map from $SO(3)$ to $\mathfrak{so}(3)$;
- $Log$ denotes the logarithm map in vector form (vee representation).

One of the challenges with this formulation is that the $SO(3)$ manifold is non-linear and compact, meaning that a straight linear combination of rotation matrices (the arithmetic mean) generally results in a matrix that violates the orthogonality constraint, $\mathbf{R}^T\mathbf{R} = \mathbf{I}$. Thus, instead of the traditional Euclidean mean, we require the definition of the Karcher mean:

$$\mathbf{\hat{R}} = \arg\min_{\mathbf{R} \in SO(3)} \sum_{i=1}^N \Vert \text{logm}(\mathbf{R}^T \mathbf{R}_i) \Vert^2_F$$

And in this case, we use the Frobenius norm of the matrix $||*||_F$.

Since there is no closed-form analytical solution to minimize this sum of squared geodesic distances, $\mathbf{\hat{R}}$ must be computed iteratively using a Riemmanian Gradient Descent algorithm on the manifold. 

The repository also contains other functions for calculating the covariance matrix in the presence of Lie group-valued states.

