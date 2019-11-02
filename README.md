# Cloud Club

A step by step tuto to progressively learn devops on clouds.

The goal is to have a CI/CD full functioning with infra as code as soon as possible. Linking to other services 
will be done in a second time.

The steps are thus proposed in different order depending on the cloud provider and type of service deployed. Just make steps as small as possible to 
know how to deploy code + infra as soon as possible.

 ## AWS Lambda
 ### 1-Console
 Just create your first lambda through AWS console. Maybe the most
 complexe thing is to create your AWS account :).
 
 Then follow the following tutorial: https://aws.amazon.com/getting-started/tutorials/run-serverless-code/
 
 It's just a Hello World lambda, *without* even API Gateway in front of it in order to
 call it through a Rest Webservice.

### 2-CLI-deploy
Deploy your code from your local machine to your account.

This will ask you to install AWS CLI and AWS SAM CLI, 
 create your first IAM Admin User and Group...

By the way, you will create the API Gateway to access the function through a Rest Webservice.

Tutorial: https://docs.aws.amazon.com/serverless-application-model/latest/developerguide/serverless-getting-started-hello-world.html#serverless-deploy

### 3-Travis-Github-pipeline
Deploy your code from a github repository using a Raw Travis CI pipeline.

By RAW we mean not using [~~travis lambda provider~~](https://docs.travis-ci.com/user/deployment/lambda/) that does all the magic, but help us learn not much.

Tutorial: https://dev.to/codevbus/deploy-aws-lambda-functions-with-aws-sam-cli-and-travis-ci-part-2-2goh
(Verify that SAM still need Python 2?)

### 4-Use-CloudForm
Instead of manually creating the environments in 3, declare it in a Cloudform Template like in 2, but deployoing the infra in the pipeline.

Inspiration from: https://github.com/aws-samples/lambda-refarch-webapp pointed by https://aws.amazon.com/lambda/ 
(taking from it the smallest step, that is only a simple 
CloudForm template).

Having a look at the functionality to export sam yaml configuration from the lambda 
function page?

_**ACHIEVEMENT UNLOCKED: FULL CI-CD with infra as code.**_

### 5-other-CI-CD-tools
What about configuring other CI/CD tools such as Jenkins or Gitlab?
 
### 6-diving-into-services
Adding access to database and s3 in your lambda

### 7-a-real-front-end
In angular or react

Same inspiration than 4, getting a small step further


### 8-understanding-security

## AWS EC2 and Ansible