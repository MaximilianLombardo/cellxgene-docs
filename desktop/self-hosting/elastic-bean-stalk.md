---
description: Hosting cellxgene with Elastic Beanstalk
---

# AWS Elastic Bean Stalk

### Contributors:

The cellxgene team



### Hosting Use Case:

* Cellxgene desktop deployed with elastic beanstalk
* Used to host data in a read-only fashion \(can't use annotations\)
* Solution for an AWS compute environment

### Components:

* [Cellxgene Desktop](https://github.com/chanzuckerberg/cellxgene): the application to be run
* [Elastic Beanstalk](https://aws.amazon.com/elasticbeanstalk/): AWS based solution for deploying and scaling web applications

### Notes:

Need familiarity with IAM and S3 

{% embed url="https://github.com/chanzuckerberg/cellxgene/tree/main/backend/czi\_hosted/eb" %}

Need familiarity with IAM and S3, propose as a read only version of hosted with the desktop app \(go with this!\)

~~Docker image + EB setup?~~

~~~~



