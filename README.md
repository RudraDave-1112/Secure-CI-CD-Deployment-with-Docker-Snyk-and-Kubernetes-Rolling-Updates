# Secure-CI-CD-Deployment-with-Docker-Snyk-and-Kubernetes-Rolling-Updates
Link for Packages and Report: https://drive.google.com/file/d/1DJuz7Z0E-7Ri66PySoAE_OGXqf9xUONG/view?usp=drive_link

Analyzed Docker image vulnerabilities via Snyk; initially found 5 critical and 23 high issues. Updated dependencies in the fix branch, reducing to 1 high issue. Used Terraform and Kubernetes with rolling updates to deploy both versions, validating improved security and deployment stability.
This lab focused on integrating secure DevOps practices within a CI/CD pipeline using Docker, Terraform, Snyk, and Kubernetes. The primary objective was to identify and remediate known vulnerabilities in containerized applications and deploy secure builds using rolling update strategies.

The infrastructure was provisioned using Terraform, enabling consistent and repeatable deployments of Kubernetes clusters. This approach allowed seamless deployment of containerized applications across environments while maintaining infrastructure as code (IaC) principles.

The application image was built and pushed to Docker Hub, which served as the central image registry. From there, vulnerability scanning was conducted using Snyk, a security platform for open-source and container security. The initial scan of the latest branch reported 5 critical and 23 high-severity vulnerabilities, primarily due to outdated dependencies listed in the pom.xml file.

A fix branch was created, where dependency versions were updated to resolve these issues. Upon rescanning, the results showed significant improvement—0 critical and only 1 high vulnerability remained. This validated the effectiveness of dependency upgrades in improving the security posture of the application.

The next phase involved deploying both versions of the application (latest and fix) to the Kubernetes cluster using the Rolling Update strategy. This ensured zero downtime during the update process by gradually replacing old pods with new ones.

Both deployments were validated via kubectl commands and confirmed through application outputs. The rolling update mechanism proved effective, with both versions being deployed and accessible in a controlled, staged manner.

This lab demonstrated practical implementation of DevSecOps by combining secure coding practices, infrastructure automation, and resilient deployment strategies—all of which are critical components of modern cloud-native operations.

