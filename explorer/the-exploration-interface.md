---
description: Explaining the capabilities of the cellxgene's hosted and desktop explorers
---

# The Exploration Interface

## Feature Intro

Cellxgene explorer is the core tool which allows for real time interaction and exploration with a single cell data set. On our hosted system, this means that analysis of a hosted dataset is just a click away \(for the desktop explorer, setup is slightly more involved\). Features of the explorer allow for common operations on single cell datasets such as querying gene expression and performing selection based on metadata \(among other tasks\). All features in the hosted explorer are present in the desktop explorer in addition to two desktop only features: computing re-embedding and annotations. You will learn more about [general features](universal-features.md) and [desktop only features](desktop-features/) later in this section.

## User Interface

![](../.gitbook/assets/image%20%2819%29.png)

Cellxgene's user interface organizes single cell data similarly to how it is organized in commonly used single cell data formats. On the lefthand side, you can find information about categorical sample metadata \(observations\). The right hand sidebar contains information about continuous observational metadata and variable metadata \(i.e. expression\). Finally in the center, you can find the embedding scatterplot displaying the data.

![Cellxgene essential buttons](../.gitbook/assets/image%20%289%29.png)

Important icons and functionalities in cellxgene's user interface are displayed above. Here is a look at buttons and functionalities that are located in the toolbar.

![Cellxgene toolbar](../.gitbook/assets/image%20%2814%29.png)

The cellxgene toolbar buttons provide the following functionalities:

1. Subsets the cells based on current selection \(based on categorical, numerical, or manual\). Only active when a selection is active
2. Get the complete set of cells. Only active when a subset is currently active
3. Lasso selection of cells on the plot \(manual selection\)
4. Zoom and move embedding plot
5. When the cells are colored by a categorical metadata field, this button allows the display of values of in that field displayed over the appropriate group of cells \(i.e. when coloring by "cell type", cell type names are displayed over the medoid of the cluster\)
6. Clip outlier values \(used for plotting continuous metadata when color map is thrown off by outliers\)
7. Undo
8. Redo

Now that we have established a sense of the functionality in our UI, let's go ahead and see what types of operations can be performed with these tools.

