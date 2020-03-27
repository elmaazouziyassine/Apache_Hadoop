
hdfs commands are programs written in Java. 
hdfs dfs = hadoop fs
hdfs dfs version | to display HDFS version
hdfs dfs -help | to display help
hdfs dfs -ls <hdfs_path_dir> | to list the content of a directory
hdfs dfs -cat <hdfs_path_file> | to read the content of a file
hdfs dfs -mkdir <hdfs_path_dir> | to create a folder
hdfs dfs -put <local_path_file> <hdfs_path_dir> | to copy a file from localSystem to HDFS
hdfs dfs -copyFromLocal <local_path_file> <hdfs_path_dir> | to copy a file from localSystem to HDFS

hdfs dfs -get <hdfs_path_file> <local_path_dir> | to copy a file from HDFS to localSystem
hdfs dfs -copyToLocal <hdfs_path_file> <local_path_dir> | to copy a file from HDFS to localSystem

hdfs dfs -cp <hdfs_path__dir1_file> <hdfs_path_dir2>  | to copy a file from dir1 to dir2
hdfs dfs -mv <hdfs_path__dir1_file> <hdfs_path_dir2>  | to move a file from dir1 to dir2
