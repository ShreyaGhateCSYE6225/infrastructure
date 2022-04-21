# Setting up your AWS infrastructure using CloudFormation
## Prerequisites for building and deploying your Template locally:
Have an AWS Account, VSCode and AWS CLI configured

## Installation & Run
```bash
# Download this project locally
git clone git@github.com:ShreyaGhateCSYE6225/infrastructure.git
```

```bash
# Build and Run
cd infrastructure 

# Create Stack
aws cloudformation create-stack --profile demo --region us-east-1 --stack-name devdemo --parameters ParameterKey=ImageId,ParameterValue="AMI ID" ParameterKey=S3BucketName,ParameterValue="Bucket Name"  ParameterKey=MyDomainName,ParameterValue="Domain Name" --template-body file://csye6225-infra.yml --capabilities CAPABILITY_NAMED_IAM --profile demo CAPABILITY_AUTO_EXPAND

# Update Stack
aws cloudformation update-stack --profile demo --region us-east-1 --stack-name devdemo --parameters ParameterKey=ImageId,ParameterValue="AMI ID" ParameterKey=S3BucketName,ParameterValue="Bucket Name"  ParameterKey=MyDomainName,ParameterValue="Domain Name" --template-body file://csye6225-infra.yml --capabilities CAPABILITY_NAMED_IAM --profile demo CAPABILITY_AUTO_EXPAND

# Delete Stack
aws cloudformation delete-stack --profile demo --region us-east-1 --stack-name devdemo   

# Command to import SSL Certificate into AWS Certificate Manager 
```shell
aws acm import-certificate --certificate fileb://prod_shreyaghate_me.crt \
      --certificate-chain fileb://prod_shreyaghate_me.ca-bundle \
      --private-key fileb://prod_shreyaghate_me-privatekey \
      --profile demo --region us-east-1
```

