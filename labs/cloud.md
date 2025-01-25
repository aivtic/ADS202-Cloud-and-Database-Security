
# **Cloud Security Labs (Sunday)**

## **Lab 1: Cloud IAM Configuration**  

### **Objective**:
- Learn how to configure **Identity and Access Management (IAM)** roles on cloud platforms (AWS in this case).
- Secure cloud resources through proper IAM roles and policies, ensuring that only authorized users have access to specific resources.

---

### **Step 1: Create a Free AWS Account**

**Action**:  
1. **Create an AWS account** by going to the [AWS Free Tier](https://aws.amazon.com/free/) page and clicking on **Create a Free Account**.
2. Complete the account creation process by providing your details and setting up billing preferences. You’ll be using the **Free Tier** to avoid any charges.

**Why**:  
You need an AWS account to interact with AWS services and complete your IAM tasks.

---

### **Step 2: Set Up IAM Roles in AWS**

**Action**:  
1. **Log in to the AWS Management Console** using the credentials you created in Step 1.
2. **Navigate to IAM**:
   - In the **search bar**, type **IAM** and click on **Identity and Access Management**.
3. **Create IAM Roles** for different user types:
   - **Admin**: This role will have full access to all AWS resources.
   - **Manager**: This role will have the ability to access EC2 and manage certain AWS services but without IAM permissions.
   - **User**: This role will only have read-only access.
   - **Guest**: This role will have view-only access to very limited resources.

**Why**:  
By creating these roles, we establish clear boundaries between different types of users and ensure that users only have the necessary permissions to perform their tasks.

---

### **Step 3: Attach Policies to Roles**

**Action**:  
1. **Attach Policies to Roles**:
   - For **Admin**: Attach the `AdministratorAccess` policy (full access).
   - For **Manager**: Attach the `PowerUserAccess` policy (no IAM management access).
   - For **User**: Attach the `ReadOnlyAccess` policy (read-only access).
   - For **Guest**: Attach a custom policy that grants limited access (e.g., `ViewEC2Instances` policy for view-only access to EC2).

**Why**:  
Policies define the actions that users or services can take on AWS resources. The correct policies should be attached to each role to ensure the principle of least privilege is followed.

---

### **Step 4: Create IAM Users and Assign Roles**

**Action**:  
1. **Create IAM Users** for **Admin**, **Manager**, **User**, and **Guest**:
   - In the **IAM Dashboard**, click on **Users** in the sidebar and then click **Add user**.
   - For each user, choose the appropriate role from Step 2.
   - Enable **MFA (Multi-Factor Authentication)** for additional security.

**Why**:  
Creating users and assigning them to specific roles ensures that we can securely manage who can access what in AWS.

---

### **Step 5: Test User Access**

**Action**:  
1. **Login and test the roles**:
   - As **Admin**: Ensure that you can create, modify, and delete resources (e.g., EC2, S3).
   - As **Manager**: Ensure you can access EC2 and RDS but cannot create or delete users, or perform IAM-related actions.
   - As **User**: Test read-only access to various resources (e.g., EC2 and S3) to verify you cannot make changes.
   - As **Guest**: Ensure that you only have view-only access.

**Why**:  
Testing each role ensures that the correct level of access is granted, and this helps to identify any configuration issues.

---

### **Step 6: Documentation & Reflection**

**Action**:  
- **Screenshots**: Capture screenshots of the IAM roles, policies, and users you have created.
- **Access Tests**: Document the tests you performed for each user role (admin, manager, user, guest).
- **Reflection**: Write a brief reflection (200–300 words) on how IAM configuration and role-based access are important for securing cloud environments. Discuss the **principle of least privilege** and why it is crucial in maintaining security.

---

## **Lab 2: Cloud Security Posture Management**  

### **Objective**:
- Learn to use cloud-native tools (AWS Security Hub, GuardDuty, and Config) to monitor and manage the **security posture** of your AWS environment.
- Implement security best practices to identify, analyze, and mitigate potential risks in your cloud infrastructure.

---

### **Step 1: Enable AWS Security Hub**

**Action**:  
1. **Navigate to AWS Security Hub**:
   - In the AWS Management Console, type **Security Hub** in the search bar and select it.
2. **Enable Security Hub**:
   - Click **Get Started** to enable AWS Security Hub.
   - Choose a region and enable integrations with other AWS services like **GuardDuty**, **AWS Config**, and **Amazon Inspector**.
   - Enable **Security Standards** for AWS Foundational Security Best Practices.

**Why**:  
AWS Security Hub aggregates findings from various AWS security services, providing an overview of the security posture of your cloud environment.

---

### **Step 2: Set Up AWS GuardDuty for Threat Detection**

**Action**:  
1. **Navigate to AWS GuardDuty**:
   - In the AWS Management Console, type **GuardDuty** in the search bar and click on it.
2. **Enable GuardDuty**:
   - Click **Enable GuardDuty** to start monitoring your account for potential threats (such as compromised instances or unauthorized access).
   - Set up GuardDuty in a specific AWS region.

**Why**:  
GuardDuty helps to detect malicious activity in your AWS account and provides detailed security findings for immediate action.

---

### **Step 3: Enable AWS Config for Compliance Monitoring**

**Action**:  
1. **Navigate to AWS Config**:
   - In the AWS Management Console, type **AWS Config** and select it.
2. **Set Up AWS Config**:
   - Click **Get Started** and enable AWS Config for your account.
   - Select the AWS resources to be tracked (e.g., EC2, S3, Lambda).
   - Enable compliance rules to monitor best practices such as encryption on S3 or ensuring that EC2 instances are not publicly accessible.

**Why**:  
AWS Config continuously monitors your resources and evaluates them for compliance with best practices, ensuring your environment remains secure.

---

### **Step 4: Review and Implement Security Best Practices**

**Action**:  
1. **Review Findings** in AWS Security Hub:
   - Go to the **Findings** section in AWS Security Hub to review security alerts.
2. **Take Actions Based on Findings**:
   - Address issues such as:
     - **Restricting access**: Adjust security groups or IAM roles.
     - **Enabling encryption**: Enable encryption for S3 buckets, RDS instances, and other storage resources.
     - **Applying patches**: Use **AWS Systems Manager** to automate patching of EC2 instances.

**Why**:  
Following security recommendations and addressing findings from AWS Security Hub ensures that your cloud environment follows security best practices and reduces the risk of exposure.

---

### **Step 5: Documentation & Reflection**

**Action**:  
- **Screenshots**: Capture screenshots of the findings in Security Hub, GuardDuty alerts, and AWS Config compliance checks.
- **Action Plan**: Document the actions you took to address any security findings, such as restricting access or enabling encryption.
- **Reflection**: Write a brief reflection (200–300 words) on the importance of continuous monitoring and security posture management in the cloud. Discuss the role of tools like AWS Security Hub in managing cloud security.

---

### **Conclusion**:
By completing these labs, you will gain valuable hands-on experience in configuring IAM roles, securing resources, and managing your cloud security posture using AWS tools. These practices are crucial for maintaining a secure cloud environment and mitigating security risks effectively.

---

Let me know if you need any further adjustments or additional instructions!
