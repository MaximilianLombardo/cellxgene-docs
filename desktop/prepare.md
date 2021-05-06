# Prepare

## Using `cellxgene prepare`

If your data is in a different format, and/or you still need to perform dimensionality reduction and/or clustering, `cellxgene` can do that for you with the `prepare` command.

### What is `cellxgene prepare`?

`cellxgene prepare` offers an easy command line interface \(CLI\) to preliminarily wrangle your data into the required format for previewing it with cellxgene. It runs `scanpy` under the hood and can read in any format that is currently supported by `scanpy` \(including mtx, loom, and more listed [in the scanpy documentation](https://scanpy.readthedocs.io/en/latest/api/index.html#reading)\).

`prepare` uses scanpy to:

* Handle simple data normalization \(from a [recipe](https://www.pydoc.io/pypi/scanpy-0.2.3/autoapi/preprocessing/recipes/index.html)\)
* Do basic preprocessing to run PCA and compute the neighbor graph
* Reduce dimensionality to generate embeddings
* Infer clusters

You can control which steps to run and their methods \(when applicable\), via the CLI. The CLI also includes options for computing QC metrics, enforcing matrix sparcity, specifying index names, and plotting output.

### What is cellxgene `prepare` _not_?

`cellxgene prepare` is not meant as a way to formally process or analyze your data. It's simply a utility for quickly wrangling your data into cellxgene-compatible format and computing a "vanilla" embedding so you can try out `cellxgene` and get a general sense of a dataset.

### Quickstart for `cellxgene prepare`

To add `cellxgene prepare` to your [cellxgene installation](https://github.com/chanzuckerberg/cellxgene/blob/main/docs/posts/install), run `pip install cellxgene[prepare]`

Then run `prepare` on your data with:

```text
cellxgene prepare dataset.h5ad --output=dataset-processed.h5ad
```

This will load the input data, perform PCA and nearest neighbor calculations, compute `UMAP` and `tSNE` embeddings and `louvain` cluster assignments, and save the results in a new file called `dataset-processed.h5ad` that can be loaded using `cellxgene launch`.

### Example usage

As a quick example, let's construct a command to use `prepare` to take a raw expression matrix and generate a processed `h5ad` ready to visualize with cellxgene.

We'll start off using the raw data from the pbmc3k dataset. This dataset is described [here](https://icb-scanpy.readthedocs-hosted.com/en/stable/api/scanpy.datasets.pbmc3k.html), and is available as part of the scanpy package. For this example, we'll assume this raw data is stored in a file called `pbmc3k-raw.h5ad`.

Our `prepare` command looks like this:

```text
cellxgene prepare pbmc3k-raw.h5ad \
	--run-qc \                                  # (A)
	--recipe seurat \                           # (B)
	--layout tsne --layout umap \               # (C)
	--output pbmc3k-prepared.h5ad               # (D)
```

Let's look at what `prepare` is doing to our data, and how each step relates to the command above. You can see a walkthrough of what's going on under the hood for this example in [this notebook](https://github.com/chanzuckerberg/cellxgene-vignettes/blob/master/dataset-processing/pbmc3k-prepare-example.ipynb).

**\(A\) - Compute quality control metrics and store this in our `AnnData` object for later inspection** **\(B\) - Normalize the expression matrix using a basic preprocessing recipe** **\(auto\) - Do some preprocessing to run PCA and compute the neighbor graph** **\(auto\) - Infer clusters with the Louvain algorithm and store these labels to visualize later** **\(C\) - Compute and store UMAP and tSNE embeddings** **\(D\) - Write results to file**

### Options for cellxgene `prepare`

**For the most up-to-date and comprehensive list of options, run `cellxgene prepare --help`**

`--embedding` controls which dimensionality reduction algorithm is applies to your data. Options are `umap` and/or `tsne`. Defaults to both.

`--recipe` controls which normalization steps to apply to your data, based on one of the preprocessing `recipes` included with `scanpy`. These recipes include steps like cell filtering and gene selection; see the `scanpy` [documentation](https://scanpy.readthedocs.io/en/latest/api/index.html#recipes) for more details. Options are `none`, `seurat`, or `zheng17`. Defaults to `none`.

`--sparse` is a flag determines whether to enforce a sparse matrix. For large datasets, `prepare` can take a long time to run \(a few minutes for datasets with 10-100k cells, up to an hour or more for datasets with &gt;100k cells\). If you want `prepare` to run faster we recommend using the `sparse` option. If this flag is not included, default is `False`

`--skip-qc` by default, `cellxgene prepare` will compute quality control metrics \(saved to `anndata.obs` and `anndata.var`\) as described in the `scanpy` [documentation](https://scanpy.readthedocs.io/en/stable/api/scanpy.pp.calculate_qc_metrics.html). Pass this flag if you would like to skip this step.

`--make-obs-names-unique` / `--make-var-names-unique` determine whether to rename `obs` \(cell\) / `var` \(gene\) names, respectively, to be unique. Default is `True`.

`--set-obs-names` controls which field in `anndata.obs` \(cell metadata\) is used as the _index_ for cells \(e.g., a cell ID column\). Default is `anndata.obs.names`

`--set-var-names` controls which field in `anndata.var` \(gene metadata\) is used as the _index_ for genes. Default is `anndata.var.names`

`--output` and `--overwrite` control where the processed data is saved.

