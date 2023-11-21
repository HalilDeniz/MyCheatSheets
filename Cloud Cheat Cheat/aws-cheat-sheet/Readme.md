# **AWS Cheat Sheet: Essential Commands for AWS Services**

<img src="../source/aws-cheat-sheet.png"><img>


## **Introduction**
In today's rapidly evolving technology landscape, Amazon Web Services (AWS) has emerged as a pivotal player, offering a vast array of cloud computing services that cater to diverse needs. 
This guide provides a succinct overview of some of the most crucial AWS services, serving as a quick reference for developers and IT professionals.

## **What is AWS?**
Amazon Web Services is a comprehensive cloud computing platform provided by Amazon. 
It offers a wide range of services including computing power, database storage, and content delivery, among others. 
AWS is renowned for its flexibility, scalability, and cost-effectiveness, making it a go-to choice for businesses of all sizes.


## 1. **EC2 (Elastic Compute Cloud)**

1. **Start an EC2 instance for a scheduled backup job:**
   - `aws ec2 start-instances --instance-ids i-xxxbackup`
   - Use case: Automatically start a backup server instance every night to perform data backup tasks.

2. **Start a seasonal EC2 instance for annual financial auditing:**
   - `aws ec2 start-instances --instance-ids i-xxxfinaudit`
   - Use case: Start a dedicated instance for financial auditing that's only needed at the end of the fiscal year.

3. **Restart a previously stopped instance for software updates:**
   - `aws ec2 start-instances --instance-ids i-xxxupdate`
   - Use case: Restart an instance to apply critical software or security updates.

4. **Stop an EC2 instance after batch processing is completed:**
   - `aws ec2 stop-instances --instance-ids i-xxxbatch`
   - Use case: Automatically stop a compute-intensive instance after completing a batch processing task.

5. **Stop an EC2 instance used for a temporary marketing website after the campaign ends:**
   - `aws ec2 stop-instances --instance-ids i-xxxmarketing`
   - Use case: Cease operations of a promotional website hosted on an EC2 instance after the campaign's conclusion.

6. **Stop a development server during weekends:**
   - `aws ec2 stop-instances --instance-ids i-xxxdev`
   - Use case: Automatically stop a development server on Friday evening and restart it on Monday morning to save costs.

7. **Terminate a temporary EC2 instance used for a training session:**
   - `aws ec2 terminate-instances --instance-ids i-xxxtraining`
   - Use case: Permanently shut down an instance after a training or workshop session is completed.

8. **Terminate EC2 instances that were part of a completed project:**
   - `aws ec2 terminate-instances --instance-ids i-xxxproject`
   - Use case: Clean up and remove resources no longer needed after project completion to avoid unnecessary costs.

9. **Start a GPU-enabled EC2 instance for periodic AI model training:**
   - `aws ec2 start-instances --instance-ids i-xxxgpu`
   - Use case: Initiate a GPU-based instance for intermittent AI or machine learning model training.

10. **Stop an EC2 instance used for event-driven processing during off-peak hours:**
    - `aws ec2 stop-instances --instance-ids i-xxxevent`
    - Use case: Temporarily stop an instance used for processing event-driven tasks during low activity periods.

11. **Terminate an EC2 instance after a successful software build and deployment:**
    - `aws ec2 terminate-instances --instance-ids i-xxxbuilder`
    - Use case: Clean up build server instances post successful deployment of software builds.

12. **Start a disaster recovery EC2 instance for testing:**
    - `aws ec2 start-instances --instance-ids i-xxxdrtest`
    - Use case: Periodically start a disaster recovery instance to perform DR drills and testing.

13. **Stop an EC2 instance hosting a seasonal e-commerce application post-holiday season:**
    - `aws ec2 stop-instances --instance-ids i-xxxecommerce`
    - Use case: Reduce costs by stopping additional e-commerce instances that were scaled up for the holiday shopping season.

14. **Terminate an EC2 instance after migration to a different region:**
    - `aws ec2 terminate-instances --instance-ids i-xxxmigrate`
    - Use case: Remove an old instance in one region after successfully migrating its workload to a new region.

15. **Restart a non-critical EC2 instance to apply non-urgent patches:**
    - Stop: `aws ec2 stop-instances --instance-ids i-xxxpatch`
    - Start: `aws ec2 start-instances --instance-ids i-xxxpatch`
    - Use case: Stop and restart an instance at a convenient time to apply patches that do not require immediate attention.

Each of these examples is designed to highlight the practical application of the `start`, `stop`, and `terminate` commands in managing EC2 instances for various business and operational needs.

---

## 2. **S3 (Simple Storage Service)**

1. **Create a bucket for storing website assets:**
   - `aws s3 mb s3://my-website-assets`
   - Use case: Create a new S3 bucket to store images, CSS, and JavaScript files for a website.

2. **Create a bucket for log storage:**
   - `aws s3 mb s3://my-log-storage`
   - Use case: Set up a dedicated S3 bucket to store logs from various applications or systems.

3. **List all buckets to review existing storage:**
   - `aws s3 ls`
   - Use case: Get a list of all S3 buckets in your AWS account to review current storage usage and organization.

4. **List buckets for a cleanup operation:**
   - `aws s3 ls`
   - Use case: List all buckets to identify and clean up any unused or old buckets to optimize storage costs.

5. **Upload a configuration file to a specific bucket:**
   - `aws s3 cp config.json s3://my-config-bucket`
   - Use case: Upload a configuration file to an S3 bucket, where it can be accessed by various applications.

6. **Upload a backup archive to a backup bucket:**
   - `aws s3 cp backup.zip s3://my-backup-bucket`
   - Use case: Upload a backup file to an S3 bucket dedicated to storing backup data.

7. **Download a report from an S3 bucket for analysis:**
   - `aws s3 cp s3://my-report-bucket/financial-report.xlsx ./`
   - Use case: Download a financial report from an S3 bucket to a local machine for further analysis.

8. **Download a software release from an S3 bucket for deployment:**
   - `aws s3 cp s3://my-software-releases/myapp-v1.2.tar.gz ./`
   - Use case: Download the latest version of a software application from an S3 bucket for deployment on servers.

9. **Upload a video file for content delivery:**
   - `aws s3 cp video.mp4 s3://my-content-delivery-bucket`
   - Use case: Upload a large video file to an S3 bucket for subsequent distribution via a Content Delivery Network (CDN).

10. **Download an eBook from a public S3 bucket:**
    - `aws s3 cp s3://public-ebooks/mybook.pdf ./`
    - Use case: Download a publicly available eBook from an S3 bucket.

11. **Create a bucket for data archiving:**
    - `aws s3 mb s3://my-data-archive`
    - Use case: Create a new S3 bucket specifically for archiving old or infrequently accessed data.

12. **Upload a dataset for machine learning:**
    - `aws s3 cp dataset.csv s3://my-ml-bucket`
    - Use case: Upload a dataset to an S3 bucket for use in machine learning training processes.

13. **Download a database backup for local restoration:**
    - `aws s3 cp s3://my-db-backups/backup.sql ./`
    - Use case: Download a database backup file from an S3 bucket for local restoration or testing.

14. **Upload website content for static hosting:**
    - `aws s3 cp index.html s3://my-website-bucket`
    - Use case: Upload HTML files to an S3 bucket configured for static website hosting.

15. **List buckets to monitor project-related storage:**
    - `aws s3 ls`
    - Use case: Regularly list all S3 buckets to monitor and manage storage related to specific projects or departments.

Each example demonstrates a practical use of the commands to create, list, upload, and download content from AWS S3, showcasing the versatility and convenience of S3 for various storage needs.

---

## 3. **IAM (Identity and Access Management)**

1. **List users to audit IAM users:**
   - `aws iam list-users`
   - Use case: Perform a routine audit of IAM users in your AWS account to ensure compliance with your organization's security policies.

2. **List users to identify inactive accounts:**
   - `aws iam list-users`
   - Use case: Generate a list of IAM users to identify and manage accounts that have been inactive for an extended period.

3. **Create a new user for a new team member:**
   - `aws iam create-user --user-name john.doe`
   - Use case: Create a new IAM user account for a newly hired employee, John Doe, to provide access to AWS services.

4. **Create a user for a specific application:**
   - `aws iam create-user --user-name my-application`
   - Use case: Set up a dedicated IAM user for an application that requires access to certain AWS resources, ensuring a clear separation between human users and applications.

5. **Attach an Administrator policy to a new IT staff member:**
   - `aws iam attach-user-policy --policy-arn arn:aws:iam::aws:policy/AdministratorAccess --user-name alice.smith`
   - Use case: Grant full administrative access to a new IT staff member, Alice Smith, allowing her to manage all aspects of the AWS environment.

6. **Attach a Read-Only policy to a user for audit purposes:**
   - `aws iam attach-user-policy --policy-arn arn:aws:iam::aws:policy/ReadOnlyAccess --user-name audit-user`
   - Use case: Provide an auditor with read-only access to AWS resources, ensuring they can perform an audit without making any changes.

7. **Create a user for an external consultant:**
   - `aws iam create-user --user-name external.consultant`
   - Use case: Create a temporary IAM user account for an external consultant, providing necessary access while maintaining security.

8. **Attach a specific policy to a user for limited S3 access:**
   - `aws iam attach-user-policy --policy-arn arn:aws:iam::aws:policy/AmazonS3ReadOnlyAccess --user-name data-analyst`
   - Use case: Grant a data analyst user read-only access to specific S3 buckets, ensuring they can access data without modifying it.

9. **Create a user for automated scripts or services:**
   - `aws iam create-user --user-name automated-script`
   - Use case: Set up an IAM user for scripts or services that automate tasks, ensuring they have the necessary permissions.

10. **Attach a custom policy to a user for specific resource access:**
    - `aws iam attach-user-policy --policy-arn arn:aws:iam::123456789012:policy/my-custom-policy --user-name project-manager`
    - Use case: Provide a project manager with specific access rights tailored to their role, using a custom policy.

11. **List users before a security compliance review:**
    - `aws iam list-users`
    - Use case: Prepare for a security compliance review by listing all IAM users and checking their assigned policies and access rights.

12. **Create a user for a temporary project:**
    - `aws iam create-user --user-name temp-project-user`
    - Use case: Establish a temporary IAM user for a short-term project, planning to revoke access once the project is completed.

13. **Attach a policy for accessing a specific AWS service:**
    - `aws iam attach-user-policy --policy-arn arn:aws:iam::aws:policy/AmazonEC2FullAccess --user-name dev-team-member`
    - Use case: Grant a development team member full access to EC2, allowing them to manage instances as part of their development work.

14. **Create a user for monitoring and logging purposes:**
    - `aws iam create-user --user-name monitoring-agent`
    - Use case: Create a user for tools or agents that perform monitoring and logging, ensuring they have the appropriate level of access.

15. **List users post-organizational restructuring:**
    - `aws iam list-users`
    - Use case: After an organizational restructuring, list all IAM users to update roles and permissions according to new department alignments.

Each of these examples demonstrates how IAM commands can be applied in real-world situations to manage user access and ensure security within an AWS environment.

--

## 4. **RDS (Relational Database Service)**

1. **Create a new RDS instance for a web application:**
   - `aws rds create-db-instance --db-instance-identifier webapp-db --allocated-storage 100 --db-instance-class db.m4.large --engine mysql --master-username admin --master-user-password securepassword`
   - Use case: Set up a new MySQL database instance for a web application, with sufficient storage and a suitable instance class for handling web traffic.

2. **Create a database for a development environment:**
   - `aws rds create-db-instance --db-instance-identifier dev-db --allocated-storage 10 --db-instance-class db.t2.micro --engine postgres --master-username devuser --master-user-password devpassword`
   - Use case: Launch a smaller, cost-effective PostgreSQL database instance for development purposes, with limited storage and a micro instance class.

3. **List all RDS instances for inventory management:**
   - `aws rds describe-db-instances`
   - Use case: Retrieve a list of all RDS instances to maintain an inventory of databases, their configurations, and statuses for management and auditing.

4. **List RDS instances to assess resource utilization:**
   - `aws rds describe-db-instances`
   - Use case: Regularly list RDS instances to review and assess their resource utilization, ensuring optimal performance and cost management.

5. **Delete an RDS instance after migrating to a larger instance:**
   - `aws rds delete-db-instance --db-instance-identifier old-db`
   - Use case: Remove an older, smaller database instance after successfully migrating its data to a larger, more capable instance.

6. **Create a test database for quality assurance:**
   - `aws rds create-db-instance --db-instance-identifier qa-db --allocated-storage 50 --db-instance-class db.t2.medium --engine mariadb --master-username qauser --master-user-password qapassword`
   - Use case: Set up a MariaDB instance specifically for the quality assurance team to test new features and updates before they go live.

7. **Delete a temporary database used for a marketing campaign:**
   - `aws rds delete-db-instance --db-instance-identifier campaign-db`
   - Use case: Clean up and remove a temporary database that was used to support a short-term marketing campaign.

8. **Create a database for storing analytical data:**
   - `aws rds create-db-instance --db-instance-identifier analytics-db --allocated-storage 200 --db-instance-class db.r4.large --engine aurora --master-username analyticsadmin --master-user-password analyt1cs`
   - Use case: Launch an Aurora database instance dedicated to storing and processing large volumes of analytical data.

9. **List RDS instances to monitor backup statuses:**
   - `aws rds describe-db-instances`
   - Use case: Regularly check the status of RDS instances to ensure that backups are being performed as expected.

10. **Create a database for a mobile application's backend:**
    - `aws rds create-db-instance --db-instance-identifier mobileapp-db --allocated-storage 30 --db-instance-class db.t3.medium --engine postgres --master-username mobileadmin --master-user-password mob1lepass`
    - Use case: Set up a PostgreSQL database to serve as the backend for a mobile application, with appropriate storage and compute resources.

11. **Delete an RDS instance after a project completion:**
    - `aws rds delete-db-instance --db-instance-identifier project-db`
    - Use case: Safely delete a database instance that was used for a project that has now been completed.

12. **Create a clone of an existing database for testing upgrades:**
    - `aws rds create-db-instance --db-instance-identifier test-upgrade-db --allocated-storage 50 --db-instance-class db.m4.large --engine mysql --master-username testuser --master-user-password testpassword`
    - Use case: Duplicate an existing MySQL database into a new instance to test software upgrades or changes without affecting the live environment.

13. **List all databases to evaluate compliance with data policies:**
    - `aws rds describe-db-instances`
    - Use case: Perform a comprehensive check of all database instances to ensure compliance with internal data handling and privacy policies.

14. **Create a multi-AZ deployment for high availability:**
    - `aws rds create-db-instance --db-instance-identifier ha-db --allocated-storage 100 --db-instance-class db.m4.large --engine mysql --master-username haadmin --master-user-password hastrongpass --multi-az`
    - Use case: Establish a high-availability MySQL database setup with Multi-AZ deployment for critical applications requiring high uptime.

15. **Delete a database used for seasonal data analysis:**
    - `aws rds delete-db-instance --db-instance-identifier seasonal-analysis-db`
    - Use case: Remove a database that was specifically used for analyzing data during a particular season, such as holiday sales data.

Each of these examples showcases how the RDS commands can be effectively used in different scenarios, from setting up new databases for various environments to managing existing databases and ensuring optimal resource utilization and compliance.

---

## 5. **Lambda**

1. **Create a Lambda function for image processing:**
   - `aws lambda create-function --function-name image-processor --zip-file fileb://image-processor.zip --handler process.handler --runtime python3.8 --role arn:aws:iam::123456789012:role/lambda-role`
   - Use case: Set up a Lambda function for processing images, such as resizing or format conversion, triggered whenever new images are uploaded to an S3 bucket.

2. **Create a function for data cleaning in a data pipeline:**
   - `aws lambda create-function --function-name data-cleaner --zip-file fileb://data-cleaner.zip --handler clean.handler --runtime java11 --role arn:aws:iam::123456789012:role/lambda-role`
   - Use case: Establish a Lambda function to clean and preprocess data as part of an ETL (Extract, Transform, Load) pipeline.

3. **Invoke a Lambda function for a manual test:**
   - `aws lambda invoke --function-name test-function outputfile.txt`
   - Use case: Manually invoke a Lambda function named `test-function` for testing or debugging purposes, with the output saved to `outputfile.txt`.

4. **Invoke a function for generating a report:**
   - `aws lambda invoke --function-name generate-report reportoutput.txt`
   - Use case: Trigger a Lambda function to generate a business report, perhaps aggregating data from various sources.

5. **List all Lambda functions for an audit:**
   - `aws lambda list-functions`
   - Use case: Retrieve a list of all Lambda functions in your AWS account as part of a routine audit or to monitor the deployed functions.

6. **List functions to review resource utilization:**
   - `aws lambda list-functions`
   - Use case: List all Lambda functions to assess their configurations and usage, ensuring efficient use of resources.

7. **Create a function for handling user authentication:**
   - `aws lambda create-function --function-name auth-handler --zip-file fileb://auth-handler.zip --handler auth.validate --runtime nodejs12.x --role arn:aws:iam::123456789012:role/lambda-role`
   - Use case: Develop a Lambda function dedicated to handling user authentication requests in a serverless application.

8. **Invoke a Lambda function for ad-hoc data processing:**
   - `aws lambda invoke --function-name process-data tempoutput.txt`
   - Use case: Manually trigger a Lambda function to process data for ad-hoc analysis, storing the output temporarily.

9. **Create a Lambda function for IoT device data processing:**
   - `aws lambda create-function --function-name iot-data-processor --zip-file fileb://iot-processor.zip --handler processIotData.handler --runtime python3.8 --role arn:aws:iam::123456789012:role/lambda-role`
   - Use case: Set up a Lambda function to process and analyze data coming from IoT devices.

10. **List functions to identify unused or redundant functions:**
    - `aws lambda list-functions`
    - Use case: Periodically list Lambda functions to identify and remove those that are no longer used or have redundant functionality.

11. **Create a Lambda function for scheduled database backups:**
    - `aws lambda create-function --function-name db-backup --zip-file fileb://db-backup.zip --handler backup.handler --runtime nodejs12.x --role arn:aws:iam::123456789012:role/lambda-role`
    - Use case: Automate database backups using a Lambda function that is triggered on a schedule.

12. **Invoke a function for processing user feedback submissions:**
    - `aws lambda invoke --function-name feedback-processor feedbackResult.txt`
    - Use case: Manually run a Lambda function to process and analyze user feedback collected via a web application.

13. **Create a function for real-time stream processing:**
    - `aws lambda create-function --function-name stream-processor --zip-file fileb://stream-processor.zip --handler stream.handler --runtime java11 --role arn:aws:iam::123456789012:role/lambda-role`
    - Use case: Develop a Lambda function to process and analyze data streams in real time, such as log files or social media feeds.

14. **List functions to monitor the deployment of new features:**
    - `aws lambda list-functions`
    - Use case: After deploying new features in a series of Lambda functions, list all functions to ensure that the deployments were successful.

15. **Create a Lambda function for sending notification emails:**
    - `aws lambda create-function --function-name email-sender --zip-file fileb://email-sender.zip --handler sendEmail.handler --runtime python3.8 --role arn:aws:iam::123456789012:role/lambda-role`
    - Use case: Set up a Lambda function to automatically send notification emails in response to certain triggers or events.

Each of these examples highlights a practical application of Lambda functions, demonstrating their versatility and power in various scenarios ranging from data processing to automation and real-time analysis.

---

## 6. **CloudFormation**

1. **Create a stack for a basic web application:**
   - `aws cloudformation create-stack --stack-name web-app-stack --template-body file://web-app-template.json`
   - Use case: Launch a stack using a JSON template that sets up the necessary AWS resources (like EC2 instances, an RDS database, and S3 buckets) for a basic web application.

2. **Create a stack for a network infrastructure:**
   - `aws cloudformation create-stack --stack-name network-stack --template-body file://network-template.json`
   - Use case: Set up a network infrastructure, including VPCs, subnets, and security groups, using a CloudFormation template.

3. **Describe stacks to review current infrastructure:**
   - `aws cloudformation describe-stacks`
   - Use case: Get details on all the CloudFormation stacks to review the current state of your AWS infrastructure.

4. **Describe stacks for troubleshooting:**
   - `aws cloudformation describe-stacks`
   - Use case: Inspect the details of CloudFormation stacks to troubleshoot issues like failed deployments or resource misconfigurations.

5. **Delete a stack after project completion:**
   - `aws cloudformation delete-stack --stack-name project-stack`
   - Use case: Safely remove all AWS resources associated with a specific project by deleting the corresponding CloudFormation stack.

6. **Create a stack for a serverless application:**
   - `aws cloudformation create-stack --stack-name serverless-app-stack --template-body file://serverless-app-template.yaml`
   - Use case: Deploy a serverless application, including Lambda functions, API Gateway, and DynamoDB tables, using a YAML template.

7. **Delete a test environment stack:**
   - `aws cloudformation delete-stack --stack-name test-env-stack`
   - Use case: Clean up a temporary testing environment by deleting the CloudFormation stack, ensuring no ongoing charges for those resources.

8. **Describe stacks for an audit:**
   - `aws cloudformation describe-stacks`
   - Use case: Perform an infrastructure audit by detailing all CloudFormation stacks to ensure compliance with company policies and best practices.

9. **Create a stack for a disaster recovery setup:**
   - `aws cloudformation create-stack --stack-name dr-setup-stack --template-body file://dr-setup-template.json`
   - Use case: Establish a disaster recovery setup, including backup resources and replication configurations, using CloudFormation.

10. **Delete a stack for a decommissioned application:**
    - `aws cloudformation delete-stack --stack-name old-app-stack`
    - Use case: Remove all AWS resources for an application that has been decommissioned or replaced.

11. **Create a stack for an IoT application infrastructure:**
    - `aws cloudformation create-stack --stack-name iot-app-stack --template-body file://iot-app-template.json`
    - Use case: Set up the necessary infrastructure for an IoT application, including IoT Core, associated databases, and processing resources.

12. **Describe stacks to ensure successful updates:**
    - `aws cloudformation describe-stacks`
    - Use case: Verify the status and configuration of CloudFormation stacks after making updates to ensure the changes were successful.

13. **Create a stack for a multi-tier application architecture:**
    - `aws cloudformation create-stack --stack-name multi-tier-app-stack --template-body file://multi-tier-app-template.yaml`
    - Use case: Deploy a multi-tier application, with separate layers for the web interface, application logic, and database, using a structured CloudFormation template.

14. **Delete a stack used for a temporary marketing event:**
    - `aws cloudformation delete-stack --stack-name marketing-event-stack`
    - Use case: After the conclusion of a marketing event, remove all related AWS resources by deleting the event-specific CloudFormation stack.

15. **Create a stack for a data analytics platform:**
    - `aws cloudformation create-stack --stack-name analytics-platform-stack --template-body file://analytics-platform-template.json`
    - Use case: Build a comprehensive data analytics platform, including data storage, processing, and analysis tools, with a CloudFormation template.

Each of these examples demonstrates the practical use of CloudFormation in managing and automating the deployment of AWS resources, from simple web applications to complex, multi-tier architectures and specialized setups like IoT or analytics platforms.

---

## 7. **DynamoDB**

1. **Create a table for user data storage:**
   - `aws dynamodb create-table --table-name Users --attribute-definitions AttributeName=UserId,AttributeType=S --key-schema AttributeName=UserId,KeyType=HASH --provisioned-throughput ReadCapacityUnits=5,WriteCapacityUnits=5`
   - Use case: Set up a DynamoDB table named 'Users' to store user profiles, with 'UserId' as the primary key and provisioned read/write capacity units based on expected traffic.

2. **Create a table for a product catalog:**
   - `aws dynamodb create-table --table-name Products --attribute-definitions AttributeName=ProductId,AttributeType=S --key-schema AttributeName=ProductId,KeyType=HASH --provisioned-throughput ReadCapacityUnits=10,WriteCapacityUnits=10`
   - Use case: Establish a 'Products' table in DynamoDB for an e-commerce application, with 'ProductId' as the primary key to store details of products.

3. **List tables to review existing databases:**
   - `aws dynamodb list-tables`
   - Use case: Get a list of all DynamoDB tables in your AWS account for a general overview or to review the database structure.

4. **List tables for database cleanup:**
   - `aws dynamodb list-tables`
   - Use case: Regularly list DynamoDB tables to identify and remove old or unused tables, optimizing resource usage and costs.

5. **Delete a table used for a completed project:**
   - `aws dynamodb delete-table --table-name ProjectData`
   - Use case: Remove a DynamoDB table named 'ProjectData' that was used for storing temporary data for a project that is now complete.

6. **Create a table for event logging:**
   - `aws dynamodb create-table --table-name EventLogs --attribute-definitions AttributeName=EventId,AttributeType=S --key-schema AttributeName=EventId,KeyType=HASH --provisioned-throughput ReadCapacityUnits=3,WriteCapacityUnits=3`
   - Use case: Set up a DynamoDB table for logging application events, using 'EventId' as the primary key.

7. **Delete a table after migrating data to another database:**
   - `aws dynamodb delete-table --table-name OldData`
   - Use case: Clean up by deleting the 'OldData' table in DynamoDB after its data has been migrated to a more suitable database solution.

8. **Create a table for session management in web applications:**
   - `aws dynamodb create-table --table-name UserSessions --attribute-definitions AttributeName=SessionId,AttributeType=S --key-schema AttributeName=SessionId,KeyType=HASH --provisioned-throughput ReadCapacityUnits=2,WriteCapacityUnits=2`
   - Use case: Develop a DynamoDB table named 'UserSessions' for managing user sessions in a web application, using 'SessionId' as the primary key.

9. **List tables as part of a regular audit:**
   - `aws dynamodb list-tables`
   - Use case: Conduct a regular audit of your AWS environment, listing all DynamoDB tables to ensure that they align with current data storage and access policies.

10. **Create a table for IoT device data:**
    - `aws dynamodb create-table --table-name IoTDeviceData --attribute-definitions AttributeName=DeviceId,AttributeType=S --key-schema AttributeName=DeviceId,KeyType=HASH --provisioned-throughput ReadCapacityUnits=15,WriteCapacityUnits=15`
    - Use case: Instantiate a DynamoDB table for storing data from IoT devices, with 'DeviceId' as the primary key.

11. **Delete a table for a discontinued service:**
    - `aws dynamodb delete-table --table-name ServiceData`
    - Use case: Remove the 'ServiceData' table from DynamoDB that was used for a service your company has since discontinued.

12. **Create a table for storing inventory data:**
    - `aws dynamodb create-table --table-name Inventory --attribute-definitions AttributeName=ItemId,AttributeType=S --key-schema AttributeName=ItemId,KeyType=HASH --provisioned-throughput ReadCapacityUnits=8,WriteCapacityUnits=8`
    - Use case: Set up a 'Inventory' table in DynamoDB to manage inventory data for a retail business, with 'ItemId' as the primary key.

13. **List tables for capacity planning:**
    - `aws dynamodb list-tables`
    - Use case: List all DynamoDB tables to evaluate current usage and plan for future capacity needs.

14. **Create a table for a mobile app's user interactions:**
    - `aws dynamodb create-table --table-name UserInteractions --attribute-definitions AttributeName=InteractionId,AttributeType=S --key-schema AttributeName=InteractionId,KeyType=HASH --provisioned-throughput ReadCapacityUnits=4,WriteCapacityUnits=4`
    - Use case: Create a 'UserInteractions' table in DynamoDB to store and analyze user interactions data from a mobile application.

15. **Delete a table used for a temporary marketing campaign:**
    - `aws dynamodb delete-table --table-name CampaignData`
    - Use case: After the conclusion of a marketing campaign, delete the 'CampaignData' table from DynamoDB to tidy up and reduce costs.

Each of these examples showcases how DynamoDB's commands can be effectively used in different scenarios, from managing user data and product catalogs to handling IoT device data and user sessions, demonstrating the flexibility and scalability of DynamoDB as a NoSQL database service.

## Contributing

Contributions are welcome! If you find any issues or have suggestions for improvements, feel free to open an issue or submit a pull request.

## Contact

If you have any questions, comments, or suggestions about **AWS Cheat sheet**, please feel free to contact me:

- Linktr [halildeniz](https://linktr.ee/halildeniz)
- DenizHalil [DenizHalil](https://denizhalil.com)
- LinkedIn: [Halil Ibrahim Deniz](https://www.linkedin.com/in/halil-ibrahim-deniz/)
- TryHackMe: [Halilovic](https://tryhackme.com/p/halilovic)
- Instagram: [deniz.halil333](https://www.instagram.com/deniz.halil333/)
- YouTube: [Halil Deniz](https://www.youtube.com/c/HalilDeniz)
- Email: halildeniz313@gmail.com


## License
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for more details.

## 💰 You can help me by Donating
  Thank you for considering supporting me! Your support enables me to dedicate more time and effort to creating useful **Cheat Sheet** and developing new projects. By contributing, you're not only helping me improve existing tools but also inspiring new ideas and innovations. Your support plays a vital role in the growth of this project and future endeavors. Together, let's continue building and learning. Thank you!"<br>
[![BuyMeACoffee](https://img.shields.io/badge/Buy%20Me%20a%20Coffee-ffdd00?style=for-the-badge&logo=buy-me-a-coffee&logoColor=black)](https://buymeacoffee.com/halildeniz)
[![Patreon](https://img.shields.io/badge/Patreon-F96854?style=for-the-badge&logo=patreon&logoColor=white)](https://patreon.com/denizhalil) 

  
