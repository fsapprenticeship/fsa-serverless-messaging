# react-sls-messaging
Simple, functional messaging system w/notifications built in React with 5 Serverless Functions.

## Serverless Messaging in 5 Functions

# Tools
- Serverless framework
- AWS Lambda
- DynamoDB
- AWS Cognito

# Process

1. `$ npm install` package.json in root.
2. Update serverless.yml with service-name, preferred region.
3. Create two AWS DynamoDB Tables, with the following attributes:
Messages
ThreadId (PrimaryAttribute Key)| MessageId | SenderId | RecipientId | Content | Attachment | CreatedAt
4. Notifications
RecipientId | SenderId | NotificationId | NotificationMessage | CreatedAt | Thread | Unread
5. Deploy SLS functions with SLS Deploy

## To-Do

1. Front-end implementation (Coming Soon)
2. ApiGateway helper function for authentication using AWS Sig4 for IaM.
3. Kinesis Stream implementation to enable 'real-time' chat.


# Shoutout to Anomaly Innovations
They made a a great ES7 starter pack, which I have modified to remove a few things to decrease complexity & increase security. I've removed the information about setting sls .env variables, as I would not recommend defining them in the serverless.yml file. Instead, use AWS Parameter Store, store the environment variables as encrypted keys for maximum security. I've also removed serverless-offline.

Below are links to Anomaly Innovation's serverless quick-start.

# Serverless Node.js Starter

A Serverless starter that adds ES7 syntax, serverless-offline, environment variables, and unit test support. Part of the [Serverless Stack](http://serverless-stack.com) guide.

[Serverless Node.js Starter](https://github.com/AnomalyInnovations/serverless-nodejs-starter) uses the [serverless-webpack](https://github.com/serverless-heaven/serverless-webpack) plugin, [Babel](https://babeljs.io), [serverless-offline](https://github.com/dherault/serverless-offline), and [Jest](https://facebook.github.io/jest/).