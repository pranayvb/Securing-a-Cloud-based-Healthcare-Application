# Vulnerability-Assessment-of-a-Cloud-based-Healthcare-Application-

# **Securing a Cloud-based Healthcare Application: Midterm & Final Project**

This repository contains the findings, reports, and architectural design for securing a healthcare company's cloud-based application. This project was completed as part of the **ENPM665-Cloud Security Course** taught by **Kevin Shivers**, with a focus on identifying vulnerabilities and proposing a secure infrastructure for handling sensitive patient data, including medical records and billing information.

## **Midterm Project Overview**

In the midterm phase, we conducted a thorough vulnerability assessment of the cloud infrastructure used by the healthcare company. The following key issues were identified:

- **Weak Access Controls**: Misconfigured IAM policies allowed excessive permissions and unauthorized access to sensitive resources.
- **Unencrypted Data**: Sensitive patient information was stored in unencrypted databases, exposing it to potential breaches.
- **Vulnerable Virtual Machines**: Outdated software and unpatched vulnerabilities on VMs posed significant risks.
- **Inadequate Network Security**: Network security groups and firewall rules were insufficient, allowing unrestricted access to critical resources.
- **Lack of Logging and Monitoring**: The absence of proper logging and monitoring mechanisms made it difficult to detect and respond to security incidents.
- **Insufficient Disaster Recovery**: No comprehensive backup or disaster recovery plan was in place, increasing the risk of data loss and extended downtime.

## **Final Project Overview**

For the final phase, we proposed a series of improvements to address the vulnerabilities identified in the midterm. Our solution focuses on enhancing the security, scalability, and availability of the healthcare application platform. The following recommendations were made:

1. **Identity and Access Management (IAM)**: Implementation of stricter IAM policies with role-based access control to ensure least-privilege access. We proposed a redesign of IAM policies for the **Admin**, **Developer**, and **Guest** roles, which limit access based on job responsibilities.
2. **Data Encryption**: Ensuring that all sensitive patient data is encrypted both at rest and in transit, using **AWS KMS** or **Azure Key Vault** for key management.
3. **Network Security**: Implementation of stricter firewall rules and security groups to limit inbound and outbound traffic, and the use of **VPN** and **private subnets** for internal communication.
4. **Multi-AZ/Multi-Region Deployment**: To ensure availability and redundancy, we recommended deploying resources across multiple availability zones (AZs) and regions.
5. **Logging and Monitoring**: Deployment of robust logging and monitoring services such as **AWS CloudTrail**, **Azure Monitor**, and **SIEM** tools to track system activity and detect potential threats in real time.
6. **Disaster Recovery**: A comprehensive disaster recovery plan was designed, including **regular backups**, replication of databases, and automated failover mechanisms across regions.

## **Architecture Design**

We designed a secure cloud infrastructure architecture, which includes the following components:

- **Web Servers**: Handle user requests and serve the frontend of the application.
- **Application Servers**: Process business logic and manage interactions between the frontend and backend.
- **Database Servers**: Store sensitive patient data, including medical records and personal information, with encryption enabled.

### **Dataflows for Key Scenarios**:

1. **Patient's Point of View**: Patients access the application via personal devices for telemedicine consultations, viewing test results, and scheduling appointments. Data flows securely between patient devices and cloud services via encrypted channels.
  
2. **Care Provider's Point of View**: Care providers access the system to manage patient records, send and receive messages, and interact with third parties such as hospitals. Strict access controls and encrypted communication channels are enforced to protect sensitive data.

3. **IT Support's Point of View**: The IT team has different roles (end user support, DBAs, security team, system administrators, super admins) with varying levels of access, managed through IAM policies and monitored with logging services to prevent unauthorized access.

### **Network Architecture Diagram**

The proposed infrastructure includes a secure **VPC** with public and private subnets, **NAT gateways**, **load balancers**, and **multi-region replication** for high availability. The diagram provides a visual representation of the dataflows for patients, care providers, and IT support, ensuring that security is enforced at every level.

![Network Architecture Diagram](link_to_diagram)

## **Tools Used**

- **AWS IAM** / **Azure Active Directory** for identity and access management.
- **CloudFormation** templates for infrastructure automation.
- **nmap** for vulnerability scanning and network security assessment.
- **CloudTrail** for logging and monitoring cloud activity.
- **KMS** / **Key Vault** for data encryption management.

## **Conclusion**

This project addresses the critical need for security in cloud-based healthcare applications. By identifying vulnerabilities in the initial assessment and proposing a secure architecture with enhanced IAM, encryption, network security, and disaster recovery, we have improved the overall security posture of the healthcare company’s infrastructure.

---

This README provides an overview of both the midterm and final project, summarizing the key findings, recommendations, and technical details. The architectural diagram is included to highlight the proposed infrastructure and secure dataflows.
