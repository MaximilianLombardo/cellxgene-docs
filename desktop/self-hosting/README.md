---
description: Hosting Advice and Recipes
---

# Self-Hosting

## Hosting cellxgene desktop on the web

Cellxgene desktop is intended to be used by researchers on their local machines. In scenarios where hosting on the web is essential for data sharing and dissemination, we strongly recommend to utilize the hosted explorer in the cellxgene data portal \(see [here for a more comprehensive definition of use cases](../../portal/hosted-intro.md) and [here for a rundown of hosted explorer features](../../explorer/feature-overview/universal-features.md)\). However, there are some scenarios where you may need to self-host the desktop version of cellxgene explorer. Here are some examples of scenarios where this type of setup would be advantageous:

* you need to share data with collaborators \(in a private or public manner\) and cannot submit your data to the portal because of controlled access to your data
* you need access to features such as experimental re-embeddding or annotations \(which are not available in the hosted version of the system\)
* You are still generating data \(or iterating through analyses\) and working to finalize your submission

To help you consider a self-hosting path, you can check out examples of how other groups have approached this [below](./#live-examples-of-self-hosted-cellxgene-desktop). While we don't officially support web deployment, we've offered some guidance in the following sections on ways to deploy cellxgene to the web.

### General notes and cautions

Please consider the following when deploying cellxgene in any "hosted" environment, especially where access from the broader Internet is possible:

* Information security requires careful configuration of the host environment, including firewall, logging, etc. Please follow best practices.
* cellxgene includes features which may be inappropriate for a hosted deployment. You may wish to use the following command line option: `--disable-diffexp`.
* `cellxgene launch` currently uses Flask's development server, which is not recommended for hosted deployment \(see the [Flask documentation](https://flask.palletsprojects.com/en/1.1.x/tutorial/deploy/#run-with-a-production-server)\)
* We have no testing or official support for deployments where multiple users are accessing the same cellxgene instance.
* Your cellxgene instance is likely to hang or crash if too many people access it at the same time, especially if they using functions that call the Python backend \(such as differential expression, noted above\).
* cellxgene only supports one instance per dataset

If you believe you have found a security-related issue with cellxgene, please report the issue immediately to [security@chanzuckerberg.com](mailto:security@chanzuckerberg.com).

### Configuration options

The following configuration options require special consideration in any multi-user or hosted environment:

`--disable-diffexp`: the differential expression computation can be resource intensive, in particular for large datasets. If many differential expression calculation requests are made in rapid sequence, it may cause the server CPU or memory resources to be exhausted, and impact the ability of other users to access data. This command line option will disable the differential expression feature, including the removal of the `Differential expression` button.

`--disable-annotations`: annotations, which is enabled by default, may not be appropriate for hosted environments. It will write to the local file system, and in extreme cases could be used to abuse \(or exceed\) file system capacity on the hosting server. We recommend disabling this with this flag.

`--annotations-file`: this specifies a single file for all end-user annotations, and is incompatible with hosted or multi-user use of cellxgene. Using it will cause loss of user annotation data \(ie, the CSV file will be overwritten\). If you wish to explore using the annotations feature in a multi-user environment, please refer to the [annotations documentation](../../explorer/feature-overview/desktop-features/annotations.md), and in particular the `--annotations-dir` flag.

### Community software projects

There are a number of teams building tools or infrastructure to better utilize cellxgene in a multiple user environment. While we do not endorse any particular solution, you may find the following helpful.

* [Novartis Cellxgene Gateway](https://github.com/Novartis/cellxgene-gateway) - a multiple-user and multiple-dataset gateway for cellxgene.
* Interactive Environment in the [Galaxy Project](https://galaxyproject.org/) \([patch notes](https://docs.galaxyproject.org/en/release_19.05/releases/19.05_announce.html)\)

If you know of other solutions, drop us a note and we'll add to this list.

### Live Examples of self-hosted Cellxgene Desktop

Several groups have independently deployed various versions of cellxgene to the web. Check out the cool data that our users are using cellxgene to explore!

[Kidney cell atlas](https://www.kidneycellatlas.org/)

[Tabula muris senis](https://tabula-muris-senis.ds.czbiohub.org/)

[Hemocytes](https://hemocytes.cellgeni.sanger.ac.uk/)

[Melanoma](https://melanoma.cellgeni.sanger.ac.uk/)

[CZI's own cellxgene site](https://cellxgene.cziscience.com/)

_Want us to link to your dataset here?_ [_Just send us a note!_](../../contact.md)

