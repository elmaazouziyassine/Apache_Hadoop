### Problem Statement 
I have a csv file “myFile.txt” located in the local system within the folder 
/home/cloudera/Desktop/datasets and I want to upload it into Hadoop file system (HDFS)
within the folder /user/cloudera/my_datasets while specifying the : block size and the factor of replication.

### Solution 
- **Step 1** : Check the content of the file before the upload \
`less /home/cloudera/Desktop/datasets/myFile.txt`

- **Step 2** : Create in HDFS the folder ***hdfs_workshops*** within ***/user/cloudera*** directory \
`hdfs dfs -mkdir /user/cloudera/my_datasets`

- **Step 3** : Copy the file from ***/home/cloudera/Desktop/datasets*** to ***/user/cloudera/my_datasets*** while specifying the blocksize \
`hdfs dfs -D dfs.blocksize=1048576 -put /home/cloudera/Desktop/datasets/myFile.txt /user/cloudera/my_datasets`

Note : The value of dfs.blocksize has to be greater than the minimal value (dfs.namenode.fs-limits.min-block-size = 1048576) and has to be a multiple of 512 (the size of the checksum).

- **Step 3** : Verify that the file is well uploader in ***/user/cloudera/my_dataset*** \
`hdfs dfs -ls /user/cloudera/my_dataset`
or 
`hdfs dfs -cat /user/cloudera/my_dataset/myFile.txt`

- **Step 4** : Visualize the number of blocks created for the uploaded file \
`hdfs fsck /user/cloudera/my_dataset/myFile.txt`

- **Step 5** : Display the list of blocks associated with the uploaded file along with their locations \
`hdfs fsck /user/cloudera/my_dataset/myFile.txt -files -blocks`
Note : The block IDs correspond to the names of the files on the DataNodes.BP-1074076978-127.0.0.1-1470864870049

`hdfs fsck /user/cloudera/my_dataset/myFile.txt -files -blocks -locations`
Note : The IP address of the DataNodes appears next to each block

- **Step 6** : Read the content of each block of data \
