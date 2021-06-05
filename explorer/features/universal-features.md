# Universal Features



mention diff exp, mention that hosted has 50,000 cell limit



### Cross-filter cells and color by metadata

Categorical metadata can be used not only to color cells in the embedding scatterplot, but also to examine the representation of a particular metadata across other metadata fields. In the example below, check out how we can:

1. Select all the cells that have the value "marrow" in the tissue category
2. Subset these cells so that only they are displayed
3. Expand another metadata category \("subtissue"\) to reveal how cells from the marrow are distributed across different sub-tissues

![](../../.gitbook/assets/crossfilter.gif)

### Compare groups of cells with differential expression

Differential expression can be run between selections of two different groups of cells. In the media below, these steps are to:

1. Select cells for the first group \("B Cells"\)
2. Select cells for the second group \("granulocytes"\)
3. Click the differential expression icon \( ![](../../.gitbook/assets/image%20%282%29.png) \)
4. The top 10 differentially expressed features will appear on the right hand side-bar

![](../../.gitbook/assets/diffexp.gif)

Note: In the hosted explorer present on the cellxgene data portal, the differential expression feature has a limit of 50,000 cells \(i.e. the sum of the number of cells in group 1 and group 2 cannot exceed 50,000\). We are currently working on ways to scale this calculation in the hosted setting.

### See how metadata and gene expression break down across different categories

Cellxgene can give you information on how different categorical and continuous metadata are distributed within any metadata field on the left-hand sidebar. To accomplish this, one simply needs to:

1. Color the cells by a desired categorical or continuous metadata field.
2. Expand another categorical metadata field to examine either the cross-occupancy \(categorical metadata\) or distribution \(continuous metadata\) within that newly expanded field.

![](../../.gitbook/assets/category-breakdown.gif)

One could imagine using this feature in a scenario where it is expected that certain cell types are only present in a particular disease state for instance.





