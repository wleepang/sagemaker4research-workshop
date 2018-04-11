# computing model metrics

Store the confusion matrix dataframe for future referencing:

```python
cm = pd.crosstab(np.where(test_set[1] == 0, 1, 0), predictions, rownames=['actuals'], colnames=['predictions'])
```

output. for this classification case, a "1" corresponds to a true prediction - found a "0" 

```text
predictions   0.0  1.0
actuals               
0            8972   48
1              40  940
```

Compute true positive, false positive, and false negative counts:

```python
tp = cm.loc[1, 1.0]  # true positives
fp = cm.loc[0, 1.0]  # false positives
fn = cm.loc[1, 0.0]  # false negatives
```

Compute metrics:

```python
precision = tp / (tp + fp)
recall = tp / (tp + fn)
f1 = 2 * precision * recall / (precision + recall)


print(f"precision: {precision}")
print(f"recall: {recall}")
print(f"f1: {f1}")
```

```text
precision: 0.951417004048583
recall: 0.9591836734693877
f1: 0.9552845528455284
```

# change from linear learner to factorization machine
from:

```python
import boto3
import sagemaker

sess = sagemaker.Session()

linear = sagemaker.estimator.Estimator(containers[boto3.Session().region_name],
                                       role, 
                                       train_instance_count=1, 
                                       train_instance_type='ml.c4.xlarge',
                                       output_path=output_location,
                                       sagemaker_session=sess)
linear.set_hyperparameters(feature_dim=784,
                           predictor_type='binary_classifier',
                           mini_batch_size=200)

linear.fit({'train': s3_train_data})
```

to:

```python
import boto3
import sagemaker

sess = sagemaker.Session()

fm = sagemaker.estimator.Estimator(containers[boto3.Session().region_name],
                                   role, 
                                   train_instance_count=1, 
                                   train_instance_type='ml.c4.xlarge',
                                   output_path=output_location,
                                   sagemaker_session=sess)
fm.set_hyperparameters(feature_dim=784,
                      predictor_type='binary_classifier',
                      mini_batch_size=200,
                      num_factors=10)  # <=== THIS IS THE ONLY DIFFERENCE

fm.fit({'train': s3_train_data})
```