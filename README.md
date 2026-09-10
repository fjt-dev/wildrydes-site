# wildrydes-site

This is a repository for learning hands-on how to build a simple serverless application on AWS.

URL: [https://aws.amazon.com/jp/getting-started/hands-on/build-serverless-web-app-lambda-apigateway-s3-dynamodb-cognito/](https://aws.amazon.com/jp/getting-started/hands-on/build-serverless-web-app-lambda-apigateway-s3-dynamodb-cognito/)

## Modifications Made This Time

Points modified to align with the current AWS environment.

- Lambda Runtime
  - Material: Node.js 16.x
  - Current: Node.js 22.x

- AWS SDK
  - Material
    ```
    const AWS = require('aws-sdk');
    const ddb = new AWS.DynamoDB.DocumentClient();
    ```
  - Current
    ```
    import { DynamoDBClient } from '@aws-sdk/client-dynamodb';
    import { DynamoDBDocumentClient, PutCommand } from '@aws-sdk/lib-dynamodb';
    ```

- Module Format
  - Material: CommonJS
    ```
    require(...)
    exports.handler = ...
    ```
  - Current: ES Modules
    ```
    import ...
    export const handler = ...
    ```

## Overview

The application's HTML-based user interface allows users to specify where they want to ride. The application also interacts with a backend RESTful web service to submit requests and dispatch a nearby unicorn. Furthermore, the application provides functionality for users to register and log in to the service before requesting a unicorn ride.

## Application Architecture

[AWS Lambda](https://aws.amazon.com/jp/lambda/) \
[Amazon API Gateway](https://aws.amazon.com/jp/api-gateway/) \
[Amazon DynamoDB](https://aws.amazon.com/jp/dynamodb/) \
[Amazon Cognito](https://aws.amazon.com/jp/cognito/) \
[AWS Amplify](https://aws.amazon.com/jp/amplify/)

## Modules

1. Host a Static Website (15 mins): Configure AWS Amplify to host the static resources of the web application with built-in continuous deployment.
2. Manage Users (30 mins): Create an Amazon Cognito user pool to manage user accounts.
3. Build a Serverless Backend (30 mins): Build a backend process to handle requests from the web application.
4. Deploy a RESTful API (15 mins): Use Amazon API Gateway to expose the Lambda function built in the previous module as a RESTful API.
5. Terminate Resources (10 mins): Terminate all resources created in this tutorial.
