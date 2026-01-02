
## USERS TABLE


### **TC_USERS_01 — CREATE: Insert New User**

**Priority:** High

**Test Data:**
* full_name: `John Mare`
* email: `john.mar.tc01@example.com`
* password_hash: `hashedpassword123`

**Steps:**
1. Open DBeaver and connect to the MySQL database.
2. Select the project database.
3. Insert a new user:

   ```sql
   INSERT INTO users (full_name, email, password_hash)
   VALUES ('John Mare', 'john.mar.tc01@example.com', 'hashedpassword123');
   ```
4. Retrieve the inserted user:

   ```sql
   SELECT * FROM users
   WHERE email = 'john.mar.tc01@example.com';
   ```

**Expected Result:**

* INSERT query executes successfully
* One new row is added to `users`
* `user_id` is auto-generated
* SELECT returns exactly one row with correct values


### **TC_USERS_02 — READ: Verify User Details**

**Priority:** High

**Steps:**

1. Connect to the database.
2. Execute:

   ```sql
   SELECT * FROM users
   WHERE email = 'john.mar.tc01@example.com';
   ```

**Expected Result:**

* User record is returned
* full_name, email, and password_hash match inserted data


### **TC_USERS_03 - UPDATE: Update User Password**

**Priority:** High

**Preconditions:**
* User exists

**Test Data:**
* new password_hash: `new_hashed_password`

**Steps:**

1. Connect to the database.
2. Update password:

   ```sql
   UPDATE users
   SET password_hash = 'new_hashed_password'
   WHERE email = 'john.mar.tc01@example.com';
   ```
3. Verify update:

   ```sql
   SELECT password_hash
   FROM users
   WHERE email = 'john.mar.tc01@example.com';
   ```

**Expected Result:**

* Exactly 1 row is updated
* password_hash value is changed


### **TC_USERS_04 — NEGATIVE: Duplicate Email Not Allowed**

**Priority:** High

**Preconditions:**
* User with email `john.mar.tc01@example.com` already exists

**Steps:**
1. Connect to database.
2. Try inserting another user with the same email:

   ```sql
   INSERT INTO users (full_name, email, password_hash)
   VALUES ('Another User', 'john.mar.tc01@example.com', 'hash2');
   ```

**Expected Result:**

* INSERT fails
* MySQL returns error:
  `Duplicate entry for key 'email'`
* No new user is created


## 📦 PRODUCTS TABLE


### **TC_PROD_05 — CREATE: Add New Product**

**Priority:** High

**Test Data:**
* product_name: `Test Product 01`
* price: `19.99`
* stock: `10`

**Steps:**

1. Connect to database.
2. Insert product:

   ```sql
   INSERT INTO products (product_name, price, stock)
   VALUES ('Test Product 01', 19.99, 10);
   ```
3. Verify insertion:

   ```sql
   SELECT * FROM products
   WHERE product_name = 'Test Product 01';
   ```

**Expected Result:**

* Product is created successfully
* product_id auto-generated
* created_at populated automatically


### **TC_PROD_06 — READ: Retrieve Product by ID**

**Preconditions:**
* Product exists

**Steps:**

1. Retrieve product:

   ```sql
   SELECT * FROM products
   WHERE product_id = <product_id>;
   ```

**Expected Result:**
* Correct product returned
* All fields match the inserted data


### **TC_PROD_07 — UPDATE: Update Product Price**

**Preconditions:**
* Product exists

**Steps:**

1. Update price:

   ```sql
   UPDATE products
   SET price = 29.99
   WHERE product_id = <product_id>;
   ```
2. Verify update:

   ```sql
   SELECT price
   FROM products
   WHERE product_id = <product_id>;
   ```

**Expected Result:**

* Price updated to 29.99
* Exactly 1 row affected


### **TC_PROD_08 — NEGATIVE: Insert Product with Invalid Price**
 
**Priority:** High  

**Objective**
* Verify that the system **does not allow non-numeric values** to be inserted into the `price` column of the `products` table.

**Preconditions:**
* Database `project_r` exists and is accessible  
* No product named **"Invalid Product"** exists

**Test Data**

* product_name - Invalid Product 
* price       - 'abc' (invalid string) 
* stock       -  5              

**Steps:**

1. Select the target database:
   ```sql
   USE project_r;
```

2. Attempt to insert a product with a non-numeric value in the `price` field:

   ```sql
   INSERT INTO products (product_name, price, stock)
   VALUES ('Invalid Product', 'abc', 5);
   ```

3. Observe the database response (error or success).

4. Verify whether the product was inserted:

   ```sql
   SELECT product_id, product_name, price
   FROM products
   WHERE product_name = 'Invalid Product';
   ```

**Expected Result**

* The INSERT operation **fails**
* Database returns a data type validation error (e.g., Incorrect decimal value)
* No record with `product_name = 'Invalid Product'` is inserted into the table


## 🧾 ORDERS & ORDER_ITEMS


### **TC_ORD_09 - CREATE: Create Order with Items**

**Preconditions:**
* User exists (`user_id = 1`)
* Products exist (`product_id = 1, 2`)

**Steps:**

1. Create order:

   ```sql
   INSERT INTO orders (user_id, status, total_amount)
   VALUES (1, 'Pending', 59.97);
   ```
2. Capture order ID:

   ```sql
   SELECT LAST_INSERT_ID();
   ```
3. Insert order items:

   ```sql
   INSERT INTO order_items (order_id, product_id, quantity, price)
   VALUES
   (<order_id>, 1, 1, 19.99),
   (<order_id>, 2, 2, 19.99);
   ```

**Expected Result:**

* order_id is auto-generated
* Items linked correctly
* No errors


### **TC_ORD_10 — READ: Verify Order Items & Total**

**Steps:**

1. Retrieve order:

   ```sql
   SELECT * FROM orders WHERE order_id = <order_id>;
   ```
2. Retrieve items:

   ```sql
   SELECT * FROM order_items WHERE order_id = <order_id>;
   ```
3. Calculate total:

   ```sql
   SELECT SUM(quantity * price)
   FROM order_items
   WHERE order_id = <order_id>;
   ```

**Expected Result:**

* All items returned
* Calculated total matches `total_amount`


### **TC_ORD_NEG_11 — NEGATIVE: Invalid Order Status**

**Priority:** High  

**Objective**
Verify that the system **rejects updates to the `orders.status` field with invalid values** that do not comply with allowed statuses

**Preconditions**
- `orders` table exists with at least one order (`order_id = 1`)  
- User has UPDATE permissions on the `orders` table  
- Allowed status values: `Pending`, `Paid`, `Shipped`, `Cancelled`  

**Test Data**

* status    -  FlyingToMars    
* order_id  - 1               

**Steps**
1. Select the target database:
   ```sql
   USE project_r;
   ```
2. Retrieve current status of the order to verify initial value:
```
SELECT status FROM orders WHERE order_id = 1;
```
3. Attempt to update the order status to an invalid value:
```
UPDATE orders
SET status = 'FlyingToMars'
WHERE order_id = 1;
```
4. Verify whether the update was applied:
```
SELECT status FROM orders WHERE order_id = 1;
```
**Expected Result**
* If database constraints or business logic exist, the update is rejected.
* If status is updated successfully, this is logged as a BUG (missing validation).
* Status should remain unchanged in a correctly implemented system.


## PAYMENTS


### **TC_PAY_12 - CREATE: Add Payment**

**Priority:** High  

**Objective**
Verify that a **valid payment can be added** to the `payments` table for an existing order.

**Preconditions**
* `orders` table exists with at least one order (`order_id = 1`)  
* `payments` table exists  
* Payment method allowed: e.g., 'Credit Card', 'PayPal'

**Test Data**
* order_id = 1  
* amount = 699.00  
* method = 'Credit Card'  
* status = 'Paid'  

**Steps:**
1. Select the target database:
   ```
   USE project_r;
   ```
2. Insert a new payment:
```
INSERT INTO payments (order_id, amount, method, status)
VALUES (1, 699.00, 'Credit Card', 'Paid');
```
3. Verify that the payment was added:
```
SELECT * FROM payments WHERE order_id = 1 ORDER BY payment_id DESC LIMIT 1;
```

**Expected Result**
* New payment record is created.
* All inserted values match the test data.


### **TC_PAY_13 — READ: Verify Payment Amount & Status**

**Priority:** High

**Objective**
* Verify that payment amount and status are correctly stored and retrievable.

**Preconditions**
* Payment exists in the payments table for order_id = 1
  
**Test Data**
* order_id = 1
  
**Steps:**
1. Retrieve the payment details:
```
SELECT amount, status, method, payment_date
FROM payments
WHERE order_id = 1;
```

**Expected Result**
* amount matches the inserted value.
* status = 'Paid'.
* method = 'Credit Card'.
* payment_date is correctly populated.


### **TC_PAY_NEG_14 — NEGATIVE: Insert Payment with Negative Amount**

**Priority:** High

**Objective**
* Verify that negative payment amounts are rejected.
  
**Preconditions**
* payments table exists
* orders table exists with order_id = 1
* User has INSERT permissions on payments
* Business rules or CHECK constraints prevent negative amounts
  
**Test Data**
* order_id = 1
* amount = -20.00
* method = 'Credit Card'
* status = 'Paid'
  
**Steps:**
1. Attempt to insert a payment with negative amount:
```
INSERT INTO payments (order_id, amount, method, status)
VALUES (1, -20.00, 'Credit Card', 'Paid');
```
2. Verify whether the row exists:
```
SELECT * FROM payments WHERE amount < 0;
```

**Expected Result**
* Insert is rejected by database constraints or business logic validation.
* No new row with negative amount exists.

  

