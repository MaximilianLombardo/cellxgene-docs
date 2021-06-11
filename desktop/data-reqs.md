---
description: How to format your data for use with cellxgene
---

# Data Format Requirements

Cellxgene requires that data be represented in `AnnData` format. This page describes the data format considerations that need to be met for visualization of a single cell dataset with the desktop explorer. The data format requirements for visualizing your data in the desktop explorer are a subset of the requirements that are defined for submitting your data to the data portal. For more details on how to format a dataset for submission to the data portal, please refer to the [publishing page](../portal/publishing.md) in this documentation.

## Data structure: _anndata_ fields used for visualization

### Matrix data

 Values from the data matrix to be visualized \(i.e. gene expression values in the case of scRNA-seq\) are pulled from `anndata.X`. These feed into the histograms, scatterplot, colorscale, and differential expression calculations. We're [working on ways](https://github.com/chanzuckerberg/cellxgene/issues/689) to incorporate `anndata.raw` and other `anndata.layers`!

### Metadata

Categorical \(e.g., cluster labels\) and continuous \(e.g., pseudotime\) metadata are pulled from `anndata.obs`. Any column added here will be available for visualization in cellxgene. You can also [create new categorical annotations](../explorer/feature-overview/desktop-features/annotations.md) within the application.

### Embeddings

cellxgene looks for embeddings \(e.g., tSNE, UMAP, PCA, spatial coordinates\) in `anndata.obsm`. These fields must follow the scanpy convention of starting with `X_`, e.g., `anndata.obsm['X_umap']`. If an embedding has more than two components, the first two will be used for visualization.

## Data format requirements

If your data is in `h5ad` file \(from the [`anndata`](https://anndata.readthedocs.io/en/latest/index.html) library\) and meets the following requirements, you can go straight to `cellxgene launch`:

* Matrix data \(i.e. raw or normalized expression values\) in `anndata.X`
* At least one embedding \(e.g., tSNE, UMAP\) in `anndata.obsm`, specified with the prefix `X_` \(e.g., by default scanpy stores UMAP coordinates in `anndata.obsm['X_umap']`\)
* A unique identifier is required for each cell, which by default will be pulled from the `obs` DataFrame index. If the index is not unique or does not contain the cell ID, an alternative column can be specified with `--obs-names`
* A unique identifier is required for each gene, which by default will be pulled from the `var` DataFrame index. If the index is not unique or does not contain the gene ID, an alternative column can be specified with `--var-names`

#### What about R objects from seurat / bioconductor!?

We hear you! We'd also love to be able to ingest these files directly. This isn't currently possible, but in the meantime, you can use [sceasy](https://bioconda.github.io/recipes/r-sceasy/README.html) \([docs](https://cellgeni.readthedocs.io/en/latest/visualisations.html)\) to convert to `h5ad`. Seurat also has some [handy conversion tools](https://satijalab.org/seurat/v3.0/conversion_vignette.html) that you can try out.

#### Can I use data hosted on the web somewhere?

Yes! You can launch from a URL instead of a filepath. The same data format requirements apply. Please see [here](https://github.com/chanzuckerberg/cellxgene/blob/main/docs/posts/launch) for more details.

## Data format options

#### Category colors

`cellxgene` will display [scanpy-style color information](https://github.com/chanzuckerberg/cellxgene/issues/1152#issue-564361541) for category-label pairs. An example of this format is shown below:

```text
>>> category = "louvain"
>>> # colors stored in adata.uns must be matplotlib-compatible color information
>>> adata.uns[f"{category}_colors"]
array(['#1f77b4', '#ff7f0e', '#2ca02c', '#d62728', '#9467bd', '#8c564b', '#e377c2', '#bcbd22'], dtype='>> # there must be a matching category in adata.obs
>>> category in adata.obs
True
```

To test that you've done this properly, check that for your given `category` the number of colors match the number of category values and that the second command below results in a mapping from categories to colors.

```text
>>> len(adata.obs[category].cat.categories) == len(adata.uns[f"{category}_colors"])
True
>>> dict(zip(adata.obs[category].cat.categories, adata.uns[f"{category}_colors"]))
{'CD4 T cells': '#1f77b4', 'CD14+ Monocytes': '#ff7f0e', 'B cells': '#2ca02c', 'CD8 T cells': '#d62728', 'NK cells': '#9467bd', 'FCGR3A+ Monocytes': '#8c564b', 'Dendritic cells': '#e377c2', 'Megakaryocytes': '#bcbd22'}
```

You can disable this feature using the `--disable-custom-colors` flag for `cellxgene launch`. cellxgene will then chose colors from its standard color palettes.



