# Python Web Application Deployment using AWS CDK

This repository provides an end-to-end solution for deploying a Python web application using the AWS Cloud Development Kit (CDK). The CDK allows you to define infrastructure as code (IAC), automating the creation and management of AWS resources. With this project, you can deploy a fully functional Python web application on an Amazon EC2 instance, complete with a CI/CD pipeline.

## Overview

The deployment involves setting up a range of AWS services to create a complete environment for hosting and deploying the Python web application. The main components of this deployment are:

- **EC2 Instance**: An Amazon EC2 instance will host the Python web application. The instance is configured with the necessary IAM role and security groups to ensure secure and controlled access.

- **Amazon VPC**: The Virtual Private Cloud (VPC) provides network isolation for your resources. The VPC in this setup has public subnets to allow internet connectivity to the EC2 instance.

- **CI/CD Pipeline**: A CodePipeline is created to automate the build and deployment of the Python web application. This pipeline includes stages for source code retrieval, application building, and application deployment.

- **Security Groups**: Security groups are defined to control inbound and outbound network traffic to the EC2 instance, ensuring secure communication.

- **IAM Permissions**: Identity and Access Management (IAM) roles and policies are established to grant necessary permissions to the EC2 instance, CodePipeline, and other resources.

## Prerequisites

Before getting started, ensure you have the following:

1. **AWS Account**: An active AWS account is required to deploy resources.
2. **AWS CDK**: Install the AWS CDK on your local development environment using npm:

   ```bash
   npm install -g aws-cdk-lib
   ```

3. **GitHub OAuth Token**: Obtain a GitHub OAuth token to access the source code repository.
   
## Deployment Steps

Follow these steps to deploy the Python web application:

1. **Clone the Repository**: Clone this repository to your local machine:

   ```bash
   git clone https://github.com/sobebarali/sample-python-web-app.git
   ```

2. **Navigate to the Stack Directory**: Move to the directory containing the AWS CDK stack:

   ```bash
   cd sample-python-web-app
   ```

3. **Install Dependencies**: Install the required dependencies using npm:

   ```bash
   npm install
   ```

4. **Configure GitHub Token**: Store your GitHub OAuth token as a secret in AWS Secrets Manager with the name `github-oauth-token`.

5. **Deploy the Stack**: Deploy the AWS CDK stack:

   ```bash
   cdk deploy
   ```

6. **Monitor Deployment**: Monitor the deployment progress in the AWS Management Console under AWS CodePipeline.

7. **Access the Application**: After a successful deployment, access the deployed Python web application using the EC2 instance's public IP address.

## Cleanup

To avoid ongoing charges, delete the AWS resources created by the stack:

```bash
cdk destroy
```

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Acknowledgments

This project showcases the power of AWS CDK for automating infrastructure deployment and enabling continuous integration and deployment for Python web applications. Feel free to use it as a starting point for more complex projects.

## Contact

If you have any questions or need assistance, please don't hesitate to reach out to the project maintainers. We're here to help!

Happy coding and deploying!
