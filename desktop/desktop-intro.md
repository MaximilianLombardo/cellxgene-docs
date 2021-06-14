# Intro to Desktop Explorer

{% hint style="info" %}
Cellxgene desktop explorer will be maintained, but no longer actively developed by the cellxgene team
{% endhint %}

Cellxgene desktop explorer is a tool in the cellxgene suite that should be used for basic analysis and exploration of your data. The use cases that are covered in this category are:

* When you need to work with other team members to make **collaborative annotations** of your dataset
* Performing **early data exploration** 
* **Rapidly iterating on analysis** of a dataset \(i.e. renormalizing, etc...\)

You can also use the cellxgene desktop explorer in [self-hosted](https://en.wikipedia.org/wiki/Self-hosting_%28web_services%29) manner to allow close collaborators to view data in scenarios where it cannot be submitted to a third-party \(CZI\).

For use cases like dissemination of your data to a broader audience \(i.e. sharing publication data\) or viewing other people's published datasets, you should use the [cellxgene data portal](../portal/hosted-intro.md) and [hosted explorer](../explorer/feature-overview/universal-features.md) to fulfill those needs.

 The cellxgene desktop explorer is launched via the command line with a reference to the local path of a properly formatted `AnnData` object. The desktop version of the cellxgene explorer can be [distinguished](../explorer/feature-overview/desktop-features/) from the hosted explorer by its ability to annotate cell types and recompute a new embedding based on a selection of cells. For a more complete feature description and descriptions of how to execute them in cellxgene, refer to our [explorer documentation](../explorer/feature-overview/). Otherwise, continue onto the next section to start demoing the desktop explorer.

