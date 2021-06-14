# Overview

![](.gitbook/assets/cellxgene_logo.svg)

Cellxgene is a collection of computational tools enabling the exploration, analysis, and reuse of single cell data. The cellxgene ecosystem is currently composed of the [cellxgene data portal](https://cellxgene.cziscience.com/) \(which includes the hosted cellxgene explorer\) and the [cellxgene desktop explorer](https://github.com/chanzuckerberg/cellxgene). 

![cellxgene explorer](.gitbook/assets/image%20%281%29.png)

The cellxgene data portal is a place where you can search and download publicly available single cell datasets. Each dataset that is hosted on the cellxgene data portal is accompanied by a hosted instance of the cellxgene explorer; enabling frictionless visualization, exploration, and basic analysis of single cell data \(with the capability to handle datasets with millions of cells\). To serve use cases where it is not possible to submit your data to our portal, cellxgene is also available as a "desktop" explorer which can be used locally or in a self-hosted setup \([documentation on self-hosting](desktop/self-hosting/)\). In most cases, using the hosted explorer is preferred and sufficient. However, there are a select few scenarios where it may be preferable to use desktop explorer \(see [use cases](./#use-cases) below\) 

![cellxgene data portal](.gitbook/assets/image%20%288%29.png)

### Use Cases

As a web based data platform, the **cellxgene data portal** and **hosted explorer** system serve the following use cases around data sharing and consumption:

* Disseminating self-authored single cell publication data
* Finding publicly available relevant single cell datasets and running comparisons between them
* Quickly visualizing single cell publication data of other authors
* Single cell data reuse \(i.e. integration or benchmarking\)

The **desktop explorer** serves a different set of use cases. Namely:

*  Annotation and re-analysis of single cell datasets
* Collaboration and iteration of analysis on a dataset
* Setting up a closed self-hosted system for high sensitivity data

### **Explorer Features**

To get a sense of the capabilities of the cellxgene explorers, here is a rundown of their features, along with the notable differences between the hosted and desktop versions. To learn more about the cellxgene explorers, take a look at our [explorer documentation](explorer/feature-overview/).

|  |                  Hosted |                  Desktop |
| :--- | :--- | :--- |
|  |                                                              |                                                              |
| Display embeddings |                     ![](.gitbook/assets/google_material_design_check.svg.png)  |                       ![](.gitbook/assets/google_material_design_check.svg.png)  |
| [Color cells by categorical \(i.e. cell type\) and continuous metadata \(i.e. gene expression\)](explorer/feature-overview/universal-features.md#find-cells-where-a-gene-is-expressed) |                     ![](.gitbook/assets/google_material_design_check.svg.png)  |                       ![](.gitbook/assets/google_material_design_check.svg.png)  |
| Clip outlier values when plotting  continuous data |                     ![](.gitbook/assets/google_material_design_check.svg.png)  |                       ![](.gitbook/assets/google_material_design_check.svg.png)  |
| Select groups of cells via categorical and numeric metadata gates or manual lasso selection |                     ![](.gitbook/assets/google_material_design_check.svg.png)  |                       ![](.gitbook/assets/google_material_design_check.svg.png)  |
| [Run differential expression](explorer/feature-overview/universal-features.md#compare-groups-of-cells-with-differential-expression) |                     ![](.gitbook/assets/google_material_design_check.svg.png)  |                       ![](.gitbook/assets/google_material_design_check.svg.png)  |
| [Categorical metadata co-occurrence and within category continuous feature distributions](explorer/feature-overview/universal-features.md#see-how-metadata-and-gene-expression-break-down-across-different-categories) |                     ![](.gitbook/assets/google_material_design_check.svg.png)  |                       ![](.gitbook/assets/google_material_design_check.svg.png)  |
| [Recalculate embedding](explorer/feature-overview/desktop-features/#recompute-embedding) |                        - |                       ![](.gitbook/assets/google_material_design_check.svg.png)  |
| [Custom annotations](explorer/feature-overview/desktop-features/annotations.md) |                        - |                       ![](.gitbook/assets/google_material_design_check.svg.png)  |

### Quick Links

If you are ready and raring to see what cellxgene is capable of, you can:

* jump right into a [hosted cellxgene explorer instance](https://cellxgene.cziscience.com/e/human_cell_landscape.cxg/) and start exploring
* find out more about the cellxgene data portal and data contribution in the [corresponding section](portal/hosted-intro.md) of this documentation
* read about how to use the cellxgene explorer via the [explorer documentation](explorer/feature-overview/)
* or if your use case demands it, you can check out information that is relevant to using [cellxgene desktop](desktop/desktop-intro.md).

Additionally, here are some important links for resources that exist outside of this documentation site:

* [cellxgene data portal](https://cellxgene.cziscience.com/)
* [cellxgene github repo](https://github.com/chanzuckerberg/cellxgene)

