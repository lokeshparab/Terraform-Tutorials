# Requirements
## Install AWS CLI (Windows)
* Download and run the AWS CLI MSI installer for Windows (64-bit): [click here](https://awscli.amazonaws.com/AWSCLIV2.msi) 
* Open MSI File this will open Wizard Installation
* Check aws cli install by using this command on cmd given below:
    ```
    aws --version
    ```
## Config AWS Crendentials
1. Open the IAM console at [IAM](https://console.aws.amazon.com/iam/). On the navigation menu, choose Users.
2. Choose your IAM user name (not the check box).
3. If not having user then create User and Create Group which have **full granted access administrator**.
3. After that Open the Security credentials tab, and then choose Create access key.
4. To see the new access key, choose Show. Your credentials resemble the following:
    ```
    Access key ID: AKIAIOSFODNN7EXAMPLE
    Secret access key: wJalrXUtnFEMI/K7MDENG/bPxRfiCYEXAMPLEKEY
    ```
5. To download the key pair, choose Download .csv file. Store the .csv file with keys in a secure location.
6. Open CMD or Command Prompt paste this to config aws crendetials:
    ```
    aws configure
    AWS Access Key ID [****************A7WI]: YOUR_ACCESS_KEY
    AWS Secret Access Key [****************83n1]: YOUR_SECRET_ACCESS_KEY
    Default region name [None]: 
    Default output format [None]:
    ```
7. Sucessfully Config AWS Crendentials

# About 

**main.tf** is used to create infrastructure of aws ec2 instant. 

**Note**: *Go through the main.tf file and understand the setup of infrastructure

# Execute Terraform

1. **Initialize the directory**
    ```
    terraform init
    ```
2. **Format and validate the configuration**
    ```
    terraform fmt
    ```
    ```
    terraform validate
    ```
3. **Create infrastructure**
    ```
    terraform apply
    ```
4. **Inspect state**
    ```
    terraform show
    ```

5. **Manually Managing State**
    ```
    terraform state list
    ```

6. **Troubleshooting**
if *terraform validate* fails then 
    * **If you use a region other than us-west-2**, you will also need to change your ami, since AMI IDs are region-specific 
    * **If you do not have a default VPC in your AWS account in the correct region**
    ```
    resource "aws_instance" "app_server" {
        ami                    = "ami-830c94e3"
        instance_type          = "t2.micro"
        +  vpc_security_group_ids = ["sg-0077..."]
        +  subnet_id              = "subnet-923a..."
    }

# Reference
[Build AWS Infrastructure](https://developer.hashicorp.com/terraform/tutorials/aws-get-started/aws-build)