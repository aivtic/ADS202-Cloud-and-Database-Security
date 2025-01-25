
# **Assignment 1: Implementing Role-Based Access Control (RBAC)**

## **Objective:**
The purpose of this assignment is to implement **Role-Based Access Control (RBAC)** in a database. You will:
- Create a database with multiple tables.
- Define different user roles (admin, manager, user, guest).
- Assign access levels to each role.
- Test the access of each role to ensure the system functions as intended.

By the end of this assignment, you will have a solid understanding of how to restrict and manage user access to sensitive data using roles.

---

### **Steps for Assignment:**

---

### **Task 1: Create the Database and Tables**

1. **Create a New Database:**
   - Start by creating a new database. Choose a meaningful name like `db_security` to represent the database for this project.
   - The database should have the following tables: 
     - **`users`**: Stores user information like usernames, passwords, and roles.
     - **`products`**: Stores product data (e.g., product name, price).
     - **`orders`**: Stores order data linking users and products.

   **Guidance:**
   - Use SQL statements to create each table. Make sure to define appropriate data types (e.g., `VARCHAR`, `INT`, `DECIMAL`) for each column and ensure that `PRIMARY KEY` and `FOREIGN KEY` constraints are properly set.

2. **Define the `users` Table:**
   - Include columns like `user_id`, `username`, `password`, and `role`. The `role` column will help you define different access levels (admin, manager, user, guest).
   
3. **Define the `products` Table:**
   - The table should have a `product_id`, `product_name`, and `price` to store product details.

4. **Define the `orders` Table:**
   - This table should have `order_id`, `user_id`, `product_id`, `order_date`, and `order_status`. The `user_id` and `product_id` should be foreign keys referencing the `users` and `products` tables, respectively.

---

### **Task 2: Insert Sample Data**

1. **Insert Sample Data into `users`:**
   - Create several sample users with different roles such as `admin`, `manager`, `user`, and `guest`.
     - **Admin** should have access to all data.
     - **Manager** should be able to modify orders but not products.
     - **User** should be able to view products but not make changes.
     - **Guest** should also only be able to view products.
   
2. **Insert Sample Data into `products`:**
   - Add a few sample products, for example, a laptop, smartphone, and tablet. These will be referenced in the orders table.

3. **Insert Sample Data into `orders`:**
   - Insert a few orders with references to `users` and `products`. This will simulate real-world transactions.

---

### **Task 3: Implement Users and Assign Roles**

1. **Define User Roles:**
   - You will need to create four roles: `admin`, `manager`, `user`, and `guest`. 
   - Each role will have different levels of access to the database.
     - The **admin** should have full privileges (can create, read, update, delete data).
     - The **manager** should have access to update and view orders but cannot access product data.
     - The **user** should only be able to view product data.
     - The **guest** should have the same access as the **user** but with even more limited access (e.g., only able to view products without making queries).

2. **Grant Privileges to Roles:**
   - Use `GRANT` statements to assign the appropriate privileges to each role based on their job responsibilities.
     - **Admin** will have full privileges across all tables.
     - **Manager** will have privileges to view and modify the `orders` table but no access to the `products` table.
     - **User** will only have read access to the `products` table.
     - **Guest** will have the same read access as the **user**, but cannot perform any other actions.

---

### **Task 4: Test the Access Levels for Each Role**

1. **Login as Each Role:**
   - For each user role, log into the database and test various SQL queries. This will help you verify that each role has the correct level of access:
     - **Admin:** Should be able to perform all CRUD (Create, Read, Update, Delete) operations on the `users`, `products`, and `orders` tables.
     - **Manager:** Should be able to view and modify orders, but attempts to view or modify products should result in an access error.
     - **User:** Should only be able to view the `products` table. Any attempts to interact with the `orders` table should be denied.
     - **Guest:** Should have the same access as the **user**, but even more limited.

2. **Record the Results:**
   - Document what happened when you performed the tests. For example:
     - **Admin** was able to update a product’s price.
     - **Manager** was able to update an order status but couldn’t modify product details.
     - **User** could only see products but couldn’t interact with the orders.
     - **Guest** could only view product details.

---

### **Deliverables:**

1. **SQL Queries:**
   - Submit the SQL queries you used to create the tables and define user roles (without the actual code being provided).

2. **Screenshots:**
   - Submit screenshots showing:
     - The SQL queries used to create the database, tables, and roles.
     - The query results showing successful access and denied access for each user.

3. **Reflection:**
   - Provide a brief reflection on your implementation of **Role-Based Access Control (RBAC)**. Answer the following questions:
     - How did you decide on the privileges for each role?
     - Why is RBAC important for database security?
     - How does the principle of least privilege apply in this context?
   
   Your reflection should be no more than a few paragraphs and should show a deep understanding of the importance of access control in maintaining a secure database.

---

### **Submission Instructions:**

- Compile your work into a PDF format. Your submission should include:
  - A cover page with your name, student ID, and course information.
  - The SQL code (without sensitive data) used to create the tables, roles, and privileges.
  - Screenshots of your tests for each role (admin, manager, user, guest).
  - A reflection on how RBAC was implemented and its importance for database security.

- **Upload your submission to the course portal**.

---

### **Grading Criteria:**

Your submission will be graded on the following criteria:
1. **Database Setup and Structure (20 points)**:
   - Correct table definitions and relationships.
   - Correctly implemented role-based access control.

2. **Data Insertion (10 points)**:
   - Appropriate sample data inserted into the tables.

3. **Privilege Management (25 points)**:
   - Correct privileges assigned to each user role.

4. **Testing and Results (25 points)**:
   - Successful testing of each user role with correct access restrictions.

5. **Reflection and Documentation (20 points)**:
   - Clear and concise reflection on RBAC and its importance.
   - Well-organized and complete documentation.
