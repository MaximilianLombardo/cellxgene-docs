---
description: An explanation of publishing and data submission to the cellxgene data portal
---

# Submitting and Publishing Data

## Data submission overview

{% hint style="info" %}
We are currently alpha testing the publishing portal and are not accepting submissions publicly at this time. However, if you have a dataset and are interested in helping us test upload and other portal features please reach out to [cellxgene@chanzuckerberg.com](mailto:cellxgene@chanzuckerberg.com) and we'll be happy to discuss whether your dataset is something that we can accept at this time.
{% endhint %}

The [cellxgene data portal](https://cellxgene.cziscience.com/) provides access to a standardized data corpus that removes the friction of finding and reusing single cell datasets. Each dataset uploaded to cellxgene adheres to a minimal schema which captures key information about the dataset and its observations \(i.e. cells\). These metadata are used by the Data Portal to provide advanced searching of datasets at the cellular level, and facilitate easy combination and integration of downloaded data.

If you wish to contribute your data to the portal then your data must be submitted as an AnnData object that adheres to [the single-cell annotated data schema](https://github.com/chanzuckerberg/single-cell-curation/blob/main/schema/2.0.0/corpora_schema.md). 

1. Format data into an `AnnData` object which meets cellxgene [data format requirements](../desktop/data-reqs.md)
2. Use the cellxgene curation tools and a specified config file to apply schema information to your AnnData object \(alternatively, you can perform this process manually, by adding new fields to the appropriate locations in the `AnnData` object\)
3. Use the cellxgene curation tools to validate that your curated object meets the cellxgene schema requirements
4. Upload to dropbox and then to the data portal.
5. Hit publish to make your dataset publicly available \(when you are ready\)!

It is important to note that the schema is applied in an additive way, meaning that none of the original information in your object will be overwritten or changed. In general, datasets that are displayed on the portal are meant to be represented as the authors originally intended, with no interpretation added by cellxgene or its team members.

If you have any further questions around data submission and requirements, feel free to [reach out](mailto:cellxgene@chanzuckerberg.com)!

