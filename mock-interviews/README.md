# Technical Interview Q&A

This document contains common technical interview questions and model answers based on the skills demonstrated in the 30-day capstone project.

---

## 1. Networking

**Q: You need to allow a server to be accessible from the internet over SSH. How would you configure the firewall?**

**A:** I would configure the server's security group or firewall (like UFW) to allow inbound traffic on TCP port 22. To improve security, instead of allowing traffic from anywhere (`0.0.0.0/0`), I would restrict the source to a specific IP address, such as a corporate VPN or a bastion host. In my Terraform project, I implemented this by changing the ingress rule from an open CIDR block to a placeholder for a specific IP.

**Q: Can you explain the difference between a public and a private subnet in a VPC?**

**A:** A public subnet has a route table with a route to an Internet Gateway, allowing resources within it (like a bastion host or web server) to be directly accessible from the internet. A private subnet does not have a route to an Internet Gateway, so its resources (like a database server) are isolated from the internet and can only be accessed from within the VPC. I implemented both in my Terraform project to create a secure network architecture.

---

## 2. Cloud & DevOps

**Q: What is "Infrastructure as Code" and why is it important?**

**A:** Infrastructure as Code (IaC) is the practice of managing and provisioning infrastructure using code and automation tools, like Terraform. It's important because it makes deployments repeatable, version-controlled, and less prone to human error. By defining my entire AWS network in Terraform code, I can deploy the exact same environment reliably every time and track every change through Git.

**Q: In your CI/CD pipeline, what is the purpose of a "smoke test"?**

**A:** A smoke test is a quick, basic test to ensure the most critical functionality of an application is working after a new build. In my Docker CI pipeline, after building the container, I ran a smoke test using `curl` to check the `/health` endpoint. If the application couldn't even start up and respond to a simple health check, the test would fail, preventing a broken build from proceeding.

---

## 3. Penetration Testing & Security

**Q: You've found a SQL Injection vulnerability. How would you explain the business risk to a non-technical manager?**

**A:** I would explain that a SQL Injection flaw allows an attacker to bypass security controls, like the login page, and directly control our database. This could lead to a catastrophic data breach where an attacker steals all of our customer data, or they could delete or modify our data, causing a major service outage. In the project, I used this to log in as the administrator, proving it could lead to a full system compromise.

**Q: What is the difference between a tool like Nmap and a tool like Splunk?**

**A:** Nmap is an active reconnaissance tool used by attackers (or pentesters) to scan a network and discover hosts, open ports, and running services. It's an *offensive* tool. Splunk is a SIEM, a *defensive* tool used to collect, search, and analyze log data from many different sources. In my project, I used Nmap to find the open web server port and then used Splunk to analyze the logs from that server to detect the attack.
