# Serverless-CRUD-API-on-AWS
This project implements a serverless CRUD API using AWS API Gateway, Lambda, DynamoDB, and CloudWatch. The API supports basic create, read, update, and delete operations. Postman was used to test the endpoints, and images of the operations are included in the repository.![Screenshot 2025-02-24 084859](https://github.com/user-attachments/assets/dd1722e8-4a51-4f05-a5e6-6ea552642313)


# Table of Contents
+ [Architecture](https://github.com/Kun009/Serverless-CRUD-API-on-AWS/edit/main/README.md#architecture)
+ [Prerequisites](https://github.com/Kun009/Serverless-CRUD-API-on-AWS/edit/main/README.md#prerequisites)
+ [Setup Steps](https://github.com/Kun009/Serverless-CRUD-API-on-AWS/tree/main#setup-steps)
+ [Lambda Code Overview](https://github.com/Kun009/Serverless-CRUD-API-on-AWS/blob/main/README.md#lambda-code-overview)
+ [Testing](https://github.com/Kun009/Serverless-CRUD-API-on-AWS/edit/main/README.md#testing)

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
![Screenshot 2025-02-24 132637](https://github.com/user-attachments/assets/1e9eb8b7-e034-4372-a094-a2eaa8c6c063)


## Lambda Code Overview 
The Lambda function handles CRUD operations based on the HTTP method. It uses AWS SDK v3 commands for DynamoDB interactions. Check the Lambda.mjs for the code.


## Testing 
1. Use Postman

+ Send a GET request to retrieve tasks.
  
+ Send a POST request with JSON body { "name": "Sample Task", "completed": false } to create a task.
![Screenshot 2025-02-24 122835](https://github.com/user-attachments/assets/003d5796-d02d-4878-aa88-517651553803)

+ Send a PATCH request with JSON body { "id": "<task-id>", "name": "Updated Task", "completed": true } to update a task.
![Screenshot 2025-02-24 123305](https://github.com/user-attachments/assets/383bfe0a-6d25-4e5f-b3a4-fd8b4a605f1b)

+ Send a DELETE request with JSON body { "id": "<task-id>" } to delete a task.
![Screenshot 2025-02-24 123742](https://github.com/user-attachments/assets/eefc577d-bd73-42e8-897e-9dd9cbdc7ef6)

2. Check Postman Responses

+ Validate response status codes and messages.
  
+ Review the changes in the CRUD table.
  
Below is the image of the details posted
![Screenshot 2025-02-24 123245](https://github.com/user-attachments/assets/192debdf-0de8-42fe-97b2-f81fa836b9fd)

Below is the image of the details updated where the completed for email check became false
![Screenshot 2025-02-24 123320](https://github.com/user-attachments/assets/31211dac-b20a-4e5d-8905-c3e130854508)

Below is the image for delete operation where task was deleted 
![Screenshot 2025-02-24 123917](https://github.com/user-attachments/assets/d226ad53-ec10-4ef6-a899-b06a72ace357)


3. Verify CloudWatch Logs

+ Confirm that logs capture the requests and responses.

![Screenshot 2025-02-19 231442](https://github.com/user-attachments/assets/c27021ae-9c82-4c32-8185-786b99298784)
