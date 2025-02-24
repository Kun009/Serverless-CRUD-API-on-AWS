# Serverless-CRUD-API-on-AWS
This project implements a serverless CRUD API using AWS API Gateway, Lambda, DynamoDB, and CloudWatch. The API supports basic create, read, update, and delete operations. Postman was used to test the endpoints, and images of the operations are included in the repository.![Screenshot 2025-02-24 084859](https://github.com/user-attachments/assets/dd1722e8-4a51-4f05-a5e6-6ea552642313)


# Table of Contents
+ [Architecture](https://github.com/Kun009/Serverless-CRUD-API-on-AWS/edit/main/README.md#architecture)
+ [Prerequisites](https://github.com/Kun009/Serverless-CRUD-API-on-AWS/edit/main/README.md#prerequisites)
+ Setup Steps
+ Lambda Code Overview
+ Deployment
+ Testing

## Architecture
+ API Gateway: Routes HTTP requests to Lambda.

+ AWS Lambda: Processes CRUD operations using Node.js.

+ DynamoDB: Stores task data in a table named CRUD.

+ CloudWatch: Captures logs from API Gateway and Lambda.

## Prerequisites

+ AWS account with proper permissions.

+ AWS CLI installed and configured.

+ Node.js installed.

+ Git installed.

+ Postman for API testing.

  ## Setup Steps
1. Create DynamoDB Table
+Create a table named CRUD with id as the primary key.
![Screenshot 2025-02-24 130806](https://github.com/user-attachments/assets/69309921-7ff9-4376-b6c9-2c2f40ef21f8)

2. Create and Configure Lambda Function

+ In the AWS Console, create a new Lambda function (Node.js runtime).
+ Paste the provided Lambda code.
+ Ensure the Lambda function has the necessary IAM role to access DynamoDB and CloudWatch.
+ Save and deploy the function.
![Screenshot 2025-02-24 122931](https://github.com/user-attachments/assets/716623ee-409e-4d11-a7e3-fac2ee686b34)

3. Set Up API Gateway

+ Create a new API in API Gateway.
+ Create methods (GET, POST, PATCH, DELETE) linked to the Lambda function.
+ Enable CORS.
+ Deploy the API to a stage.
![Screenshot 2025-02-24 131145](https://github.com/user-attachments/assets/23f6e16e-d225-4ba6-bc55-d1c6addbf745)

5. Configure CloudWatch

+ CloudWatch logging is enabled by default for Lambda.
+ Check the CloudWatch console to review logs and monitor requests.
![Screenshot 2025-02-24 124222](https://github.com/user-attachments/assets/28e4077f-b17b-45ff-bd99-acab09d083c8)
