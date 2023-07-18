# A Typical Business organisation

**Assumption that our startup using the following:**

**Google Apps:**  For emails, docs and other shared files.

**Marketing:**  Mixpanel, Google Analytics

**Code Repository:** Github / Bitbucket / Gitlab (Instead of AWS services)

**Database:** RDS, DynamoDB or NOSQL on EC2.

\*No one will have full IAM access unless he is architect or above.
Pipelines will be used from the code repository. (Either Bitbucket pipelines or Gitlab Pipelines) (Instead of AWS services)

## Role 1:  Business Owner

**Description:**  Ultimate owner of the business / CEO / Founder

Everything including billing. Owners should setup the Multi Factor Authentication. All the others users (including admin/ctos) should only login via IAM logins. Owner can set up an IAM role to share billing settings with CTO but this should be done via console.

**AWS Resource Permissions:** Everything from the workplace IP (Static IP)


## Role 2:  Frontend Developer

**Description:**  Responsible for development of user facing front-end.

Needs permission to debug issues related to frontend and setup some notifications if needed.

**AWS Resource Permissions:**

- Code commit
- Cloudfront to check and handle caching issues if needed.
- Simple Storage Service (S3)
- SQS
- SNS
- Route53

## Role 3:  Backend Developer

**Description:**  Responsible for development and monitoring of backend APIS

Needs permission to debug issues related to frontend and setup some notifications if needed.

**AWS Resource Permissions:**

- Code commit
- Cloudfront to check and handle caching issues if needed.
- EC2
- Lambda
- RDS
- Cloudsearch
- Elastic Search
- Simple Storage Service (S3)
- API Gateway
- CloudTrail
- SQS
- SNS
- Key Management
- Elastic Beanstalk
- Cloud Trail
- XRay
- Cognito



## Role: Manual QA Specialist*

Doesnt need any access from AWS. Usually they test on browsers, but scope is in general very vague.

## Role 4: Automated QA Specialist

**Description:** This job is closer to backend developer. As he will write the QA tests and Devops guys is responsible to run them as a part of deployment process.

**AWS Resource Permissions:**

  - s3
  - sns
  - sqs
  - cloudfront
  - ec2
  - lambda
  - rds
  - s3
  - dynamodb
  - cloudsearch
  - es
  - logs
  - apigateway
  - cloudtrail
  - kms
  - elasticbeanstalk
  - cognito
  - xray