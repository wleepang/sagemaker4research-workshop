# Bringing Your Own Model

A crucial aspect to scientific research is  building new tools / methods along 
the way to making new discoveries.  For machine learning problems the code that 
implements a specialized algorithm could be quite complex, or special framework 
additions are needed.  Amazon SageMaker provides the flexibility to bring your 
own algorithms and models and train and host them in the same way as built-in 
algorithms.  In this lab, we'll explore how to integrate a decision tree 
algorithm written using the [https://scikit-learn.org](scikit-learn) machine 
learning package for Python into SageMaker.

Follow these steps:

1. In your notebook instance, click on the top level folder.
2. Navigate to `sample-notebooks / advanced_functionality / scikit_bring_your_own`
3. Open the `scikit_bring_your_own.ipynb` notebook, the follow the directions in the notebook.

There are two main parts in this example:

1. building the container for a custom algorithm

    1. Modify your current SageMakerExecution Role to have full access to Amazon ECR by adding the managed policy `AmazonEC2ContainerRegistryFullAccess`
    2. The container build step takes about 1-2min to finish

2. training and hosting the algorithm

    1. Training for this algorithm typicall takes about 5 minutes
