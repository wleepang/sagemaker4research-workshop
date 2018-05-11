# Digit Classification with Linear Learner

In this lab we will introduce you to Amazon Sagemaker using the Amaazon-provided Linear Learner algorithm to perform
binary classification of images of handwritten digits from the [MNIST Database](http://yann.lecun.com/exdb/mnist/).
Specifically, we'll train a model to identify whether or not a digit is a "0". In doing so, we will demonstrate how to 
use a Jupyter notebook and the [SageMaker Python SDK](https://github.com/aws/sagemaker-python-sdk) to create a script to 
pre-process data, train a model, create a SageMaker hosted endpoint, and make predictions against this endpoint - 
completing a full machine learning workflow end-to-end.

1. In your notebook instance, click on the top level folder.
2. Navigate to `sample-notebooks / introduction_to_amazon_algorithms / linear_learner_mnist`
3. Open the `linear_learner_mnist.ipynb` notebook, the follow the directions in the notebook.
4. In the `bucket = '<your_s3_bucket_name_here>'` code line, paste the name of the S3 bucket you created in Module 1 to 
   replace `<your_s3_bucket_name_here>`.  The code line should now read similar to `bucket = 'smworkshop-john-smith'`.
   Do NOT paste the entire path (s3://.......), just the bucket name.

> **NOTE:** training the model for this example typically takes about 5 minutes

## Extra Credit

1. How good is the model?  Compute precision, recall, and f1 metrics to find out.
2. Re-train the model to identify an other digit.
3. Try changing the classification algorithm (e.g. to a factorization machine) and repeating the workflow
