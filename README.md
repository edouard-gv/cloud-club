# Cloud Club

A step by step tuto to progressively create lambdas on AWS.

The goal is to have a CI/CD full functioning with infra as code as soon as possible. Linking to other services 
will be done in a second time.

The steps are thus proposed in the following order

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

Some notes:
- on windows, if using *git bash* as terminal, to launch sam cli, type 'sam.cmd', and not ~~sam~~ .
- on windows, if python installed with anaconda and not added to classpath, you can launch sam from anaconda prompt
- had to regenerate access keys and token, and reconfigure aws CLI with this new pair, for it didn't handle cloudformation requests (sam deploy) 
- no need to provide --region parameter if given during aws cli configuration (note : Paris = _eu-west-3_ ).


### 3-Travis-Github-pipeline
Deploy your code from a github repository using a Raw Travis CI pipeline.

By RAW we mean not using [~~travis lambda provider~~](https://docs.travis-ci.com/user/deployment/lambda/) that does all the magic, but help us learn not much.

Tutorial: https://dev.to/codevbus/deploy-aws-lambda-functions-with-aws-sam-cli-and-travis-ci-part-2-2goh
(Verify that SAM still need Python 2?)

What can has been changed:
- access to AWS key id and secret key through (secret) configuration variable provided by travis. 