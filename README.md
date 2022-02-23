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
aws cloudformation create-stack --profile demo --stack-name assignment --template-body file://csye6225-infra.yml
OR
aws cloudformation deploy --profile demo --stack-name assignment --template-file csye6225-infra.yml

# Update Stack
aws cloudformation update-stack --profile demo --stack-name assignment --template-body file://csye6225-infra.yml

# Delete Stack
aws cloudformation delete-stack --profile demo --stack-name assignment                                   
```