# Capstone Project: Resume Bullets

### Cloud Infrastructure & DevOps

* **Designed and deployed a reusable cloud network foundation on AWS using Terraform**, creating a multi-subnet VPC, routing tables, and an internet gateway to establish a secure and scalable environment for application deployment.
    * *Artifacts: [Terraform Code](https://github.com/RezaAramjou/terraform/tree/main/examples/ec2-vpc-demo), [Architecture Diagram](https://github.com/RezaAramjou/portfolio/blob/main/assets/architecture.png)*

* **Automated infrastructure validation and application testing by building CI/CD pipelines with GitHub Actions**, reducing potential deployment errors by automatically formatting Terraform code, validating syntax, and running smoke tests on container builds.
    * *Artifacts: [Terraform CI](https://github.com/RezaAramjou/terraform/blob/main/.github/workflows/terraform-ci.yml), [Docker CI](https://github.com/RezaAramjou/docker-app/blob/main/.github/workflows/ci.yml)*

* **Containerized a Python Flask web application using Docker**, ensuring consistent and portable deployments by defining a reproducible build process in a Dockerfile and publishing documentation for local testing.
    * *Artifact: [Dockerized Application](https://github.com/RezaAramjou/docker-app)*

* **Developed an automated EC2 startup script (`user data`) to deploy the containerized application on boot**, minimizing manual configuration and ensuring the application was immediately available after infrastructure provisioning.
    * *Artifact: [User Data Script](https://github.com/RezaAramjou/terraform/blob/main/examples/ec2-vpc-demo/userdata.sh)*

* **Implemented a local testing environment using LocalStack and Docker Compose**, enabling rapid, cost-free iteration and validation of Terraform configurations by simulating AWS services locally.
    * *Artifact: [LocalStack Configuration](https://github.com/RezaAramjou/labs/blob/main/docker/localstack/docker-compose-localstack.yml)*
    
### Cybersecurity (Offensive & Defensive)

* **Conducted a penetration test on a target web application, identifying and exploiting Critical and High-risk vulnerabilities**, including SQL Injection for authentication bypass and Stored XSS for session compromise.
    * *Artifact: [Penetration Test Report](https://github.com/RezaAramjou/pentest/blob/main/reports/juice-shop-report.md)*

* **Deployed and configured a Splunk SIEM to ingest, parse, and monitor application logs**, establishing a centralized security monitoring capability for a simulated production environment.
    * *Artifact: [Log Ingestion Script](https://github.com/RezaAramjou/siem-lab/blob/main/elk/load-logs.sh)*

* **Developed a custom detection rule in Splunk to create real-time alerts for observed malicious activity**, successfully identifying a SQL injection attack by building a query to detect its specific log signature.
    * *Artifact: [Detection Rule Documentation](https://github.com/RezaAramjou/siem-lab/blob/main/rules/suspicious-web-sqli.yml)*

* **Authored a professional penetration test report to communicate findings to stakeholders**, detailing the scope, methodology, technical risk, business impact, and actionable remediation steps for each vulnerability.
    * *Artifact: [Final Report](https://github.com/RezaAramjou/pentest/blob/main/reports/juice-shop-report.md)*

* **Remediated application-level vulnerabilities and hardened infrastructure configuration**, applying input sanitization to prevent XSS, replacing vulnerable code to fix SQLi, and restricting overly permissive firewall rules to reduce the system's attack surface.
    * *Artifacts: [Hardened Application Code](https://github.com/RezaAramjou/docker-app), [Hardened Infrastructure Code](https://github.com/RezaAramjou/terraform/blob/main/examples/ec2-vpc-demo/security.tf)*
