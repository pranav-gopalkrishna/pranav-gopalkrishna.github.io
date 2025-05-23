<head>
  <script>
    MathJax = {tex: {inlineMath: [['$', '$']]}};
  </script>
  <script id="MathJax-script" async
    src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-chtml.js">
  </script>
</head>

[<< Back to **Linear Algebra**](https://pranav-gopalkrishna.github.io/mathematics/linear-algebra)

**CONCEPTUAL MAP**

---

**NOTE**: `A~B` $\implies$ `A` with respect to `B`

- `V`: Vectors
    - `V.base`: General definition of vector and specific interpretations
        - Physics context (_relative change in position_)
        - Computer science and data science context (_ordered list of values_)
        - Mathematics, i.e. generalised context (_generalises all other contexts_)
        - Relation between geometric and numeric interpretations
    - `V.Op`: Vector operations and their meaning w.r.t. geometric interpretation<br> **NOTE**: _Full clarity of some topics requires understanding linear transformations_
        - Vector addition (_obtaining the resultant vector of a series of vector movements_)
        - Scalar product (_scaling a vector, i.e. changing its magnitude while maintaining direction_)
        - Vector product
        - Dot product and its meaning (_discussed later_)
        - Cross product and its meaning (_discussed later_)
    - `V.Sp`: Span of a set of vectors
    - `V.M`: Matrices as vectors of vectors
    - `V.VS`: Vector spaces
        - `V.VS.Dim`: Dimensions of a vector space (_in every interpretation, i.e. every context_)
        - `V.VS.B`: Basis of a vector space<br> **KEY POINT**: _Every vector of the vector space is a linear combination of the basis vectors_
        - `LT~V.VS`: Linear transformations as transformations of vector spaces
            - Representing a LT as a transformation of basis vectors<br> **KEY POINT**: _Every transformedd vector is a linear combination of the transformed basis vectors_
            - Reducing the dimensionality of a vector space through LT

Matrices are deeply tied to linear transformations, so always consider matrix-related topics in the context of LT...

- `M`: Matrices<br> _... extends from_ `V.M`
    - `M.base`: General definition of matrix and specific interpretations
    - `M.Op`: Matrix operations and their meaning w.r.t. vectors
        - Matrix addition (_ordered sequence of multiple vector additions_)
        - Scalar product (_ordered sequence of the scaling of multiple vectors_)
        - Matrix multiplication (_ordered sequence of linear combinations of multiple vectors_)
    - `LT~M`: Linear transformations as matrices
        - Representing a LT as a matrix
        - Linearly transforming a vector with matrix multiplication
        - Relating composition of functions to composition of LT's to composition of matrices<br> _Note that LT is a kind of function_
    - `M.Det`: Determinant
        - `M.Det~LT`: Determinant as a number related to a LT<br> _More specifically, it gives the scale and orientation of the LT_ <br> **NOTE**: _Scaling_ $\implies$ _Scaling of any subspace of the original space_
            - _Validating this representation of scale and orientation_
            - _What does zero determinant mean?_
        - Calculation and justification of the calculation method
        - Key results on determinants and their validation
            - $\det(A B) = \det(A) \det(B)$
    - `M.Inv`: Inverse of a matrix
        - `M.Det~LT`: Inverse of a matrix as inverse (i.e. reversal) of a LT<br> _LT is a function; think in terms of inverse of functions_
        - Relation between inverse and identity transformations
        - Relation between determinant and inverse
    - `M.SoE`: Systems of equations as matrices
        - `M.SoE~LT`: SoE as finding the preimage of a vector w.r.t. a LT<br> _Looking for the vector(s) that is mapped by the LT to the given vector_
        - Zero determinant and possible solutions given coefficient <br> _Connect with LT_
        - Specifying zero determinant cases using _rank_ <br> _Connect with LT_
        - Obtaining the solution of a SoE using the inverse of the coefficient matrix

Generalising linear transformation topics...

- `LT`: Linear transformation (general concepts)<br> **NOTE**: _We shall take for granted that LT's are represented as matrices_
    - **REFERENCE FOR INTUITION**: [Inverse matrices, column space and null space \| Chapter 7, Essence of linear algebra](https://www.youtube.com/watch?v=uQhTuRlWMxw)
    - `LT.base`: Basics
        - LT as a function defined on a vector space
        - Representing LT as a transformation of the basis vectors
        - Representing LT as a matrix (_directly related to the above_)
    - `LT.Rank`: Rank of a matrix a.k.a. rank of a LT
    - `LT.CS`: Column space of a matrix<br> _Essentially, the span of the transformed basis vectors, i.e. the columns_
        - `LT.Rank~LT.CS`: _Rank is the number of dimensions in the column space_
        - "Full rank" matrix $\implies$ Rank equals the number of columns $\implies$ Maximum dimensions for the column space
    - `LT.DimRed`: Dimensionality reduction of vector space with LT
    - `LT.NS`: Nullspace of a matrix a.k.a. nullspace of a LT<br> _... related to_ `LT.DimRed`
        - _The set of vectors that get mapped by the LT to a null vector, i.e. the origin_
        - `LT.NS~M.SoE`: _The set of all solution to a homogenous system of equations represented by the matrix_
