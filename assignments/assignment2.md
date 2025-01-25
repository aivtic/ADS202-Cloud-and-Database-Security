
# **Lab 2: Implementing Audit Logging and Data Integrity Constraints**

## **Objective:**
In this lab, you will learn how to:
- Implement **data integrity constraints** to ensure that the data in your database is valid and consistent.
- Create an **audit log** to track sensitive operations performed on the database.
- Use **triggers** to automate the logging of specific operations.

By the end of this lab, you will have a deeper understanding of how to ensure data validity and maintain a log of critical actions taken within the database for compliance and security purposes.

---

### **Steps for Lab 2:**

---

### **Task 1: Add Data Integrity Constraints**

1. **Add a `CHECK` Constraint to the `orders` Table:**
   - The goal is to ensure that only valid order statuses (e.g., "Pending", "Processing", or "Shipped") are stored in the `orders` table.
   - You'll need to modify the `orders` table and use a `CHECK` constraint to restrict the `order_status` column to these values.
   
   **Guidance:**
   - A `CHECK` constraint ensures that only data that satisfies the defined condition can be inserted or updated in a column. In this case, we are restricting the values in the `order_status` column to a limited set of options (e.g., "Pending", "Processing", "Shipped").
   - Think about how you would use SQL statements to alter a table and apply constraints.

---

### **Task 2: Create an Audit Log Table**

1. **Create a Table to Log Sensitive Operations:**
   - You will need to create an `audit_log` table to store information about sensitive operations such as updates to the `orders` table.
   - The `audit_log` table should store:
     - The `user_id` of the person performing the action.
     - The `action` that was performed (e.g., "UPDATE").
     - The `table_name` where the action occurred (in this case, it will mostly be the `orders` table).
     - The `timestamp` of when the action occurred.

   **Guidance:**
   - The `audit_log` table should include a `PRIMARY KEY` column, such as `log_id`, and should also store important information like the type of action, the timestamp, and user information.
   - The `timestamp` should be automatically set to the current date and time whenever an entry is added.

---

### **Task 3: Create a Trigger to Automatically Log Updates**

1. **Create a Trigger for the `orders` Table:**
   - The goal of the trigger is to automatically log any updates made to the `orders` table.
   - When an `UPDATE` operation occurs on the `orders` table, the trigger should automatically insert a record into the `audit_log` table.
   - The trigger should log the `user_id` (the ID of the user who made the change), the action type (e.g., "UPDATE"), the name of the table being updated (in this case, "orders"), and the `timestamp`.

   **Guidance:**
   - Triggers in SQL allow you to automate actions based on specific events, such as inserting a record when an update occurs. The trigger should be set to fire **AFTER UPDATE** so that it can capture the change after it happens.
   - Think about how you would write the trigger to insert into the `audit_log` table whenever an update is made to the `orders` table. Use the `NEW` keyword to access the updated values in the `orders` table.

---

### **Task 4: Test the Audit Log Functionality**

1. **Update an Order and Check the Log:**
   - Log in as a **manager** or **admin** and perform an `UPDATE` operation on the `orders` table (for example, updating the `order_status` of an order).
   - After performing the update, check the `audit_log` table to ensure that a record of the update was created.
   
   **Guidance:**
   - Run an `UPDATE` query on the `orders` table and verify that the audit log is being correctly populated. The `audit_log` should contain the `user_id`, action type (`UPDATE`), table name (`orders`), and the timestamp of the action.

---

### **Deliverables for Lab 2:**

1. **SQL Queries:**
   - Submit the SQL code you used to:
     - Alter the `orders` table to add the `CHECK` constraint.
     - Create the `audit_log` table.
     - Create the trigger that logs updates to the `orders` table.

2. **Screenshots:**
   - Submit screenshots showing the following:
     - The successful execution of the `UPDATE` operation on the `orders` table.
     - The contents of the `audit_log` table showing the log entry for the update.
   
3. **Reflection:**
   - Write a brief reflection on how **audit logging** can improve the security and accountability of database operations.
     - Why is it important to track changes to the database?
     - How does the **CHECK** constraint enhance data integrity?
     - What role do triggers play in automating tasks in database security?

---

### **Submission Instructions:**

- Compile your work into a PDF format. Your submission should include:
  - A cover page with your name, student ID, and course information.
  - The SQL code (without sensitive data) used to create the constraints, triggers, and audit log.
  - Screenshots of your test results showing that the log entries were correctly captured.
  - A brief reflection on the benefits of **audit logging** and **data integrity** in database security.

- **Upload your submission to the course portal**.

---

### **Grading Criteria:**

Your submission will be graded on the following criteria:

1. **Database Setup and Constraints (20 points):**
   - Correctly implemented data integrity constraints on the `orders` table.
   - Clear and correct SQL statements for the constraints.

2. **Audit Log Setup (20 points):**
   - Correct creation of the `audit_log` table.
   - Properly structured columns for logging sensitive operations.

3. **Trigger Implementation (25 points):**
   - Correct use of triggers to automatically log updates on the `orders` table.
   - Functional trigger that inserts data into the `audit_log` after an update.

4. **Testing and Results (25 points):**
   - Successfully demonstrated audit logging by performing an update on the `orders` table.
   - Provided evidence that the log entries were captured correctly.

5. **Reflection and Documentation (10 points):**
   - Clear and concise reflection on the role of audit logging and data integrity in improving database security.
