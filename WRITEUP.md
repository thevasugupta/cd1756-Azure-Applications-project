# WRITEUP.md  
## Article CMS – Deployment Resource Analysis

### Overview
This project deploys a Flask-based Article CMS application on Microsoft Azure. The application uses Azure SQL Database for structured data, Azure Blob Storage for image storage, and Microsoft Entra ID (Azure AD) for authentication. The deployment required choosing between an Azure Virtual Machine (VM) and Azure App Service.

---

## Option 1: Azure Virtual Machine (VM)

### Cost
Azure VMs require payment for compute resources as long as the VM is running, regardless of usage. Additional costs include disk storage, networking, and maintenance overhead. This generally makes VMs more expensive for small or medium web applications.

### Scalability
Scaling with VMs is mostly manual. Increasing capacity requires resizing the VM or creating additional VMs behind a load balancer, which adds operational complexity.

### Availability
Availability depends on how the VM is configured. High availability requires availability sets or zones, which increase setup complexity and cost.

### Workflow
VMs require full server management, including OS updates, security patches, web server configuration, and application process management. This increases operational effort and slows development iteration.

---

## Option 2: Azure App Service

### Cost
Azure App Service provides a lower-cost option for hosting web applications. Pricing is predictable and based on the App Service Plan. It is cost-effective for student projects and small production workloads.

### Scalability
App Service supports built-in vertical and horizontal scaling with minimal configuration. Scaling can be done automatically or manually without changing application code.

### Availability
Azure App Service offers high availability by default, backed by Azure’s managed infrastructure. No additional configuration is required to achieve reliable uptime.

### Workflow
App Service provides a streamlined deployment workflow with GitHub integration, built-in logging, environment variable support, and automatic process management. Developers can focus on application logic rather than infrastructure.

---

## Final Decision

**Azure App Service was chosen for deployment.**

This choice was made because App Service offers lower cost, easier scalability, built-in availability, and a much simpler development and deployment workflow compared to a Virtual Machine. For a Flask-based CMS application with standard web requirements, App Service is the most efficient and appropriate solution.

---

## When This Decision Might Change

If the application required full control over the operating system, custom system-level dependencies, or specialized background services, a Virtual Machine would be more appropriate. Additionally, for very high-performance workloads or non-web workloads requiring fine-grained infrastructure tuning, deploying on VMs could be justified.

---

## Conclusion

Azure App Service provides the best balance of cost, scalability, availability, and ease of use for this project. It aligns well with the project requirements and supports rapid development and reliable deployment with minimal operational overhead.
