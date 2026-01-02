
### **TC_SQL_01 — Find Users with No Orders**

**Objective:**
* Identify users who have never placed an order.

**Steps:**
```
SELECT u.user_id, u.full_name, u.email
FROM users u
LEFT JOIN orders o ON u.user_id = o.user_id
WHERE o.order_id IS NULL;
```

**Expected Result:**
* List of users with no orders (can be empty if all users ordered something)
* No errors in query execution

### **TC_SQL_02 — Find Products Ordered 0 Times**

**Objective:**
* Identify products that were never included in any order.

**Steps:**
```
SELECT p.product_id, p.product_name
FROM products p
LEFT JOIN order_items oi ON p.product_id = oi.product_id
WHERE oi.order_item_id IS NULL;
```

**Expected Result:**
* List of products never sold
* No duplicate rows

### **TC_SQL_03 — Validate Order Totals**

**Objective:**
* Check if orders.total_amount matches the sum of order_items prices × quantities.

**Steps:**
```
SELECT o.order_id,
       o.total_amount,
       SUM(oi.quantity * oi.price) AS calculated_total
FROM orders o
JOIN order_items oi ON o.order_id = oi.order_id
GROUP BY o.order_id
HAVING o.total_amount != SUM(oi.quantity * oi.price);
```

**Expected Result:**
* Should return 0 rows if totals match
* Any row returned indicates data inconsistency

### **TC_SQL_04 — Check Duplicate Emails**

**Objective:**
* Ensure email uniqueness in users table.

**Steps:**
```
SELECT email, COUNT(*) AS count
FROM users
GROUP BY email
HAVING COUNT(*) > 1;
```

**Expected Result:**
* No rows returned
* If rows exist → duplicate emails detected

### **TC_SQL_05 — Verify Referential Integrity (Orders → Users)**

**Objective:**
* Ensure all orders reference valid users.

**Steps:**
```
SELECT o.order_id, o.user_id
FROM orders o
LEFT JOIN users u ON o.user_id = u.user_id
WHERE u.user_id IS NULL;
```

**Expected Result:**
* No rows returned
* If rows exist → orders reference nonexistent users (FK violation)

### **TC_SQL_06 — Find Orders Missing Payments**

**Objective:**
* Detect orders that have no payments recorded.

**Steps:**
```
SELECT o.order_id
FROM orders o
LEFT JOIN payments p ON o.order_id = p.order_id
WHERE p.payment_id IS NULL;
```

**Expected Result:**
* List of unpaid orders
* Should match expectations from test data

### **TC_SQL_07 — Compare API Response vs DB (Dummy Example)**

**Objective:**
* Compare total orders from API vs database (manual step).

**Steps:**
1. Get orders count from DB:

```
SELECT COUNT(*) AS db_orders_count
FROM orders;
```

3. Compare with API response (dummyjson) manually or via script

**Expected Result:**
* DB count matches API response

