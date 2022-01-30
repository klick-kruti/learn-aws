## Setting Up the Serverless Framework with AWS

### References 
[Serverless Framework](https://www.serverless.com/framework/docs)
  - a cli to help develop - deploy - troubleshoot ..
  
[Serverless + AWS](https://www.serverless.com/framework/docs/providers/aws/guide/intro)
  - serverless framework integrates with any provider we are using aws. 
  - this will help us create AWS lambda functions  and the AWS infrastructure.

[Serverless + AWS Credentials ](https://www.serverless.com/framework/docs/providers/aws/guide/credentials)
  - create account on AWS
  - Create IAM user on AWS - prefix it with serverless 
  - have admin access/polic set 


### Setup IAM account on AWS

** prerequisite : an account on AWS

1. We need to create IAM user on the AWS console (aka the website). The idea behing this account creation is to allow the tool serverless to access aws with programatic access. Add Administrator access :  policy access
2. once the user is created - you will have access key and private key user 


### Install Serverless Framework: 

> 'The Serverless Framework needs access to your cloud provider account so that it can create and manage resources on your behalf.'

1. via terminal * you need node installed and it is installed globally hence the -g

     `npm install -g serverless` 
     
2. Next is to configure your credentials of AWSW so it works with serverless framework. There are multiple ways to set these credentails. See the ref above on more details. Here we are going to do it via AWS cli. 

  2.1  Install (AWS Cli)[https://docs.aws.amazon.com/cli/latest/userguide/cli-chap-getting-started.html] first. 
  
  2.2  Once it is installed type 
  
      `aws configure`
      
  2.3  This will prompt you to enter the AWS Access key and secret that you obtained when you set up the IAM user account from Step 1. Enter the details in this from your IAM setup/
  
  2.4 Profile? 
  
  
  
## Creating a new Serverless Project and deploying a Lambda

[services](https://www.serverless.com/framework/docs/providers/aws/guide/services)


 ### Services 
 This is the project main file - this is where we will hold the infomation and configuration of the functions triggers and infrastucture setup. This is where you start first.
 
 > A service is like a project. It's where you define your AWS Lambda Functions, the events that trigger them and any AWS infrastructure resources they require, all in a file called serverless.yml.


1. Create the Services - the serverless framework has bulit in templates that we can utilize - we will use aws + node 

`serverless create --template aws-nodejs --path learn-aws`

2. This will create boiler plate code - with two files serverless.yml and handler.js

3. Serverless.yml

> serverless.yml
Each service configuration is managed in the serverless.yml file. The main responsibilities of this file are:

  >Declare a Serverless service
  
  >Define one or more functions in the service
  
  >Define the provider the service will be deployed to (and the runtime if provided)
  
  >Define any custom plugins to be used
  
  >Define events that trigger each function to execute (e.g. HTTP requests)
  
  >Define a set of resources (e.g. 1 DynamoDB table) required by the functions in this service
  
  >Allow events listed in the events section to automatically create the resources required for the event upon deployment
  
  >Allow flexible configuration using Serverless Variables

4. handler.js 

> The handler.js file contains your function code. The function definition in serverless.yml will point to this handler.js file and the function exported here.

5. Deploy: to deploy we simply cd into the directory that is has the serverless.yml file and then say serverless deploy


  
