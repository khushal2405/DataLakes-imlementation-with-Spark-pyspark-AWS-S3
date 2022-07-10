# DataLakes-imlementation-with-Spark-pyspark-AWS-S3
The ETL pipeline, to populate the AWS S3 Data Lake using Spark
# In this project we will build an ETL pipeline that extracts their data from the data lake hosted on S3, processes them using Spark which will be deployed on an EMR cluster using AWS, and load the data back into S3 as a set of dimensional tables in parquet format.
#ETL pipeline Design
1. Load credentials

2. Read data from S3

Song data: s3a://<S3 bucket name>/song_data
Log data: s3a://<S3 bucket name>/log_data

3. The script reads song_data and load_data from S3.

4. Process data using spark

Transforms them to create five different tables listed under Dimension Tables and Fact Table. Each table includes the right columns and data types. Duplicates are addressed where appropriate.

5. Load it back to S3

Writes them to partitioned parquet files in table directories on S3.

Each of the five tables are written to parquet files in a separate analytics directory on S3. Each table has its own folder within the directory. Songs table files are partitioned by year and then artist. Time table files are partitioned by year and month. Songplays table files are partitioned by year and month.
####Issues faced while implementing#
  1. use s3a instead of s3 while writitng parquet files back to the S3 bucket.
  2. you might need to change inbound settings of the master node of EMR cluster in order to access Jupyter notebook and lab via security VPC instances of EC2.(you can ask me if you want)
  
