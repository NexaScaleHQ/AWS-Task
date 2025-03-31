# AWS Task

You are required to complete at least two of the following tasks

### **Task 1: Deploy a Load-Balanced Web Application**

1. **Create a VPC** with:
    - 2 private subnets (each in different availability zones).
    - 1 public subnet for the load balancer.
    - An internet gateway for the public subnet.
    - A NAT gateway in the public subnet to allow outbound traffic from the private instances.
2. **Launch two EC2 instances** in the private subnets:
    - Install and configure **Nginx**.
    - Deploy a simple **web application** that displays the hostname of the server handling the request (e.g., use a simple HTML/PHP app that prints the server’s hostname).
3. **Deploy an Application Load Balancer (ALB)**:
    - Place it in the **public subnet**.
    - Configure target groups to route traffic to the two EC2 instances.
    - Ensure the app is accessible via the ALB’s public DNS and that requests get served by both instances.

---

### **Task 2: Configure AWS Client VPN for Secure Access**

1. **Set up AWS Client VPN**:
    - Create a **Client VPN Endpoint**.
    - Configure authentication (use AWS Active Directory, certificate-based auth, or mutual authentication).
    - Associate the VPN with the **private subnets**.
2. **Connect to the VPN from a local machine**:
    - Install AWS VPN Client.
    - Use provided credentials/certificates to establish a connection.
3. **SSH into the private EC2 instances**:
    - Once connected to the VPN, confirm access by SSHing into the private EC2 instances.
    - Verify that the load-balanced app is working internally.

---

### **Task 3: Implement Auto Scaling for High Availability**

1. **Create an Auto Scaling Group (ASG)**:
    - Ensure that if an EC2 instance goes down, another one is launched automatically.
    - Set the desired capacity to **2 instances**.
2. **Modify the Load Balancer to use the ASG**:
    - Configure the target group to automatically register new instances from the ASG.
3. **Test Scaling**:
    - Terminate one instance and verify that AWS automatically launches a new one.
    - Ensure that the ALB continues routing traffic to healthy instances.

---

**Deliverables:
Task 1:**

- A screenshot of your **VPC topology** from AWS.
- The **private IP addresses** of the two instances.
- A screenshot of the **Nginx configuration** and the deployed app’s output (showing different instance hostnames when refreshing the page).
- **ALB DNS Name** (Public URL).
- A video or GIF demonstrating the **app serving requests from both instances** (by refreshing and seeing different instance hostnames).
- **Target group status screenshot** showing both instances as "Healthy".

**Task 2:**

- A screenshot of the **Client VPN endpoint configuration** in AWS.
- VPN **Connection logs** or **screenshot of an active connection** from your PC.
- A screenshot of your terminal **showing SSH access** to a private EC2 instance while connected to the VPN.

**Task 3:**

- A screenshot of the **Auto Scaling Group (ASG) settings**.
- A **list of currently running EC2 instances** before and after terminating one manually.
- A video or screenshots showing:
    - One instance being **terminated**.
    - A new instance **automatically launching** to replace it.
    - Load balancer still serving traffic from available instances.

Submission is Due on Saturday by 10PM
