# Introduction to SageMaker for Researchers

Amazon SageMaker is a fully managed service that enables developers and data scientists to quickly and easily build, train, and deploy machine learning models at any scale. This repository contains a collection of hands on content that will introduce and guide you through using SageMaker for your research.

![Overview](./images/overview.png)

During this workshop, you'll explore various data sets, create model training jobs using SageMaker's hosted training feature, and create endpoints to serve predictions from your models using SageMaker's hosted endpoint feature.  

**BEFORE attempting this workshop, please review the Prerequisites below and complete any actions that are required.**

## Prerequisites

### AWS Account

In order to complete this workshop you'll need an AWS Account, and an AWS IAM user in that account with at least full permissions to the following AWS services: 

- AWS IAM
- Amazon S3
- Amazon SageMaker

**Use Your Own Account**: The code and instructions in this workshop assume only one student is using a given AWS account at a time. If you try sharing an account with another student, you'll run into naming conflicts for certain resources. You can work around these by appending a unique suffix to the resources that fail to create due to conflicts, but the instructions do not provide details on the changes required to make this work. Use a personal account or create a new AWS account for this workshop rather than using an organization’s account to ensure you have full access to the necessary services and to ensure you do not leave behind any resources from the workshop.

**Costs**: Some, but NOT all, of the resources you will launch as part of this workshop are eligible for the AWS free tier if your account is less than 12 months old. See the [AWS Free Tier page](https://aws.amazon.com/free/) for more details. An example of a resource that is **not** covered by the free tier is the ml.m4.xlarge notebook instance used in some workshops. To avoid charges for endpoints and other resources you might not need after you've finished a workshop, please refer to the [**Cleanup Guide**](./CleanupGuide). 


### AWS Region

SageMaker is not available in all AWS Regions at this time.  Accordingly, we recommend running this workshop in one of the following supported AWS Regions:  N. Virginia, Oregon, Ohio, or Ireland.

Once you've chosen a region, you should create all of the resources for this workshop there, including a new Amazon S3 bucket and a new SageMaker notebook instance. Make sure you select your region from the dropdown in the upper right corner of the AWS Console before getting started.

![Region selection screenshot](./images/region-selection.png)

### Browser

We recommend you use the latest version of Chrome or Firefox to complete this workshop.

## Modules

This workshop is divided into multiple modules. After completing **Preliminaries**, complete the module **Creating a Notebook Instance** next.  
It is recommended that you complete the lab modules in the order listed.

- Preliminaries

- Creating a Notebook Instance

- Lab Modules

  - Digit Classification with Linear Learner
  - Distributed Training with TensorFlow 
  - Bringing Your Own Model
  - Using Public Datasets

## Preliminaries

Be sure you have completed all of the prerequisites above.

If you are new to using Jupyter notebooks, read the next section, otherwise you may now skip ahead to the next module.

### Jupyter Notebooks:  A Brief Overview

Jupyter is an open-source web application that allows you to create and share documents that contain live code, equations, visualizations and narrative text. Uses include: data cleaning and transformation, numerical simulation, statistical modeling, data visualization, machine learning, and much more. With respect to code, it can be thought of as a web-based IDE that executes code on the server it is running on instead of locally. 

There are two main types of "cells" in a notebook:  code cells, and "markdown" cells with explanatory text. You will be running the code cells.  These are distinguished by having "In" next to them in the left margin next to the cell, and a greyish background.  Markdown cells lack "In" and have a white background. In the screenshot below, the upper cell is a markdown cell, while the lower cell is a code cell:

![Cells](./images/cells.png)

To run a code cell, simply click in it, then either click the **Run Cell** button in the notebook's toolbar, or use Control+Enter from your computer's keyboard. It may take a few seconds to a few minutes for a code cell to run. You can determine whether a cell is running by examining the `In[]:` indicator in the left margin next to each cell:  a cell will show `In [*]:` when running, and `In [a number]:` when complete.

Please run each code cell in order, and **only once**, to avoid repeated operations.  For example, running the same training job cell twice might create two training jobs, possibly exceeding your service limits.


## Creating a Notebook Instance

SageMaker provides hosted Jupyter notebooks that require no setup, so you can begin processing your training data sets immediately. With a few clicks in the SageMaker console, you can create a fully managed notebook instance, pre-loaded with useful libraries for machine learning. You need only add your data.

To create a SageMaker notebook instance for this workshop, follow the instructions at [**Creating a Notebook Instance**](./Modules/NotebookCreation), then return here to continue with the next module of the workshop.


## Lab Modules

1. [Digit Classification with Linear Learner](./Modules/Labs/01-digit-classification-linear-learner.md)

2. [Distributed Training with TensorFlow](./Modules/Labs/02-distributed-training-tensorflow.md)

3. [Bringing Your Own Model](./Modules/Labs/03-bring-your-own-model.md)

4. [Using Public Datasets](./Modules/Labs/04-using-public-datasets.md)


## Cleanup

To avoid charges for resources you no longer need when you're done with this workshop, you can delete them or, in the case of your notebook instance, stop them.  Here are the resources you should consider:

- **Endpoints**:  these are the clusters of one or more instances serving inferences from your models. If you did not delete them from within a notebook, you can delete them via the SageMaker console.  To do so:

  - Click the **Endpoints** link in the left panel.  
  
  - Then, for each endpoint, click the radio button next to it, then select **Delete** from the **Actions** drop down menu. 
  
  - You can follow a similar procedure to delete the related Models and Endpoint configurations.


- **Notebook instance**:  you have two options if you do not want to keep the notebook instance running. If you would like to save it for later, you can stop rather than deleting it. 

  - To **stop** a notebook instance:  click the **Notebook instances** link in the left pane of the SageMaker console home page. Next, click the **Stop** link under the 'Actions' column to the left of your notebook instance's name.  After the notebook instance is stopped, you can start it again by clicking the **Start** link.  Keep in mind that if you stop rather than delete it, you will be charged for the storage associated with it.  

  - To **delete** a notebook instance:  first stop it per the instruction above. Next, click the radio button next to your notebook instance, then select **Delete** from the **Actions** drop down menu. 

- **S3 Bucket**:  if you retain the S3 bucket created for this workshop, you will be charged for storage.  To avoid these charges if you no longer wish to use the bucket, you may delete it. To delete the bucket, go to the S3 service console, and locate your bucket's name in the bucket table. Next, click in the bucket table row for your bucket to highlight the table row. At the top of the table, the **Delete Bucket** button should now be enabled, so click it and then click the **Confirm** button in the resulting pop-up to complete the deletion.  


## License

The contents of this workshop are licensed under the [Apache 2.0 License](./LICENSE).
