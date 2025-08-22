### Deploying Metabase on Amazon ECS with Fargate and PostgreSQL on Amazon RDS
---

### Objective
The goal of this project was to deploy Metabase using Amazon ECS with the Fargate launch type and connect it to a PostgreSQL database hosted on Amazon RDS. The deployment used the official Metabase Docker image from Docker Hub and environment variables were configured for database connectivity. Networking was configured to ensure both ECS and RDS were in the same VPC and the RDS security group allowed inbound traffic on port 5432 from the ECS tasks.

### Skills Learned
- Deploying containerized applications on Amazon ECS with Fargate.
- Provisioning and configuring a PostgreSQL database on Amazon RDS.
- Setting up environment variables for application-to-database connectivity.
- Configuring security groups for secure communication between ECS and RDS.
- Managing ECS task definitions and services.
- Accessing and completing initial setup of Metabase through the browser.

### Tools Used
- Amazon ECS (Fargate): To deploy the containerized Metabase application.
- Amazon RDS (PostgreSQL): Managed database service for backend storage.
- Docker Hub: Source of the official Metabase container image.
- AWS IAM: To provide ECS tasks with the necessary permissions.
- AWS VPC & Subnets: Networking for ECS tasks and RDS instance.
- AWS Security Groups: To allow PostgreSQL communication between ECS and RDS.
- Web Browser (Chrome): To access the Metabase setup interface.

### Environment Setup
- Cloud Provider: Amazon Web Services (AWS)
- ECS Launch Type: Fargate
- Container Image: metabase/metabase
- Database: PostgreSQL on Amazon RDS
- Port: 5432 (PostgreSQL), 3000 (Metabase UI)
- Access: Browser access via ECS task public IP

### Steps
1. I created a PostgreSQL Database in Amazon RDS. I launched a PostgreSQL instance in the same VPC as the ECS cluster,and configured the RDS security group to allow inbound traffic on port 5432 from ECS tasks.

  [Create User]( ./screenshots/image1.png)

2. I deployed an ECS Cluster using the Fargate launch type.

  [Create User](./screenshots/image2.png)

3. I Created an ECS Task Definition for Metabase using the official metabase/metabase Docker image and I configured the neccessary environment variables.

  [Create User](./screenshots/image3.png)

4. I launched a service to ensure Metabase is continuously running in ECS.

  [Create User](./screenshots/image4.png)

5. I opened a browser and navigated to the ECS task’s public IP on port 3000. I Successfully accessed the Metabase setup interface from my browser.

  [Create User](./screenshots/image5.png)

  ### Conclusion 
I successfully deployed Metabase on ECS with Fargate and connected it to a PostgreSQL database hosted on Amazon RDS.
- ECS tasks ran Metabase using the official Docker image.
- Database connectivity was achieved through correctly set environment variables.
- Security groups were configured to allow only the necessary communication between ECS and RDS.
- Verified successful login and setup via the Metabase web UI.
