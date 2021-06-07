---
description: >-
  An explanation of publishing and data submission to the cellxgene data
  explorer (Should we make this a sub heading of the introduction?)
---

# Publishing

### Data submission overview

One of the main draws of the [cellxgene data portal](https://cellxgene.cziscience.com/) is a standardized data corpus that removes the friction of finding and reusing single cell datasets that are relevant to your research. Standardization of a single cell dataset occurs via the application of a standardized data schema which captures key metadata about the dataset and observations \(i.e. cells\) within the dataset. These metadata are used within our database to provide advanced searching of datasets at the cellular level.

If you wish to contribute your data to the portal \(and have it be discoverable and integrable\), then your data must be curated according to our schema. To get an overview of the curation process, you can refer to the following [tutorial](https://github.com/chanzuckerberg/single-cell-curation/blob/tutorial-prototype/docs/curation-proto-tut.md). For an in-depth look at how our data schema is defined, you can refer to this [document](https://github.com/chanzuckerberg/single-cell-curation/blob/main/docs/corpora_schema.md). For a description of how schema information is encoded into your `AnnData` object,  you can refer to this [document](https://github.com/chanzuckerberg/single-cell-curation/blob/ambrosecarr/schema-v1.1.1/schema/1.1.1/anndata_encoding.md).

Briefly, the curation and publishing process looks like this:

1. Format data into an `AnnData` object which meets cellxgene [data format requirements](../desktop/data-reqs.md)
2. Use the cellxgene curation tools and a specified config file to apply schema information to your AnnData object \(alternatively, you can perform this process manually, by adding new fields to the appropriate locations in the `AnnData` object\)
3. Use the cellxgene curation tools to validate that your curated object meets the cellxgene schema requirements
4. Upload to dropbox and then to the data portal.
5. Hit publish to make your dataset publicly available \(when you are ready\)!

It is important to note that the schema is applied in an additive way, meaning that none of the original information in your object will be overwritten or changed. In general, datasets that are displayed on the portal are meant to be represented as the authors originally intended, with no interpretation added by cellxgene or its team members.

If you have any further questions around data submission and requirements, feel free to [reach out](mailto:cellxgene@chanzuckerberg.com)!



### Archive \(To Be deleted\)

~~Link to single-cell curation repo~~

~~link to curation tutorial~~

Explain the concept of publishing on cellxgene \(need help from Ambrose\)



~~~~

