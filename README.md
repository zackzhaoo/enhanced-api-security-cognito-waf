# enhanced-api-security-cognito-waf
Introduction: Following these steps will assist you in creating a secure infrastructure for accessing your API, through the integration of Cognito-generated tokens to ensure only authorized requests are granted access. This approach adopts a Zero trust strategy, and trust is evaluated at multiple layers for redundancy in security, including the prevention of SQL and cross-site scripting (XSS) attacks. 

Installations:
- none

Steps:

Part 1: Deploy the Infrastructure Using CloudFormation
1.1 Deploy the First CloudFormation Stack
1. Open the AWS Management Console and navigate to the S3 console
2. Create a bucket with a unique name a slect us-east-1 (N.Virginia) as the region and note this bucket name. Leave everything else as default.
3.  Download the 3 Lambda deployment packages, as they will be used by the CloudFormation stack to create Lambda functions
  - rds-create-table.zip
  - rds-query.zip
  - python-requests-lambda-layer.zip
4. Upload all 3 packages to your new bucket, keep the file names as is
5. Download the first CloudFormation template (cloudformation-section1.yaml)
6. Open the CloudFormation console and create a stack, enusring us-east-1 (N.Virginia) is selected as your region
7. Upload the stack template you just downloaded as a template, choose next
8. For the stack name use walab-api and enter the name of the bucket you just created in the S3BucketName parameter. You can leave all other paremeters as the default value. Choose next twice to get the Review step.
