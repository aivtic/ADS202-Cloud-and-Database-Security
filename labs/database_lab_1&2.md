
## **ADS 202 Database Security Labs: Information Assurance and Network Security Database Security**

This lab will provide students with hands-on experience in securing databases through access control management, role-based access, privilege enforcement, and auditing. The students will learn how to configure database users, create access control models, and implement audit logging to track sensitive operations.

---

### **Lab 1: Database Access Control Model (SQL Example)**

#### **Objective:**
- Understand and configure role-based access control (RBAC) for databases.
- Implement different levels of access for users (Admin, Manager, User, Guest) based on their role.
- Learn about privilege management and the principle of least privilege.
  
#### **Resources:**
- **Database**: MySQL or PostgreSQL
- **SQL Client**: MySQL Workbench, pgAdmin, or any preferred SQL interface
- **Tools**: Optional – PHPMyAdmin for a graphical user interface

---

### **Step 1: Create a Database**

We will start by creating a database called `db_security` to hold all the tables for our system.

1. Open your SQL client and connect to the MySQL/PostgreSQL server.
2. Run the following SQL command to create the database:

   ```sql
   CREATE DATABASE db_security;
   USE db_security;
   ```

   **Explanation**: This will create a new database named `db_security` and switch to that database to execute subsequent commands.

---

### **Step 2: Create Tables**

Now, we'll create multiple tables: `users`, `orders`, and `products`.

1. **Create the `users` Table**:

   ```sql
   CREATE TABLE users (
       user_id INT PRIMARY KEY,
       username VARCHAR(50) NOT NULL,
       password VARCHAR(100) NOT NULL,
       role VARCHAR(20)
   );
   ```

   **Explanation**: The `users` table will store user credentials and their roles (admin, manager, user, guest).

2. **Create the `products` Table**:

   ```sql
   CREATE TABLE products (
       product_id INT PRIMARY KEY,
       product_name VARCHAR(100),
       price DECIMAL(10, 2)
   );
   ```

   **Explanation**: The `products` table stores information about products, including the `product_id`, name, and price.

3. **Create the `orders` Table**:

   ```sql
   CREATE TABLE orders (
       order_id INT PRIMARY KEY,
       user_id INT,
       product_id INT,
       order_date DATE,
       order_status VARCHAR(50),
       payment_method VARCHAR(50),
       FOREIGN KEY (user_id) REFERENCES users(user_id),
       FOREIGN KEY (product_id) REFERENCES products(product_id)
   );
   ```

   **Explanation**: The `orders` table stores order data. It includes references to both the `users` and `products` tables (foreign keys) to link orders to specific users and products.

---

### **Step 3: Insert Sample Data**

Insert some sample data into the tables so we can simulate access control scenarios.

1. **Insert Sample Users**:

   ```sql
   INSERT INTO users (user_id, username, password, role) VALUES
   (1, 'admin_user', 'admin123', 'admin'),
   (2, 'manager_user', 'manager123', 'manager'),
   (3, 'regular_user', 'user123', 'user'),
   (4, 'guest_user', 'guest123', 'guest');
   ```

2. **Insert Sample Products**:

   ```sql
   INSERT INTO products (product_id, product_name, price) VALUES
   (1, 'Laptop', 999.99),
   (2, 'Smartphone', 499.99),
   (3, 'Tablet', 249.99);
   ```

3. **Insert Sample Orders**:

   ```sql
   INSERT INTO orders (order_id, user_id, product_id, order_date, order_status, payment_method) VALUES
   (1, 1, 1, '2025-01-25', 'Shipped', 'Credit Card'),
   (2, 2, 2, '2025-01-26', 'Processing', 'PayPal'),
   (3, 3, 3, '2025-01-27', 'Pending', 'Debit Card');
   ```

   **Explanation**: Sample data is inserted to simulate real-world usage. You now have several users, products, and orders in the system.

---

### **Step 4: Create Database Users and Assign Roles**

We'll create four users: `admin`, `manager`, `user`, and `guest`, each with different levels of access to the database.

1. **Create Users**:

   ```sql
   CREATE USER 'admin'@'localhost' IDENTIFIED BY 'adminpass';
   CREATE USER 'manager'@'localhost' IDENTIFIED BY 'managerpass';
   CREATE USER 'user'@'localhost' IDENTIFIED BY 'userpass';
   CREATE USER 'guest'@'localhost' IDENTIFIED BY 'guestpass';
   ```

   **Explanation**: These commands create users for the database with different privileges.

2. **Grant Privileges**:

   ```sql
   GRANT ALL PRIVILEGES ON db_security.* TO 'admin'@'localhost';        -- Admin can do everything
   GRANT SELECT, UPDATE, DELETE ON db_security.orders TO 'manager'@'localhost'; -- Manager can access orders
   GRANT SELECT ON db_security.products TO 'user'@'localhost';          -- User can only view products
   GRANT SELECT ON db_security.products TO 'guest'@'localhost';         -- Guest can only view products
   ```

   **Explanation**: This step assigns appropriate permissions to each user:
   - `admin` has full access to all tables and actions.
   - `manager` can view, update, and delete orders but cannot access product data.
   - `user` can only view the product data.
   - `guest` can also only view product data.

---

### **Step 5: Test User Access**

Now, we will simulate logging in as each user and test their access levels.

1. **Login as Admin:**
   Log in as `admin` and attempt various operations (e.g., `SELECT`, `INSERT`, `UPDATE`, `DELETE`) on all tables. Admin should be able to perform any operation.

   ```sql
   SELECT * FROM products;  -- Should succeed
   INSERT INTO products (product_id, product_name, price) VALUES (4, 'Monitor', 199.99);  -- Should succeed
   ```

2. **Login as Manager:**
   Log in as `manager` and attempt operations. The manager should be able to view and modify orders but not access product data.

   ```sql
   SELECT * FROM orders;  -- Should succeed
   UPDATE orders SET order_status = 'Shipped' WHERE order_id = 2;  -- Should succeed
   SELECT * FROM products;  -- Should fail (Access Denied)
   ```

3. **Login as User:**
   Log in as `user` and attempt operations. The user should only be able to view products.

   ```sql
   SELECT * FROM products;  -- Should succeed
   SELECT * FROM orders;  -- Should fail (Access Denied)
   ```

4. **Login as Guest:**
   Log in as `guest` and attempt operations. The guest should only be able to view products.

   ```sql
   SELECT * FROM products;  -- Should succeed
   SELECT * FROM orders;  -- Should fail (Access Denied)
   ```

---

### **Deliverables for Lab 1:**

- **Screenshots**: Include screenshots showing the SQL commands executed and results (successful or denied access).
- **Explanation**: For each user, describe the access granted and explain how role-based access control (RBAC) is enforced.
- **Reflection**: Discuss how the principle of least privilege was implemented and its importance in real-world database security.

---

---

### **Lab 2: Database Access Example**

#### **Objective:**
- Deepen understanding of data access control by managing relationships between tables and introducing more complex access scenarios.
- Learn how to use triggers, views, and auditing to enhance security.

---

### **Step 1: Add Additional Data Integrity Constraints**

1. **Modify `orders` Table to Add Constraints**:

   Add constraints like `CHECK` to ensure data integrity. For example, ensure that the `order_status` is one of a few predefined values.

   ```sql
   ALTER TABLE orders ADD CONSTRAINT chk_status CHECK (order_status IN ('Pending', 'Processing', 'Shipped'));
   ```

   **Explanation**: This constraint ensures that only valid order statuses can be inserted into the table.

---

### **Step 2: Implement Audit Logging**

1. **Create an Audit Log Table**:

   We'll track sensitive actions like updating or deleting orders using an audit log.

   ```sql
   CREATE TABLE audit_log (
       log_id INT PRIMARY KEY AUTO_INCREMENT,
       user_id INT,
       action VARCHAR(100),
       table_name VARCHAR(50),
       timestamp TIMESTAMP DEFAULT CURRENT_TIMESTAMP
   );
   ```

   **Explanation**: The `audit_log` table will record every sensitive action, capturing the `user_id`, type of action (insert, update, delete), the table being affected, and a timestamp.

2. **Create Trigger to Log Updates**:

   We'll create a trigger that logs every time an order is updated.

   ```sql
   DELIMITER //
   CREATE TRIGGER order_update AFTER UPDATE ON orders
   FOR EACH ROW
   BEGIN
       INSERT INTO audit_log (user_id, action, table_name)
       VALUES (NEW.user_id, 'UPDATE', 'orders');
   END;
   //
   DELIMITER ;
   ```

   **Explanation**: This trigger will automatically log any updates made to the `orders` table, including which user performed the action.

---

### **Step 3: Test the Audit Log**

1. **Perform an Update**:
   Log in as `manager` and update an order status. Afterward, check the `audit_log` table to confirm the log entry.

   ```sql
   UPDATE orders SET order_status = 'Shipped' WHERE order_id = 2;  -- Manager updates the order
   SELECT * FROM audit_log;  -- Check the audit log
   ```

   **Explanation**: When the order is updated, a new record will appear in the `audit_log` table.

---

### **Deliverables for Lab 2:**

- **Screenshots** of successful operations and the audit log entries.
- **Discussion** on the significance of audit logging and its role in securing sensitive data.
- **Reflection** on the implementation of data integrity constraints and their benefits.

---

### **Conclusion:**

In this lab, students have learned how to implement role-based access control, apply privileges to different user roles, and utilize triggers and audit logging to track sensitive actions. These practices are essential in maintaining database security, ensuring that data access is controlled, and monitoring for unauthorized changes.

