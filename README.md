# **ADS202: Cloud and Database Security - Lab Documentation**

Welcome to the **ADS202: Cloud and Database Security** course repository! This repository is designed to help you gain hands-on experience in securing databases and cloud systems through practical exercises. Below, you'll find comprehensive instructions and guidelines for each lab, along with SQL scripts and code to ensure that you master the essential security concepts for both databases and cloud environments.

---

## **Labs Overview**

### **Database Security Labs (Saturday)**
- **Lab 1:** Database Access Control Model (SQL Example)  
  Explore the concept of database access control using SQL, focusing on role-based access management and privilege enforcement.
  
- **Lab 2:** Database Access Example  
  Learn about data integrity, audit logging, and advanced SQL queries to track sensitive operations in databases.

### **Cloud Security Labs (Sunday)**
- **Lab 1:** Cloud IAM Configuration  
  Understand the configuration of Identity and Access Management (IAM) roles on cloud platforms such as AWS, GCP, or Azure, and how to secure cloud resources through proper IAM roles and policies.
  
- **Lab 2:** Cloud Security Posture Management  
  Delve into tools and practices for monitoring and managing the security posture of your cloud environment, focusing on tools like AWS Security Hub, Google Cloud Security Command Center, and Azure Security Center.

### **Additional Resources**
- The **Assignments** folder contains extra practice and in-depth exercises to reinforce your understanding of database and cloud security concepts.
- Refer to the **Documentation** folder for detailed explanations and breakdowns of each lab.

---

## **How to Navigate the Labs**

### **Lab 1: Database Access Control Model (SQL Example)**
In this lab, you'll learn how to implement and manage **Role-Based Access Control (RBAC)** in a database system using SQL. You'll:
1. Create a sample database and implement user roles with various access levels (Admin, Manager, User, Guest).
2. Use SQL queries to simulate real-world database interactions, ensuring each user role has the appropriate privileges.
3. Implement the **Principle of Least Privilege** to restrict unnecessary access.

This lab will also include sample SQL scripts for creating the database, tables, and assigning privileges.

---

### **Lab 2: Database Access Example**
This lab focuses on **Data Integrity** and **Audit Logging**. You'll:
1. Learn to apply constraints (e.g., `CHECK`) to enforce valid data within your database.
2. Implement triggers to automatically log actions such as updates and deletes to sensitive tables.
3. Use the **Audit Log** technique to track changes and ensure compliance.

By the end of this lab, you'll understand the importance of tracking sensitive operations and how audit logs help detect malicious activity.

---

### **Cloud Security Labs**

### **Lab 1: Cloud IAM Configuration**
In this lab, you'll learn how to configure **Identity and Access Management (IAM)** roles in cloud environments:
1. Set up IAM roles and assign them to cloud resources (e.g., EC2 in AWS, VM in GCP, etc.).
2. Explore **least privilege** access by defining precise permissions for each role.
3. Implement **multi-factor authentication (MFA)** and **role-based policies** for users and services in your cloud platform.
4. Secure cloud resources through proper IAM role configuration.

---

### **Lab 2: Cloud Security Posture Management**
This lab will guide you through managing and monitoring the **security posture** of your cloud environment:
1. Learn about **cloud security best practices** and tools used by major cloud providers (AWS, GCP, Azure).
2. Implement security policies, configure encryption, and manage vulnerabilities.
3. Use tools like **AWS Security Hub**, **Google Cloud Security Command Center**, and **Azure Security Center** to monitor and improve the security of your cloud environment.
4. Understand how to implement **continuous monitoring** to ensure ongoing security.

---

## **Folder Structure**

Below is the structure of the repository. Each folder contains lab instructions, SQL scripts, code files, and additional resources to complete each lab.

```
/ADS202-Cloud-and-Database-Security
|-- /assignments           # Assignment instructions and resources
|   |-- databse_lab_1&2.md
|   
|
|-- /labs                      
|   |-- /labs 1&2              
|   |-- /lab 3                 
|
|-- README.md              # This file
|-- LICENSE                # License information
|-- .gitignore             # Git ignore file for unwanted files
```

### **Key Sections of the Repo**
- **Assignments**: Contains detailed assignment instructions that complement the labs, helping you apply the concepts you’ve learned.
- **Documentation**: Contains guides and explanations for each lab, including steps for each task and examples.
- **Labs**: Contains the SQL scripts, code files, and setup instructions required to complete the labs.

---

## **Lab Instructions**

Each lab folder includes:
- **SQL Code and Scripts**: Pre-written SQL queries and code snippets that you will execute during the lab.
- **Step-by-Step Instructions**: Clear instructions for completing each task.
- **Deliverables**: Instructions for what to submit upon completing the lab, such as screenshots, code, and written reflections.

---

## **Assignment Guidelines**

### **Assignment 1: Role-Based Access Control (RBAC)**
- **Objective**: Implement RBAC in your database system.
- **Tasks**:
  1. Create a database and tables for users, products, and orders.
  2. Implement roles for Admin, Manager, User, and Guest.
  3. Assign permissions based on these roles and test the access for each.
  4. Submit SQL code, screenshots of queries, and a reflection on the importance of RBAC.

### **Assignment 2: Audit Logging and Data Integrity Constraints**
- **Objective**: Apply data integrity constraints and implement an audit log to track changes.
- **Tasks**:
  1. Add constraints (e.g., `CHECK`) to the `orders` table.
  2. Create a trigger to log sensitive changes to the `audit_log` table.
  3. Test the logging by updating data in the `orders` table.
  4. Submit SQL scripts, screenshots of audit logs, and a reflection on how audit logging contributes to security.

---

Certainly! Here's the updated **grading criteria** to ensure everything totals to **100%**, incorporating the changes and making sure all elements are covered for a more balanced distribution.

---

## **Lab Grading Criteria**

### **Lab 1: Database Access Control Model (SQL Example) – 30%**
This lab covers role-based access control (RBAC), privilege assignment, and testing for different users (Admin, Manager, User, Guest).

#### Grading Breakdown:
1. **Lab Setup and Execution (15%)**
   - Proper setup and execution of the database, including tables and roles.
   - Successfully created users with different roles and tested access control functionality.
   
2. **Role and Privileges Assignment (10%)**
   - Correctly assigned roles and privileges (e.g., Admin can perform all operations, Manager has restricted access to orders, User and Guest have minimal access).
   - Implemented the **Principle of Least Privilege**.
   
3. **Testing and Documentation (5%)**
   - Thorough testing of user access control with detailed explanations in the report.
   - Clear reflections on the results and any challenges encountered.

---

### **Lab 2: Database Access Example – 30%**
This lab focuses on implementing data integrity constraints and setting up audit logging with SQL triggers.

#### Grading Breakdown:
1. **Data Integrity Constraints Implementation (10%)**
   - Correctly implemented constraints (e.g., `CHECK`, `FOREIGN KEY`, `NOT NULL`) on relevant tables to ensure data quality and consistency.
   
2. **Audit Logging and Trigger Setup (10%)**
   - Properly set up the audit logging system with a trigger to log sensitive operations (insert, update, delete).
   - Ensured that the audit log captures necessary details (user_id, action, timestamp).
   
3. **Testing and Documentation (10%)**
   - Screenshots of successful operations (e.g., audit log entries).
   - Clear explanation of why audit logging and data integrity are critical for database security.
   - Reflection on how these practices apply in the real world.

---

### **Cloud Security Lab – 30%**
This lab focuses on cloud IAM configuration, role-based access, and security posture management tools (AWS, GCP, or Azure).

#### Grading Breakdown:
1. **IAM Configuration and Role Management (15%)**
   - Correctly configured IAM roles with specific permissions for cloud resources (e.g., EC2, VM, etc.).
   - Applied **Principle of Least Privilege** in IAM configurations.
   - Implemented roles that enforce secure access control within the cloud environment.
   
2. **Cloud Security Posture Management (10%)**
   - Configured cloud security tools (e.g., AWS Security Hub, GCP Security Command Center, or Azure Security Center) to monitor security posture.
   - Monitored resources and set up security alerts for misconfigurations or vulnerabilities.
   
3. **Testing and Documentation (5%)**
   - Screenshots and explanations of the cloud configuration and security posture setup.
   - Reflection on the importance of IAM and cloud security monitoring.

---

### **Overall Reflection and Report – 10%**
Your **overall reflection** should discuss:
- **What you learned** from the labs, highlighting key concepts like RBAC, IAM, audit logging, and cloud security posture.
- **Challenges faced** during the labs and how you overcame them.
- **Real-world application** of these concepts, emphasizing how the skills learned can be applied to enhance security in actual enterprise systems.

#### Grading Breakdown:
1. **Comprehensive Reflection (5%)**
   - Insightful reflection that ties together the concepts from both database and cloud labs.
   - Clear, well-thought-out connections to real-world scenarios.

2. **Clarity and Detail (5%)**
   - Well-organized and concise reflection.
   - Thorough explanation of the practical application of the learned skills.

---

### **Total Grading Breakdown:**

| **Component**                            | **Percentage** |
|------------------------------------------|----------------|
| **Lab 1: Database Access Control Model** | 30%            |
| **Lab 2: Database Access Example**       | 30%            |
| **Cloud Security Lab**                   | 30%            |
| **Overall Reflection and Report**        | 10%            |
| **Total**                                | **100%**       |

---

## **Additional Information**

- **Cloud Labs**: For Cloud Security labs, you may need access to cloud platforms like AWS, Google Cloud, or Azure. Ensure that your account is set up with the appropriate permissions to perform tasks such as IAM configuration and resource management.
  
- **Lab Tools**: You will be using database management tools such as MySQL Workbench, pgAdmin, or command-line tools for SQL. For Cloud Security labs, tools like AWS CLI, GCP Console, or Azure Portal will be required.

- **Lab Completion**: Make sure to complete the labs in sequence as the concepts build on each other. Start with database security and move to cloud security to get a holistic view of securing modern infrastructures.

---

## **Conclusion**

In this course, you will gain essential hands-on experience in securing both databases and cloud environments. Each lab provides practical exercises that will enhance your understanding of security practices such as:
- Implementing **Role-Based Access Control** (RBAC)
- Enforcing **Data Integrity** and logging sensitive activities
- Configuring **Cloud IAM** and managing the **security posture** of cloud resources

By the end of this course, you'll be equipped with the tools and knowledge to implement robust security measures for both on-premise databases and cloud infrastructure.

---

For any issues or questions, refer to the **Assignments** section or reach out to the course instructor. Happy learning! 🎓🔐
