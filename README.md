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
|   |-- assignment1.md
|   |-- assignment2.md
|
|-- /docs                  # Documentation for each lab and concept
|   |-- /lab1              # Documents related to Lab 1 (Database Access Control)
|   |-- /lab2              # Documents related to Lab 2 (Database Access Example)
|   |-- /cloud-security    # Documents related to Cloud Security
|
|-- /labs                  # SQL scripts and code files for labs
|   |-- /lab1              # SQL scripts and setup for Lab 1
|   |-- /lab2              # SQL scripts and setup for Lab 2
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
