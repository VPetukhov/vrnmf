# vrnmf
Volume-regularized NMF.

Package implements a set of methods to perform non-negative matrix decomposition with minimum volume contraints. A general problem is to decompose a non-negative matrix <img src="https://render.githubusercontent.com/render/math?math=X_{nm}"> in a product of non-negative matrix <img src="https://render.githubusercontent.com/render/math?math=C_{nr}"> and matrix <img src="https://render.githubusercontent.com/render/math?math=D_{rm}"> of lower rank r: <img src="https://render.githubusercontent.com/render/math?math=X = C\cdot D">. In case of additional non-negativity constraint on matrix <img src="https://render.githubusercontent.com/render/math?math=D"> the problem is known as NMF. 

This problem, and NMF as a particualr case, is not identifiable in general case, meaning that there are potentially many different solutions that deliver the same decomposition quality. It makes interpretation of factorized matrices challenging and limits applications of NMF to instrumental dimensionality reduction. However, recent theoretical advances showed that the issue can be overcome under a relatively mild assumption on "spread" of column vectors of C known as sufficient spreading (SECOND MATRIX? CITES!). If matrix C is non-negative and have sufficiently spread column vectors than volume minimization of a matrix D delivers a correct and unique, up to a scale and permutation, solution (C, D). 

_AnhorFree_ approach enables efficient estimation of matrix C by reformulating the problem in covariance domain following by application of volume minimization criterion (CITES!). A short walkthrough can be found hereLINK.

A more general formulation of the problem that accounts for noise in matrix X, such that only approximately <img src="https://render.githubusercontent.com/render/math?math=X \approx CD">, is called volume-regularized NMF (_vrnmf_). To balance goodness of matrix approximation and matrix D volume, _vrnmf_ minimizes the following objective function (cites):

<img src="https://render.githubusercontent.com/render/math?math=F = \| X-CD \|_{F}^{2} %2B \lambda \cdot Vol(D)"> 

We provide implementation of _vrnmf_ approach and devise its reformulation in covariance domain. A detailed walkthrough is available hereLINK.

"...the **go to** statement should be abolished..." [[1]](#1).

TODO:
- links.
- citations.
- ADD VISUAL GEOMETRIC INTERPRETATION.

## Installation instructions

```{r setup}
install.packages("devtools")
devtools::install_github("kharchenkolab/vrnmf")
library(vrnmf)
```

## References
<a id="1">[1]</a> 
Dijkstra, E. W. (1968). 
Go to statement considered harmful. 
Communications of the ACM, 11(3), 147-148.

