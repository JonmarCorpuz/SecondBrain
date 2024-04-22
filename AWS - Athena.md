Athena is a serverless interactive query service that users can use to analyze data in AWS S3 by using SQL

* Doesn't make a copy the user's data, meaning that users need to specify the S3 bucket prefix that Athena will look for when they create an Athena table
* The data in an S3 bucket needs to match the table's schema
* Users can create multiple Athena tables that reference different S3 buckets and join them
