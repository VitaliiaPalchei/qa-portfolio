# User Registration


## TC-REG-01: Create Account with Valid Data

**Preconditions:**
User is not logged in.
The registration page is accessible.

**Steps:**
1. Open the Registration page.
2. Select a valid gender option.
3. Enter a valid First Name and Last Name.
4. Enter a valid and unique Email address.
5. Enter a valid Password.
6. Enter the same password in the Confirm Password field.
7. Click the Register button.

**Expected Result:**
- Account is created successfully.
- User is automatically redirected to the homepage or account dashboard.

## TC-REG-02: Validate Required Fields on Empty Registration Form

**Steps:**
1. Open the Registration page.
2. Leave all required fields empty.
3. Click the Register button.
   
**Expected Result:**
- Validation messages are displayed for all required fields (e.g., “First name is required”).
- User remains on the Registration page.

## TC-REG-03: Validate First Name Field – Invalid Characters

**Preconditions:**
The registration page is open.

**Steps:**
1. Enter invalid characters in the First Name field (e.g., @@@ or 123).
2. Fill all other required fields with valid data.
3. Click the Register button.

**Expected Result:**
- Validation message appears, indicating invalid characters.
- Registration is not completed.

## TC-REG-04: Validate Last Name Field – Below Minimum Length

**Preconditions:**
The registration page is open.

**Steps:**
1. Enter a value shorter than the minimum allowed length (e.g., A) in the Last Name field.
2. Fill all other required fields with valid data.
3. Click the Register button.

**Expected Result:**
Validation message indicates the minimum length requirement.
Registration is not completed.

## TC-REG-05: Validate Duplicate Email Error

**Steps:**
1. Open the Registration page.
2. Enter valid data in all fields.
3. Enter an email address that already exists in the system.
4. Click the Register button.
   
**Expected Result:**
- Error message appears: “This email is already registered.”
- Registration request is not submitted.
- User remains on the Registration page.

## TC-REG-06: Validate Password and Confirm Password Mismatch

**Steps:**
1. Open the Registration page.
2. Enter valid data in all required fields.
3. Enter Test123! in the Password field.
4. Enter Test12! in the Confirm Password field.
5. Click the Register button.
   
**Expected Result:**
Error message appears: “Passwords do not match.”
Registration is not completed.


# User Login


## TC-LOGIN-01: Login with Valid Credentials

**Steps:**
1. Open the Login page.
2. Enter a valid email address.
3. Enter the correct password.
4. Click the Login button.
   
**Expected Result:**
- User is logged in successfully.
- User is redirected to the homepage or account dashboard.

## TC-LOGIN-004: Verify user is logged out after deleting authentication cookies

**Preconditions:**
User has a valid registered account.
User is logged in successfully.
Browser DevTools are available.

**Steps:**
1. Log in to the application using valid credentials.
2. Confirm the user is successfully logged in and redirected to the homepage.
3. Open the browser Developer Tools.
4. Navigate to the Application tab.
5. Select Cookies under Storage.
6. Identify authentication/session cookies.
7. Delete all authentication/session cookies.

**Expected Result:**
- The user session is terminated.
- The user is logged out automatically.
- The system redirects the user to the Login page or Homepage.

## TC-LOGIN-02: Login with Invalid Email Format

**Steps:**
1. Open the Login page.
2. Enter an invalid email format (e.g., user@@test).
3. Enter any password.
4. Click the Login button.
   
**Expected Result:**
- Validation error message appears for an invalid email format.
- User remains on the Login page.
  
## TC-LOGIN-03: Login with Incorrect Password

**Steps:**
1. Open the Login page.
2. Enter a valid registered email address.
3. Enter an incorrect password.
4. Click the Login button.
   
**Expected Result:**
- Error message appears: “Incorrect email or password.”
- User remains on the Login page.


# User Logout


## TC-LOGOUT-01: Logout from Application

**Steps:**
1. Log in with a valid user account.
2. Click the Logout option from the navigation menu.
   
**Expected Result:**
- User is logged out successfully.
- User is redirected to the homepage or login page.
- Authentication session is terminated.

