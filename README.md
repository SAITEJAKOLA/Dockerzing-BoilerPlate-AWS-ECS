# Dockerzing-BoilerPlate-AWS-ECS

Dockerzing an boilerplate template NEST application and Deploying the applicationusing AWS ECS.

<!-- Building the image -->

docker build -t helloworldapp .

<!-- Running the image -->

docker run -p 80:80 helloworldapp

<!-- Pushing image to ECR

Make sure that you have the latest version of the AWS CLI and Docker installed. For more information, see Getting Started with Amazon ECR .
Use the following steps to authenticate and push an image to your repository. For additional registry authentication methods, including the Amazon ECR credential helper, see Registry Authentication .
Retrieve an authentication token and authenticate your Docker client to your registry. Use the AWS CLI: -->

aws ecr-public get-login-password --region us-east-1 | docker login --username AWS --password-stdin public.ecr.aws/i6c0p3v3

<!-- Note: If you receive an error using the AWS CLI, make sure that you have the latest version of the AWS CLI and Docker installed.
Build your Docker image using the following command. For information on building a Docker file from scratch see the instructions here . You can skip this step if your image is already built: -->

docker build -t helloworldrepository .

<!-- Build your Docker image using the following command. For information on building a Docker file from scratch see the instructions here . You can skip this step if your image is already built: -->

docker tag helloworldrepository:latest public.ecr.aws/i6c0p3v3/helloworldrepository:latest

<!-- Run the following command to push this image to your newly created AWS repository: -->

docker push public.ecr.aws/i6c0p3v3/helloworldrepository:latest
