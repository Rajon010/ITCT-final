# ITCT-final
## tasks for Huang (flexible)
* math
  * PCA (refer to sklearn): how it works
  * kernel PCA (refer to sklearn): how it works?	what kind (positive semi-definite?) of similarity matrix is required
  * Jensen-Shannon divergence: justify the following properties (by online metarials or papers or something else)
    * its square root is a metric
    * its lower bound: my guess is that JSD(P1, P2, ..., Pn) >= 0, and the equality holds iff all Pi with alpha_i != 0 are identical. I hope we can either find online or prove this property inorder to supports the iterative rotation algorithm
  * affinity propagation (refer to sklearn): how it works? what kind (positive semi-definite?) of similarity matrix if required is affinity='precomputed'
  * hope we can find online or prove that the two ways listed in the website "http://scikit-learn.org/stable/modules/metrics.html" can convert a distance metric to a similarity measure, which can produce the positive semi-definite similarity matrix (if positive semi-definiteness required by kernel PCA and affinity propagation). Then put all the above together to conclude that similarity matrix based on JSD is reasonable
* the iterative rotation algorithm to minimize JSD(P1, P2, ..., Pn)
```
  * while not converge
    * for each i
      * rotation[i] = argmin_(r_i) JSD(r_1(P1), r_1(P2), ..., r_1(Pn))
```
* draw images:
  * 希望是色塊而不是漸層
    * 色塊例如 https://www.researchgate.net/figure/257129126_fig2_Fig-4-Triangle-plot-of-uncertainty-showing-a-U-1-p-max-and-b-entropy-H-of-pixel
  * tool: https://github.com/marcharper/python-ternary
  * four triangles
    * entropy
    * L1 norm
    * L2 norm
    * nested triangles
