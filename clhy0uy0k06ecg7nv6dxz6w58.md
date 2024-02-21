---
title: "Fitness Company Scales Up Data Processing with Amazon SQS and Lambda Functions."
seoTitle: "Management of high volume of data with Amazon SQS and Lambda Functions"
datePublished: Sun May 21 2023 23:00:39 GMT+0000 (Coordinated Universal Time)
cuid: clhy0uy0k06ecg7nv6dxz6w58
slug: fitness-company-scales-up-data-processing-with-amazon-sqs-and-lambda-functions
cover: https://cdn.hashnode.com/res/hashnode/image/upload/v1683725652452/1e4f3295-c2d2-4f1f-af67-8450808853f9.jpeg
tags: lambda, aws, cloud-computing, sql, aws-lambda

---

There is a fitness company that had a lot of subscribers who were keen on keeping track of their workouts.  
  
The company realized that they needed to find a solution to handle the influx of workout data for their subscribers. They decided to build their infrastructure in AWS and use a Lambda function to process the data.  
  
However, they faced a new challenge. They needed to ensure that the data was processed in the order that it was received. The team quickly realized that if the data was processed out of order, it could result in inaccurate tracking of users' workouts.  
  
To solve this problem, the team decided to use Amazon Simple Queue Service (SQS) to manage the processing of the data. Whenever a user uploaded their workout data, it would be added to the end of the queue. The Lambda function would then process the data in the order that it was received, one message at a time.  
  
By using SQS, the company could ensure that the data was processed in the correct order and that no data was lost or duplicated. Additionally, they could easily scale up their processing capacity by adding more Lambda functions to handle the workload.  
  
In conclusion, using Amazon SQS to manage the processing of workout data for the fitness company was a smart decision. It allowed the company to handle a large volume of data while ensuring that it was processed in the correct order. This, in turn, resulted in a better user experience for the subscribers, and helped the company to continue to grow and thrive.  
  
AWS Lambda is a serverless compute service that enables users to run code without provisioning or managing servers. In the story, the fitness company uses Lambda to process workout data uploaded by subscribers.  
  
Amazon Simple Queue Service (SQS) is a fully managed message queuing service that enables users to decouple and scale microservices, distributed systems, and serverless applications. In the story, the fitness company uses SQS to manage the order in which workout data is processed by Lambda.