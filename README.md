# DevOpsProject2
Hi everyone! hope you are doing well. 

About this simple project:

Honestly, it's pretty manual. But it reflects a good basis for some of the capabilities that AWS provides for more accurate and efficient management of our application infrastructure.
- At the end you will have a simple rest api app that get POST resuests and send it to a SQS that you are going to create.
- The SQS will triggered the Lambda function that we have here (copy that to a new lambda func in you account).
- The Lambda func will take only the "body" of the massage ( after a validation check), convert it into a CSV file and save it at your S3 bucket (that you will create) with the date & time the message has been received and any name you want with it (check my Lambda code).

Lets see what we have here:

1) So we have a very small rest_api written with python and using flask that listening on port 8080 for posts requests in JSON format and set it to your sqs.
2) We also have a Lambda function. 
3) A Dockerfile and a yaml file to deploy the application with k8s (if you are not using my fist project delete the 2 last lines in the yaml file).

What we are doing:

1) Create the image from my Dockerfile and deploy it. **Download AWSCLI and set your keys because it will copy the "~/.aws" directory for secure connection**.
2) Create Lambda function and copy my code.
3) Create a *Standard que* with SQS with the default settings and trigger it with your lambda func.
4) Create an S3 bucket (Defual settings).
5) Allow your user full access to the SQS and write access for the S3 bucket.
6) Run it. 

Bouns: check how you can get an EMAIL every time the que has been received a new massage.

Good Luck.
