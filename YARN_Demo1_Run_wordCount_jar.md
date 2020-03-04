### Problem Statement
I have a jar program and I want to apply it upon some data using YARN. 

### Solution 
- **Step 1** : Check the content of the input file \
`less /home/cloudera/Desktop/datasets/article.txt`

- **Step 2** : Load the input file ***article.txt*** into HDFS directory ***/user/cloudera/my_datasets*** \
`hdfs dfs -mkdir /user/cloudera/my_datasets` \
`hdfs dfs -put /home/cloudera/Desktop/datasets/article.txt /user/cloudera/my_datasets` \
`hdfs dfs -ls /user/cloudera/my_dataset`  

- **Step 3** : Load the jar ***hadoop-mapreduce-examples.jar*** into HDFS directory ***/user/cloudera/my_scripts*** \
`hdfs dfs -mkdir /user/cloudera/my_scripts` \
`hdfs dfs -put /home/cloudera/Desktop/datasets/hadoop-mapreduce-examples.jar /user/cloudera/my_scripts` \
`hdfs dfs -ls /user/cloudera/my_scripts` 

- **Step 4** : Launch the job ***wordcount*** & write the result in the folder ***/user/cloudera/my_outputs*** \
`yarn jar /user/cloudera/my_scripts/hadoop-mapreduce-examples.jar wordcount /user/cloudera/my_datasets/article.txt /user/cloudera/my_outputs` 
