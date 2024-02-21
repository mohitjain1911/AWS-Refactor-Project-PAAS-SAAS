# Project README: Refactoring with AWS

## Project Overview:

This project focuses on enhancing the existing vprofile application stack deployed on both local machines and AWS Cloud. We aim to re-architect and refactor our services to improve agility, business continuity, scalability, and overall performance.

## Project Objectives:

1. **Boost Agility and Business Continuity:**
   - Implement re-architecture/refactoring to facilitate the addition of new features.
   - Enhance scalability for effective and easy scaling of application workloads.

2. **Reduce Operational Overhead:**
   - Minimize the need for multiple teams managing various services.
   - Decrease operational overhead related to uptime, scaling, and infrastructure management.

3. **Infrastructure as Code and Cloud Services:**
   - Utilize AWS services for Platform as a Service (PaaS) and Software as a Service (SaaS).
   - Implement Infrastructure as Code (IaC) for easy management and automation.

4. **Cost Optimization:**
   - Move away from traditional infrastructure to cloud-managed services.
   - Embrace a pay-as-you-go model to optimize costs.

## Project Scenario:

Imagine working on a project where services are distributed across physical machines, virtual machines, or cloud instances (e.g., EC2 instances). The application stack includes various components such as databases, application servers, web servers, and network services. Managing such a diverse and distributed environment requires multiple teams, including cloud computing, virtualization, operations, monitoring, and system administration.

The challenges include high operational overhead, uptime struggles, manual processes, and difficulties in automation. The upfront capital and operational expenditures are significant, especially when dealing with virtualization. The goal is to transition from this complex setup to a more streamlined and automated cloud-based solution.

## Project Solution:

To address these challenges, we will leverage AWS services, focusing on PaaS and SaaS offerings. The key AWS services utilized in this project include:

- **Elastic Beanstalk:** For hosting the application stack with features like auto-scaling and load balancing.
- **Amazon RDS:** Platform as a Service for managing databases with easy scalability and automatic backups.
- **Elasticache:** Replacement for memcache, providing a managed caching service.
- **Amazon MQ:** Substituting RabbitMQ for messaging services.
- **Route 53:** AWS DNS service for domain management.
- **Amazon CloudFront:** Content Delivery Network (CDN) for serving global audiences efficiently.

## Project Architecture:

The architecture involves a combination of frontend and backend services:

### Frontend:
- Elastic Beanstalk for hosting, auto-scaling, and load balancing.
- Amazon S3 for artifact storage.
- Amazon CloudFront for content delivery to a global audience.

### Backend:
- Amazon RDS for the database.
- Elasticache for caching.
- Amazon MQ for messaging services.
- Route 53 for DNS.

## Project Execution Flow:

1. **AWS Account Setup:**
   - Login to AWS account.
   - Create a key pair for Beanstalk instance.

2. **Security Groups Setup:**
   - Create security groups for backend services (Elasticache, RDS, Amazon MQ).

3. **Backend Service Provisioning:**
   - Create RDS, Elasticache, and Amazon MQ instances.

4. **Elastic Beanstalk Environment:**
   - Create Elastic Beanstalk environment.

5. **Security Group Updates:**
   - Update backend security group to allow traffic from Beanstalk security group.
   - Allow internal traffic within the backend services.

6. **Backend Initialization:**
   - Launch an EC2 instance to initialize RDS database.

7. **Application Configuration:**
   - Update health check in Beanstalk for /login.
   - Add HTTPS listener to Elastic Load Balancer.

8. **Artifact Build:**
   - Build artifacts from source code with backend information.

9. **Artifact Deployment:**
   - Deploy artifacts to Beanstalk environment.

10. **Content Delivery Network Setup:**
    - Create a CloudFront distribution with SSL certificate.

11. **DNS Configuration:**
    - Update load balancer and endpoint information in GoDaddy or Route 53.

12. **Testing:**
    - Test the application from the configured URL.

## Conclusion:

By following this refactoring strategy and leveraging AWS services, we aim to achieve a more flexible, scalable, and cost-effective infrastructure. The project's success will be measured by improved agility, reduced operational overhead, and enhanced overall performance of the vprofile application.

## Prerequisites

- JDK 1.8 or later
- Maven 3 or later
- MySQL 5.6 or later

## Technologies
- Spring MVC
- Spring Security
- Spring Data JPA
- Maven
- JSP
- MySQL
## Database
Here,we used Mysql DB
MSQL DB Installation Steps for Linux ubuntu 14.04:
- $ sudo apt-get update
- $ sudo apt-get install mysql-server

Then look for the file :
- /src/main/resources/accountsdb
- accountsdb.sql file is a mysql dump file.we have to import this dump to mysql db server
- > mysql -u <user_name> -p accounts < accountsdb.sql