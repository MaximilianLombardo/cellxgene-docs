# Overview

![](.gitbook/assets/cellxgene_logo.svg)

Cellxgene is a collection of computational tools enabling the exploration, analysis, and reuse of single cell data. The cellxgene ecosystem is currently composed of the [cellxgene data portal](https://cellxgene.cziscience.com/) \(which includes the hosted cellxgene explorer\) and the [cellxgene desktop explorer](https://github.com/chanzuckerberg/cellxgene). 

The cellxgene data portal is a place where you can search and download publicly available single cell datasets. Each dataset that is hosted on the cellxgene data portal is accompanied by a hosted instance of the cellxgene explorer; enabling frictionless visualization, exploration, and basic analysis of single cell data. To serve use cases where it is not possible to submit your data to our portal, cellxgene is also available as a "desktop" explorer which can be used locally or in a self-hosted setup \(to find out more about one might like to do this, see our [documentation on self-hosting](desktop/self-hosting/)\). In most cases, using the hosted explorer is preferred and sufficient. However, there are a select few scenarios where it may be preferable to use desktop explorer \(ex: needing to make use of the [desktop only features](explorer/feature-overview/desktop-features/)\)  For further reference, here is a brief rundown of potential use cases and which member of the cellxgene product family they would best served by:

|  |                  Hosted |                  Desktop |
| :--- | :--- | :--- |
|  |                                                              |                                                              |
| Display embeddings |                     ![](.gitbook/assets/google_material_design_check.svg.png)  |                       ![](.gitbook/assets/google_material_design_check.svg.png)  |
| [Color cells by categorical \(i.e. cell type\) and continuous metadata \(i.e. gene expression\)](explorer/feature-overview/universal-features.md#find-cells-where-a-gene-is-expressed) |                     ![](.gitbook/assets/google_material_design_check.svg.png)  |                       ![](.gitbook/assets/google_material_design_check.svg.png)  |
| Clip outlier values when plotting  continuous data |                     ![](.gitbook/assets/google_material_design_check.svg.png)  |                       ![](.gitbook/assets/google_material_design_check.svg.png)  |
| Select groups of cells via categorical and numeric metadata gates or manual  |                     ![](.gitbook/assets/google_material_design_check.svg.png)  |                       ![](.gitbook/assets/google_material_design_check.svg.png)  |
| [Run differential expression](explorer/feature-overview/universal-features.md#compare-groups-of-cells-with-differential-expression) |                     ![](.gitbook/assets/google_material_design_check.svg.png)  |                       ![](.gitbook/assets/google_material_design_check.svg.png)  |
| [Categorical metadata co-occurrence and within category continuous feature distributions](explorer/feature-overview/universal-features.md#see-how-metadata-and-gene-expression-break-down-across-different-categories) |                     ![](.gitbook/assets/google_material_design_check.svg.png)  |                       ![](.gitbook/assets/google_material_design_check.svg.png)  |
| [Recalculate embedding](explorer/feature-overview/desktop-features/#recompute-embedding) |                        - |                       ![](.gitbook/assets/google_material_design_check.svg.png)  |
| [Custom annotations](explorer/feature-overview/desktop-features/annotations.md) |                        - |                       ![](.gitbook/assets/google_material_design_check.svg.png)  |

To learn more about how to achieve these tasks in cellxgene, take a look at our [explorer documentation](explorer/feature-overview/).

### Quick Links

If you are ready and raring to see what cellxgene is capable of, you can:

* jump right into a [hosted cellxgene explorer instance](https://cellxgene.cziscience.com/e/human_cell_landscape.cxg/) and start exploring
* find out more about the cellxgene data portal and data contribution in the [corresponding section](portal/hosted-intro.md) of this documentation
* read about how to use the cellxgene explorer via the [explorer documentation](explorer/feature-overview/)
* or if your use case demands it, you can check out information that is relevant to using [cellxgene desktop](desktop/desktop-intro.md).

Additionally, here are some important links for resources that exist outside of this documentation site:

* [cellxgene data portal](https://cellxgene.cziscience.com/)
* [cellxgene github repo](https://github.com/chanzuckerberg/cellxgene)

### ARCHIVE \(DELETE\)

To get a sense of the capabilities of the cellxgene explorer, here is a rundown of its features, along with the notable differences between the hosted and desktop versions:

* Publishing single cell data
  * **hosted**
* Finding relevant single cell datasets and running comparisons between them
  * **hosted**
* Setting up a self-hosted system or making use of the [desktop only features](explorer/feature-overview/desktop-features/)
  * **desktop**
* Coloring by categorial meta \(i.e. cell type, batch, treatment group, donor origin...\) and continuous metadata \(i.e. gene expression, QC metadata, prediction scores...\)
* Value clipping when coloring by continuous metadata \(when outliers distort the color scale\)
* Cell selection based on categorical metadata, numeric selection based on continuous metadata via range selection, or manual selection via lasso tool.
* Run differential expression between custom selections of groups of cells
* Breakdown of specific categorical metadata fields \(i.e. tissue\) by any other categorical metadata field \(i.e. cell type\)
* Embedding display and support for multiple embeddings \(umap, tSNE, PCA, pseudotime...\)
* Recalculate embeddings: **Desktop Explorer Only**
* Custom cell type annotations: **Desktop Explorer Only**

