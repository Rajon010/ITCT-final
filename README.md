# ITCT-final
* python3 is used
## Tasks for Huang (flexible)
* Math
  * PCA (refer to sklearn): How does it work?
  * Kernel PCA (refer to sklearn): How does it work?	What kind (positive semi-definite?) of similarity matrix is required?
  * Jensen-Shannon divergence: check the following properties (by online metarials or papers or something else).
    * Its square root is a metric. Well, this is already proven in the paper, so you can use it directly.
    * Its lower bound: I've already proved that JSD(P1, P2, ..., Pn) >= 0, and the equality holds iff all Pi with alpha_i != 0 are identical. So you can directly use this in your slides. This makes the iterative rotation algorithm reasonable.
    * Its upper bound: I've already proved that JSD(P1, P2, ..., Pn) <= ln(dim(P)).
  * Affinity propagation (refer to sklearn): How does it work? What kind (positive semi-definite?) of similarity matrix is required if affinity='precomputed'.
    * No need to specity the number of clusters.
  * Hope we can find online or prove that the two ways listed in the website "http://scikit-learn.org/stable/modules/metrics.html" can convert a distance metric to a similarity measure, which can produce the positive semi-definite similarity matrix (if positive semi-definiteness required by kernel PCA and affinity propagation). Then put all the above together to conclude that similarity matrix based on JSD is reasonable.
  * Rand Index and Adjust Rand Index. See http://scikit-learn.org/stable/modules/clustering.html#adjusted-rand-score
* The iterative rotation algorithm to minimize JSD(P1, P2, ..., Pn). I've already finished this. You don't need to include this in your slides.
``` python
  * while not converge
    * for each i
      * r_i = argmin_(r_i) JSD(r_1(P1), r_1(P2), ..., r_1(Pn))
      # r stands for "rotation"
```
* Draw images:
  * 希望是色塊而不是漸層
    * 色塊例如 https://www.researchgate.net/figure/257129126_fig2_Fig-4-Triangle-plot-of-uncertainty-showing-a-U-1-p-max-and-b-entropy-H-of-pixel
  * Tool: https://github.com/marcharper/python-ternary or http://freakonometrics.hypotheses.org/18971 or else
  * Five triangles
    * Entropy. Looks like https://github.com/marcharper/python-ternary/blob/master/readme_images/heatmap_shannon.png
    * L1 norm. Looks like http://constantinequilts.com.au/wp-content/uploads/2014/12/Nested-hexagons.jpg
    * L2 norm. Looks like https://f.hypotheses.org/wp-content/blogs.dir/253/files/2015/01/ENTROPY2-KOLM.png
    * L-Infinity norm.
    * Nested triangles. Looks like https://i.stack.imgur.com/wFtg2.png
    * It will be interesting to try to draw L3, L4, ...
