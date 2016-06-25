#### AWS Serverless

Create the project

    mkdir -p ~/GitHub/rkiel
    cd ~/GitHub/rkiel
    git clone https://github.com/rkiel/aws-serverless.git
    cd aws-serverless

# AWS Console

Create a new user

* click **IAM**
* click **Users**
* click **Create New Users**
* enter `aws-serverless`

Generate credentials

* check **Generate an access key for each user**
* click **Create**
* click **Download Credentials**

Grant user permissions

* click **IAM**
* click **Users**
* click **aws-serverless**
* click **Permissions**
* click **Attach Policy**
* type in `admin`
* check **AdministratorAccess**
* click **Attach Policy**

# OS X

Parse out the AWS credentials

```unix
grep aws-serverless ~/Downloads/credentials.csv |awk  -F "\"*,\"*" '{print $2}' > aws_access_key_id.txt
grep aws-serverless ~/Downloads/credentials.csv |awk  -F "\"*,\"*" '{print $3}' > aws_secret_access_key.txt
```

Start up vagrant

```unix
vagrant up

vagrant ssh node

cd /vagrant
```
