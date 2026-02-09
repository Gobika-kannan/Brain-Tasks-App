# Brain Tasks App 

## Overview
This project demonstrates deploying a production-ready frontend application
using Docker, AWS ECR, AWS EKS (Kubernetes), and CI/CD with AWS CodeBuild
and CodePipeline.
## Repository Note
This repository is forked from the original application source:
https://github.com/Vennilavan12/Brain-Tasks-App
## Docker Implementation
- The application is containerized using Docker
- The container exposes port 80
- The application was tested locally and on EC2

## Amazon ECR
- An Amazon ECR repository named `brain-tasks-app` was created
- The Docker image was tagged and pushed to ECR
- ECR is used as the image source for Kubernetes

## Kubernetes Deployment (AWS EKS)
- An EKS cluster was created using `eksctl`
- Worker nodes were created using EC2
- Kubernetes Service of type LoadBalancer was created
- AWS automatically provide an Elastic Load Balancer

## CI/CD Pipeline
The CI/CD pipeline automates build and deployment.

**Pipeline Flow**
GitHub → CodePipeline → CodeBuild → ECR → EKS

### CodeBuild Responsibilities
- Build Docker image
- Tag and push image to ECR
- Deploy application to EKS using kubectl

### LoadBalancer URL
http://a433533f6268046d281fb48cccf5855a-1431978777.ap-south-1.elb.amazonaws.com/

### LoadBalancer ARN
arn:aws:ec2:ap-south-1:127424156101:instance/i-06d0f9ef2455867a7
## Conclusion
This project successfully demonstrates an end-to-end DevOps workflow.
All DevOps implementation including Dockerization, AWS services,
Kubernetes deployment, and CI/CD pipeline setup was completed.
