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
* type in `power`
* check **PowerUserAccess**
* click **Attach Policy**

# Vagrant

Prepare AWS credentials before starting up Vagrant

```unix
grep aws-serverless ~/Downloads/credentials.csv |awk  -F "\"*,\"*" '{print $2}' > aws_access_key_id.txt
grep aws-serverless ~/Downloads/credentials.csv |awk  -F "\"*,\"*" '{print $3}' > aws_secret_access_key.txt
rm -f ~/Downloads/credentials.csv
```

Start up Vagrant

```unix
vagrant up

vagrant ssh serverless
```
# Serverless

Create a new project called `hello`

```unix
cd /vagrant

serverless project create -n hello -s dev -r us-east-1 -p default -c true

cd hello
mv *.env _meta *.json ..
cat .gitignore >> ../.gitignore
rm .gitignore

cd ..
rmdir hello
```
