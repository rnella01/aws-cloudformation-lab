# AWS CloudFormation lab
- [Create an EC2 instance and attach a Security Group](ec2-template.json)
  ```bash
  $ aws cloudformation update-stack \
      --stack-name my-ec2-stack \
      --template-body file://ec2-template.json \
      --profile skr-dev

  $ aws cloudformation delete-stack \
      --stack-name my-ec2-stack 
  ```
- [LAMP Stack - step 1](lamp-template-01.json)
  ```bash
  $ aws cloudformation create-stack \
      --stack-name lamp-stack \
      --template-body file://lamp-template-01.json \
      --parameters ParameterKey=KeyName,ParameterValue=ec2-dev-lab  \
      --profile skr-dev
  ```
- [LAMP Stack - step 2](lamp-template-02.json)
  ```bash
  $ aws cloudformation update-stack \
      --stack-name lamp-stack \
      --template-body file://lamp-template-02.json \
      --parameters ParameterKey=KeyName,ParameterValue=ec2-dev-lab \
      --profile skr-dev
  ```
- [S3 Website](S3_Website_Bucket.json)
  ```bash
  $ aws cloudformation update-stack \
      --stack-name s3-web-stack \
      --template-body file://S3_Website_Bucket.json \
      --profile skr-dev

  $ aws cloudformation delete-stack \
      --stack-name s3-web-stack \
      --profile skr-dev
  ```