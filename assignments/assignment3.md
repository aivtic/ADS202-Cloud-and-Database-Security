
# **Assignment: Advanced Cloud Security Research and Application (30 points)**

## **Objective:**
- To research, analyze, and present an in-depth understanding of **cloud security best practices** and how they can be implemented across different cloud platforms (AWS, Azure, or GCP).
- To enhance understanding of current security challenges in cloud computing and evaluate real-world security tools and strategies.

---

### **Part 1: Research Cloud Security Challenges and Best Practices (15 points)**

#### **Action:**
1. **Research Cloud Security Challenges**:  
   - Investigate current **security challenges** that organizations face when using public cloud platforms (AWS, Azure, GCP).
     - Consider challenges like **data breaches**, **insider threats**, **misconfigurations**, **insecure APIs**, and **denial-of-service attacks**.
     - Look into **regulatory compliance** and how different industries (healthcare, finance, etc.) must comply with standards like **GDPR**, **HIPAA**, **SOC 2**, etc.
   
2. **Best Practices for Cloud Security**:  
   - Research cloud security **best practices** across major platforms. This may include:
     - Implementing **least privilege** access.
     - Setting up **Identity and Access Management (IAM)** roles and policies.
     - Using **encryption** (at rest and in transit) for sensitive data.
     - Regular **security audits** and **penetration testing**.
     - Monitoring and logging through **Cloud Security Posture Management** (CSPM) tools like AWS Security Hub, Azure Security Center, or GCP Security Command Center.

#### **Deliverables:**
- Provide a **summary** (500-600 words) of your findings, discussing the most pressing cloud security challenges, and how organizations can use best practices to mitigate risks.
- Include **at least 3 external references** (peer-reviewed papers, blog posts, articles from reputable sources like AWS, Google Cloud, or Microsoft Azure).
- **Reflection**: In **200 words**, reflect on how these challenges might affect businesses today, and discuss what role cloud security tools (e.g., AWS GuardDuty, Google Chronicle) can play in mitigating those risks.

---

### **Part 2: Hands-On Cloud Security Configuration (15 points)**

#### **Action:**
1. **Platform Selection**: Choose a cloud platform (AWS, Azure, or GCP) and configure the following security features:
   - **Identity and Access Management (IAM)**: Create at least three IAM roles (Admin, User, Guest) and define appropriate permissions for each.
   - **Multi-Factor Authentication (MFA)**: Enable MFA for the Admin user.
   - **Security Monitoring Tool**: Set up a security monitoring tool like **AWS Security Hub**, **Azure Security Center**, or **Google Cloud Security Command Center** to detect security findings.
   - **Data Protection**: Set up **encryption** for at least one storage service (e.g., S3 bucket in AWS, Blob Storage in Azure, or Cloud Storage in GCP).
   
2. **Test Configurations**:  
   - Test access control by logging in with different IAM roles and ensuring that the permissions are correctly applied (admin can perform any action, users have limited access).
   - Trigger security alerts (e.g., by misconfiguring something) and confirm that the monitoring tool detects them.

#### **Deliverables:**
- **Screenshots**: Capture screenshots of your configurations, showing IAM roles, MFA setup, and encryption settings.
- **Test Results**: Provide evidence that your IAM roles are working as expected (e.g., test logging in as a guest, user, and admin, and show the results).
- **Reflection**: In **200 words**, discuss the importance of each security configuration (IAM, MFA, encryption, monitoring) and how they contribute to securing cloud environments.

---

### **Bonus Task: Advanced Cloud Security Configuration (Optional, 5 points)**

#### **Action:**
1. **Advanced Security Tools**:  
   - Choose one additional security feature, such as setting up **AWS WAF**, **Azure Firewall**, or **Google Cloud Armor** to protect against web application attacks.
   - Configure a **Cloud Key Management Service (KMS)** to manage encryption keys.
   - Set up an automated **incident response** using **AWS Lambda** or **Azure Functions** based on security alerts from monitoring tools.

#### **Deliverables**:
- **Configuration Documentation**: Describe how you configured the advanced security tools and why they are important in protecting cloud resources.
- **Bonus Reflection**: In **200 words**, explain how these advanced tools provide an additional layer of security and how they can prevent sophisticated cloud attacks.

---

### **Submission Requirements**:
1. **Research Report** (Part 1):  
   - Submit your summary and reflection (500-600 words + 200 words).
   
2. **Hands-On Configuration** (Part 2):  
   - Submit your screenshots and a brief explanation of the setup process (100-200 words for each step).
   - Provide the reflection on the importance of IAM, MFA, encryption, and security monitoring (200 words).
   
3. **Optional Bonus Task** (if completed):  
   - Submit the documentation for the advanced security configurations (100-200 words).

---

### **Submission Instructions**:
- Submit your completed assignment as a single PDF document containing all parts of the assignment (Research Report, Hands-On Configuration Documentation, and Reflection).
- Include all the screenshots in the document with proper labeling for each step.
- Push any relevant configuration scripts to your GitHub repository (if applicable).

---

### **Grading Criteria**:
1. **Research Depth**: How thoroughly you researched cloud security challenges and best practices (Part 1).
2. **Hands-On Implementation**: The accuracy and completeness of your hands-on configuration, including proper application of IAM, encryption, and security monitoring (Part 2).
3. **Reflection**: The quality of your written reflections and how well you demonstrate understanding of cloud security principles.
4. **Bonus Task (if applicable)**: Completion of the advanced security configurations and explanation of their impact on cloud security.

---
