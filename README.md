
# devops
this is my first git repository
<br>
author - uddhav misal


# Introduction to Virtualization and Cloud Computing

Welcome to the **AWS Batch Day 1** session! This document provides an overview of the topics we'll cover today, along with helpful resources and instructions for hands-on practice.

## Topics Covered

### 1. **Introduction to Virtualization**
- **What is Virtualization?**
  - Virtualization is the creation of a virtual version of hardware, allowing multiple operating systems to run on a single physical machine.
  
- **Types of Virtualization**
  - Server Virtualization: Multiple virtual servers on one physical machine.
  - Storage Virtualization: Combining multiple physical storage devices into a single virtual unit.
  - Network Virtualization: Abstracting network resources into a manageable virtual framework.

- **Key Benefits**:
  - Efficient resource utilization
  - Cost savings
  - Scalability
  - Simplified management

#### **Deep Dive Knowledge**:
- Virtualization uses a hypervisor (like VMware or VirtualBox) to manage VMs.
- Popular tools include KVM, Xen, and Microsoft Hyper-V.
- Real-time Example: A company can run a legacy Windows app on a Linux server using virtualization.

#### **Simple Explanation**:
- Think of virtualization as renting rooms in a house (the physical machine) where each room (VM) has its own tenant (OS).

### 2. **Virtualization vs Cloud**
- Virtualization is a foundational technology; cloud computing builds on it.
- **Comparison Table**:
  | **Feature**          | **Virtualization**                     | **Cloud Computing**                       |
  |-----------------------|----------------------------------------|-------------------------------------------|
  | **Definition**        | Technology to create virtual environments. | Delivery of on-demand computing resources via the internet. |
  | **Deployment**        | Local (on-premises servers).           | Hosted on the internet.                   |
  | **Scalability**       | Limited by physical hardware.          | Highly scalable without physical limits.  |
  | **Access**            | Internal network only.                | Accessible from anywhere with an internet connection. |

#### **Deep Dive Knowledge**:
- Virtualization focuses on optimizing hardware usage, while cloud emphasizes service delivery and flexibility.
- Real-time Example: Virtualization is like owning apartments in a building, whereas cloud is like Airbnb where anyone can rent as needed.

### 3. **Cloud Models (IaaS, PaaS, SaaS)**
- **Infrastructure as a Service (IaaS)**:
  - Virtualized hardware resources.
  - **Examples**: AWS EC2, Google Compute Engine.
  - **Real-time Example**: Hosting a website on AWS EC2 where you control the OS and applications.

- **Platform as a Service (PaaS)**:
  - Platforms for application development.
  - **Examples**: AWS Elastic Beanstalk, Google App Engine.
  - **Real-time Example**: Using AWS Elastic Beanstalk to deploy a web app without worrying about the underlying infrastructure.

- **Software as a Service (SaaS)**:
  - Software accessible over the internet.
  - **Examples**: Gmail, Salesforce.
  - **Real-time Example**: Using Google Docs to collaborate on documents in real-time.

#### **Simple Explanation**:
- **IaaS**: Like renting a raw apartment and furnishing it yourself.
- **PaaS**: Like renting a fully furnished apartment but adding your own decorations.
- **SaaS**: Like booking a hotel room where everything is ready.

### 4. **AWS Account Creation**

Follow these steps to create your AWS account:
1. Visit [AWS Free Tier](https://aws.amazon.com/free/).
2. **Sign Up**:
   - Enter your email address and password.
   - Create an account name.
3. **Account Type**: Choose "Personal" or "Professional."
4. **Payment Method**: Add a valid credit/debit card for identity verification.
5. **Verify Identity**: Enter your mobile number for OTP verification.
6. **Select Support Plan**: Choose "Basic (Free)."
7. Log in to the AWS Management Console.

#### **Deep Dive Knowledge**:
- AWS Free Tier offers 12 months of free services like EC2, S3, and Lambda with usage limits.
- Real-time Example: Use the free tier to deploy a simple static website using S3 and monitor costs via the AWS Billing Dashboard.

---

## Hands-On Practice
- **Objective**: Create an AWS account and explore the Management Console.
- **Tasks**:
  1. Sign up for an AWS account using the steps above.
  2. Navigate through the AWS Console to identify key services like EC2, S3, and RDS.

---

## Resources
- [AWS Free Tier Overview](https://aws.amazon.com/free/)
- [AWS Documentation](https://docs.aws.amazon.com/)
- [Virtualization Basics](https://www.vmware.com/topics/glossary/content/virtualization.html)

---

## Key Takeaways
- Virtualization is the backbone of cloud computing.
- Understand the differences between IaaS, PaaS, and SaaS.
- AWS provides a user-friendly interface for cloud services.

----

# AWS Batch Day 2: Introduction to AWS Dashboard and EC2

## Topics Covered

### 1. **Introduction to AWS Dashboard**
The AWS Management Console is the primary interface for managing AWS resources. It is a web application that allows you to:
- Access and manage services like EC2, S3, RDS, and Lambda.
- Monitor your usage and billing.
- Set up security configurations and permissions.

#### **Key Components of the Dashboard**:
1. **Navigation Bar**: Displays your logged-in account, active region, and access to global services like billing and support.
2. **Service Search Bar**: Helps you quickly locate AWS services by name.
3. **Resource Groups**: Allows grouping and managing related resources.
4. **Recent Services**: A list of services you used recently for quick access.
5. **Build a Solution**: Quick links to common tasks such as launching an instance or creating a database.

#### **Best Practices**:
- Always verify the active region to avoid deploying resources in unintended locations.
- Use the Billing Dashboard to track costs and identify unusual usage patterns.

![Sample Image](images/2024-12-30%2010.14.03.gif)

---

### 2. **Region vs Availability Zone (AZ)**
AWS resources are deployed in Regions and Availability Zones to ensure high availability, fault tolerance, and low latency.

#### **Region**:
- A geographical location, such as **US East (N. Virginia)** or **Asia Pacific (Mumbai)**.
- Each region is independent and contains multiple Availability Zones.
- Choose a region based on proximity to your users, compliance requirements, and cost considerations.

#### **Availability Zone (AZ)**:
- A physically distinct data center within a region.
- Each AZ is isolated but connected to other AZs in the same region via low-latency links.
- Example: The **Asia Pacific (Mumbai)** region has three AZs: ap-south-1a, ap-south-1b, and ap-south-1c.

#### **Why Regions and AZs Matter**:
- **High Availability**: Deploy resources across multiple AZs to ensure uptime during failures.
- **Low Latency**: Choose regions close to your users to minimize network delays.
- **Cost Optimization**: Some regions have lower costs for the same services.

![Sample Image](images/Regions.gif)

---

### 3. **Introduction to EC2 Service**
Amazon Elastic Compute Cloud (EC2) is a core service for deploying scalable virtual servers in the cloud.

#### **Features**:
- **Scalability**: Easily scale instances up or down based on demand.
- **Customizable Instances**: Choose instance types based on CPU, memory, and storage needs.
- **Secure Access**: Use SSH keys and security groups for secure connections.
- **Flexible Pricing**:
  - **On-Demand Instances**: Pay per hour with no long-term commitments.
  - **Reserved Instances**: Commit for 1-3 years for lower prices.
  - **Spot Instances**: Bid for unused capacity at discounted rates.

#### **Use Cases**:
- Hosting web applications.
- Running batch jobs or machine learning models.
- Building development and testing environments.

---

### 4. **Creating Your First EC2 Instance (Ubuntu)**

#### **Steps to Launch an EC2 Instance**:
1. **Navigate to EC2 Service**:
   - Log in to the AWS Management Console.
   - Search for "EC2" in the service search bar and select it.

2. **Launch Instance**:
   - Click on the "Launch Instance" button.

3. **Choose an Amazon Machine Image (AMI)**:
   - Select **Ubuntu Server 20.04 LTS** (or another version as needed).

4. **Select Instance Type**:
   - Choose **t2.micro** for free tier eligibility (1 vCPU, 1 GB RAM).

5. **Configure Instance Details**:
   - Leave the default settings.
   - Optionally, enable Auto-Assign Public IP for internet access.

6. **Add Storage**:
   - Keep the default storage size (e.g., 8 GB).
   - Modify if additional storage is required.

7. **Add Tags**:
   - Create a tag to identify your instance (e.g., `Key: Name, Value: MyFirstInstance`).

8. **Configure Security Group**:
   - Create a new security group.
   - Add an inbound rule to allow **SSH (port 22)** from your IP address.

9. **Review and Launch**:
   - Verify your settings and click "Launch."
   - Select an existing key pair or create a new one for SSH access.

10. **Access Your Instance**:
    - Download the private key file (`.pem`) if creating a new key pair.
    - Use an SSH client (like PuTTY or Terminal) to connect:
      ```bash
      ssh -i /path/to/key.pem ubuntu@<Public-IP-Address>
      ```

#### **Best Practices**:
- Always restrict SSH access to specific IP addresses for security.
- Use Elastic IPs for instances requiring a static public IP.

---

## Resources
- [AWS EC2 Documentation](https://docs.aws.amazon.com/ec2/)
- [AWS Free Tier Details](https://aws.amazon.com/free/)
- [SSH Key Management](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-key-pairs.html)

---

## Key Takeaways
- The AWS Dashboard is your central hub for managing cloud resources.
- Regions and AZs provide resilience and flexibility for deployments.
- EC2 is a powerful service for launching virtual servers with customizable configurations.

----

# AWS Batch Day 3: Security Groups and Instance Management

## Topics Covered

### 1. **Security Group (SSH and RDP Port)**
Security Groups act as virtual firewalls that control inbound and outbound traffic for your AWS instances. 

#### **Key Concepts**:
- **Inbound Rules**: Define the traffic allowed to reach your instance.
- **Outbound Rules**: Define the traffic allowed to leave your instance.
- Rules specify:
  - Protocol (e.g., TCP, UDP, ICMP).
  - Port Range (e.g., 22 for SSH, 3389 for RDP).
  - Source (IP address or another security group).

#### **Common Ports**:
- **SSH (Port 22)**: Used for secure remote access to Linux instances.
- **RDP (Port 3389)**: Used for remote access to Windows instances.

#### **Best Practices**:
- Restrict access to specific IP ranges for security.
- Use custom security groups for different applications or roles.

#### **Steps to Configure a Security Group**:
1. Open the EC2 Dashboard and navigate to "Security Groups."
2. Create a new security group.
3. Add inbound rules:
   - For SSH: Protocol = TCP, Port = 22, Source = My IP.
   - For RDP: Protocol = TCP, Port = 3389, Source = My IP.
4. Add outbound rules (default allows all traffic).
5. Attach the security group to your instance during or after creation.

---
# SSH Service: Secure Shell Basics

## What is SSH?
SSH (Secure Shell) is a cryptographic network protocol that provides a secure way to access remote servers and systems. It allows administrators and developers to log in, execute commands, and manage resources over an encrypted connection.

---

## Key Features of SSH
- **Secure Communication**: Uses encryption to secure the connection.
- **Authentication**: Supports various methods like password-based or key-based authentication.
- **Port Forwarding**: Allows secure tunneling of other protocols.
- **File Transfers**: Includes tools like `scp` and `rsync` for transferring files securely.
- **Session Management**: Offers features like persistent sessions and command execution.

---

## SSH in AWS
SSH is commonly used in AWS to manage EC2 instances and other Linux-based resources securely.

### Default Settings for AWS EC2:
- **Port**: 22 (must be open in the security group).
- **Authentication**: Key-pair (`.pem` file) generated during instance creation.

---

## Setting Up SSH for Remote Access

### 1. **Installing SSH Client**
Most operating systems come with SSH clients pre-installed. For example:
- **Linux/MacOS**: SSH is available by default in the terminal.
- **Windows**: Use `ssh` in PowerShell or install third-party tools like PuTTY.

### 2. **Connect to a Remote Server**
To connect to a remote server:
```bash
ssh -i /path/to/key.pem username@<remote-ip-address>
```
- Replace `/path/to/key.pem` with the path to your private key file.
- Replace `username` with the server's default user (e.g., `ubuntu` for Ubuntu instances).
- Replace `<remote-ip-address>` with the public IP of the remote server.

---

### 3. **Configuring SSH Access on AWS EC2**
1. **Verify Security Group**:
   - Ensure the inbound rule allows SSH (port 22).
   - Restrict access to your IP address for enhanced security.

2. **Set File Permissions**:
   ```bash
   chmod 400 /path/to/key.pem
   ```
   This ensures that the private key has the correct permissions.

3. **Connect Using the SSH Command**:
   ```bash
   ssh -i /path/to/key.pem ubuntu@<Public-IP>
   ```

4. **Troubleshooting Connection Issues**:
   - Verify that the instance is running.
   - Check the public IP and ensure it matches the instance.
   - Ensure your IP is allowed in the security group.

---

### 4. **Using SSH Config File**
Simplify repeated connections by creating an SSH configuration file:

#### Example Config File (`~/.ssh/config`):
```plaintext
Host myserver
    HostName <Public-IP>
    User ubuntu
    IdentityFile /path/to/key.pem
```
Connect with:
```bash
ssh myserver
```

---

### 5. **Advanced SSH Usage**
- **Port Forwarding**:
  Securely access local or remote ports.
  ```bash
  ssh -L local_port:remote_host:remote_port user@remote_ip
  ```
- **Transfer Files with `scp`**:
  Copy files securely between local and remote systems.
  ```bash
  scp -i /path/to/key.pem file.txt user@<remote-ip>:/path/to/destination
  ```
- **Persistent Sessions with `tmux` or `screen`**:
  Keep SSH sessions active even if the connection drops.

---

## Security Best Practices
- **Restrict Access**: Limit SSH access to specific IP addresses.
- **Disable Root Login**: Prevent direct root access by modifying `/etc/ssh/sshd_config`.
- **Use Strong Keys**: Always use strong, unique key pairs.
- **Regular Key Rotation**: Replace keys periodically to maintain security.

---

## Resources
- [Official OpenSSH Documentation](https://www.openssh.com/manual.html)
- [AWS EC2 Key Pair Guide](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-key-pairs.html)
- [Secure File Transfer with scp](https://linux.die.net/man/1/scp)

---

## Summary
SSH is an essential tool for securely managing remote servers. By understanding its features and applying best practices, you can ensure secure and efficient access to your resources. Let’s practice setting up and using SSH in our next session! 🚀


---
### 2. **Create Instance of Windows**
AWS EC2 supports launching instances with Windows operating systems for various use cases, such as hosting .NET applications or running Windows-based tools.

#### **Steps to Launch a Windows Instance**:
1. **Navigate to EC2**:
   - Log in to the AWS Management Console.
   - Search for "EC2" and open the service.

2. **Launch Instance**:
   - Click on "Launch Instance."

3. **Choose AMI**:
   - Select a Windows Server AMI, such as **Windows Server 2019 Base**.

4. **Choose Instance Type**:
   - Select **t2.micro** (free tier eligible).

5. **Configure Instance Details**:
   - Leave default settings.
   - Optionally, assign an Elastic IP for a static public IP.

6. **Add Storage**:
   - Keep the default storage size or increase based on your needs.

7. **Configure Security Group**:
   - Add an inbound rule for RDP (port 3389).

8. **Launch and Download Key Pair**:
   - Download the `.pem` key file for accessing the instance.

9. **Retrieve Password**:
   - After launching, go to the instance details.
   - Click on "Get Windows Password" and decrypt it using the `.pem` key file.

10. **Connect to the Instance**:
    - Use Remote Desktop Protocol (RDP) on your local machine:
      - Hostname: Public IP of the instance.
      - Username: Administrator.
      - Password: Retrieved from the AWS console.

---

### 3. **Remote Access of Linux and Windows Machines**

#### **Linux Instance Remote Access**:
1. **Prerequisites**:
   - Ensure SSH is allowed in the security group.
   - Have the `.pem` key file downloaded during instance creation.

2. **Using SSH Command**:
   ```bash
   ssh -i /path/to/key.pem ubuntu@<Public-IP>
   ```

3. **Troubleshooting**:
   - Verify that the instance is running.
   - Ensure your local machine's IP is added to the security group.

#### **Windows Instance Remote Access**:
1. **Enable RDP Access**:
   - Ensure RDP is allowed in the security group.

2. **Using Remote Desktop Client**:
   - Open Remote Desktop Connection (Windows) or install an RDP client (Linux/Mac).
   - Enter the public IP address of the instance.
   - Use the Administrator username and decrypted password.

3. **Troubleshooting**:
   - Check the RDP port in the security group.
   - Ensure the instance has a public IP.

---

## Resources
- [AWS Security Group Documentation](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/using-network-security.html)
- [Launching Windows Instances](https://docs.aws.amazon.com/AWSEC2/latest/WindowsGuide/LaunchingAndUsingInstances.html)
- [Connecting to Linux Instances](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/AccessingInstancesLinux.html)

---

## Key Takeaways
- Security Groups are essential for controlling access to your instances.
- RDP and SSH are the primary protocols for remote access to Windows and Linux instances, respectively.
- Proper configuration of Security Groups ensures both accessibility and security.


----

# SSH Service: Advanced Usage

## Topics Covered
- **SSH Service (Key-Based Authentication)**
- **Practical: Create Another Login User**
- **Deploy Web Server Using NGINX**
- **Deploy Web Server Using HTTPD**

---

## 1. **SSH Service (Key-Based Authentication)**
Key-based authentication in SSH replaces password-based authentication with a more secure method using cryptographic keys. This ensures enhanced security and eliminates the risks of brute force attacks.

### **Key Concepts**:
- **Private Key**: Stays on the client machine and is used to initiate authentication.
- **Public Key**: Placed on the server in the `~/.ssh/authorized_keys` file.
- SSH uses the private key to prove the identity of the client.

### **Steps to Set Up Key-Based Authentication**:
1. **Generate an SSH Key Pair**:
   ```bash
   ssh-keygen -t rsa -b 2048 -C "your_email@example.com"
   ```
   - `-t rsa`: Specifies the key type.
   - `-b 2048`: Sets the key size.
   - `-C`: Adds a comment for identification.

   Save the keys in the default location (`~/.ssh/id_rsa`).

2. **Copy the Public Key to the Server**:
   ```bash
   ssh-copy-id -i ~/.ssh/id_rsa.pub user@<server-ip>
   ```
   Alternatively, manually copy the contents of `id_rsa.pub` to the server's `~/.ssh/authorized_keys` file.

3. **Test the Connection**:
   ```bash
   ssh -i ~/.ssh/id_rsa user@<server-ip>
   ```

4. **Disable Password Authentication** (Optional):
   - Edit the SSH configuration file on the server (`/etc/ssh/sshd_config`):
     ```plaintext
     PasswordAuthentication no
     ```
   - Restart the SSH service:
     ```bash
     sudo systemctl restart sshd
     ```

### **Benefits**:
- No need to remember complex passwords.
- Stronger security with encrypted keys.
- Automated processes (e.g., scripts) become seamless.

---

## 2. **Practical: Create Another Login User**
Adding a new user to the system allows multiple individuals to securely access and manage the server.

### **Steps to Create a New User**:
1. **Add a New User**:
   ```bash
   sudo adduser <username>
   ```
   - Replace `<username>` with the desired username.
   - Follow the prompts to set a password and additional details.

2. **Add the User to the Sudo Group** (Optional):
   ```bash
   sudo usermod -aG sudo <username>
   ```

3. **Set Up SSH Access**:
   - Switch to the new user:
     ```bash
     su - <username>
     ```
   - Create the `.ssh` directory:
     ```bash
     mkdir ~/.ssh && chmod 700 ~/.ssh
     ```
   - Add the public key:
     ```bash
     echo "<public-key>" > ~/.ssh/authorized_keys
     chmod 600 ~/.ssh/authorized_keys
     ```

4. **Verify Access**:
   From your local machine, test SSH access:
   ```bash
   ssh -i ~/.ssh/id_rsa <username>@<server-ip>
   ```

---

## 3. **Deploy Web Server Using NGINX**
NGINX is a lightweight, high-performance web server and reverse proxy server used to host websites and applications.

### **Steps to Deploy NGINX**:
1. **Update the Package Manager**:
   ```bash
   sudo apt update
   ```

2. **Install NGINX**:
   ```bash
   sudo apt install nginx -y
   ```

3. **Start and Enable the NGINX Service**:
   ```bash
   sudo systemctl start nginx
   sudo systemctl enable nginx
   ```

4. **Verify the Installation**:
   - Open a web browser and navigate to the server's public IP.
   - You should see the default NGINX welcome page.

5. **Configure the Firewall** (If Enabled):
   - Allow HTTP and HTTPS traffic:
     ```bash
     sudo ufw allow 'Nginx Full'
     ```
   - Check the firewall status:
     ```bash
     sudo ufw status
     ```

6. **Host a Custom Website**:
   - Replace the default content:
     ```bash
     sudo nano /var/www/html/index.html
     ```
     Add your HTML content and save the file.

7. **Restart NGINX**:
   ```bash
   sudo systemctl restart nginx
   ```

8. **Verify the Website**:
   - Open the server's public IP in a web browser to view your hosted site.

---

## 4. **Deploy Web Server Using HTTPD**
HTTPD (Apache HTTP Server) is a widely-used open-source web server known for its flexibility and robustness.

### **Steps to Deploy HTTPD**:
1. **Update the Package Manager**:
   ```bash
   sudo yum update -y
   ```

2. **Install HTTPD**:
   ```bash
   sudo yum install httpd -y
   ```

3. **Start and Enable the HTTPD Service**:
   ```bash
   sudo systemctl start httpd
   sudo systemctl enable httpd
   ```

4. **Verify the Installation**:
   - Open a web browser and navigate to the server's public IP.
   - You should see the default Apache HTTPD test page.

5. **Configure the Firewall**:
   - Allow HTTP and HTTPS traffic:
     ```bash
     sudo firewall-cmd --permanent --add-service=http
     sudo firewall-cmd --permanent --add-service=https
     sudo firewall-cmd --reload
     ```

6. **Host a Custom Website**:
   - Navigate to the default document root:
     ```bash
     cd /var/www/html
     ```
   - Replace or add content to `index.html`:
     ```bash
     sudo nano index.html
     ```
     Add your HTML content and save the file.

7. **Restart HTTPD**:
   ```bash
   sudo systemctl restart httpd
   ```

8. **Verify the Website**:
   - Open the server's public IP in a web browser to view your hosted site.

---

## Resources
- [NGINX Documentation](https://nginx.org/en/docs/)
- [Apache HTTPD Documentation](https://httpd.apache.org/docs/)
- [OpenSSH Documentation](https://www.openssh.com/manual.html)
- [Linux User Management Guide](https://linuxize.com/post/how-to-create-a-new-user-on-linux/)

---

## Key Takeaways
- Key-based authentication is a secure and efficient way to access servers via SSH.
- Adding new users enables secure multi-user environments.
- NGINX and HTTPD provide robust platforms for hosting web applications.

------------

# Amazon EC2: Comprehensive Guide

This README provides detailed information about Amazon EC2, covering its dashboard, instance types, status checks, AMIs, launch templates, and purchasing options. The content is organized to ensure clarity and practical usability for users.

---

## Day 5 : **Amazon EC2 Dashboard Overview**

The Amazon EC2 Dashboard provides a centralized interface to manage EC2 resources. Key components of the dashboard include:

- **Instances**: View and manage running instances.
- **Launch Instances**: Create new EC2 instances using preconfigured settings.
- **Instance Types**: Explore the various types of instances available.
- **Elastic Block Store (EBS)**: Manage attached storage volumes.
- **Key Pairs**: Secure access to instances with SSH keys.
- **Security Groups**: Configure firewall settings for your instances.
- **Elastic IPs**: Allocate static public IP addresses to your instances.

---

## **Instance Types**

Amazon EC2 offers a wide range of instance types to suit diverse workloads. Below are the main categories:

### **General Purpose**
Balanced compute, memory, and storage.
- Examples: M5, T2, T3, M6a, Mac2

### **Compute Optimized**
Ideal for compute-intensive tasks.
- Examples: C5, C6i, C7g

### **Memory Optimized**
Designed for high-performance databases and memory-intensive applications.
- Examples: R5, X1, X2idn

### **Storage Optimized**
For workloads requiring high, sequential read/write access to large data sets.
- Examples: I3, D2, H1

### **Accelerated Computing**
Designed for applications requiring GPUs or hardware accelerators.
- Examples: P3, G5, Inf1

### **High-Performance Computing (HPC)**
For HPC applications requiring low latency and high performance.
- Examples: Hpc6a, Hpc7g

[Refer to AWS Instance Types Documentation](https://aws.amazon.com/ec2/instance-types/)

---

## **Status Checks for Amazon EC2 Instances**

### **Overview**
Amazon EC2 continuously monitors instance health via automated status checks. These checks ensure instances are running without issues.

- **System Status Check**: Verifies the infrastructure hosting your instance is functioning correctly.
- **Instance Status Check**: Monitors the software and network configuration of your instance.

### **Common Failure Causes**
- Networking issues
- Exhausted memory
- Corrupted file systems
- Kernel incompatibilities

### **CloudWatch Alarms**
You can set alarms to monitor status checks and take automated actions, such as instance recovery, if issues are detected.

[Refer to AWS Status Checks Documentation](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/monitoring-system-instance-status-check.html)

---

## **AMI (Amazon Machine Image)**

### **AMI Types**
1. **EBS-backed AMI**: Boot volume stored on Amazon EBS.
2. **Instance-store-backed AMI**: Boot volume stored on local instance storage.

### **Creating an AMI**
1. Navigate to the EC2 dashboard.
2. Select the instance you wish to create an AMI from.
3. Choose **Actions > Image > Create Image**.
4. Provide the necessary details and click **Create Image**.

### **Copying an AMI**
You can copy AMIs between regions to enhance redundancy or deploy in multiple regions.

[Refer to AWS AMI Documentation](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/AMIs.html)

---

## **Launch Templates**

Launch templates enable consistent configuration of EC2 instances. They support settings like:
- AMI ID
- Instance Type
- Security Groups
- Key Pair

### **Creating a Launch Template**
1. Open the EC2 dashboard.
2. Navigate to **Launch Templates**.
3. Click **Create Launch Template**.
4. Fill in required details, including AMI ID, instance type, and security groups.

[Refer to AWS Launch Template Documentation](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ec2-launch-templates.html)

---

## **Purchasing Options**

### **Overview**
Amazon EC2 offers several purchasing options to optimize costs:

1. **On-Demand Instances**: Pay for instances by the second.
2. **Savings Plans**: Commit to a consistent usage level for 1 or 3 years.
3. **Reserved Instances**: Commit to specific configurations for 1 or 3 years.
4. **Spot Instances**: Use spare EC2 capacity at reduced costs.
5. **Dedicated Hosts**: Full physical servers for your instances.
6. **Dedicated Instances**: Single-tenant instances.
7. **Capacity Reservations**: Reserve capacity in specific AZs.

[Refer to AWS Purchasing Options Documentation](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/instance-purchasing-options.html)

---
# EBS Volumes and Operations Guide

This document provides a detailed overview of Amazon Elastic Block Store (EBS) volumes, their types, and step-by-step instructions for attaching volumes, creating partitions, and mounting them to EC2 instances.

---

## **EBS Volumes and Its Types**

Amazon Elastic Block Store (EBS) provides persistent block storage for use with Amazon EC2 instances. These volumes are highly available, reliable, and scalable.

### **Types of EBS Volumes**

1. **General Purpose SSD (gp3, gp2)**
   - Ideal for a wide range of workloads, including boot volumes, dev/test environments, and low-latency interactive apps.
   - **gp3** offers predictable IOPS and lower costs compared to **gp2**.

2. **Provisioned IOPS SSD (io1, io2)**
   - Designed for I/O-intensive applications, such as databases.
   - Offers high durability and supports features like Multi-Attach.

3. **Throughput Optimized HDD (st1)**
   - Suitable for frequently accessed, throughput-intensive workloads such as big data and log processing.

4. **Cold HDD (sc1)**
   - Ideal for infrequently accessed workloads, such as backups and archiving.

5. **Magnetic (Standard)**
   - Suitable for workloads where data is infrequently accessed.

[Refer to AWS EBS Volume Types Documentation](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/ebs-volume-types.html)

---
![alt text](images/EBS.png)
---

## **Attach Volumes, Create Partition, and Mount**

### **Attaching an EBS Volume to an EC2 Instance**
1. Go to the **EC2 Dashboard** on the AWS Management Console.
2. Select **Volumes** from the left menu.
3. Choose the volume you want to attach and click **Actions > Attach Volume**.
4. Select the instance to attach the volume to and click **Attach**.

### **Creating a Partition**
1. SSH into the EC2 instance to which the volume was attached.
2. Use the `lsblk` command to list all block devices and confirm the new volume is attached (e.g., `/dev/xvdf`).
3. Create a partition on the volume using the `fdisk` command:
   ```bash
   sudo fdisk /dev/xvdf
   ```
   - Press `n` to create a new partition.
   - Follow the prompts and press `w` to write changes.
4. Format the partition:
   ```bash
   sudo mkfs.ext4 /dev/xvdf1
   ```

### **Mounting the Volume**
1. Create a mount directory:
   ```bash
   sudo mkdir /mnt/ebs-volume
   ```
2. Mount the volume:
   ```bash
   sudo mount /dev/xvdf1 /mnt/ebs-volume
   ```
3. Verify the volume is mounted:
   ```bash
   df -h
   ```

### **Persisting the Mount (Optional)**
To make the mount persistent across reboots:
1. Open the `/etc/fstab` file:
   ```bash
   sudo nano /etc/fstab
   ```
2. Add the following entry:
   ```bash
   /dev/xvdf1   /mnt/ebs-volume   ext4   defaults,nofail   0   2
   ```
3. Save the file and exit.
4. Test the configuration:
   ```bash
   sudo mount -a
   ```

---

## **Summary**

- **EBS Volumes**: Provide persistent, reliable block storage.
- **Volume Types**: Include SSDs (gp3, gp2, io1, io2), HDDs (st1, sc1), and magnetic storage.
- **Operations**: Attach a volume, create partitions, format, and mount it to an EC2 instance.

----

# EBS Snapshot and Partition Management Guide

This document provides detailed instructions for managing partitions, configuring permanent mounts, taking EBS backups using snapshots, and automating the snapshot process through policies.

---

## **Partitions and Permanent Mount**

### **Creating a Partition**
1. List available block devices:
   ```bash
   lsblk
   ```
2. Select the device to partition (e.g., `/dev/xvdf`) and run the `fdisk` command:
   ```bash
   sudo fdisk /dev/xvdf
   ```
   - Press `n` to create a new partition.
   - Follow the prompts to define partition size.
   - Press `w` to write changes and exit.
3. Format the partition:
   ```bash
   sudo mkfs.ext4 /dev/xvdf1
   ```

### **Mounting the Partition**
1. Create a directory to mount the partition:
   ```bash
   sudo mkdir /mnt/data
   ```
2. Mount the partition:
   ```bash
   sudo mount /dev/xvdf1 /mnt/data
   ```
3. Verify the mount:
   ```bash
   df -h
   ```

### **Making the Mount Permanent**
To ensure the partition mounts automatically on reboot:
1. Retrieve the UUID of the device:
   ```bash
   sudo blkid
   ```
   Example output:
   ```
   /dev/xvdf1: UUID="abcd-1234" TYPE="ext4"
   ```
2. Edit the `/etc/fstab` file:
   ```bash
   sudo nano /etc/fstab
   ```
3. Add the following line:
   ```
   UUID=abcd-1234   /mnt/data   ext4   defaults,nofail   0   2
   ```
4. Test the configuration:
   ```bash
   sudo mount -a
   ```

---

## **Taking Backup Using Snapshots**

### **Manual Snapshot Creation**
1. Navigate to the **EC2 Dashboard** on the AWS Management Console.
2. Select **Volumes** from the left-hand menu.
3. Choose the volume to back up and click **Actions > Create Snapshot**.
4. Provide a description for the snapshot and click **Create Snapshot**.
5. To view snapshots, navigate to **Snapshots** in the EC2 Dashboard.

### **Snapshot via CLI**
1. Use the following command to create a snapshot:
   ```bash
   aws ec2 create-snapshot --volume-id vol-0123456789abcdef0 --description "My Snapshot"
   ```
2. Verify the snapshot:
   ```bash
   aws ec2 describe-snapshots --snapshot-ids snap-0123456789abcdef0
   ```

---

## **Automating Snapshots Using Snapshot Policies**

### **Create a Snapshot Lifecycle Policy**
1. Navigate to the **Amazon Data Lifecycle Manager (DLM)** in the AWS Management Console.
2. Click **Create lifecycle policy**.
3. Select **EBS Snapshot policy**.
4. Configure policy details:
   - Select resource type as **Volume**.
   - Add tags to identify the volumes to be included in the policy (e.g., `Environment:Production`).
5. Define a schedule:
   - Specify the frequency of snapshots (e.g., daily).
   - Define a retention period (e.g., retain snapshots for 7 days).
6. Review and create the policy.

### **Automating Snapshots via AWS CLI**
1. Create a policy JSON file (`snapshot-policy.json`):
   ```json
   {
       "ResourceType": "VOLUME",
       "TargetTags": [
           {
               "Key": "Environment",
               "Value": "Production"
           }
       ],
       "Schedules": [
           {
               "Name": "DailySnapshot",
               "Frequency": "24",
               "RetentionPeriod": "7"
           }
       ]
   }
   ```
2. Create the lifecycle policy:
   ```bash
   aws dlm create-lifecycle-policy --policy-details file://snapshot-policy.json
   ```
3. Verify the policy:
   ```bash
   aws dlm get-lifecycle-policies
   ```

---

## **Summary**

- **Partition Management**: Create and persist partitions using `fstab`.
- **Snapshots**: Manual and CLI-based snapshot creation.
- **Automation**: Implement lifecycle policies for scheduled backups.

---

# In-depth Guide to NFS and EFS File Systems

## 1. Introduction to NFS (Network File System)

NFS is a distributed file system protocol developed to allow users on client machines to access files over a network as if they were on local storage. It is widely used in UNIX/Linux environments for sharing data.

### Key Features of NFS:
- **Centralized File Storage:** Provides a centralized location for file storage, reducing redundancy.
- **Access Control:** File access is controlled using permissions, user IDs, and group IDs.
- **Cross-platform Compatibility:** Works seamlessly across Linux, UNIX, and some Windows environments.
- **Performance Optimization:** Supports mounting options to enhance performance and security.

### Use Cases of NFS:
1. Centralized file sharing for teams in an organization.
2. Hosting shared directories for applications and databases.
3. Providing user home directories in networked environments.

### Real-world Example:
A company uses NFS to share a directory containing logs and reports across all servers in a data center, allowing administrators to access the same files from any server.

---

## 2. Creating an EFS (Elastic File System)

Amazon EFS is a fully managed elastic file system that provides scalable, shared storage for AWS services and on-premises resources. EFS supports NFS protocols and is optimized for cloud environments.

### Steps to Create an EFS File System

#### Step 1: Log in to the AWS Management Console
1. Open the AWS Management Console and search for **EFS** in the services menu.

#### Step 2: Start the File System Creation
1. Click on **Create File System**.
2. Choose the **VPC** (Virtual Private Cloud) where the file system will be accessible.
3. Select the performance mode based on your requirements:
   - **General Purpose:** For most workloads.
   - **Max I/O:** For highly parallelized workloads requiring high throughput.
4. Choose the throughput mode:
   - **Bursting Throughput:** Automatically adjusts based on usage.
   - **Provisioned Throughput:** Manually set throughput independent of storage size.

#### Step 3: Configure Access
1. Create **mount targets** in the desired Availability Zones.
2. Assign security groups to control network access to the file system.

#### Step 4: Add Tags (Optional)
1. Add metadata in the form of tags to organize your resources.

#### Step 5: Review and Create
1. Confirm the configuration and click **Create File System**.

---

## 3. Attaching and Mounting an EFS File System

### Step 1: Preparing EC2 Instances

#### Install NFS Client

Before mounting EFS, ensure that the NFS client is installed on your EC2 instance.

- For Amazon Linux or RHEL:
  ```bash
  sudo yum install -y nfs-utils
  ```

- For Ubuntu or Debian:
  ```bash
  sudo apt update && sudo apt install -y nfs-common
  ```

### Step 2: Attach EFS to EC2 Instance
1. Go to the **EFS Dashboard** in the AWS Management Console.
2. Select the EFS file system and click **Attach**.
3. Copy the NFS mount command displayed.

### Step 3: Mount the File System
1. **Create a Mount Directory:**
   ```bash
   sudo mkdir /mnt/efs
   ```

2. **Mount the File System:**
   Replace `<mount-target-endpoint>` with your EFS DNS name from the console:
   ```bash
   sudo mount -t nfs4 <mount-target-endpoint>:/ /mnt/efs
   ```

3. **Verify the Mount:**
   ```bash
   df -h
   ```
   This should list the mounted file system with its capacity and usage.

### Step 4: Enable Persistent Mounting
1. **Edit the `/etc/fstab` file:**
   ```bash
   sudo nano /etc/fstab
   ```

2. **Add the Mount Entry:**
   ```
   <mount-target-endpoint>:/ /mnt/efs nfs4 defaults,_netdev 0 0
   ```

3. **Test the Configuration:**
   ```bash
   sudo mount -a
   ```

---

## Practical Example: Multi-instance File Sharing
1. Create an EFS file system.
2. Launch two EC2 instances in the same VPC.
3. Attach and mount the EFS file system on both instances.
4. Create a test file on one instance:
   ```bash
   echo "Hello, EFS!" > /mnt/efs/testfile.txt
   ```
5. Verify the file is accessible from the second instance:
   ```bash
   cat /mnt/efs/testfile.txt
   ```

This demonstrates EFS's shared storage capability.

---

# Basics of Networking

Networking is the backbone of modern computing and communication systems. It involves connecting devices to share resources, data, and information efficiently. Key components and concepts of networking include:

## Key Networking Components:
1. **IP Address (Internet Protocol Address):** A unique identifier assigned to each device on a network. It can be IPv4 (e.g., 192.168.1.1) or IPv6 (e.g., 2001:0db8:85a3:0000:0000:8a2e:0370:7334).

2. **Subnet Mask:** Defines the network and host portions of an IP address. For example, in IPv4, a subnet mask of 255.255.255.0 allows 256 total addresses, of which one is for the network and one for broadcast.

3. **Gateway:** A node that routes traffic from one network to another, typically connecting a private network to the internet.

4. **DNS (Domain Name System):** Translates human-readable domain names (e.g., www.example.com) into IP addresses.

5. **MAC Address (Media Access Control):** A hardware address that identifies devices within a local network.

## Types of Networks:
- **LAN (Local Area Network):** Small networks, typically within a single location, such as a home or office.
- **WAN (Wide Area Network):** Large networks spanning geographic locations, such as the internet.
- **VLAN (Virtual Local Area Network):** Logical segmentation of a LAN for better management and security.

## Networking Protocols:
1. **TCP/IP (Transmission Control Protocol/Internet Protocol):** Core protocol suite for communication over the internet.
2. **HTTP/HTTPS:** Protocols for transferring hypertext data (webpages).
3. **FTP (File Transfer Protocol):** For transferring files over a network.
4. **SSH (Secure Shell):** For secure remote administration.

---

# CIDR (Classless Inter-Domain Routing)

## What is CIDR?
Classless Inter-Domain Routing (CIDR) is a method for efficiently allocating IP addresses and routing data. It replaces the older class-based IP addressing system (Class A, B, and C).

## CIDR Notation:
CIDR uses a suffix to specify the number of significant bits in the subnet mask. The format is:

```
IP Address/Prefix Length
```
For example:
- `192.168.1.0/24` means the first 24 bits are for the network, and the remaining 8 bits are for hosts.

## CIDR Example:
### Given `192.168.1.0/24`:
- **Subnet Mask:** 255.255.255.0
- **Total IPs:** 256 (2^8 for the last octet)
- **Usable IPs:** 254 (Subtract 1 for the network and 1 for broadcast address)
- **Range:** 192.168.1.1 to 192.168.1.254

## Benefits of CIDR:
1. **Efficient IP Address Allocation:** Prevents waste by allowing subnets of variable sizes.
2. **Improved Routing Efficiency:** Reduces the size of routing tables by grouping multiple networks under a single prefix.
3. **Scalability:** Supports hierarchical network design for better scalability.

## Practical Steps:

### Step 1: Understand Your Network Requirements
- Determine the number of hosts and subnets needed.
- Choose an IP range and prefix length that accommodates your needs.

### Step 2: Subnetting
- Use tools like subnet calculators or calculate manually.
- Example: Subnet `192.168.1.0/24` into smaller subnets like `192.168.1.0/26` and `192.168.1.64/26`.

### Step 3: Configure Networking Devices
- Assign IP addresses, subnet masks, and gateways to devices.
- Update DNS records as needed.

### Step 4: Verify Network Configuration
- Use commands like `ping`, `traceroute`, and `nslookup` to test connectivity and resolve issues.

---

## Better understanding Refer Below PDF.

[View the PDF](images/Notes_%20Networks,%20Subnets,%20and%20CIDR.pdf)

---

# Introduction to VPC

## What is a VPC?
Amazon Virtual Private Cloud (VPC) allows you to launch AWS resources in a logically isolated network that you define. You have complete control over your virtual networking environment, including selecting your own IP address range, creating subnets, and configuring route tables and gateways.

### Key Features of a VPC:
- **Logical Isolation:** Operates within a region, providing control over network setup.
- **Subnets:** Divide your VPC into smaller segments based on your requirements.
- **Security:** Use security groups and network ACLs for fine-grained control.
- **Internet Gateway:** Attach to a VPC for internet access.
- **Private Connectivity:** Use VPN or Direct Connect to connect on-premises environments.
- **Elastic IPs:** Assign static IP addresses to resources in your VPC.

### VPC Types:
1. **Default VPC:** Automatically created by AWS in each region. It includes a public subnet in each Availability Zone, enabling immediate access to AWS services.
2. **Custom VPC:** Created manually to meet specific networking requirements, offering full control over the network configuration.

### Reserved IPs in AWS:
Within each subnet's CIDR block, AWS reserves the following IP addresses:
- **.0:** Network address.
- **.1:** Reserved by AWS for the VPC router.
- **.2:** Reserved for mapping Amazon-provided DNS.
- **.3:** Reserved for future use.
- **Last IP:** Reserved for the network broadcast address. 

For example, in a `/24` subnet (`192.168.1.0/24`):
- Reserved IPs: `192.168.1.0`, `192.168.1.1`, `192.168.1.2`, `192.168.1.3`, and `192.168.1.255`.

---

# CIDR Calculation for Subnets

## What is CIDR?
Classless Inter-Domain Routing (CIDR) is a method for allocating IP addresses and routing. Instead of using the traditional class-based system, CIDR allows IP ranges to be split into subnets with flexible sizes.

### CIDR Notation:
A CIDR block is expressed as `IP address/prefix length`. For example, `192.168.0.0/24`:
- **192.168.0.0**: Network portion.
- **/24**: Indicates that the first 24 bits represent the network, leaving 8 bits for host addresses.

### Subnetting Calculation:
1. **Determine the Number of Hosts:**
   - Formula: `2^(32 - prefix length) - 2`
   - Example: `/24` = `2^(32 - 24) - 2 = 254 usable hosts`

2. **Divide a Larger Block:**
   - Example: To split `10.0.0.0/16` into four subnets, increase the prefix length to `/18`. Resulting subnets:
     - `10.0.0.0/18`
     - `10.0.64.0/18`
     - `10.0.128.0/18`
     - `10.0.192.0/18`

### Practical Example:
- **Base CIDR:** `10.0.0.0/16`
- **Required Subnets:** 4
- **Step:** Adjust prefix length to `/18` to accommodate each subnet.

---

# Create VPC and Subnet

## Step-by-Step Guide:

### Create a VPC:
1. Log in to the **AWS Management Console**.
2. Navigate to **VPC Dashboard**.
3. Click **Create VPC**.
4. Provide details:
   - **Name:** MyVPC
   - **IPv4 CIDR Block:** `10.0.0.0/16`
   - Enable DNS settings if required.
5. Click **Create VPC**.

### Create a Subnet:
1. Go to the **Subnets** section in the VPC Dashboard.
2. Click **Create Subnet**.
3. Select your VPC (e.g., `MyVPC`).
4. Specify details:
   - **Name:** PublicSubnet
   - **Availability Zone:** Choose an AZ (e.g., us-east-1a).
   - **CIDR Block:** `10.0.0.0/24`
5. Click **Create Subnet**.

### Verify:
1. Go to the **VPC Dashboard**.
2. Confirm that your VPC and Subnet appear in the list.
3. Associate your subnet with a route table if necessary.

---

![VPC](images/VPC.gif)

## 1. Create an Internet Gateway (IGW) and Route

### What is an IGW?
An Internet Gateway is a horizontally scaled, highly available, and redundant VPC component that allows communication between instances in your VPC and the internet.

### Steps to Create an IGW and Attach to VPC:
1. **Navigate to the AWS Management Console:**
   - Go to the "VPC" section.

2. **Create an Internet Gateway:**
   - Select "Internet Gateways" from the left-hand menu.
   - Click "Create internet gateway."
   - Provide a name for the IGW (optional).
   - Click "Create internet gateway."

3. **Attach the IGW to a VPC:**
   - Select the IGW you just created.
   - Click "Actions" → "Attach to VPC."
   - Select the desired VPC from the dropdown list.
   - Click "Attach internet gateway."

### Create a Route Table and Associate with Subnets:
1. **Navigate to Route Tables:**
   - Under the "VPC" dashboard, click "Route Tables."

2. **Create a Route for Internet Access:**
   - Select the route table associated with the public subnet.
   - Click on the "Routes" tab and "Edit routes."
   - Add a route:
     - **Destination:** `0.0.0.0/0`
     - **Target:** Select the Internet Gateway ID.
   - Click "Save routes."

3. **Associate the Route Table with the Subnet:**
   - Go to the "Subnet Associations" tab.
   - Click "Edit subnet associations."
   - Select the public subnet.
   - Click "Save."

## 2. Launch Private and Public Instances

### Public Instance:
1. **Ensure Public Subnet Configuration:**
   - Verify that the subnet is associated with a route table pointing to an Internet Gateway.

2. **Launch an EC2 Instance:**
   - Navigate to the EC2 dashboard.
   - Click "Launch Instance."
   - Select an AMI (e.g., Amazon Linux 2).
   - Choose an instance type.
   - In the "Configure Instance" step, select the public subnet.
   - Enable "Auto-assign Public IP."
   - Add storage and tags as needed.
   - Configure a security group to allow SSH (port 22).
   - Launch the instance.

### Private Instance:
1. **Ensure Private Subnet Configuration:**
   - The subnet should not be associated with a route to an Internet Gateway.

2. **Launch an EC2 Instance:**
   - Follow the same steps as for a public instance.
   - In the "Configure Instance" step, select the private subnet.
   - Ensure "Auto-assign Public IP" is disabled.

## 3. NAT Gateway

### What is a NAT Gateway?
A Network Address Translation (NAT) Gateway enables instances in a private subnet to access the internet while preventing unsolicited inbound traffic from the internet.

### Steps to Create a NAT Gateway:
1. **Navigate to NAT Gateways:**
   - Under the "VPC" section, click "NAT Gateways."

2. **Create a NAT Gateway:**
   - Click "Create NAT gateway."
   - Select the public subnet.
   - Allocate an Elastic IP (EIP) for the NAT Gateway.
   - Click "Create NAT gateway."

3. **Update Route Table for Private Subnet:**
   - Go to "Route Tables."
   - Select the route table associated with the private subnet.
   - Click on the "Routes" tab and "Edit routes."
   - Add a route:
     - **Destination:** `0.0.0.0/0`
     - **Target:** Select the NAT Gateway ID.
   - Click "Save routes."

## 4. VPC Peering

### What is VPC Peering?
VPC Peering is a networking connection between two VPCs that enables you to route traffic between them using private IP addresses.

### Steps to Create a VPC Peering Connection:
1. **Create a Peering Connection:**
   - Navigate to the "VPC" dashboard.
   - Click "Peering Connections."
   - Click "Create peering connection."
   - Provide a name for the connection.
   - Select the requester VPC and the accepter VPC (can be in the same or different AWS accounts).
   - Click "Create peering connection."

2. **Accept the Peering Connection:**
   - If the accepter VPC is in the same account:
     - Select the peering connection.
     - Click "Actions" → "Accept request."
   - If in a different account, log in to the other account, navigate to "Peering Connections," and accept the request.

3. **Update Route Tables for Communication:**
   - Go to "Route Tables" in both VPCs.
   - Edit the routes to allow traffic to the CIDR block of the peer VPC.

4. **Update Security Groups:**
   - Ensure security group rules allow traffic between instances in the peered VPCs.

---

# Networking, Elastic IPs, Placement Groups, and Security

## NIC (Network Interface Controller) and Elastic IP

### NIC (Network Interface Controller)
A Network Interface Controller (NIC) in AWS is also referred to as an Elastic Network Interface (ENI). It is a virtual network interface that you can attach to an instance in a Virtual Private Cloud (VPC). ENIs provide network connectivity for instances and include attributes such as a private IPv4 address, an IPv6 address (optional), security groups, a MAC address, and a source/destination check flag.

#### Key Features of NIC:
- **Primary Network Interface**: Automatically created with every instance and cannot be detached.
- **Secondary Network Interfaces**: Can be attached or detached from instances, offering flexibility in multi-network configurations.
- **Custom Configuration**: Security groups, IP addresses, and MAC addresses can be customized.

#### Practical Steps to Manage ENIs:
1. Navigate to the **EC2 Dashboard** in the AWS Management Console.
2. Select **Network Interfaces** from the left-hand menu.
3. Create a new ENI by providing the VPC, Subnet, and security group details.
4. Attach the ENI to an instance from the **Actions** menu.

### Elastic IP
An Elastic IP (EIP) is a static IPv4 address designed for dynamic cloud computing. You can associate an EIP with your instance or ENI to allow external internet access.

#### Key Features of Elastic IP:
- **Static**: Remains unchanged unless manually released.
- **Reassignable**: Can be reassigned between instances in your account.
- **One Free IP**: AWS provides one Elastic IP per account without cost if it is associated with a running instance.

#### Practical Steps to Assign an Elastic IP:
1. Go to the **EC2 Dashboard** in the AWS Management Console.
2. Select **Elastic IPs** from the left-hand menu.
3. Click **Allocate Elastic IP address**.
4. Associate the EIP with an instance or network interface.

---

## Placement Groups
AWS Placement Groups are logical groupings of instances that allow applications to meet specific performance or redundancy requirements.

### Types of Placement Groups:
1. **Cluster Placement Group**:
   - Instances are placed close together within a single Availability Zone.
   - High throughput and low latency.
   - Ideal for HPC (High-Performance Computing) and big data workloads.

2. **Spread Placement Group**:
   - Instances are placed across different hardware within an Availability Zone.
   - Increases fault tolerance.
   - Ideal for small critical workloads.

3. **Partition Placement Group**:
   - Instances are divided into logical partitions.
   - Each partition is isolated from others.
   - Used for large distributed and replicated workloads such as HDFS, HBase, and Cassandra.

#### Practical Steps to Create a Placement Group:
1. Open the **EC2 Dashboard** in the AWS Management Console.
2. Select **Placement Groups** from the left-hand menu.
3. Click **Create Placement Group** and provide a name.
4. Choose the type of placement group and add the instances during or after creation.

---

## NACL (Network Access Control List) vs Security Group

### NACL (Network Access Control List):
- Acts as a firewall for controlling traffic in and out of one or more subnets.
- Operates at the subnet level.
- **Stateless**: Rules need to be explicitly defined for both inbound and outbound traffic.
- Supports rules by rule number with allow and deny actions.

### Security Group:
- Acts as a firewall for controlling traffic to and from an instance.
- Operates at the instance level.
- **Stateful**: Automatically allows responses to inbound traffic.
- Only supports allow rules.

### Key Differences:
| Feature                | NACL                         | Security Group             |
|------------------------|------------------------------|----------------------------|
| Scope                  | Subnet-level                 | Instance-level             |
| State                  | Stateless                    | Stateful                   |
| Rule Actions           | Allow and Deny               | Allow only                 |
| Default Behavior       | Allows all traffic by default| Denies all traffic by default|

#### Practical Steps to Manage NACL:
1. Navigate to the **VPC Dashboard** in the AWS Management Console.
2. Select **Network ACLs** from the left-hand menu.
3. Create a new NACL and associate it with subnets.
4. Add inbound and outbound rules as required.

#### Practical Steps to Manage Security Groups:
1. Open the **EC2 Dashboard**.
2. Select **Security Groups** from the left-hand menu.
3. Create a new security group by specifying rules for inbound and outbound traffic.
4. Attach the security group to instances during or after launch.


----

# Introduction to Load Balancer

A Load Balancer in AWS is a service that automatically distributes incoming application traffic across multiple targets, such as Amazon EC2 instances, containers, and IP addresses. It acts as a "traffic cop," ensuring no single resource is overwhelmed, thereby improving application availability and reliability.

Load Balancers are designed to handle varying loads of application traffic while automatically scaling up or down based on demand. AWS offers Elastic Load Balancing (ELB), which supports three types of Load Balancers: Application Load Balancer, Network Load Balancer, and Gateway Load Balancer.

---

## Load Balancer and Its Types

AWS provides the following types of Load Balancers:

1. **Application Load Balancer (ALB):**
   - Operates at the **application layer** (Layer 7 of the OSI model).
   - Best suited for HTTP and HTTPS traffic.
   - Supports advanced request routing, based on URL, hostname, query string, or headers.
   - Features include WebSocket support, SSL termination, and integration with AWS Web Application Firewall (WAF).

2. **Network Load Balancer (NLB):**
   - Operates at the **transport layer** (Layer 4 of the OSI model).
   - Designed for TCP, UDP, and TLS traffic.
   - Best for high-performance use cases that require extremely low latency.
   - Provides static IP addresses and preserves the source IP of the client.

3. **Gateway Load Balancer (GWLB):**
   - Designed to deploy, scale, and manage third-party virtual appliances such as firewalls, intrusion detection, and prevention systems.
   - Operates at Layer 3 (network layer).

---

## Difference: Application Load Balancer vs. Network Load Balancer

| Feature                     | Application Load Balancer (ALB)           | Network Load Balancer (NLB)           |
|-----------------------------|-------------------------------------------|---------------------------------------|
| **OSI Layer**              | Layer 7 (Application Layer)               | Layer 4 (Transport Layer)            |
| **Traffic Type**           | HTTP, HTTPS                               | TCP, UDP, TLS                        |
| **Routing**                | Content-based (URL, headers, etc.)        | Connection-based                     |
| **Performance**            | Optimized for web applications            | High throughput and low latency      |
| **Source IP Preservation** | Not preserved (uses Load Balancer IP)     | Preserved                            |
| **Use Case**               | Web applications, microservices           | Gaming, real-time communication      |
| **Static IP Support**      | No                                        | Yes                                  |
| **WebSocket Support**      | Yes                                       | No                                   |

---

## Practical Steps

### Step 1: Create a Load Balancer
1. **Navigate to the EC2 Dashboard:**
   - Log in to the AWS Management Console.
   - Go to **Services** > **EC2** > **Load Balancers**.

2. **Select Load Balancer Type:**
   - Choose **Application Load Balancer** or **Network Load Balancer** depending on your use case.

3. **Configure Load Balancer Settings:**
   - Provide a name for the Load Balancer.
   - Select the **Scheme** (Internet-facing or internal).
   - Choose **IP address type** (IPv4 or dualstack).

4. **Configure Listeners:**
   - Define listener ports and protocols (e.g., HTTP:80, HTTPS:443).

5. **Configure Target Group:**
   - Specify the target type (Instance, IP, or Lambda).
   - Provide health check settings to ensure targets are healthy.

6. **Review and Create:**
   - Review the settings and click **Create Load Balancer**.

### Step 2: Attach Targets
- Register your EC2 instances or other resources with the Target Group.
- Ensure that your instances are in the same VPC as the Load Balancer.

### Step 3: Test Load Balancer
- Access the DNS name of the Load Balancer from your browser or use tools like `curl` to test the setup.

---

Let me know if you need more details or assistance with implementation!

------

# Auto Scaling and its Types

Auto Scaling in AWS helps maintain application availability by automatically adjusting capacity to ensure stable and predictable performance. Auto Scaling dynamically scales the number of EC2 instances based on demand.

## Types of Auto Scaling:

1. **Dynamic Scaling**
   - Automatically adjusts the number of instances based on demand.
   - Uses scaling policies like Target Tracking, Simple Scaling, and Step Scaling.

2. **Scheduled Scaling**
   - Allows you to scale at specific times based on predictable load changes.
   - Useful for applications with known peak hours.

3. **Predictive Scaling**
   - Uses machine learning to forecast future traffic and scales resources proactively.
   - Reduces latency and ensures application availability.

---

# Create Launch Template

A Launch Template simplifies the process of configuring and launching EC2 instances. Follow these steps:

1. **Navigate to EC2 Console:**
   - Log in to AWS Management Console.
   - Go to the EC2 Dashboard.

2. **Create Launch Template:**
   - Select **Launch Templates** from the left menu.
   - Click **Create Launch Template**.

3. **Configure the Template:**
   - **Launch Template Name:** Provide a descriptive name.
   - **Template Version Description:** Optional but useful for versioning.
   - **AMI ID:** Choose an Amazon Machine Image.
   - **Instance Type:** Select the instance type (e.g., t2.micro).
   - **Key Pair:** Choose an existing key pair or create a new one.
   - **Network Settings:** Configure security groups and VPC settings.
   - **Storage:** Specify root volume size and additional storage if needed.

4. **Review and Create:**
   - Review the details.
   - Click **Create Launch Template**.

---

# Create Auto Scaling Group (Demo)

1. **Navigate to Auto Scaling Groups:**
   - In the EC2 Dashboard, select **Auto Scaling Groups**.

2. **Create Auto Scaling Group:**
   - Click **Create Auto Scaling Group**.

3. **Basic Configuration:**
   - **Group Name:** Enter a descriptive name.
   - **Launch Template:** Select the previously created Launch Template.

4. **Network Settings:**
   - Select a VPC and subnets where the instances will launch.

5. **Set Scaling Policies:**
   - Choose scaling policies like Target Tracking, Step Scaling, or Simple Scaling.
   - Optionally configure notifications and tags.

6. **Review and Create:**
   - Review all settings and click **Create Auto Scaling Group**.

---

# Demo Auto Scaling using Stress Command

1. **Launch Instances:**
   - Ensure Auto Scaling is set up with dynamic scaling policies.

2. **Install Stress Tool:**
   - SSH into an instance.
   - Install the stress tool:
     ```bash
     sudo yum install -y stress
     ```

3. **Simulate Load:**
   - Run the following command to simulate high CPU usage:
     ```bash
     stress --cpu 2 --timeout 300
     ```
   - Monitor the Auto Scaling Group as it adjusts the number of instances.

---

# Scheduled Scaling Theory

Scheduled Scaling enables pre-planned scaling adjustments based on known traffic patterns. For example:

- Scale up to 10 instances every day at 8 AM.
- Scale down to 2 instances at 10 PM.

**Steps to Configure:**
- Navigate to Auto Scaling Group settings.
- Add a scheduled action.
- Define the time and desired capacity.

---

# Predictive Scaling Theory

Predictive Scaling uses machine learning to forecast traffic and scales resources in advance. It analyzes historical data to:

- Anticipate usage trends.
- Provision resources proactively.

**Advantages:**
- Reduced latency.
- Optimized cost by avoiding over-provisioning.

Predictive Scaling can be configured through AWS Auto Scaling policies with minimal manual intervention.

---

With these configurations, you can ensure that your application remains scalable and cost-efficient while meeting user demands effectively.

----

#  <span style="color:blue">IAM Services: Notes and Practical Guide.</span> 

## Today's Agenda

- Introduction to IAM Services
- Creating IAM Users
- Assigning Console and Programmatic Access
- Group Creation and Policy Attachment
- Practical Demo: Policy Implementation and Restriction Tests
- Different Types of Roles, Importance of Roles & Practical Demo for Role

---

## 1. Introduction to IAM Services

### What is IAM?
AWS Identity and Access Management (IAM) allows you to manage access to AWS services and resources securely. IAM helps control who can use your resources (authentication) and what actions they can perform (authorization).

### Key Features:
- Centralized control of AWS resources.
- Secure access to AWS services.
- Granular permissions for users and groups.
- Multi-Factor Authentication (MFA).
- Integration with third-party identity providers.

---

## 2. Creating IAM Users

### Steps:
1. **Navigate to the IAM Console:**
   - Log in to the AWS Management Console.
   - Go to **Services** > **IAM**.

2. **Create a User:**
   - Click **Users** > **Add Users**.
   - Provide a unique **User Name**.
   - Select **Access Type** (e.g., Console Access, Programmatic Access).

3. **Set Permissions:**
   - Attach existing policies directly.
   - Add the user to a group with appropriate permissions.

4. **Review and Create:**
   - Review details and click **Create User**.

---

## 3. Assigning Console and Programmatic Access

### Types of Access:
1. **Console Access:**
   - For web-based AWS Management Console access.
   - Requires a password setup.

2. **Programmatic Access:**
   - For AWS CLI, SDKs, or APIs.
   - Provides an **Access Key ID** and **Secret Access Key**.

### Steps to Assign Access:
- While creating a user, select the desired access type.
- Ensure policies are attached to grant required permissions.

---

## 4. Group Creation and Policy Attachment

### Steps:
1. **Create a Group:**
   - Navigate to **Groups** > **Create New Group**.
   - Provide a descriptive group name.

2. **Attach Policies:**
   - Select existing AWS-managed policies or create a custom policy.

3. **Add Users to Group:**
   - Select users to add to the group for inheriting its permissions.

---

## 5. Practical Demo: Policy Implementation and Restriction Tests

### Objective:
- Implement policies to manage access control.
- Test restrictions to validate policies.

### Steps:
1. **Create a Custom Policy:**
   - Navigate to **Policies** > **Create Policy**.
   - Use the visual editor or JSON editor to define permissions.

2. **Attach Policy:**
   - Attach the policy to users or groups.

3. **Test Policy Restrictions:**
   - Log in as the user with restricted access.
   - Attempt actions outside the policy scope to verify restrictions.

---

## 6. Different Types of Roles, Importance of Roles & Practical Demo for Role

### Types of Roles:
1. **Service Role:**
   - Used by AWS services to perform actions on your behalf.

2. **Cross-Account Role:**
   - Grants access to resources in another AWS account.

3. **IAM Role for EC2:**
   - Allows EC2 instances to interact with AWS services securely.

### Importance of Roles:
- Enables temporary access without sharing credentials.
- Ensures secure and flexible access control.
- Facilitates automation and service-to-service interactions.

### Practical Demo:
1. **Create a Role:**
   - Navigate to **Roles** > **Create Role**.
   - Select the type (e.g., AWS Service, Another AWS Account).

2. **Attach Policies:**
   - Choose policies to define permissions for the role.

3. **Assign Role to a Service:**
   - For example, attach the role to an EC2 instance during or after launch.

4. **Test Role Functionality:**
   - Access the AWS service using the assigned role.
   - Validate permissions by performing actions defined in the role's policies.

------

# Amazon S3: Object Storage and Management

## Agenda
- **Introduction to S3**
- **Create Bucket**
- **Upload Objects**
- **S3 Properties**
- **Versioning, Static Website Hosting, Server Access Logging**

---

### 🌟 **Introduction to S3**
Amazon S3 (Simple Storage Service) is a scalable, secure, and durable object storage service offered by AWS. It allows users to store and retrieve any amount of data at any time, from anywhere on the web.

#### Key Features:
- Unlimited storage capacity.
- 99.999999999% durability.
- Supports multiple storage classes for different use cases.
- Secure data with encryption and access control.
- Lifecycle policies to automate object management.

---

### 🛠️ **Create Bucket**
#### Steps to Create an S3 Bucket:
1. **Navigate to the S3 Console:**
   - Log in to the AWS Management Console.
   - Open the S3 service.

2. **Create a New Bucket:**
   - Click **Create Bucket**.
   - Enter a unique bucket name.
   - Choose a region close to your users for reduced latency.

3. **Configure Bucket Settings:**
   - **Block Public Access:** Choose whether to block public access.
   - **Versioning:** Enable or disable versioning.
   - **Default Encryption:** Enable server-side encryption.

4. **Review and Create:**
   - Review the configurations.
   - Click **Create Bucket**.

---

### 📤 **Upload Objects**
#### Steps to Upload Files:
1. Open the created bucket.
2. Click **Upload**.
3. Drag and drop files or browse to select files.
4. Configure optional settings such as storage class and encryption.
5. Click **Upload** to store the object.

---

### 🔧 **S3 Properties**
S3 buckets come with various properties for customization:
- **Versioning:**
  - Maintains multiple versions of an object.
  - Protects against accidental overwrites or deletions.

- **Static Website Hosting:**
  - Host static content such as HTML, CSS, and JavaScript.
  - Configure an index document and optional error document.

- **Server Access Logging:**
  - Records access requests for auditing.
  - Logs are stored in a specified bucket.

- **Lifecycle Policies:**
  - Automates transitioning objects to different storage classes.
  - Configures object expiration for cost efficiency.

---

### 🌍 **Versioning, Static Website Hosting, and Server Access Logging**

#### **Versioning:**
1. Open the bucket.
2. Go to **Properties** > **Versioning**.
3. Enable versioning to maintain object versions.

#### **Static Website Hosting:**
1. Navigate to the bucket.
2. Open **Properties** > **Static Website Hosting**.
3. Enable hosting and configure index and error documents.
4. Use the provided bucket endpoint for access.

#### **Server Access Logging:**
1. Open the bucket.
2. Go to **Properties** > **Server Access Logging**.
3. Specify a target bucket to store logs.

---

### 💻 **Practical Tasks**

1. **Create a Bucket:**
   - Create a bucket named `my-first-s3-bucket-[your-initials]`.
   - Enable versioning during setup.

2. **Upload an Object:**
   - Upload an image or text file to the bucket.
   - Enable server-side encryption.

3. **Host a Static Website:**
   - Upload an `index.html` file.
   - Enable static website hosting and test the endpoint.

4. **Enable Server Access Logging:**
   - Configure logging for your bucket.
   - Verify log files in the target bucket.

5. **Test Versioning:**
   - Upload a file with the same name multiple times.
   - View and restore previous versions.

---

### 🎯 **Key Takeaways**
- Amazon S3 offers robust storage with versatile management features.
- Versioning protects data from unintended overwrites or deletions.
- Static website hosting allows for easy deployment of web content.
- Server access logging provides valuable insights into bucket usage.


---

## Storage Classes

Amazon S3 provides various storage classes to optimize costs for different use cases. Each storage class is designed for specific data access, durability, and cost requirements.

### Types of Storage Classes:

1. **S3 Standard (General Purpose):**
   - Designed for frequently accessed data.
   - Provides high durability (99.999999999%) and availability (99.99%).
   - Ideal for content delivery, data analytics, and mobile applications.

2. **S3 Intelligent-Tiering:**
   - Automatically moves data between access tiers based on usage.
   - Ideal for unpredictable or changing access patterns.
   - Provides cost savings without performance impact.

3. **S3 Standard-IA (Infrequent Access):**
   - Lower cost for infrequently accessed data.
   - Retrieval fees apply.
   - Suitable for backups and disaster recovery.

4. **S3 One Zone-IA:**
   - Data stored in a single Availability Zone (AZ).
   - Costs less than Standard-IA but with reduced durability.
   - Ideal for non-critical data or easily reproducible data.

5. **S3 Glacier Instant Retrieval:**
   - Low-cost storage with millisecond retrieval.
   - Suitable for archival data that needs quick access.

6. **S3 Glacier Flexible Retrieval:**
   - Cheaper than Instant Retrieval.
   - Retrieval times vary from minutes to hours.
   - Ideal for long-term archives with less frequent access.

7. **S3 Glacier Deep Archive:**
   - Lowest-cost storage option.
   - Retrieval times are in hours.
   - Suitable for data that is rarely accessed and retained for years.

8. **S3 Reduced Redundancy Storage (Deprecated):**
   - Designed for non-critical, easily reproducible data.
   - Not recommended for most use cases.

---

## Replication Rule

Replication in S3 enables you to automatically copy objects from one bucket to another within the same or a different AWS Region. This is useful for disaster recovery, compliance requirements, and data distribution.

### Key Features of S3 Replication:

1. **Cross-Region Replication (CRR):**
   - Replicates objects to a bucket in a different AWS Region.
   - Enhances data durability and disaster recovery.

2. **Same-Region Replication (SRR):**
   - Replicates objects to another bucket in the same AWS Region.
   - Useful for data redundancy within a region.

### Steps to Configure Replication Rule:

1. **Navigate to the S3 Console:**
   - Open the AWS Management Console and go to the S3 service.

2. **Select the Source Bucket:**
   - Choose the bucket where you want to configure replication.

3. **Enable Versioning:**
   - Ensure that versioning is enabled on both the source and destination buckets.

4. **Configure Replication Rules:**
   - Go to the **Management** tab and click **Create replication rule**.
   - Provide a name for the rule.
   - Define the source and destination buckets.
   - Choose replication options (e.g., entire bucket or specific prefixes).

5. **Assign IAM Role:**
   - Specify an IAM role with the necessary permissions to perform replication.

6. **Save the Rule:**
   - Review and save the replication rule.

### Use Cases:
   - Maintaining a backup in a different region.
   - Complying with data residency regulations.
   - Distributing data closer to end-users for lower latency.

---

## Permissions and Metrics Tab

### Permissions Tab:

The **Permissions** tab in S3 allows you to manage access control for buckets and objects.

#### Key Components:

1. **Bucket Policy:**
   - Define access permissions for the entire bucket using JSON-based policy documents.
   - Example:
     ```json
     {
       "Version": "2012-10-17",
       "Statement": [
         {
           "Effect": "Allow",
           "Principal": "*",
           "Action": "s3:GetObject",
           "Resource": "arn:aws:s3:::example-bucket/*"
         }
       ]
     }
     ```

2. **Access Control Lists (ACLs):**
   - Grant read/write permissions at the bucket or object level.
   - Supports granular access for individual users or accounts.

3. **IAM Policies:**
   - Use AWS Identity and Access Management (IAM) policies to control access to S3 resources.
   - Ideal for managing permissions across multiple services and users.

4. **Block Public Access Settings:**
   - Prevent accidental public exposure of buckets and objects.
   - Enable "Block all public access" for secure configurations.

### Metrics Tab:

The **Metrics** tab provides performance insights into bucket operations.

#### Key Metrics:

1. **Request Metrics:**
   - Tracks GET, PUT, DELETE, and other requests made to the bucket.
   - Helps monitor the frequency and type of access.

2. **Data Transfer Metrics:**
   - Tracks the volume of data transferred into and out of the bucket.
   - Useful for identifying high-cost transfer operations.

3. **Storage Metrics:**
   - Tracks the amount of data stored in the bucket.
   - Provides insights into storage class utilization.

4. **Replication Metrics:**
   - Monitors the status of replication rules.
   - Helps identify delays or failures in replication.

5. **CloudWatch Integration:**
   - Enables you to create alarms and dashboards based on S3 metrics.
   - Helps with proactive monitoring and troubleshooting.

#### Enabling Metrics:
   - Navigate to the **Metrics** tab in the bucket properties.
   - Enable the desired metrics (e.g., request or replication metrics).

---

# Introduction to AWS CLI

AWS Command Line Interface (CLI) is a powerful tool that enables users to interact with AWS services using commands. It helps automate tasks and manage AWS services efficiently.

---

## AWS CLI Setup and Configuration

### Step 1: Install AWS CLI
1. Download the AWS CLI installer for your operating system.
2. Follow the installation instructions provided [here](https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html).

### Step 2: Configure AWS CLI
Run the following command to configure AWS CLI:
```bash
aws configure
```
Provide the following details:
- Access Key ID
- Secret Access Key
- Default Region
- Output Format (e.g., JSON, table, text)

### Step 3: Verify Installation
Run this command to verify:
```bash
aws --version
```

---

## AWS CLI Commands for S3 Management

### 1. List S3 Buckets
```bash
aws s3 ls
```

### 2. Create a Bucket
```bash
aws s3 mb s3://<bucket-name>
```

### 3. Upload a File to S3
```bash
aws s3 cp <file-path> s3://<bucket-name>/
```

### 4. List Objects in a Bucket
```bash
aws s3 ls s3://<bucket-name>/
```

### 5. Delete an Object
```bash
aws s3 rm s3://<bucket-name>/<object-key>
```

### 6. Sync Local Folder to S3
```bash
aws s3 sync <local-folder-path> s3://<bucket-name>/
```
### 87. empty  bucket to S3
```
aws s3 rm s3://cbz14buck  --recursive
```
 ### 8. remove empty to S3
 ```
 
aws s3api delete-bucket --bucket cbz14buck  --region  ap-south-1
```
---

## AWS CLI Commands for EC2 Management

### 1. List EC2 Instances
```bash
aws ec2 describe-instances
```

### 2. Start an EC2 Instance
```bash
aws ec2 start-instances --instance-ids <instance-id>
```

### 3. Stop an EC2 Instance
```bash
aws ec2 stop-instances --instance-ids <instance-id>
```

### 4. Terminate an EC2 Instance
```bash
aws ec2 terminate-instances --instance-ids <instance-id>
```

### 5. Create a Key Pair
```bash
aws ec2 create-key-pair --key-name <key-name>
```

### 6. Create a Security Group
```bash
aws ec2 create-security-group --group-name <group-name> --description "<description>"
```

### 7. Add Inbound Rule to Security Group
```bash
aws ec2 authorize-security-group-ingress --group-id <group-id> --protocol tcp --port 22 --cidr 0.0.0.0/0
```

---

## AWS CLI Commands for IAM Management

### 1. List IAM Users
```bash
aws iam list-users
```

### 2. Create an IAM User
```bash
aws iam create-user --user-name <user-name>
```

### 3. Attach a Policy to an IAM User
```bash
aws iam attach-user-policy --user-name <user-name> --policy-arn <policy-arn>
```

### 4. Create an IAM Group
```bash
aws iam create-group --group-name <group-name>
```

### 5. Add a User to a Group
```bash
aws iam add-user-to-group --user-name <user-name> --group-name <group-name>
```

### 6. Create a Custom IAM Policy
```bash
aws iam create-policy --policy-name <policy-name> --policy-document file://<policy-document.json>
```

---

## AWS CLI Commands for VPC Management

### 1. List VPCs
```bash
aws ec2 describe-vpcs
```

### 2. Create a VPC
```bash
aws ec2 create-vpc --cidr-block <CIDR-block>
```

### 3. Create a Subnet
```bash
aws ec2 create-subnet --vpc-id <vpc-id> --cidr-block <CIDR-block>
```

### 4. Create an Internet Gateway
```bash
aws ec2 create-internet-gateway
```

### 5. Attach Internet Gateway to VPC
```bash
aws ec2 attach-internet-gateway --vpc-id <vpc-id> --internet-gateway-id <igw-id>
```

### 6. Create a Route Table
```bash
aws ec2 create-route-table --vpc-id <vpc-id>
```

### 7. Add Route to Route Table
```bash
aws ec2 create-route --route-table-id <route-table-id> --destination-cidr-block 0.0.0.0/0 --gateway-id <igw-id>
```

### 8. Associate Route Table with Subnet
```bash
aws ec2 associate-route-table --subnet-id <subnet-id> --route-table-id <route-table-id>
```

---

## Practical Demo of CLI Commands

1. Configure AWS CLI with a test user.
2. Create an S3 bucket, upload a file, and manage permissions.
3. Launch an EC2 instance and assign security groups.
4. Create a VPC, subnet, and attach an Internet Gateway.
5. Test IAM user permissions by creating a policy and restricting actions.

## Refer:https://docs.aws.amazon.com/cli/latest/

These hands-on tasks will help reinforce the understanding and practical usage of AWS CLI commands.

-------

# Monitoring and Logging with CloudWatch

Amazon CloudWatch is a monitoring and observability service provided by AWS. It provides actionable insights to optimize resource utilization, application performance, and operational health. Below are the key aspects of CloudWatch:

---

## **CloudWatch Dashboard**

### Overview:
The CloudWatch Dashboard is a customizable interface that allows you to visualize and monitor AWS resources and applications in a single view.

### Steps to Create a Dashboard:
1. **Navigate to CloudWatch Console:**
   - Go to the AWS Management Console and open the CloudWatch service.
2. **Create Dashboard:**
   - Click on **Dashboards** from the left-hand menu.
   - Select **Create Dashboard**.
3. **Add Widgets:**
   - Choose the type of widget (e.g., Line, Number, Stacked Area).
   - Select the resource and metrics to monitor (e.g., EC2 CPU utilization, S3 Bucket Requests).
4. **Save Dashboard:**
   - Provide a name and save the dashboard for future use.

### Benefits:
- Real-time monitoring.
- Single view for multiple AWS services.
- Easy sharing and collaboration.

---

## **Metrics**

### Overview:
Metrics are the fundamental monitoring data in CloudWatch. Each AWS service sends metrics to CloudWatch, which you can analyze and use for alarms.

### Common Metrics:
- **EC2 Instances:** CPUUtilization, DiskReadOps, NetworkIn.
- **S3 Buckets:** NumberOfObjects, BucketSizeBytes.
- **RDS Databases:** CPUUtilization, FreeStorageSpace.

### Steps to View Metrics:
1. **Navigate to Metrics:**
   - In the CloudWatch Console, click on **Metrics** in the left-hand menu.
2. **Select a Namespace:**
   - Choose a namespace (e.g., EC2, S3, Lambda).
3. **Filter and Analyze:**
   - Use filters and search to locate specific metrics.
   - View graphs and statistics for the selected metric.

### Use Cases:
- Identify performance bottlenecks.
- Track resource utilization trends.

---

## **Alarms**

### Overview:
CloudWatch Alarms help you respond to changes in your metrics by sending notifications or performing actions like scaling.

### Steps to Create an Alarm:
1. **Navigate to Alarms:**
   - In the CloudWatch Console, click on **Alarms** from the left-hand menu.
2. **Create Alarm:**
   - Click on **Create Alarm**.
3. **Select a Metric:**
   - Choose the metric to monitor.
4. **Set Thresholds:**
   - Define the condition (e.g., CPU utilization > 80%).
5. **Configure Actions:**
   - Choose actions like sending an Amazon SNS notification or triggering an Auto Scaling action.
6. **Review and Create:**
   - Verify the configuration and create the alarm.

### Use Cases:
- Alert when an EC2 instance is over-utilized.
- Automatically scale resources when thresholds are breached.

---

## **Logs Insights**

### Overview:
CloudWatch Logs Insights is a powerful query language for analyzing log data from various AWS services.

### Steps to Use Logs Insights:
1. **Navigate to Logs:**
   - In the CloudWatch Console, click on **Logs Insights**.
2. **Select a Log Group:**
   - Choose a log group (e.g., Lambda logs, VPC flow logs).
3. **Write Queries:**
   - Use the query editor to analyze logs.
     Example:
     ```sql
     fields @timestamp, @message
     | filter @message like /Error/
     | sort @timestamp desc
     | limit 20
     ```
4. **Run Query:**
   - Execute the query to view results.
5. **Save Queries:**
   - Save frequently used queries for quick access.

### Benefits:
- Identify errors and anomalies.
- Gain operational insights from log data.

---

CloudWatch is an essential tool for monitoring and logging in AWS, offering a robust set of features to ensure the health and performance of your applications and infrastructure.





