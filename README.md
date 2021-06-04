---
description: An overview of the cellxgene product family
---

# Overview

![](.gitbook/assets/cellxgene_logo.svg)

Cellxgene is a collection of computational tools enabling the exploration, analysis, and reuse of single cell data. The cellxgene ecosystem is currently composed of the [cellxgene data portal](https://cellxgene.cziscience.com/) \(which includes the hosted cellxgene explorer\) and the [cellxgene desktop explorer](https://github.com/chanzuckerberg/cellxgene). 

The cellxgene data portal is a place where you can search and download publicly available single cell datasets. Each dataset that is hosted on the cellxgene data portal is accompanied by a hosted instance of the cellxgene explorer, enabling frictionless visualization, exploration, and basic analysis of single cell data. To serve use cases where it is not possible to submit your data to our portal, cellxgene is also available as a "desktop" explorer which can be used locally or in a self hosted setup. For further reference, here is a brief rundown of potential use cases and which member of the cellxgene product family they would best served by:

* use case 1
  * product 1
* use case 2
  * product 2
* etc...
  * etc...

Since there are two versions of the cellxgene explorer, here is a brief rundown of the features in cellxgene explorer, along with the notable differences between the hosted and desktop versions:

* Coloring by categorial meta \(i.e. cell type, batch, treatment group, donor origin...\) and continuous metadata \(i.e. gene expression, QC metadata, prediction scores...\)
* Value clipping when coloring by continuous metadata \(when outliers distort the color scale\)
* Cell selection based on categorical metadata, numeric selection based on continuous metadata via range selection, or manual selection via lasso tool.
* Breakdown of specific categorical metadata fields \(i.e. tissue\) by any other categorical metadata field \(i.e. cell type\)
* Embedding display and support for multiple embeddings \(umap, tSNE, PCA, pseudotime...\)
* Recalculate embeddings: **Desktop Explorer Only**
* Custom cell type annotations: **Desktop Explorer Only**

### Quick Links

For more information regarding the cellxgene data portal and data contribution, please check out the [corresponding section](portal/hosted-intro.md) in this documentation. If you are interested in learning more about the capabilities of the cellxgene explorer, you can refer to [this section](explorer/explorer-intro.md). Finally if your use case demands it, you can check out information that is relevant to using [cellxgene desktop](desktop/desktop-intro.md).

Additionally, here are some important links for resources that exist outside of this documentation site:

* [cellxgene data portal](https://cellxgene.cziscience.com/)
* [cellxgene github repo](https://github.com/chanzuckerberg/cellxgene)
* ...









