# A_Simple_Data_pipeline
![data-pipeline-img](https://user-images.githubusercontent.com/59966722/179762451-82d3d9de-5a4d-4dca-af32-20b51251e210.png)


1. The code in ***main.py*** file is the driver code, which gets the data from CoinCap API and converts to json file.
It also creates an S3 bucket and uploades the file to that bucket and asks for another bucket name to place the processed CSV file


2. Now, create a ***lambda function*** and attach ***S3FullAccess*** and ***AWSGlueServiceRole*** policies. In The ***aws_lambda.py*** file, replace the necessary variable values like S3 bucket name etc.

3. Other Main thing is we have used ***AWS Wrangler***, so we need to add the dependency layer to our function, click on add layer and add ***AWSWrangler38*** and select version 8, set the code execution timeout to 2 mins or so....

4. After the execution of Lambda function, in the ***AWS Glue*** console, a table will be created, select the table and click on View Data, it will navigate to ***AWS Athena***, where you can query to view the data. 

From Document type data from API to Structured data in AWS Athena.
