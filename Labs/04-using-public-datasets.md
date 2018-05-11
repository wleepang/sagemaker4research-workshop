# Using Public Datasets

Machine learning is a data driven process.  Sharing key datasets publicly allows
smart minds around the world to perform novel analyses and generate new insights.
In this lab, we will use the [1000 Genomes Project](https://aws.amazon.com/1000genomes/) 
dataset - a collection of DNA sequence variations from over 1000 individuals.  
We will apply unsupervised learning via the Amazon-provided K-Means algorithm to 
group the geographic location of sequences based on their variant information.

1. In your notebook instance, click the **New** button on the right and select **Folder**.  
2. Click the checkbox next to your new folder, click the **Rename** button above in the menu bar, and give the folder a name such as 'genomics-clustering'.
3. Click the folder to enter it.
4. To upload the notebook, click the **Upload** button on the right. Then in the file selection popup, select the file 'genome-kmeans-py3.ipynb' from the notebooks subdirectory in the folder on your computer where you downloaded this GitHub repository. Click the blue **Upload** button that appears to the right of the notebook's file name.
5. You are now ready to begin the notebook:  click the notebook's file name to open it.
6. In the ```bucket = '<your_s3_bucket_name_here>'``` code line, paste the name of the S3 bucket you created in Module 1 to replace ```<your_s3_bucket_name_here>```.  The code line should now read similar to ```bucket = 'smworkshop-john-smith'```.  Do NOT paste the entire path (s3://.......), just the bucket name.