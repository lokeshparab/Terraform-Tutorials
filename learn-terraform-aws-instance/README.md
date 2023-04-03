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