---
description: Desktop explorer's main unique features
---

# Desktop Features

### Unique Features

Cellxgene desktop explorer is differentiated from the hosted explorer by two significant features:

* Re-computing the UMAP embedding based on a selection of cells
* Collaborative annotation of cell type

### Recompute Embedding

The feature for recomputing an embedding based on a selection of cells is hidden behind a feature flag \(which is not featured in the help page for `cellxgene launch`\). To access this feature, run the following launch command \(the below code assumes you are running this command from the local directory where you `AnnData` object is located\):

```text
cellxgene launch pbmc3k.h5ad --experimental-enable-reembedding
```

You should get a terminal output which directs you to go to [http://localhost:5005](http://localhost:5005) in your browser \(if you have specified another port via `--port,` the output will direct to a different port\). When enter the cellxgene explorer you should see a cellxgene instance with an expanded tool bar:

![Expanded tool bar for computing re-embeddings](../../.gitbook/assets/image%20%2811%29.png)

Specifically, the re-embedding icon  \(![](../../.gitbook/assets/image%20%2818%29.png)\) will allow you to re-compute an embedding after a selection of cells has been made. The sequence of steps used to complete the workflow look like this:

1. Make a selection of cells \(manual, categorical, or numeric selection\)
2. After you have made your selection, click the subset cells icon \(![](../../.gitbook/assets/image%20%2815%29.png)\)
3. Click the  re-embedding icon \( ![](../../.gitbook/assets/image%20%2818%29.png) \)
4. The new embedding with the selected group of cells should now be displayed in the middle pane

### Annotations

The annotations feature is not hidden and is therefore active in the explorer with the base `launch` command. This feature allows for the addition of categorical annotations such as new sub-populations of cells after manually inspecting a dataset. The workflow behind annotations can support multiple use cases so we will save that discussion for the next section. The only thing to note here is to highlight the UI component that enables annotations in the desktop explorer:

![Annotations button](../../.gitbook/assets/image%20%2812%29.png)

