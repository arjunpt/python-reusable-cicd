# Deployment of dockerized python application to EC2 

Pipeline Overview
The CI/CD pipeline is designed to automate the testing, analysis, and deployment process. Below is an overview of the steps involved:


1. Trigger
The pipeline is triggered by a push or pull request to the main branch of this GitHub repository.
2. Unit Testing (pytest)
Runs unit tests using pytest to ensure the core functionalities of the application work as expected.
3. Code Linting (flake8)
Lints the code using flake8 to verify adherence to PEP8 coding standards, identifying any syntax or style issues.
4. Dependency Security Scan (Snyk)
Performs a security scan of the application's dependencies using Snyk to detect vulnerabilities in the code.
5. Static Code Analysis (SonarQube)
Integrates with SonarQube to perform static code analysis. This step checks for code smells, bugs, and potential issues in the codebase.
6. Docker Image Creation
Builds a Docker image for the application using the provided Dockerfile. This image contains the application and all necessary dependencies.
7. Docker Image Security Scan (Snyk)
Conducts a security scan on the built Docker image using Snyk to ensure no vulnerabilities exist within the containerized environment.
8. Deployment to AWS
The Docker image is pushed to AWS Elastic Container Registry (ECR).
The image is deployed to an AWS EC2 instance, ensuring that the application is up-to-date and running securely in the production environment.
Requirements


To successfully run this pipeline, the following prerequisites must be met:

Python 3.x
Docker
AWS CLI configured with appropriate credentials
GitHub Actions Secrets:
SNYK_TOKEN
AWS_ACCESS_KEY
AWS_SECRET_KEY
AWS_REGION
EC2_HOST
EC2_SSH_KEY
EC2_USERNAME
SONAR_TOKEN
SONAR_HOST_URL

Architecture:

![image](https://github.com/user-attachments/assets/aac8d41a-1d6f-4fb5-8204-bb440c225325)





folder structure:


![image](https://github.com/user-attachments/assets/1e245629-0b61-4e55-88ec-27912e527c1f)



outcome:

![image](https://github.com/user-attachments/assets/833ccf8b-a87f-44c2-a3d2-9b2a17c9856a)
