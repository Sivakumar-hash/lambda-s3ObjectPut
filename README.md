# AUTOMATION WITH Lambda-s3ObjectPut integrate with IIS WebServer :


Steps to do :

Launch Windows Server 2012 R2 Base image with size t2.micro with security group 80 http

Run the script to install IIS package

Also disable IE enahanced security from SERVER MANAGER

create folder under C:\

mkdir ANCILE

Go to IIS manager > feature view > Directory browsing > enable and update the home directory 

create a bucket with public read access

Enable Static Website Hosting on S3 bucket with index.html as the index document.

Upload a test index.html file to the S3 bucket

create lambda with function name test and give the role 

choose “Create new role from template(s)
Select “S3 object read-only permissions from Policy templates drop down

 AWS IAM under “Roles” select role you just created
Attach polices “AmazonS3FullAccess” (you will need this to be able to write to the S3
bucket

Go to lambda and add the code that i have mention above with filename "lambda-s3_current_time" > deploy the change and run after that u will see the current time and hello world in content of file.
