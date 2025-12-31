### Project: DummyJSON API Testing
### Tools: Postman, Environment Variables (baseUrl, auth_token, etc.)
### Scope: Users, Products, Cart, Authentication

# Users API

## TC-API-REG-01 Register user – success

**Endpoint:** POST /users/add

**Priority:** High

**Preconditions:** User email does not exist, Postman environment set up

**Test Data:**
{
  "email": "validuser@example.com",
  "username": "vilaa",
  "password": "Test12345!",
  "firstName": "Vita",
  "lastName": "Snow"
}

**Steps:**
1. Open Postman
2. Create a POST request to /users/add
3. Select Body → raw → JSON
4. Paste valid user data
5. Click Send

**Expected Result:**
- 201 Created
- Response body contains user ID, email, username, firstName, and lastName
- Header: Content-Type: application/json

## TC-API-REG-02 Register user – existing email (negative)

**Endpoint:** POST /users/add

**Priority:** High

**Preconditions:** User with email existinguser@example.com exists

**Test Data:**
{
  "email": "existinguser@example.com",
  "username": "existinguser",
  "password": "Test12345!",
  "firstName": "Vita",
  "lastName": "Snow"
}

**Steps:**
1. Open Postman
2. Send POST request to /users/add
3. Provide existing email in request body
4. Click Send

**Expected Result:**
- 400 Bad Request
- Response: { "message": "User already exists" }

## TC-API-LOGIN-03 Login – valid credentials

**Endpoint:** POST /auth/login

**Priority:** High

**Test Data:**
{
  "username": "vitaa",
  "password": "Test12345!"
}

**Steps:**
1. Open Postman
2. Create POST request to /auth/login
3. Enter valid username and password
4. Click Send

**Expected Result:**
- Status code: 200 OK
- Response contains token, id, username
- Token can be reused for authorized requests

## TC-API-LOGIN-04 Login – invalid password (negative)

**Endpoint:** POST /auth/login

**Priority:** High

**Test Data:**
{
  "username": "vitaa",
  "password": "invalidpass"
}

**Steps:**
1. Click Send
2. Send POST request to /auth/login
3. Enter valid username and invalid password
4. Click Send

**Expected Result:**
- 401 Unauthorized
- Error message: { "Invalid credentials" }
- No token returned

# Products API

## TC- API-PRODUCTS-05 Get product list – success

**Endpoint:** GET /products

**Priority:** Medium

**Steps:**
1. Open Postman
2. Create a new GET request
3. Enter endpoint: https://dummyjson.com/products
4. Click Send

**Expected Result:**
- 200 OK
- Returns an array of products
- Each product has id, title, price, stock

## TC-API-PRODUCTS-06 Get product details – invalid ID (negative)

**Endpoint:** GET /products/{id}

**Priority:** Medium

**Steps:**
1. Open Postman
2. Create a GET request
3. Enter endpoint: https://dummyjson.com/products/1
4. Click Send

**Expected Result:**
- 404 Not Found
- { "message": "Product not found" }

## TC-API-PRODUCTS-07 Search products – positive

**Endpoint:** GET /products/search?q=phone

**Priority:** Medium

**Steps:**
1. Open Postman
2. Create a GET request
3. Enter endpoint: https://dummyjson.com/products/search?q=phone
4. Click Send

**Expected Result:**
- Status code: 200 OK
- Response contains matching products
- Each product has id, title, price

## TC-API-PRODUCTS-08 Search products – invalid query(negative)

**Endpoint:** GET /products/search?q=123@@@

**Priority:** Low

**Steps:**
1. Open Postman
2. Create a GET request
3. Enter endpoint with invalid keyword: https://dummyjson.com/products/search?q=123@@@
4. Click Send

**Expected Result:**
- Status code: 200 OK
- Response contains empty products array
- No error returned
- API handles invalid search gracefully

# Cart API

## TC-API-CART-09 Add to cart – success

**Endpoint:** POST /carts/add

**Priority:** High

**Preconditions:** Valid user ID and product ID exist

**Steps:**
1. Open Postman
2. Create a POST request
3. Enter endpoint: https://dummyjson.com/carts/add
4. Go to Body → raw → JSON
5. Enter valid request body:
{
  "userId": 1,
  "products": [
    {
      "id": 1,
      "quantity": 1
    }
  ]
}
6. Click Send

**Expected Result:**
- Status code: 200 OK
- Cart object is created
- Response contains: id, userId, products, total

## TC-API-CART-10 Add to cart – invalid product (negative)

**Endpoint:** POST /carts/add

**Priority:** High

**Steps:**
1. Open Postman
2. Create a POST request
3. Enter endpoint:
https://dummyjson.com/carts/add
4. Enter request body with invalid product ID:
{
  "userId": 1,
  "products": [
    {
      "id": 99999,
      "quantity": 1
    }
  ]
}
5. Click Send

**Expected Result:**
- Status code: 400 Bad Request or 404 Not Found
- Error message returned
- The cart is not created

## TC-API-CART-11 Delete from cart – success

**Endpoint:** DELETE /carts/{cartId}

**Priority:** Medium

**Precondition:** Cart exists (created via add-to-cart)

**Steps:**
1. Open Postman
2. Create a DELETE request
3. Enter endpoint: https://dummyjson.com/carts/1
4. Click Send

**Expected Result:**
- Status code: 200 OK
- Response contains isDeleted: true
- Cart ID matches requested ID

## TC-API-CART-12 Delete from cart – invalid ID (negative)

**Endpoint:** DELETE /carts/99999

**Priority:** Medium

**Steps:**
1. Open Postman
2. Create a DELETE request
3. Enter endpoint with invalid cart ID: https://dummyjson.com/carts/99999
4. Click Send

**Expected Result:**
- 404 Not Found
- { "message": "Cart not found" }

# Profile / Auth API

## TC-API-AUTH-13 Access user profile without authorization token

**Endpoint:** GET /auth/me

**Priority:** High

**Steps:**
1. Open Postman
2. Create a GET request
3. Enter endpoint: https://dummyjson.com/auth/me
4. Click Send

**Expected Result:**
- Status code: 401 Unauthorized
- Error message returned
- Access denied without a token

## TC- API-AUTH-14 Access profile – valid token

**Endpoint:** GET /auth/me

**Priority:** High

**Preconditions:**
User is successfully logged in
Valid authentication token is saved in Postman environment as {{auth_token}}

**Steps:**
1. Open Postman
2. Create a GET request
3. Enter endpoint: https://dummyjson.com/auth/me
4. Go to Headers
5. Add header:
     Key: Authorization
     Value: Bearer {{auth_token}}
6. Click Send

**Expected Result:**
- Status code: 200 OK
- Response body contains authenticated user information:
                   -id  -username  -email  -firstName  -lastName
- Response does NOT contain password or sensitive data
- Token is validated successfully
