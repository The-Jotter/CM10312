# Matrices, Permutations

$A = \begin{pmatrix}
    a_{11} & a_{12} & \dots  & a_{1m}\\
    a_{21} & a_{22} & \dots  & a_{2m}\\
    \vdots & \vdots & \ddots & \vdots\\
    a_{n1} & a_{n2} & \dots & a_{nm}  
\end{pmatrix}$

Where $a_{ij}$ is a general element in $A$.

For shorthand, we can also write $A$ like this: $A = \left\|a_{ij}\right\|$, where:
* $1\leq i \leq n$,
* $1\leq j \leq m$ 
for an $(n \times m)$ &mdash; matrix $A$.

We'll be considering the case of the case $n=m$ or matrices with dimensions $(n \times n)$, also known as *square matrices*.

## Determinants of Matrices
### A brief aside: Induction, and the Factorial
$n!$ can be written as $n! = 1 \cdot 2 \cdot \dots \cdot n$.

If we:
* define $0! = 1$ (a base case),
* and assuming factorial is defined for $(n-1)$,
* we can define $n! = n\cdot (n-1)!$

### Determinants of Matrices: by Induction
Where $A$ is an $(n \times n)$ matrix.
#### 1. Base case 
$\det A$, when a is in the form $\begin{pmatrix}
    a_{11}
\end{pmatrix}$ is, by definition, the element $a_{11}$ itself:
$\det\begin{pmatrix}
    a_{11}
\end{pmatrix} = a_{11}$
#### 2. Assumption
Assume the determinant of an $(n-1) \times (n-1)$ matrix is defined.

#### 3. Induction
**Notation:**
> Here, $A_{ij}$ will be defined as a submatrix, removing row $i$ and column $j$ from matrix $A$:
> For matrix $B = \begin{pmatrix}
    1 & 2\\
    3 & 4
\end{pmatrix}$, 
> 
> $B_{11} = \begin{pmatrix}\cancel{1} & \cancel{2}\\ \cancel{3} & 4\end{pmatrix} \rightarrow B_{11} = \begin{pmatrix}
    4
\end{pmatrix}$
>

**Proof:**

Chosoe any row $i$ of $A$:

$\det A = (-1)^{i+1}a_{i1}\det A_{i1} + (-1)^{i+2}a_{i2}\det A_{i2}\\+ \dots + (-1)^{i+j}a_{ij}\det A_{ij} + \dots (-1)^{i+n}a_{in}\det A_{in}$

It turns out that this works for any row $i$, but the convention is to use just the first row...

**Testing**:

Let $A = \begin{pmatrix}
    a_{11} & a_{12} \\
    a_{21} & a_{22}
\end{pmatrix}$

Using $i=1$, by our previous work, we should get:

$\det A = (-1)^{1+1} a_{11} \det A_{11} + (-1)^{1 + 2} a_{12} \det A_{12}\\ = a_{11} \det \begin{pmatrix}
    a_{22}
\end{pmatrix} + (-1) a_{12} \det \begin{pmatrix} a_{21}\end{pmatrix}\\
= a_{11} a_{22} - a_{12} a_{21}$

## Permutations

A permutation of the elements $1, 2, 3, \dots, n$ is another ordered collection of elements: $i_1, i_2, \dots, I_n$.

The number of all possible permutations of a collection $1, 2, \dots, n$ is $n!$.

### Inversions
Let $i_1, i_2, \dots, i_n$ be a permutation of $1, 2, \dots, n$.

An *inversion* in $i_1, i_2, \dots, i_n$ is a a pair $(i_k, i_l)$ of elements such that that both:
* $k < l$; and 
* $i_k > i_e$

**Example**:

For $1,2,3$:
* Inversion $1,2,3$ has no inversions.
* $2,3,1$ has two inversions $(2,1), (3,1)$

### Configuration
A *configuration* $C$ in matrix $A$ is a maximal set of elements in $A$ in different rows and different columns.

**Example**:
for any two $a_{ij}, a_{kl}$ in $C$:

* $i \neq j$; and
* $j \neq l$

Each configuration has $n$ elements.

#### How many different configurations
Since we can make an ordered collection of elements $a_{1j_{kl}}$