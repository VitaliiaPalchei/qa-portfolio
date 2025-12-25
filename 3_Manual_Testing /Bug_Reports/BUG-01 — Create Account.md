## Title: Registration allows invalid email format

**Environment:**
Browser: Chrome
OS: macOS
Build: Web Shop Test Environment

**Preconditions:**
User is on the Create Account / Registration page.

**Steps to Reproduce:**
1. Open the website homepage.
2. Navigate to the Create Account page.
3. Enter a valid First Name and Last Name.
4. Enter an invalid email format: user@@test.
5. Enter valid password and confirm password.
6. Click Register.
   
**Actual Result:**
The system accepts the invalid email and attempts to create an account.

**Expected Result:**
The system should display an email validation error and prevent account creation.

**Severity:**  Medium

**Priority:**  High
