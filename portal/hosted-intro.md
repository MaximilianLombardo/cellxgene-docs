# Introduction

## Features & Functionality

The [cellxgene data portal](https://cellxgene.cziscience.com/) is a single cell publishing platform that is optimized for the access, exploration, and reuse of single cell data. In addition to providing a [standardized data corpus](https://github.com/chanzuckerberg/single-cell-curation/blob/main/docs/corpora_schema.md), the cellxgene data portal serves the following use cases:

* **Citation:** the portal provides permanent publication links that can be cited in your paper or preprint \(no more dead links!\)
* **Private Collaboration:** sharing of private datasets with collaborators via private links \(keep the data private until it is ready for publication\)
  * private links are identified with a "private" flag which is appended to the end of the link
* **Instant Data Exploration:** no barrier for readers to explore your dataset \(readers can plot gene expression in a published dataset and more without the need for you to build your own single cell data explorer\)

![Instant Data Exploration](../.gitbook/assets/image%20%2817%29.png)

* **Data Reuse:** availability of datasets for download in the major single cell data formats \(this allows you or your computational collaborators to get access to publication data in formats that will easily slot into your preferred single cell analysis toolchain including `AnnData`, `seurat`, and `loom`\)

![Data Reuse](../.gitbook/assets/image%20%2822%29.png)

As we develop the functionality of our data portal, you can look forward to being able to compare expression of genes across datasets and perform basic data integration. In the meantime, you can find out how to explore data using the hosted explorer by referring to our [section on explorer features](../explorer/feature-overview.md)!

We will proceed to talk about the organization of the data portal in our [next section](data-portal.md), but if you are interested in more information on our data standardization process and how to submit data to the portal, you can refer to our section on [publishing](publishing.md)!

## History

The platform itself evolved from a cellxgene based system \(the [COVID-19 data portal\)](https://www.covid19cellatlas.org/) that was developed to host single cell datasets related to COVD-19 in the face of the 2020 global pandemic. Since then, the cellxgene team has reacted to the need for a more generalized system that could increase access to single cell data and subsequently increase the velocity of biomedical research.

