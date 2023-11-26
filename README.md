# CECS_574_Cloud_IaC_K8s

# Eccommerce Project Deployment Guide

This guide provides an overview of how to deploy the frontend and backend components of our project, manage infrastructure with Terraform, automate deployment with Jenkins, and configure Kubernetes resources with Helm.

## Terraform

The Terraform directory contains IaC (Infrastructure as Code) scripts that define the cloud resources required for the project.

### Usage Instructions

1. Navigate to the Terraform directory.
2. Fill in the required variables in `values.tfvars` with your specific cloud resource values.
3. Initialize Terraform using `terraform init`.
4. Apply the configuration using `terraform apply -var-file="values.tfvars"`.

## Jenkins

The Jenkinsfile contains the definitions for the CI/CD pipeline stages.

1. Set up a Jenkins pipeline pointing to your repository.
2. Replace all instances of `${VARIABLE_NAME}` in the Jenkinsfile with your specific values (e.g., AWS credentials, repository URLs).

## Helm

The Helm directory provides the necessary charts to deploy the applications on Kubernetes.

### Deployment Instructions

1. Navigate to the Helm directory.
2. Adjust `values.yaml` as needed to configure the application pods, LoadBalancer, deployment sets, etc.
3. Deploy to your Kubernetes cluster using `helm install` or `helm upgrade`.

## Manual Steps

### Adding ELB URLs to Route53 Records

After deploying the application, you need to manually update the Route53 DNS records with the ELB URLs.

1. Retrieve the ELB URLs from the AWS Management Console.
2. Navigate to the Route53 service in the AWS Console.
3. Select your hosted zone and add a new record set.
4. Input the ELB URL as the alias for the A or CNAME record.

## Conclusion

This README provides the necessary steps to set up, configure, and deploy both the frontend and backend parts of the application, manage infrastructure with Terraform, automate deployments with Jenkins, and configure Kubernetes resources with Helm. Please ensure to replace placeholder values with your specific configuration details.
