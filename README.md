# docker-aws
Docker image and AWS cloudformation simple template.

# What is this for
This is a simple template that push a .yml file into AWS and creates a load balanced server, it is also deploying 
a docker image and a docker app into the 2 load balanced servers, and runs a very simple HTML page, with just
a versioning number

# How to change the content in this app
 1. First you need to clone the repo local in your machine Open a terminal on your machine, run the following command `git clone https://github.com/stefanogram/docker-aws`
 2. Make sure that you have the latest version of this image `git pull .`
 3. Open the files and perform any change you need to the HTML page, change the version, etc, and the commit your changes and push them on Gitub, create a new PR and wait for you PR to get approoved
--> More details: https://devops.stefanogramm.com/devops/

# How to deploy the server
You need to have lates AWS CLI installed in your machine --> https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html
You will also need to have the correct IAM --> https://docs.aws.amazon.com/cli/latest/userguide/cli-services-iam-new-user-group.html assigned to you..

 1. Once you clone the project copy the cloudformation.yml in a new directory where you want to run your project
 2. Edit and add your details ( AWS image ID etc). Once you are ready, within the same directory that your cloudflormation.yml is. run the command and name your deployment stack name (--stack-name <name>) that you ( and the team) will be able to recognize:
 `aws cloudformation create-stack --stack-name stefano --template-body file://cloudformation.yml`
 3. If you want you can check the status of the deployment with this simple `while true` script:

    ```
    while true; do clear; aws cloudformation describe-stack-events --stack-name stefano; sleep 5; done
    ```



