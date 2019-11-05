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

branch [AWS-lambda-2-CLI](../../tree/AWS-lambda-2-CLI)

### 3-Travis-Github-pipeline
Deploy your code from a github repository using a Raw Travis CI pipeline.

By RAW we mean not using [~~travis lambda provider~~](https://docs.travis-ci.com/user/deployment/lambda/) that does all the magic, but help us learn not much.

Mixing the tutorial: https://dev.to/codevbus/deploy-aws-lambda-functions-with-aws-sam-cli-and-travis-ci-part-2-2goh on the code of previous step. The most difficult to adapt are the roles of the travis service account.

branch [AWS-lambda-3-travis](../../tree/AWS-lambda-3-travis)

_**ACHIEVEMENT UNLOCKED: FULL CI-CD with infra as code.**_

### 4-other-CI-CD-tools
What about configuring other CI/CD tools such as Jenkins or Gitlab?
 
### 6-diving-into-services
Adding access to database and s3 in your lambda

### 6-a-real-front-end
You can go further here for a fullstack web application: https://github.com/aws-samples/lambda-refarch-webapp pointed by https://aws.amazon.com/lambda/ 

### 7-understanding-security

## AWS EC2 and Ansible
