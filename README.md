# Kubernetes Project: Deploying a Microservices Application with Helm

## Objective

In this project, you will reuse the **Online Boutique** application that you containerized in the first project and deploy it on a Kubernetes cluster.

The goal is to practice deploying a complete microservices architecture using **Helm** and **Helmfile**, while also working with common production tools such as **Ingress NGINX** and **cert-manager**.

## Tasks

1. Reuse the Docker Project
    - Reuse the Dockerfiles created for each microservice.
    - Ensure that the images are built and available in the GitLab Container Registry.

1. Write Helm Charts
    - Create a Helm chart for each microservice, or a global chart with subcharts.
    - Each chart must include at least:
        - A Deployment
        - A Service
        - Environment variable management
        - Probes (`readinessProbe`, `livenessProbe` where relevant)
    - **Publish the Helm chart to the GitLab packages section of your project**

1. Centralize Deployment with Helmfile
    - Create a `helmfile.yaml` file to deploy the entire application.
    - Organize configuration files (`values.yaml`) clearly.

1. Deploy on a local Kubernetes Cluster
    - 
    - The final deployment must be done using Helmfile on this machine.

1. Configure an Ingress Controller (NGINX)
    - Install Ingress NGINX in the cluster.
    - Configure an Ingress to expose the application (at least the frontend) via HTTP.

1. Configure cert-manager with Let's Encrypt (staging)
    - Install cert-manager in the cluster.
    - Configure a ClusterIssuer using Let's Encrypt ACME staging to generate a valid TLS certificate for the frontend (even if self-signed).


## Expected Deliverables

- A Git repository containing:
    - Helm charts (at least one per microservice) published as GitLab packages
    - A complete and functional `helmfile.yaml`
    - All necessary `values.yaml` files
    - A `README.md` describing installation and deployment steps
- A working deployment (**this will also be tested live during the oral exam**)
- Functional configuration of Ingress NGINX
- A TLS certificate obtained via cert-manager and Let's Encrypt ACME staging
- *(Optional)* Screenshots showing correct operation or `kubectl` command outputs

> ⚠️ **Important**
>
> Please note that the Git repository must be part of a **private group** to which only you and **@Ashley.Caselli** have access.  
> Refer to the instructions from the Docker project if you missed that.

## Tips

- Start by deploying services without Ingress, then add Ingress and TLS once everything works.
- Use domains like `.nip.io` or `.sslip.io` to test certificates without configuring custom DNS.
- Validate step by step (deploy one service first, then progressively add others).