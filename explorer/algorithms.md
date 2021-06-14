---
description: >-
  A section describing implementation details around algos in cellxgene - an
  explanation of commonly used algorithms in single cell analysis
---

# Algorithms

### Differential expression

We're actively working on how to improve differential expression within the app. **N.B.: the** [**current implementation**](https://github.com/chanzuckerberg/cellxgene/blob/6f6634a4d9766a93596674fe42efbcae6ffabea6/backend/czi_hosted/compute/diffexp_generic.py#L42) **assumes normally distributed values on a linear scale.**

Currently, we use a [Welch's _t_-test](https://en.wikipedia.org/wiki/Welch%27s_t-test), which assumes that the two populations are each normally distributed, but may have unequal variance. We use a two-sided t-test against the null hypothesis that the two populations have **equal** means. P-values are adjusted with the [Bonferroni corrrection](https://en.wikipedia.org/wiki/Bonferroni_correction).

To help avoid spurious results, we use the log fold change to filter genes, retaining those where `|log2( mean(set1) / mean(set2) )| > 0.01`; this threshold can be configured with the [`--diffexp-lfc-cutoff`](../desktop/launch.md) command. We then sort genes by their associated `|t value|` and return the top 15 genes.

{% hint style="info" %}
**Note**: In the hosted explorer present on the cellxgene data portal, the differential expression feature has a limit of 50,000 cells \(i.e. the sum of the number of cells in group 1 and group 2 cannot exceed 50,000\). You can workaround this by only selecting subsamples of large clusters. We are currently working on ways to scale this calculation in the hosted setting.
{% endhint %}

